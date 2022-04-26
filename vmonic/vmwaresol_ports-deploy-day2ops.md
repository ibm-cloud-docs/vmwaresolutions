---

copyright:

  years:  2020, 2022

lastupdated: "2022-04-06"

keywords: VLAN ports, vmware solutions ports, ports usage vmware solutions

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Ports that are used for deployment and Day 2 operations
{: #vmwaresol_ports-deploy-day2ops}

The following table provides information about the ports for deployment and Day 2 operations.

Review the following information about the ports described in the [table](#vmwaresol_ports-deploy-day2ops-table):

* Windows® Active Directory™ has two options: single Windows Virtual Service Instance (VSI) and two HA dedicated Windows Server virtual machines (VMs).
   For single Windows VSI, the VSI is in the primary subnet. For Windows server VMs, the VSIs are in the infrastructure VMs subnet.
* {{site.data.keyword.cloud}} infrastructure services network includes the following subnets. For more information, see [IBM Cloud IP ranges](/docs/hardware-firewall-dedicated?topic=hardware-firewall-dedicated-ibm-cloud-ip-ranges#ibm-cloud-ip-ranges).
   * `10.0.0.0/14`
   * `10.198.0.0/15`
   * `10.200.0.0/14`
   * `161.26.0.0/16`
* {{site.data.keyword.cloud_notm}} endpoint service network includes 166.8.0.0/14.

For more information about {{site.data.keyword.redhat_openshift_full}} (OCP) networking, see [About the {{site.data.keyword.redhat_openshift_notm}} SDN network provider](https://docs.openshift.com/container-platform/4.4/networking/openshift_sdn/about-openshift-sdn.html){: external}.

For more information about IBM CloudBuilder and IBM CloudDriver, see [IBM CloudDriver](/docs/vmwaresolutions?topic=vmwaresolutions-design_infrastructuremgmt#design_infrastructuremgmt-cloud-driver).

| Source | Subnet, IP range | Target | Subnet, IP range | Port | Protocol | Purpose | Service |
|:-------|:----------------|:-------|:----------------|:-----|:---------|:--------|:--------|
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} Service - Cloud Object Storage \n 10.1.129.0/24[^vssreqa] | {{site.data.keyword.cloud_notm}} endpoint service network | 443 | TCP | Use {{site.data.keyword.cloud_notm}} Object Storage service | HTTPS |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} Service - RabbitMQ \n 166.9.48.91, 166.9.51.14, 166.9.58.39[^vssreqb] | {{site.data.keyword.cloud_notm}} endpoint service network | 32378 | TCP | Use {{site.data.keyword.cloud_notm}} RabbitMQ service | |
| IBM CloudBuilder | Private primary subnet | vCenter Server | Infrastructure VMs | | ICMP | Install and set up vCenter Server | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | vCenter Server | Infrastructure VMs | 22 | TCP | Set up and configure vCenter Server | SSH |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | vCenter Server | Infrastructure VMs | 443 | TCP | Install and configure vCenter Server and cluster | SSH |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | vCenter Server | Infrastructure VMs | 9443 | TCP | Install and configure vCenter Server and cluster | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | vCenter Server | Infrastructure VMs | 5489 | TCP | Install and configure vCenter Server and cluster | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | ESXi™ host | Private primary subnet | 22 | TCP™ | Set up, configure, and apply patches to ESXi host | SSH |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | ESXi vMotion | vMotion traffic | | ICMP™ | Set up ESXi network | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | ESXi vSAN™  | vSAN traffic | | ICMP | Set up ESXi network | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | ESXi shared storage | Shared storage traffic | | ICMP | Set up ESXi network | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | Customer edge private | Customer edge gateway private | | ICMP | Set up NSX edge network | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | Windows Active Directory  | Private primary subnet (for Windows VSI)/ \n Infrastructure VMs (for Windows VMs) | 5986 | TCP | Set up and configure Windows Active Directory and DNS  | |
| IBM CloudBuilder | Private primary subnet \n Infrastructure VMs | NSX Manager | Infrastructure VMs | | ICMP | Install and set up NSX Manager | |
| IBM CloudBuilder | Private primary subnet \n Infrastructure VMs | NSX Manager | Infrastructure VMs | 443 | TCP | Set up and configure NSX Manager | HTTPS |
| IBM CloudBuilder | Private primary subnet \n Infrastructure VMs | NSX Manager | Infrastructure VMs | 80 | TCP | Set up and configure NSX Manager | HTTP |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure provisioning API | {{site.data.keyword.cloud_notm}} infrastructure services network | 443 | TCP | Order and provision {{site.data.keyword.cloud_notm}} infrastructure resources | HTTPS |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure DNS service | {{site.data.keyword.cloud_notm}} infrastructure services network | 53 | UDP™ | Use {{site.data.keyword.cloud_notm}} infrastructure DNS service | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure endurance storage | {{site.data.keyword.cloud_notm}} infrastructure services network | Any | ICMP and TCP | Set up endurance storage for ESXi host | |
| IBM CloudBuilder \n IBM CloudDriver | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} Activity Tracker service | {{site.data.keyword.cloud_notm}} endpoint service network | 443 | TCP | Use {{site.data.keyword.cloud_notm}} Activity Tracker service | HTPPS |
| Windows Active Directory | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure DNS service | {{site.data.keyword.cloud_notm}} infrastructure services network | 53 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure DNS service | |
| Windows Active Directory | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | |
| Windows Active Directory | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure WSUS service | {{site.data.keyword.cloud_notm}} infrastructure services network | 80 | TCP | Use {{site.data.keyword.cloud_notm}} infrastructure WSUS service | HTTP |
| Windows Active Directory | Private primary subnet \n Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure Windows KMS service | {{site.data.keyword.cloud_notm}} infrastructure services network | 1688 | TCP | Use {{site.data.keyword.cloud_notm}} infrastructure Windows KMS service | |
| ESXi host | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | |
| vCenter Server | Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | |
| NSX Manager | Infrastructure VMs | {{site.data.keyword.cloud_notm}} infrastructure NTP service | {{site.data.keyword.cloud_notm}} infrastructure services network | 123 | UDP | Use {{site.data.keyword.cloud_notm}} infrastructure NTP service | |
| NSX Manager | Infrastructure VMs | TEP subnet | TEP traffic | 443 |  |  |  |
| NSX Manager | Infrastructure VMs | Customer edge subnet | Customer edge private traffic | 443 |  |  |  |
| ESXi host shared storage | ESXi shared storage | {{site.data.keyword.cloud_notm}} infrastructure endurance storage | {{site.data.keyword.cloud_notm}} infrastructure services network | 111, 635, and 2049 | TCP and UDP | Use {{site.data.keyword.cloud_notm}} infrastructure endurance storage | |
| IBM CloudBuilder \n IBM CloudDriver \n Windows Active Directory (VSI) | Private primary subnet | {{site.data.keyword.cloud_notm}} infrastructure engine | {{site.data.keyword.cloud_notm}} infrastructure services network | 80 | TCP | Provision IBM CloudBuilder, IBM CloudDriver, and Windows Active Directory (VSI) | |
| {{site.data.keyword.cloud_notm}} infrastructure engine | {{site.data.keyword.cloud_notm}} infrastructure services network | IBM CloudBuilder \n IBM CloudDriver \n Windows Active Directory (VSI) | Private primary subnet | Any | TCP and UDP | Provision IBM CloudBuilder, IBM CloudDriver, and Windows Active Directory (VSI) |   |
| {{site.data.keyword.cloud_notm}} infrastructure engine | {{site.data.keyword.cloud_notm}} infrastructure services network | ESXi host management0 | Private primary subnet | 623 | TCP and UDP | {{site.data.keyword.cloud_notm}} infrastructure IPMI |   |
{: caption="Table 1. Ports for deployment and Day 2 operations" caption-side="top"}
{: #vmwaresol_ports-deploy-day2ops-table}

[^vssreqa]: VMware vSphere clusters require access to both Cloud Object Storage and RabbitMQ.
[^vssreqb]: VMware vSphere clusters require access to both Cloud Object Storage and RabbitMQ.

## Related links
{: #vmwaresol_ports-deploy-day2ops-related}

* [Ports used by VMware](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-vmwareuses)
* [VMware Solutions network architecture](/docs/vmwaresolutions?topic=vmwaresolutions-under_the_hood#under_the_hood-network)
