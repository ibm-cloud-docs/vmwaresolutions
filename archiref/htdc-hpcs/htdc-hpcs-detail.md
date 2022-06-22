---

copyright:

  years:  2019, 2022

lastupdated: "2022-06-20"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Entrust DataControl on IBM Cloud with IBM Hyper Protect Crypto Services
{: #htdc-hpcs-detail}

The DataControl® virtual machine (VM) is an Entrust-hardened version of FreeBSD, a light-weight, locked-down operating system that has no runtime login or SSH access to the system. This system prevents tampering or attempts to access clear-text data and encryption keys. Two VMs are deployed onto the internal management subnet.

The following examples are for the hostnames:
* Primary Host Name - `htdc01-A68ED99E.ibmcloud.local`
* Secondary Host Name - `htdc02-A68ED99E.ibmcloud.local`

In the previous examples, A68ED99E is the instance ID and `ibmcloud.local` is your VMware® vCenter Server® instance domain name.

During the deployment, the following users are configured. All service information is available in the {{site.data.keyword.cloud}} console.

* Web UI Security Admin User
* Web UI Cloud User
* Console User

## Firewall rules
{: #htdc-hpcs-detail-fw-rules}

The following figure describes the deployment of the Entrust DataControl VMs into the vCenter Server instance.

![Flows](../../images/htdc-hpcs-natfw.svg){: caption="Figure 1. Network address translation and firewall" caption-side="bottom"}

The following firewall rules are configured on the management ESG when Entrust DataControl on {{site.data.keyword.cloud_notm}} service is deployed. This configuration allows outbound connectivity to the Internet for the Entrust VMs so that the license that is applied to the Entrust DataControl installation does not expire after a year.

* `Name: Entrust DataControl VM Outbound Traffic for DC1, source: <ENTDC VM 1 IP>, destination:  any, service:  HTTPS/HTTP, action: Accept`
* `Name: Entrust DataControl VM Outbound Traffic for DC2, source: <ENTDC VM 2 IP>, destination:  any, service:  HTTPS/HTTP, action: Accept`

These rules also allow automatic vitals reporting, if you enable it, as Entrust KeyControl™must be able to send the encrypted vitals bundle outbound to `https://vitals.entrust.com` by using TCP/443.

These rules also allow access to {{site.data.keyword.cloud_notm}} IAM outbound to `https://iam.cloud.ibm.com` by using TCP/443. This access is required to validate the API key. If this access is not configured, you might receive the following error:

`Cannot retrieve HPCS access token. HTTPSConnectionPool(host-iam.cloud.ibm.com port=443)`

The following figure shows the following communication flows that are required between the Entrust DataControl components and external services.

![Ports](../../images/htdc-hpcs-ports.svg){: caption="Figure 2. Network ports" caption-side="bottom"}

In the vCenter Server instance deployment, these flows are allowed, but would need to be explicitly allowed if the default firewalls were changed.

* The Entrust KeyControl servers need to communicate to the following infrastructure services:
   * DNS - Outbound UDP/53
   * SMTP - Outbound mail server, typically TCP/25 (optional)
   * SYSLOG - An outbound UDP in the range 25 - 65535 if you want to use a remote syslog server (optional). Entrust KeyControl does not currently support TCP for syslog
   * Backup and Restore through NFS (optional) - Inbound TCP and UDP/111 (`portmapper`), 2046 (`lockd`), 2047 (`rpc statd`), 2048 (`rcpmountd`), and 2049 (default NFS port)
   * NTP - Outbound NTP servers, typically UDP/123 or TCP/123
   * {{site.data.keyword.cloud_notm}} IAM - Outbound TCP/443. Required for HPCS

* The Entrust KeyControl servers need to communicate to each other:
   * TCP/443 (HTTPS)
   * TCP/8443 and 2525

   Entrust KeyControl uses the IP address 169.254.119.1 for internal communication. This IP address must be reserved for Entrust KeyControl.
   {: note}

* The following traffic flows are required for external access:
   * Entrust KeyControl webGUI – Inbound TCP/443 and TCP/80 to the Entrust KeyControl VMs. All requests made to TCP/80 are redirected to TCP/443 so that they use HTTPS.
   * For Entrust support-level access - Inbound TCP/22 (for full support) and TCP/6666 (for restricted support) to the Entrust KeyControl VMs.

   The Entrust DataControl PAs are installed in the VMs hosted on the NSX VXLAN network segments in the overlay. These VMs have Bring Your Own IP (BYOIP) addressing. Therefore, NAT or routing changes need to be implemented on the customer-ESG so that the communication flow is allowed.

* Policy Agent to Entrust KeyControl - Inbound TCP/443 from the Policy Agent to each of the Entrust KeyControl VMs.

## NAT
{: #htdc-hpcs-detail-nat}

The following Network Address Translation (NAT) rules are configured on the customer ESG when the Entrust DataControl on {{site.data.keyword.cloud_notm}} service is deployed. These rules allow outbound connectivity to the internet to enable licensing of Entrust DataControl.

* `Type: SNAT, Applied On: public uplink, Original Source IP: <ENTDC VM 1 IP>, Translated IP Address: <Secondary IP>, Port Range: any`
* `Type: SNAT, Applied On: public uplink, Original Source IP: <ENTDC VM 2 IP>, Translated IP address: <Secondary IP>, Port Range: any`

## Entrust Policy Agent
{: #htdc-hpcs-detail-policy-agent}

The Entrust DataControl Policy Agent is a software module that provides encryption of virtual disks and individual files. It runs inside Microsoft® Windows® and Linux® operating systems. All VMs with the Policy Agent installed on them can also securely share encrypted files and disks. When a user attempts to access an encrypted disk, the Policy Agent queries Entrust KeyControl to validate the request, and returns the information to the user if Entrust KeyControl authorizes the request. You must install a copy of the Policy Agent in each VM, and on each disk, you want to encrypt with Entrust DataControl.

Policy Agent has the following features:
* Full encrypted path from the VM, through the hypervisor to the storage.
* Support for cloning and replication.
* Dynamic rekey on Windows and Linux, allowing initial encryption or rekey without taking the VM or applications offline.
* Linux file-level and folder-level encryption.
* Migration of encrypted disks between VMs in the same Cloud VM Set.
* Support for Windows failover clusters.
* Root and swap encryption for Linux and boot drive (C:) encryption for Windows.

Entrust provides several administrative interfaces to configure and maintain Entrust KeyControl and the encrypted VMs registered with Entrust KeyControl.
* Entrust KeyControl webGUI - A browser-based HTTPS interface to Entrust KeyControl to configure and manage Entrust KeyControl. You can log in to the webGUI on any Entrust KeyControl node in the cluster. Any changes that you make on that node are automatically disseminated to all other Entrust KeyControl nodes in the cluster.
* Entrust KeyControl System Console menu - The System Console menu is available on each Entrust KeyControl in the cluster. You can set local configuration options for the node, join the node to an existing Entrust KeyControl cluster, and manage support access to the node.
* `hicli` - CLI (command-line interface) commands to configure and maintain both Entrust KeyControl and the VMs registered with Entrust KeyControl.
* Entrust Policy Agent GUI - A Windows-only GUI installed with the Entrust DataControl Policy Agent. With this GUI, you can register and authenticate the VM on which it is installed and you can encrypt and decrypt the disks on that VM. Unlike the other interfaces, the Entrust Policy Agent GUI is limited to the VM on which it is installed. You cannot use the Entrust Policy Agent GUI on one VM to manage the disks on a different VM, even if both VMs are registered with Entrust KeyControl.
* REST or Python APIs - Entrust KeyControl can be configured and maintained through REST-based or Python-based API calls.

## Entrust DataControl processes
{: #htdc-hpcs-detail-processes}

With Entrust DataControl, a VM must be part of a Cloud VM Set before it can be encrypted. The set controls global options for the VMs it contains and tracks KeyIDs and FSIDs. It also allows the BoundaryControl feature to be enabled that uses Policy Rules and constraints in Entrust CloudControl to authenticate and authorize delivery of encryption keys for the data encrypted by the Entrust DataControl PA and managed by Entrust KeyControl.

A KEK provides an extra layer of security by encrypting the individual DEKs on the VMs associated with the Cloud VM Set. It also controls the expiration and revocation of the DEKs. To protect the KEK, Entrust KeyControl requires that the KEK is stored in the IBM HPCS instance. The following KEK flows are described:

1. Cloud VM Set KEK setup - This process is used when a new Cloud VM Set is configured.
2. Wrapping DEK with KEK request flow - Entrust DataControl PA requests the Entrust KeyControl server to create a new DEK when it encrypts a disk or rekeying a disk.
3. Unwrapping DEK with KEK request flow - Entrust DataControl PA requests the Entrust KeyControl server for a DEK when it attaches an encrypted disk.

### Cloud VM Set KEK setup flow
{: #htdc-hpcs-detail-processes-kek}

1. In the IBM HPCS instance, an HPCS service user creates or imports a Root Key. This root key is used by Entrust DataControl to wrap the KEK of a Cloud VM Set. The Root Key cannot be extracted or exported and it never leaves the IBM HPCS instance.
2. In Entrust DataControl, the Entrust DataControl Cloud administrator configures a KEK for a Cloud VM Set with a number of characteristics.
   * IBM HPCS REST API endpoint.
   * CA Certificate to verify the IBM HPCS instance.
   * API Key to generate a token.
   * IBM HPCS Instance ID.
   * IBM HPCS Root Key ID.
3. Using the Create & Wrap Key Request REST API (TLS), Entrust KeyControl requests IBM HPCS to create a 256-bits symmetric key and wrap it with the Root Key.
4. IBM HPCS generates the requested symmetric KEK, wraps the generated key with the Root Key, and returns the wrapped key.
5. Entrust KeyControl stores the KEK configuration; IBM HPCS Config, Root Key ID, wrapped KEK.

### Wrapping DEK with KEK request flow
{: #htdc-hpcs-detail-processes-dek-wrap}

Entrust DataControl Policy Agent (Entrust DataControl PA) requests the Entrust KeyControl server to create a new Data Encryption Key (DEK) when it encrypts or rekeys a disk.

1. The Entrust DataControl PA requests the Entrust KeyControl server to create a new Data Encryption Key (DEK).
2. Entrust KeyControl validates the status of the KEK to ensure it is not expired or revoked. If the KEK is expired or revoked, Entrust KeyControl might fail the DEK creation request.
3. Using the Unwrap Key Rest API (TLS), Entrust KeyControl requests the IBM HPCS instance to unwrap KEK.
4. After it validates the status of Root Key (not revoked), IBM HPCS unwraps the key with the Rook Key and returns the unwrapped Key. If the Root Key is revoked, IBM HPCS fails the `unwrap key` request.
5. Entrust KeyControl generates a DEK, wraps it with the KEK and stores the wrapped DEK in the Object Store.
6. Entrust KeyControl securely erases the KEK from memory.
7. Entrust KeyControl returns the newly created DEK to the Entrust DataControl PA.

### Unwrapping DEK with KEK request flow
{: #htdc-hpcs-detail-processes-dek-unwrap}

Entrust DataControl PA requests the Entrust KeyControl server for a DEK when it attaches an encrypted disk.
1. Entrust DataControl PA requests the Entrust KeyControl server to create a new DEK.
2. Entrust KeyControl validates the status of the KEK to ensure it is not expired or revoked. If the KEK is expired or revoked, Entrust KeyControl might fail the key request.
3. Entrust KeyControl requests IBM HPCS to unwrap the KEK.
4. After it validates the status of the root key (not revoked), IBM HPCS unwraps the key with the root key. If the root key is revoked, HPCS fails the `unwrap key` request.
5. Entrust DataControl retrieves the wrapped DEK from the Object Store and unwraps it with the KEK.
6. Entrust DataControl securely erases the KEK from memory.
7. Entrust DataControl returns the unwrapped DEK to the Entrust DataControl PA.

## Related links
{: #htdc-hpcs-detail-related}

* [Creating and working with service IDs](/docs/account?topic=account-serviceids)
