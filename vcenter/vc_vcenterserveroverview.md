---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-22"

---

# vCenter Server overview

Review the architecture and components of the vCenter Server deployment.

## vCenter Server architecture

The following graphic depicts the high-level architecture of a two-node cluster.

Figure 1. vCenter Server high-level architecture for a two-node cluster

![vCenter Server architecture](vc_architecture.jpg)

The architecture contains the following layers:
* **Physical infrastructure**: This layer provides the physical compute, storage, and network resources to be used by the virtual infrastructure.
* **Virtualization infrastructure**: This layer virtualizes the physical infrastructure through different VMware products:
  *  VMware vSphere virtualizes the physical compute resources.
  *  VMware NSX is the network virtualization platform that provides logical networking components and virtual networks.
* **Virtualization management**: This layer consists of vCenter Server virtual appliance, NSX Manager, two NSX ESGs, 3 NSX Controllers, Platform Services Controller (PSC) virtual appliance, vCSA, and the IBM® CloudDriver virtual machine.

The base offering is deployed with a vCenter Server appliance that is sized to support an environment with up to 100 hosts and up to 1000 VMs. The same vSphere API-compatible tools and scripts can be used to manage the IBM-hosted VMware environment.

In total, the base offering requires 32 vCPU and 58 GB vRAM that are reserved for the virtualization management layer. The remaining host capacity for your VMs depends on several factors, such as oversubscription rate, VM sizing, and workload performance requirements.

The {{site.data.keyword.vmwaresolutions_full}} console provides the interface to manage the automated snapshot-based backup of the virtualization management layer with up to 14 points of restoration.

For details about the architecture, see the _Reference architecture_ document in the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtVCenterServerPlatform){:new_window}.

## vCenter Server instance components

The following components are included in your vCenter Server instance.

**Note**: The availability and pricing of standardized hardware configurations might vary based on the data center that is selected for deployment.

### Hardware

One or more IBM Cloud bare metal servers with the following hardware options to choose from:
*  Small (Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz / 128 GB RAM / 2 disks)
*  Medium (Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz / 256 GB RAM / 2 disks)
*  Large (Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz / 512 GB RAM / 2 disks)
*  User customized (the user selects the CPU and RAM options)

### Networking

*  Three VLANs (Virtual LANs): one public VLAN and two private VLANs
*  One VXLAN (Virtual eXtensible LAN) with DLR (Distributed Logical Router) for potential east-west communication between local workloads that are connected to layer 2 (L2) networks. The VXLAN is deployed as a sample routing topology, which you can modify, build on it, or remove it. You can also add security zones by attaching additional VXLANs to new logical interfaces on the DLR.
*  Two VMware NSX Edge Services Gateways:
  * A secure management services VMware NSX Edge Services Gateway (ESG) for outbound HTTPS management traffic, which is deployed by IBM as part of the management networking typology. This ESG is used by the IBM management virtual machines to communicate with specific external IBM management components that are related to automation. For more information, see [Configuring your network to use the customer-managed ESG](../vcenter/vc_esg_config.html#configuring-your-network-to-use-the-customer-managed-nsx-edge-services-gateway-with-your-vms).

    **Important**: This ESG is not accessible to you and you cannot use it. If you modify it, you might not be able to manage the vCenter Server instance from the {{site.data.keyword.vmwaresolutions_short}} console. In addition, note that using a firewall or disabling the ESG communications to the external IBM management components will cause {{site.data.keyword.vmwaresolutions_short}} to become unusable.
  * A secure customer-managed VMware NSX Edge Services Gateway for outbound and inbound HTTPS workload traffic, which is deployed by IBM as a template that can be modified by you to provide VPN access or public access. For more information, see [Does the customer-managed NSX Edge pose a security risk?](../vmonic/faq.html#does-the-customer-managed-nsx-edge-pose-a-security-risk-)

### Virtual Server Instances

Two VSIs (Virtual Server Instances):
*  A VSI for IBM CloudBuilder, which is shut down after the instance deployment is completed.
*  A VSI for the snapshot-based backup of the management components, which keeps running after the instance deployment is completed.

### Storage

*  Shared file-level storage for backups: one 2 TB shared file-level storage that can be scaled up to 12 TB

  **Note**: With the introduction of the Veeam on IBM Cloud service, the storage for backups is no longer a standard component of vCenter Server instances. When you order an instance, you can choose whether you want storage for backups by selecting or deselecting the Veeam on IBM Cloud service.
*  Shared file-level storage for management components: one 2 TB, 4 IOPS/GB file share

### Licenses and fees

*  VMware vSphere 6.0 Enterprise Plus Edition
*  VMware vCenter Server 6.0
*  VMware NSX Base for Service Providers Edition
*  Support and Services fee (one license per node)

## vCenter Server expansion node components

Each vCenter Server expansion node will deploy and incur charges for the following components in your SoftLayer® account:

### Hardware

One IBM Cloud bare metal server, with the configuration presented in [vCenter Server instance  components](../vcenter/vc_vcenterserveroverview.html#vcenter-server-components).

### Licenses and fees

*  One VMware vSphere 6.0
*  One Support and Services fee

For details about the components, see the _Bill of Materials_ document in
the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtVCenterServerPlatform){:new_window}.

**Important**: You must manage the {{site.data.keyword.vmwaresolutions_short}} components that are created in your SoftLayer account only from the {{site.data.keyword.vmwaresolutions_short}} console, not the SoftLayer Customer Portal or any other means outside of the console. If you change these components outside of the {{site.data.keyword.vmwaresolutions_short}} console, the changes are not synchronized with the console.

**CAUTION**: Managing any {{site.data.keyword.vmwaresolutions_short}} components (which were installed into your SoftLayer account when you ordered the instance) from outside the {{site.data.keyword.vmwaresolutions_short}} console can make your environment unstable. These management activities include:
*  Adding, modifying, returning, or removing components
*  Expanding or contracting instance capacity through adding or removing ESXi servers
*  Powering off components
*  Restarting services

## Related links

* [Planning vCenter Server instances](vc_planning.html)
* [Ordering vCenter Server instances](vc_orderinginstance.html)
* [Bluemix file and block storage](https://www.ibm.com/devops/method/content/architecture/virtVCenterServerPlatform/sharedStorage){:new_window}
