---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-13"

---

# VMware vSphere on IBM Cloud overview

VMware vSphere on IBM® Cloud is a streamlined and optimized ordering platform for VMware, which allows you to build your own IBM-hosted VMware environment by customizing and ordering the VMware-compatible hardware based on your selected VMware components.

The {{site.data.keyword.vmwaresolutions_full}} console filters the hardware automatically, based on the VMware components that you select. For example, when creating a new all-flash VMware vSAN cluster, only the hardware that is validated against the [VMware Compatibility Guide](https://www.vmware.com/resources/compatibility/search.php) is presented and a minimum of four ESXi servers is required.

VMware vSphere on IBM Cloud does not automate the installation, configuration, and bring-up of the optional VMware components and it allows maximum of flexibility to design and build your hosted VMware environment while incorporating VMware-compatible hardware.

Use this offering to create a new cluster of ESXi servers or scale out an existing cluster of ESXi servers in an IBM Cloud data center. Depending on the VMware components that you select, you can start with just one ESXi server and then scale the cluster later as needed.

## Components of VMware vSphere on IBM Cloud

Review the components of VMware vSphere on IBM Cloud.

**Note**: The availability and pricing of standardized hardware configurations might vary based on the data center that is selected for deployment.

### VMware components

IBM-provided licenses or user-provided licenses for the following VMware components:
* VMware vSphere Enterprise Plus 6.0u2 or 6.5u1
* Optional VMware components:
   * VMware vCenter Server Standard
   * VMware NSX (Base, Advanced, or Enterprise)
   * VMware vSAN (Advanced or Enterprise)
   * VMware vRealize Automation Enterprise
   * VMware vRealize Operations Enterprise
   * VMware vRealize Log Insight
   * VMware Site Recovery Manager

### Hardware

One or more IBM Cloud bare metal servers with the following CPU and RAM options.
* CPU options:
   * Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz
   * Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz
   * Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz
* RAM options: 64 GB, 128 GB, 256 GB, 384 GB, 512 GB, 768 GB, 1 TB, and 1.5 TB

The options available depend on whether you selected the VMware vSAN component.

In addition, the following disk and networking specifications:
* 10 Gbps dual public and private network uplinks
* One RAID disk controller

### Storage

User-customized storage for VMware vSAN configuration when the VMware vSAN component is selected:
* Storage disk: 1.2 TB SSD
* Disk quantity options: 2, 4, 6, and 8

### Networking

* Three VLANs (Virtual LANs): one public VLAN and two private VLANs
* (Optional) An HA-pair of FortiGate Security Appliance devices

## Components of vSphere cluster expansion nodes 

Each vSphere cluster expansion node will deploy and incur charges for the following components in your IBM Bluemix Infrastructure (SoftLayer) account.

### Hardware for expansion nodes

One IBM Cloud bare metal server with the hardware configuration presented in [Components of VMware vSphere on IBM Cloud](../vsphere/vs_vsphereclusteroverview.html#components-of-vmware-vsphere-on-ibm-cloud).

### Networking for expansion nodes

One IBM Cloud bare metal server with the networking configuration presented in [Components of VMware vSphere on IBM Cloud](../vsphere/vs_vsphereclusteroverview.html#components-of-vmware-vsphere-on-ibm-cloud).

### VMware components for expansion nodes

* One IBM Cloud bare metal server with VMware vSphere Enterprise Plus 6.0u2 or VMware vSphere Enterprise Plus 6.5u1  
* Optional VMware components presented in [Components of VMware vSphere on IBM Cloud](../vsphere/vs_vsphereclusteroverview.html#components-of-vmware-vsphere-on-ibm-cloud).

**Important**: You must manage the ESXi servers, optional VMware components, and additional hardware that are ordered and delivered to your Bluemix Infrastructure (SoftLayer) account only from the Bluemix Infrastructure (SoftLayer) portal. After creating a new cluster in the {{site.data.keyword.vmwaresolutions_short}} console, you can return to the console to scale the new cluster using the saved configuration. For more information, see [Scaling existing clusters](vs_scalingexistingclusters.html).

## Related links

* [Planning vSphere clusters](vs_planning.html)
* [Ordering vSphere clusters](vs_orderinginstances.html)
* [Scaling existing vSphere clusters](vs_scalingexistingclusters.html)
