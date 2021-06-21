---

copyright:

  years:  2016, 2021

lastupdated: "2021-05-14"

keywords: VMware HCX deployment, HCX configuration, order HCX

subcollection: vmwaresolutions


---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Ordering VMware HCX
{: #hcx_ordering}

You can include the VMware HCX™ service with a new VMware vCenter Server® instance or add the service to your existing vCenter Server instance.

## Ordering VMware HCX for a new instance
{: #hcx_ordering-new}

To order a new VMware® vCenter Server instance with VMware HCX from the {{site.data.keyword.vmwaresolutions_full}} console, scroll down to the services section and select **HCX** in the **Business continuity and migration** category.

## Ordering VMware HCX for an existing instance
{: #hcx_ordering-existing}

1. On the instance details page, click **Services** on the left navigation pane.
2. Click **Add** to add the service.
3. On the **Services** page, locate the **VMware HCX** service and toggle its switch on.
4. Follow the steps to configure and add the service to your instance.

## VMware HCX configuration
{: #hcx_ordering-config}

To install HCX, complete the following settings:

1. This step does not apply to HCX installations on vCenter Server with Hybridity Bundle instances.

   If you want to use your own VMware NSX® license (BYOL), select the checkbox to confirm that your NSX license is either Advanced or Enterprise edition.
2. If you choose NSX-T™, you are asked to select the **HCX Service Mesh target cluster**. Select either the Management cluster or Workload cluster.

   If you choose NSX-V, the HCX manager and Service Mesh appliances are deployed in the management cluster.
3. Specify the **HCX network connection** by selecting one of the following options. If any of the management or service mesh target clusters are deployed with private network only, the only networking option that you can choose is private.
  * **Public network** - HCX creates an encrypted connection between sites over the public network. License registration and metering are completed over the public network.
  * **Private network** - HCX creates an encrypted connection between sites over the private network. License registration and metering are completed over a private network through HTTP proxy.  
4. If private network connection is selected, proxy information is displayed. Otherwise, a proxy option is not available.
   Complete the following fields:
   * **Proxy IP address** - The IPv4 address of the proxy server.
   * **Proxy port number** - The proxy server port. The port number is typically 8080 or 3128.
   * **Proxy user name** (Optional) - The username if proxy authentication is required.
   * **Proxy password** (Optional) - The password if proxy authentication is required.
   * **Reenter proxy password** (Optional) - Reenter the password for proxy authentication validation.
5. Specify the **Public endpoint certificate type**. If you select **CA Certificate**, configure the following settings:
  * **Certificate contents** - Enter the contents of the CA certificate.
  * **Private key** - Enter the private key of the CA certificate.
  * **Password** (Optional) - Enter the password for the private key, if it is encrypted.
  * **Reenter password** (Optional) - Enter the password for the private key again.
  * **Hostname** (Optional) - The hostname to be mapped to the common name (CN) of the CA certificate. HCX requires that the format of the CA certificate must be accepted by NSX Edge. For more information about NSX Edge certificate formats, see [Importing SSL Certificates](https://docs.vmware.com/en/VMware-NSX-Data-Center-for-vSphere/6.3/com.vmware.nsx.admin.doc/GUID-19D3A4FD-DF17-43A3-9343-25EE28273BC6.html){:external}.

## Deployment process for HCX
{: #hcx_ordering-deploy}

The deployment of HCX is automated. Whether you order a vCenter Server instance with the service included or you deploy the service later into your instance, the following steps are completed by the {{site.data.keyword.vmwaresolutions_short}} automation process:
1. Three subnets are ordered for HCX from the {{site.data.keyword.cloud_notm}} infrastructure:
   * One private portable subnet for HCX management.
   * One private portable subnet for HCX interconnects. This subnet is used when the **Private network** option is selected for **HCX connection type**.
   * One public portable subnet for HCX interconnects, if the **Public network** option is selected for **HCX connection type**. On NSX-V, this subnet is also used for activation and maintenance with VMware.

   The IP addresses in the subnets that are ordered for HCX are intended to be managed by the VMware on {{site.data.keyword.cloud_notm}} automation. These IP addresses cannot be assigned to VMware resources, such as VMs and NSX Edges, that are created by you. If you need more IP addresses for your VMware artifacts, you must order your own subnets from {{site.data.keyword.cloud_notm}}.
   {:important}
2. If **Private Network** was selected for **HCX Network Connection**, a port group that is named **SDDC-DPortGroup-HCX-Private** is created on the private Distributed Virtual Switch (DVS).
3. An HCX activation key is ordered from VMware.
4. **For vCenter Server with NSX-V instances**, a pair of VMware NSX Edge Services Gateways (ESGs) for the HCX management traffic is deployed and configured:
   * Public and private uplink interfaces are configured by using the ordered subnets.
   * The ESGs are configured as a pair of extra large edge appliances with High Availability (HA) enabled.
   * The firewall rules and network address translation (NAT) rules are configured to allow inbound and outbound HTTPS traffic to and from the HCX Manager.
   * The load balancer rules and resource pools are configured. These rules and resource pools are used to forward HCX-related inbound traffic to the appropriate virtual appliances of HCX Manager and vCenter Server (with embedded Platform Services Controller).
   * An SSL certificate to encrypt the HCX-related inbound HTTPS traffic that is coming through the ESGs is applied.

   The HCX management edge is dedicated to the HCX management traffic between the on-premises HCX components and the cloud-side HCX components. Do not modify the HCX management edge or use it for HCX network extensions. Instead, create separate edges for network extensions. In addition, if you use a firewall or you disable the HCX management edge communications to the private IBM management components or the internet, the HCX functions might be impacted.
   {:important}

5. **For vCenter Server with NSX-T instances**, the firewall rules and network address translation (NAT) rules are configured to allow inbound and outbound HTTPS traffic to and from the HCX Manager.

6. The HCX Manager is deployed, activated, and configured:
   * The HCX Manager is registered with vCenter Server.
   * The HCX Manager, vCenter Server (with embedded Platform Services Controller), and NSX Manager are configured.
   * The HCX Compute and Network profiles are created.
7. The hostname and IP address of the HCX Manager is registered with the DNS server of VMware vCenter Server.

## Related links
{: #hcx_ordering-related}

* [HCX overview](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_considerations#hcx_considerations)
* [Managing HCX ](/docs/vmwaresolutions?topic=vmwaresolutions-managinghcx)
* [Ordering, viewing, and deleting services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices)
* [Glossary of HCX terms](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_glossary)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [VMware Hybrid Cloud Extension overview](https://cloud.vmware.com/vmware-hcx){:external}
* [VMware Hybrid Cloud Extension documentation](https://cloud.vmware.com/vmware-hcx/resources){:external}
