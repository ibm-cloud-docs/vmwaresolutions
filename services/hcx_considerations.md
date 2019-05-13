---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-23"

subcollection: vmware-solutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# VMware HCX on IBM Cloud overview
{: #hcx_considerations}

The HCX on {{site.data.keyword.cloud}} service seamlessly extends the networks of on-premises data centers into {{site.data.keyword.cloud_notm}}, which allows you to migrate virtual machines (VMs) to and from the {{site.data.keyword.cloud_notm}} without any conversion or change.

This service is available only to VMware vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle instances that are deployed in V2.3 and later. The current HCX on {{site.data.keyword.cloud_notm}} version that is installed is 3.5.1.
{:note}

You can upgrade your existing vCenter Server instance to a vCenter Server with Hybridity Bundle instance. For more information about upgrading your instance and deploying the HCX on {{site.data.keyword.cloud_notm}} service, see [Procedure to upgrade to Hybridity Bundle](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_upgrade-lic#vc_upgrade-lic-procedure-upgrade-to-hybridity).

A vCenter Server instance with HCX on {{site.data.keyword.cloud_notm}} is limited to three simultaneous connections from on-premises sites.
{:note}

## Technical specifications for HCX on IBM Cloud
{: #hcx_considerations-specs}

The following components are ordered and included in the HCX on {{site.data.keyword.cloud_notm}} service.

On-premises HCX instances include only licensing and activation.
{:note}

### An active/passive pair of VMware NSX Edge Services Gateways for HCX Management
{: #hcx_considerations-nsx}

* CPU: 6 vCPU
* RAM: 8 GB
* Disk: 3 GB VMDK

### HCX Management Appliance - virtual machine
{: #hcx_considerations-vm}

* CPU: 4 vCPU
* RAM: 12 GB
* Disk: 60 GB VMDK

Additional HCX appliances are deployed during configuration as necessary for L2 connectivity, WAN optimization, and gateway connections.

### Networking
{: #hcx_considerations-networking}

* One public portable subnet with 16 IP addresses
* Two private portable subnets with 64 IP addresses
* Eight IP addresses from private portable vMotion subnet

## Considerations when you install HCX on IBM Cloud
{: #hcx_considerations-install}

Review the following considerations before attempting to install HCX on {{site.data.keyword.cloud_notm}}.

### Requirements on the number of ESXi servers
{: #hcx_considerations-esxi-servers}

The HCX on {{site.data.keyword.cloud_notm}} service cannot be installed into an instance for which the default cluster has more than 51 ESXi servers. Because HCX on {{site.data.keyword.cloud_notm}} requires eight IP addresses in the vMotion subnet from the default cluster, if the number of ESXi servers exceeds 51, no IP addresses in the vMotion subnet are available for HCX on {{site.data.keyword.cloud_notm}}.

### Requirements on firewall rules
{: #hcx_considerations-firewall}

Before you install the HCX on {{site.data.keyword.cloud_notm}} service, you must add a firewall rule to any existing firewalls to allow all outbound HTTPS traffic so that the HCX Manager virtual appliance (HCX Manager) can register itself. After the HCX Manager installation is completed, you can remove the firewall rule. In addition, you must configure firewall rules to allow HCX to function properly. For more information, see [VMware HCX on {{site.data.keyword.cloud_notm}} port access requirements](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-port-req#hcx-archi-port-req).

## Considerations when you remove HCX on IBM Cloud
{: #hcx_considerations-delete}

Review the following considerations before you remove the HCX on {{site.data.keyword.cloud_notm}} service:
* Ensure that the interconnects and extended networks between the on-premises source site and the {{site.data.keyword.cloud_notm}} target sites are removed. To remove the interconnects and extended networks, use the HCX user interface in the on-premises VMware vSphere Web Client.
* Ensure that the site pairings between the on-premises source site and the {{site.data.keyword.cloud_notm}} target sites are removed. To remove the site pairings, use the HCX user interface in the on-premises VMware vSphere Web Client.
* The removal of HCX on {{site.data.keyword.cloud_notm}} is automated. The following procedures are completed for the successful removal of this service:
   * The HCX license that is ordered for the cloud-side HCX Manager is deactivated.
   * HCX Manager is deleted.
   * The vMotion IP addresses that were reserved for HCX are released.
   * If empty, the HCX-related resource pools are removed.
   * If empty, the HCX-related folders are removed.
   * The HCX management edge appliances are deleted.

## Related links
{: #hcx_considerations-related}

* [Ordering HCX on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx_ordering)
* [Managing HCX on {{site.data.keyword.cloud_notm}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-managinghcx)
* [Glossary of HCX terms](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx_glossary)
* [Contacting IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [VMware Hybrid Cloud Extension overview](https://cloud.vmware.com/vmware-hcx)
* [VMware Hybrid Cloud Extension documentation](https://cloud.vmware.com/vmware-hcx/resources)
