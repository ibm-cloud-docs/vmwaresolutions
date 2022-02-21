---

copyright:

  years:  2020, 2022

lastupdated: "2022-02-18"

keywords: VLAN ports, vmware solutions ports, ports usage vmware solutions

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Ports for services
{: #vmwaresol_ports-services}

The following topics provide information about the ports that are used by the services.

## Ports for Caveonix RiskForesight
{: #vmwaresol_ports-vmware-optional-services-caveonix}

The following table provides information about the Caveonix RiskForesight™ ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| Caveonix | New subnet ordered in private VLAN | VMware vCenter Server® | Infrastructure VMs | 443 | TCP | Use vCenter Server REST service | HTTPS |
| Caveonix | New subnet ordered in private VLAN | Windows® Active Directory™ | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use Windows DNS service | DNS |
| Caveonix | New subnet ordered in private VLAN | {{site.data.keyword.cloud_notm}} infrastructure Redis service | {{site.data.keyword.cloud_notm}} infrastructure services network | 6379 | TCP | Use {{site.data.keyword.cloud_notm}} infrastructure Redis service | |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | Caveonix | New subnet ordered in private VLAN | 1337 | TCP | Set up and configure Caveonix | |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | Caveonix | New subnet ordered in private VLAN | 8080 | TCP | Set up and configure Caveonix | |
{: caption="Table 1. Caveonix RiskForesight ports" caption-side="top"}

## Ports for F5 BIG-IP
{: #vmwaresol_ports-vmware-optional-services-f5bigip}

The following table provides information about the F5 BIG-IP® ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| BigIP | New subnet ordered in private VLAN | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use Windows DNS service | DNS |
| Management-nsx-edge public IP | Public subnet for management edge | BigIP license server | 104.219.111.132/32 | 443 | TCP | License registration | HTTPS |
{: caption="Table 2. F5 BIG-IP ports" caption-side="top"}

## Ports for FortiGate Virtual Appliance
{: #vmwaresol_ports-vmware-optional-services-fortigate}

The following table provides information about the FortiGate® Virtual Appliance ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| Management-nsx-edge public IP | Public subnet for management edge | Fortinet® servers | 208.91.112.0/22 | 443 | TCP | FortiGate installation | HTTPS |
| Management-nsx-edge public IP | Public subnet for management edge | Fortinet servers | 96.45.33.0/24 | 443 | TCP | FortiGate installation | HTTPS |
| Management-nsx-edge public IP | Public subnet for management edge | Fortinet servers | 66.35.17.248 | 443 | TCP | FortiGate installation | HTTPS |
{: caption="Table 3. FortiGate Virtual Appliance ports" caption-side="top"}

## Ports for VMware HCX
{: #vmwaresol_ports-vmware-optional-services-hcx}

The following table provides information about the VMware HCX™ ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| HCX | New subnet ordered in private VLAN | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use Windows DNS service | DNS |
| HCX | New subnet ordered in private VLAN | vCenter Server | Infrastructure VMs | 443 | TCP | Use vCenter Server REST service | HTTPS |
| HCX | New subnet ordered in private VLAN | NSX Manager | Infrastructure VMs | 443 | TCP | Use NSX Manager registration service | HTTPS |
| HCX public IP | New subnet ordered in public VLAN | connect.hcx.  \n vmware.com | Public IP 45.60.63.140 | 443 | TCP | Registration service | HTTPS |
| vCenter Server | Infrastructure VMs | HCX | New subnet ordered in private VLAN | 443 | TCP | Use HCX REST service | HTTPS |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | HCX | New subnet ordered in private VLAN | 443 | TCP | Use HCX REST service | HTTPS |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | HCX | New subnet ordered in private VLAN | 9443 | TCP | Use HCX Virtual Appliance Management Interface for HCX system configuration | HTTPS |
{: caption="Table 4. VMware HCX ports" caption-side="top"}

## Ports for HyTrust CloudControl, HyTrust DataControl, and HyTrust KeyControl
{: #vmwaresol_ports-vmware-optional-services-hytrust}

The following table provides information about the HyTrust® CloudControl™, HyTrust DataControl®, and HyTrust KeyControl™ ports.

| Source | Subnet/IP range | Target | Subnet/IP range | Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:-----|:---------|:--------|:--------|
| HyTrust CloudControl | Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | NTP |
| HyTrust CloudControl | Infrastructure VMs | Windows Active Directory and DNS server | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use Windows DNS service | DNS |
| HyTrust CloudControl | Infrastructure VMs | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | | ICMP | Ping | Ping |
| HyTrust CloudControl | Infrastructure VMs | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 443 | TCP | Access Windows Active Directory | HTTPS |
| HyTrust DataControl | Infrastructure VMs | Windows Active Directory | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | NTP |
| HyTrust DataControl | Infrastructure VMs | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use Windows DNS service | DNS |
| HyTrust KeyControl | Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123  | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | NTP |
| HyTrust KeyControl | Infrastructure VMs | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use Windows DNS service | DNS |
{: caption="Table 5. HyTrust CloudControl, HyTrust DataControl, and HyTrust KeyControl ports" caption-side="top"}

## Ports for IBM Spectrum Protect Plus
{: #vmwaresol_ports-vmware-optional-services-spp}

The following table provides information about the IBM Spectrum® Protect Plus ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| IBM Spectrum Protect Plus | Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | NTP |
{: caption="Table 6. IBM Spectrum Protect Plus ports" caption-side="top"}

## Ports for Juniper vSRX
{: #vmwaresol_ports-vmware-optional-services-juniper-vsrx}

The following table provides information about the Juniper® vSRX ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | vSRX private IP addresses| New subnet ordered in private VLAN | 22 | TCP | Set up and configure vSRX | SSH |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | vSRX private IP addresses| New subnet ordered in private VLAN | 830 | TCP | Set up and configure vSRX by NETCONF over SSH | |
| vSRX | vSRX Private IP | vRealize Log Insight (if vROPs service is installed) | vRealize Log Insight FQDN | 514 | UDP | Remote syslog to vRealize Log Insight if vROPs service is installed | Syslog |
{: caption="Table 7. Juniper vSRX ports" caption-side="top"}

## Ports for Red Hat OpenShift for VMWare
{: #vmwaresol_ports-vmware-optional-services-red-hat-openshift}

The following table provides information about the Red Hat® OpenShift® ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| OCP | New subnet ordered in private VLAN | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use Windows DNS service | DNS |
| OCP | New subnet ordered in private VLAN | vCenter Server | Infrastructure VMs | 443 | TCP | Use vCenter Server REST service | HTTPS |
| OCP | New subnet ordered in private VLAN | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | NTP |
| OCP | New subnet ordered in private VLAN | OCP cluster network | OCP internal IP range 10.128.0.0/14 | 5443/8443 | TCP | OCP cluster management | WEBREST API |
| OCP edge public IP addresses| New subnet ordered in public VLAN | Public websites required for OpenShift installation[^osinst] | | 80/123/443 | TCP and UDP | Time service, OpenShift installation content, and images | NTP/HTTP/HTTPS |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | OCP | New subnet ordered in private VLAN | 22 | TCP | Set up and configure OCP | SSH |
{: caption="Table 8. Red Hat OpenShift for VMWare ports" caption-side="top"}

[^osinst]: For more information, see [Configuring your firewall](https://docs.openshift.com/container-platform/4.4/installing/install_config/configuring-firewall.html){: external}.

For more information about OCP networking, see [About the OpenShift SDN network provider](https://docs.openshift.com/container-platform/4.4/networking/openshift_sdn/about-openshift-sdn.html){: external}.

## Ports for Veeam
{: #vmwaresol_ports-vmware-optional-services-veeam}

The following table provides information about the Veeam® ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure DNS service | Private primary subnet  \n Infrastructure VMs | 53 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure DNS service | UDP |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | NTP |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure service - Provision Windows VSI | {{site.data.keyword.cloud_notm}} infrastructure services network | | ICMP | Use infrastructure services to provision Windows VSI for Veeam | Ping |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure service - Provision Windows VSI | {{site.data.keyword.cloud_notm}} infrastructure services network | 10000 | TCP | Use infrastructure services to provision Windows VSI for Veeam | |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure service - Provision Windows VSI | {{site.data.keyword.cloud_notm}} infrastructure services network | 10001 | TCP | Use infrastructure services to provision Windows VSI for Veeam | |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure service - Provision Windows VSI | {{site.data.keyword.cloud_notm}} infrastructure services network | 88 | TCP and UDP | Use infrastructure services to provision Windows VSI for Veeam | |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure Windows KMS service | {{site.data.keyword.cloud_notm}} infrastructure services network | 1688 | TCP | Use {{site.data.keyword.cloud_notm}} infrastructure Windows KMS service | |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} service - Cloud Object Storage | {{site.data.keyword.cloud_notm}} endpoint service network | 443 | TCP | Use {{site.data.keyword.cloud_notm}} Object Storage service | HTTPS |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure WSUS service | {{site.data.keyword.cloud_notm}} infrastructure services network | 80 | TCP | Use {{site.data.keyword.cloud_notm}} infrastructure WSUS service | HTPP |
| Veeam | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure endurance storage | {{site.data.keyword.cloud_notm}} infrastructure services network | 3260 | TCP | Use {{site.data.keyword.cloud_notm}} infrastructure endurance storage | ISCSI |
| {{site.data.keyword.cloud_notm}} infrastructure Service - Provision Windows VSI | {{site.data.keyword.cloud_notm}} infrastructure services network 10.0.0.0/14 | Veeam | Private primary subnet | 8051 | TCP | EMC2 (Legato) Networker or Sun Solstice Backup | |
| {{site.data.keyword.cloud_notm}} infrastructure Service - Provision Windows VSI | {{site.data.keyword.cloud_notm}} infrastructure services network 10.200.0.0/14 | Veeam | Private primary subnet | | ICMP | ICMP | Ping |
{: caption="Table 9. Veeam ports" caption-side="top"}

## Ports for vRealize Operations and Log Insight
{: #vmwaresol_ports-vmware-optional-services-vrops-loginsight}

The following table provides information about the vROps ports for vCenter Server with NSX-T instances.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| ESXi host | Private primary subnet | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| vCenter Server | Infrastructure VMs | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| vROps | New subnet ordered in private VLAN | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | TCP and UDP | Use Windows DNS service | DNS |
| vROps | New subnet ordered in private VLAN | vCenter Server | Infrastructure VMs | 443 | TCP | vROps configuration | HTTPS |
| vROps | New subnet ordered in private VLAN | NSX-T Manager and NSX-T Controllers | Infrastructure VMs | 443 | TCP | vROps configuration | HTTPS |
| vROps | New subnet ordered in private VLAN | NSX-T Manager and NSX-T Controllers | Infrastructure VMs | 1234 | TCP | NSX messaging | |
| vROps | New subnet ordered in private VLAN | NSX-T Manager and NSX-T Controllers | Infrastructure VMs | 1235 | TCP | NSX messaging |  |
| vROps | New subnet ordered in private VLAN | NSX-T virtual IP | Infrastructure VMs | 443 | TCP | vROps configuration | HTTPS |
| NSX-T Manager and NSX-T Controllers | Infrastructure VMs | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| Customer-nsx-edge private IP  | Customer edge gateway private | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | TCP and UDP | Use Windows DNS service | DNS |
| Customer-nsx-edge private IP  | Customer edge gateway private | NSX-T Manager and NSX-T Controllers | Infrastructure VMs | 1234 | TCP | NSX messaging | |
| Customer-nsx-edge private IP  | Customer edge gateway private | NSX-T Manager and NSX-T Controllers | Infrastructure VMs | 1235 | TCP | NSX messaging | |
| Customer-nsx-edge private IP  | Customer edge gateway private | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | vROps | New subnet ordered in private VLAN | 22 | TCP | Set up and configure vROps | SSH |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | vROps | New subnet ordered in private VLAN | 443 | TCP | Set up and configure vROps | HTTPS |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | vROps | New subnet ordered in private VLAN | 9543 | TCP | Set up and configure vROps | HTTPS |
| Windows Active Directory | Private primary subnet  \n Infrastructure VMs | vROps | New subnet ordered in private VLAN | 9543 | TCP | Set up and configure vROps | |
| Service edge | Infrastructure VMs | Windows Active Directory | Private primary subnet  \n Infrastructure VMs | 53 | TCP and UDP | Use Windows DNS service | DNS |
| Service edge | Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure DNS service | {{site.data.keyword.cloud_notm}} infrastructure services network | 53 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP | DNS |
| Service edge | Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP | NTP |
{: caption="Table 10. vROps ports for NSX-T instances" caption-side="top"}

The following table provides information about the vRealize Operations™ and vRealize Log Insight™ (vROps) ports when vROps is deployed in a vCenter Server with NSX-V instance.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| ESXi host | Private primary subnet | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| vCenter Server | Infrastructure VMs | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| Local address (192.168.100.3) | Local address | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| vROps | New subnet ordered in private VLAN | Windows Active Directory | Private primary subnet  \n Infrastructure VMs| 53 | TCP and UDP | Use Windows DNS service | DNS |
| vROps | New subnet ordered in private VLAN | vCenter Server | Infrastructure VMs | 443 | TCP | vROps configuration | HTTPS |
| vROps | New subnet ordered in private VLAN | NSX Manager | Infrastructure VMs | 443 | TCP | vROps configuration | HTTPS |
| NSX Manager | Infrastructure VMs | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| Management edge private IP | Infrastructure VMs | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| Customer-nsx-edge private IP | Customer edge gateway private | vROps | New subnet ordered in private VLAN | 514 | UDP | Remote syslog | Syslog |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | vROps | New subnet ordered in private VLAN | 22 | TCP | Set up and configure vROps | SSH |
| IBM CloudDriver | Private primary subnet  \n Infrastructure VMs | vROps | New subnet ordered in private VLAN | 443 | TCP | Set up and configure vROps | HTTPS |
| Windows Active Directory | Private primary subnet  \n Infrastructure VMs | vROps | New subnet ordered in private VLAN | 9543 | TCP | Set up and configure vROps | |
{: caption="Table 11. vROps ports for NSX-V instances" caption-side="top"}

For more information about port requirements for vROPs, see [TCP and UDP ports required to access VMware vRealize Operations Manager](https://kb.vmware.com/s/article/52964){: external}.

## Ports for Zerto
{: #vmwaresol_ports-vmware-optional-services-zert0}

The following table provides information about Zerto ports.

| Source | Subnet/IP range | Target | Subnet/IP range |  Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:------|:---------|:--------|:--------|
| Zerto Management VSI (ZVM) | Private primary subnet  \n Infrastructure VMs | Zerto VRA agents | New subnet ordered in private VLAN | 4006 | TCP | TLS over TCP communication between the ZVM and local site VRAs | |
| Zerto Management VSI (ZVM) | Private primary subnet  \n Infrastructure VMs | Zerto VRA agents | New subnet ordered in private VLAN | 4009 | TCP | TLS over TCP communication between the ZVM and local site VRAs to handle checkpoints | |
| Zerto Management VSI (ZVM) | Private primary subnet  \n Infrastructure VMs | Zerto VRA agents | New subnet ordered in private VLAN | | ICMP | Check network connectivity from ZVM to the VRAs | Ping |
{: caption="Table 12. Zerto ports" caption-side="top"}

For more information about Zerto networking, see [Zerto - prerequisites and requirements for vSphere environments](http://s3.amazonaws.com/zertodownload_docs/Latest/Zerto%20Virtual%20Replication%20vSphere%20Enterprise%20Guidelines.pdf){: external}.

## Related links
{: #vmwaresol_ports-related}

* [VMware Solutions network architecture](/docs/vmwaresolutions?topic=vmwaresolutions-under_the_hood#under_the_hood-network)
