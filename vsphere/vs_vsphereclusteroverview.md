---

copyright:

  years:  2016, 2019

lastupdated: "2019-10-14"

keywords: vSphere, vSphere component, tech specs vSphere

subcollection: vmware-solutions


---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# VMware vSphere overview
{: #vs_vsphereclusteroverview}

VMware vSphere is a streamlined and optimized ordering platform for VMware. With this platform, you can build your own IBM-hosted VMware environment by customizing and ordering the VMware-compatible hardware based on your selected VMware components.

The {{site.data.keyword.vmwaresolutions_short}} console filters the hardware automatically, based on the VMware components that you select. For example, when you create a new all-flash VMware vSAN cluster, only the hardware that is validated against the [VMware Compatibility Guide](https://www.vmware.com/resources/compatibility/search.php){:external} is presented. Also, a minimum of four ESXi servers is required.

VMware vSphere does not automate the installation, configuration, and bring-up of the optional VMware components. The platform allows maximum of flexibility to design and build your hosted VMware environment while incorporating VMware-compatible hardware.

Use this offering to create a new cluster of ESXi servers or scale out an existing cluster of ESXi servers in an {{site.data.keyword.CloudDataCent_notm}}. Depending on the VMware components that you select, you can start with just one ESXi server and then scale the cluster later as needed.

## Technical specifications for VMware vSphere clusters
{: #vs_vsphereclusteroverview-specs}

Review the components of VMware vSphere.

The availability and pricing of standardized hardware configurations might vary based on the {{site.data.keyword.CloudDataCent_notm}} that is selected for deployment.
{:note}

### VMware components
{: #vs_vsphereclusteroverview-specs-vmware-components}

Select licenses (IBM-provided or BYOL) for the following VMware components:
* VMware vSphere Enterprise Plus 6.7 U2 or 6.5 U2
* The following VMware components are optional:
   * VMware vCenter Server Standard
   * VMware NSX (Base, Advanced, or Enterprise)
   * VMware vSAN (Advanced or Enterprise)
   * VMware Site Recovery Manager
   * VMware vRealize Automation Enterprise
   * VMware vRealize Operations Enterprise
   * VMware vRealize Log Insight

### Bare Metal Server
{: #vs_vsphereclusteroverview-specs-bare-metal}

You can order one or more {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} with one of the following configurations:
* **Skylake**: 2-CPU Intel Skylake generation servers (Intel Xeon 4100/5100/6100 series) with your selected CPU model and RAM size.
* **Cascade Lake**: 2-CPU Intel Cascade Lake generation servers (Intel Xeon 4200/5200/6200 series) with your selected CPU model and RAM size.
* **SAP-certified**: Intel Skylake or Intel Broadwell generation servers (Intel Xeon 6140/E5-2690/E7-8890 series) with your selected CPU model.
* **Broadwell**: 4-CPU Intel Broadwell generation servers (Intel Xeon E7-4800 series) with your selected CPU model and RAM size.

The options available depend on whether you selected the VMware vSAN component.

Additionally, the following disk and networking specifications:
* 10 Gbps dual public and private network uplinks
* One RAID disk controller

### Networking
{: #vs_vsphereclusteroverview-specs-network}

* One VLAN (Virtual LAN) public VLAN and two private VLANs
* (Optional) An HA-pair of FortiGate Security Appliance devices

### Storage
{: #vs_vsphereclusteroverview-specs-storage}

User-customized storage for vSAN configuration when the VMware vSAN component is selected:
* Storage disk options of 960 GB SSD SED, 1.9 TB SSD SED, or 3.8 TB SSD SED
* Disk quantity options of 2, 4, 6, or 8

  Additionally, two cache disks of 960 GB are also ordered per host.

  3.8 TB SSD (Solid State Disk) drives are supported when they are made generally available in a data center.
  {:note}
* High-Performance Intel Optane option, which provides two extra capacity disk bays for a total of 10 capacity disks. This option depends on the CPU model.

## Technical specifications for vSphere cluster expansion nodes
{: #vs_vsphereclusteroverview-expansion-node-specs}

Each vSphere cluster expansion node deploys and incurs charges for the following components in your {{site.data.keyword.slportal}} account.

### Hardware for expansion nodes
{: #vs_vsphereclusteroverview-expansion-node-specs-hardware}

One {{site.data.keyword.cloud_notm}} Bare Metal Server with the hardware configuration presented in [Technical specifications for VMware vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_vsphereclusteroverview#specs).

### Networking for expansion nodes
{: #vs_vsphereclusteroverview-expansion-node-specs-network}

One {{site.data.keyword.cloud_notm}} Bare Metal Server with the networking configuration presented in [Technical specifications for VMware vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_vsphereclusteroverview#specs).

### VMware components for expansion nodes
{: #vs_vsphereclusteroverview-expansion-node-specs-vmware-components}

* One {{site.data.keyword.cloud_notm}} Bare Metal Server with VMware vSphere Enterprise Plus 6.7u2 or 6.5u2.  
* Optional VMware components presented in [Technical specifications for VMware vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_vsphereclusteroverview#specs).

You must manage the ESXi servers, optional VMware components, and additional hardware that are ordered and delivered to your {{site.data.keyword.cloud_notm}} account only from the {{site.data.keyword.slportal}}. After creating a new cluster in the {{site.data.keyword.vmwaresolutions_short}} console, you can return to the console and use the saved information to scale the new cluster. For more information, see [Scaling existing vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_scalingexistingclusters).
{:important}

## Related links
{: #vs_vsphereclusteroverview-related}

* [VMware vSphere Software Bill of Materials](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_bom)
* [Planning vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_planning)
* [Ordering vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_orderinginstances)
* [Scaling existing vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_scalingexistingclusters)
