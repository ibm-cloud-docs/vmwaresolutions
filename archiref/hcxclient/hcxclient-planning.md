---

copyright:

  years:  2016, 2019

lastupdated: "2019-10-18"

subcollection: vmware-solutions


---

# Preparing the installation environment
{: #hcxclient-planning-prep-install}

The installation of VMware HCX on {{site.data.keyword.cloud}} has the following software requirements:
* vSphere 5.5 U3, or vSphere 6.0u2 or higher.
* If NSX is used, version 6.2.2 or higher. NSX is required for policy migration.
* To use cross-cloud vMotion, the same affinity restrictions apply across clouds as they do on-premises. For more information, see the [VMware EVC and CPU Compatibility FAQ](https://kb.vmware.com/s/article/1005764).

## Configuring network connectivity
{: #hcxclient-planning-config-net}

HCX must traverse the public internet and private lines, and connect to data center components, such as networks, switches, and port groups.
* For information about the ports that must be opened so that HCX virtual appliances can install successfully, see [Port access requirements](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcx-archi-port-req).
* Both the on-premises vSphere environment and the VCS HCX Cloud environment must allow Network Time Protocol (NTP) clock synchronization among vSphere on-premises devices and the VCS HCX devices. UDP port 123 must be accessible to HCX virtual appliances and networks.

## On-premises environment
{: #hcxclient-planning-on-prem-env}

Before you install HCX, verify that your environment can support the tasks that you want to accomplish. The on-premises environment must support the following tasks before HCX can be installed.
* Virtual Center with vSphere 5.5 Update 3 or 6.0 Update 2.
* vMotion and policy migration features require NSX version 6.2.2 or higher.
* A vSphere service account with the Administrator vCenter Server system role assigned to it.
* In the vCenter, enough disk space for the HCX appliances to be installed.
* Sufficient IP addresses for the on-premises VMs provisioned during the installation.
* Ports and firewalls opened as required as documented in Port Access Requirements.
* If the single sign-on (SSO) server is remote, the URL of the vCenter, external SSO Server, or Platform Services Controller (PSC) that runs the external lookup service must be identified. When the HCX Manager is registered with the vCenter, this URL must be supplied.
* If a vCenter does not have its own internal instance of the lookup service, it might be for one of the following reasons:
  * vCenter 6.0u2 is running an external Platform Services Controller.
  * The vCenter is in linked mode (where the secondary vCenter uses the SSO service from the primary vCenter or an external SSO service).

## Verifying Layer 2 installation environment
{: #hcxclient-planning-verify-layer-2-inst}

Layer 2 network stretching has the following requirements:
* A vSphere Enterprise Plus edition.
* The vSphere vCenter must meet the following requirements to support Layer 2 extension:
  * vSphere Enterprise Plus license
  * Must have a vSphere Distributed Switch (vDS). The distributed switch is available with vSphere Enterprise Plus Edition.
  * When installed, the on-premises Layer 2 concentrator service appliance must have access to a vNIC port and any VLANs to be stretched.
  * If the network is to be stretched over the public internet or a VPN (on an alternative path) the L2C virtual machine in VCS requires an IP address. The remote IP address is required to configure the Layer 2 concentrator.
  * If multiple Layer 2 concentrators are wanted, each must have an IP address on-premises and in the cloud.

## Pre-deployment planning
{: #hcxclient-planning-predepl}

Much of the time that is spent in deploying HCX is in the pre-deployment stage. While it is typical for information systems migration projects to take months and even years to complete, HCX allows for migration to take a short time and for the network connectivity to the cloud to start immediately after deployment.

Since the deployment of HCX for an enterprise-level customer typically involves security, network, storage, and vSphere infrastructure teams, it makes sense to involve these teams in the POC if possible. Effective project management and early inclusion of stake holders, is critical to ensure the speed of deployment and operation of HCX is realized.

## Avoiding analysis paralysis
{: #hcxclient-planning-avoiding}

Many of the hurdles and time that is taken in migration of a virtual machine (VM) or group of VMs are there because of the need to modify parts of the application environment, the design of those changes and the scheduling of the downtime that is needed to make those changes. After these changes are made, the migration becomes difficult to revert, further adding to analysis paralysis. Trying to capture all aspects of the migration, coordinating across teams, and changing key stake holders can delay the project.

HCX allows for cross vSphere instance migration of a VM or group of VMs that represent a partial or complete composite application, without any modifications to the application. Because of this, backing out of a migration means moving the VMs back or restretching the networks. This negates the need for a large part of migration planning and allows for some parallelism in the planning process. After selecting the applications to move and creating a high-level network design, the applications can begin migration with minimal configuration on the cloud instance while the final network connectivity and design is worked out.

## Stretched networks
{: #hcxclient-planning-stretched-net}

The network stretch components of the HCX fleet are very stable. At one particular customer with greater than 20 VLANs that are stretched into the {{site.data.keyword.cloud}} across 1 Gbps WAN shared with other traffic and HCX migration tunnels, there are no application issues attributed to the network. The network links are up for greater than 6 months in this way.

More stretched networks were added and removed without issue. Picking an {{site.data.keyword.CloudDataCent_notm}} that is close (<6 ms latency for this particular customer) also plays into network stability of stretched networking. Leaving the stretched networks up long term, should not be a negative factor in your design given you have enough bandwidth and low enough latency for your applications.

## Migration lifecycle
{: #hcxclient-planning-mig-lifecycle}

The following sections describe the phases within a typical HCX migration lifecycle, denoting where work streams can be done in parallel.

## vSphere inventory
{: #hcxclient-planning-vsphere-planning}

- Coarse-grained assessment of VMs within an application to be migrated. Coarse grained implies understanding the VMs that participate in an application, without delving into the details.
- If you plan to migrate many VMs and network bandwidth is limited between the source and cloud sites, further group VMs by VLAN or VXLAN if NSX is employed at the source. This allows for a cascading HCX migration plan where groups of VMs by VLAN are migrated and the L2 networks they reside upon are stretched only until the point the VLANs are released.

This means that the initial group of related L2 stretched networks can only be unstretched when the cloud side network design is finalized and deployed. Unstretching implies swinging the particular VXLAN traffic to now route through the cloud instance NSX infrastructure.

## Baseline network configuration
{: #hcxclient-planning-baseline-net-config}

Create a secured perimeter network within the cloud side vSphere instance. This usually consists of an NSX DLR or Edge appliance. If you use HCX Proximity Routing, there is no need to create any firewall rules or uplink topology as it can be completed later or concurrently without effecting the stretched L2 traffic.

## Network extension
{: #hcxclient-planning-net-extension}

Extending the network merely means to take the existing VLAN or VXLAN from the source vSphere environment, represented by a virtual distributed switch port group (vDS), and extending it to an NSX VXLAN on the cloud side of HCX.

## Pre-flight tests
{: #hcxclient-planning-preflight-tests}

Pre-flight tests involve performing an HCX migration with both the vMotion and bulk migration function to establish a baseline transfer rate.

## Migration of non-production apps
{: #hcxclient-planning-mig-non-prod-apps}

Migration of VMs begins with the planned stages of less critical VMs. Development and Test teams use internet connectivity for migration and stretched L2 traffic.

## Cloud network design and implementation begins
{: #hcxclient-planning-cloud-net-begins}

While migrations continue, cloud side network designs are finalized and implemented within the cloud side vSphere instance.

## More network connectivity considerations
{: #hcxclient-planning-connect-considerations}

While migrations continue, private WAN network connectivity is ordered as it typically takes a few weeks to months to be established with the cloud provider. After private network connectivity is completed, HCX can be configured to use both, the dedicated private network link and the internet for migration and stretched L2 traffic.

## Physical servers
{: #hcxclient-planning-physical-servers}

When the goal is data center migration into the cloud, any physical servers that interact with the VMs being migrated can be assessed for
migration into the {{site.data.keyword.cloud_notm}} as either a VM (P2V), bare metal or remain at the source. If the physical server is to remain at the source, and HCX will be used only during migration, until a dedicated network is established, it is important to understand if it resides on any network that is stretched into the cloud with HCX. In this scenario, HCX is allowing not only the VMs, but the entire subnet to be migrated into the cloud.

To remove HCX at the end of the migration, the subnet cannot exist in the source and destination if connection between physical devices and the migrated VMs is to be maintained. This implies that any physical devices left behind at the source site that exist on stretched L2 networks, must be migrated to another network subnet that can be routed to the cloud side. The exception to this is if some other stretched L2 technology is employed, such as NSX L2 VPN, to replace HCX stretched L2 endpoints.

## Migrate production and complex applications
{: #hcxclient-planning-mig-prod-complex-app}

VMs with shared multi-writer VMDKs such as Oracle RAC or MS Exchange / SQL clusters or VMs with raw device mappings are examples of VMs that need extra consideration before migration.

## Network Swing
{: #hcxclient-planning-net-swing}

Network Swing occurs after the evacuation of the VMs on source side networks is complete and the network design / implementation is completed on the cloud side. Configuring HCX to unstretch the networks related to the completed VMs within migration waves, allows the migrated VMs to route network traffic by using the cloud side NSX infrastructure.

## Client platforms supported
{: #hcxclient-planning-client-platforms}

For network extension, only port groups with a vSphere virtual distributed switch (vDS) are supported. This also implies that stand-alone ESXi hosts are not supported as you can have only a vDS when ESXi hosts are managed by vCenter.
- vSphere 5.1 (command line only for vCenter 5.1 through API)
- vSphere 5.5 (web client UI supported on vCenter 5.5u3 and above)
- vSphere 6.0
- vSphere 6.5 (vDS must be at a 6.0 level)

## Cloud platforms supported
{: #hcxclient-planning-cloud-platforms}

HCX Cloud side is provisioned by {{site.data.keyword.cloud_notm}} automation.

## Connectivity options
{: #hcxclient-planning-connect-options}

### Standard HCX connectivity
{: #hcxclient-planning-standard-connect}

As deployed by the {{site.data.keyword.vmwaresolutions_short}} automation, HCX cloud side installation is configured to connect to across the public internet by default.

**Next topic:** [HCX Client deployment](/docs/services/vmwaresolutions?topic=vmware-solutions-hcxclient-vcs-client-deployment)

## Related links
{: #hcxclient-planning-related}

* [Glossary of HCX components and terms](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcxclient-components)
* [HCX on-premises Service Mesh](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcxclient-vcs-mesh-deployment)
* [VMware Hybrid Cloud migrations](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcxclient-migrations)
* [Monitoring parameters and components](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcxclient-monitoring)
* [HCX troubleshooting](/docs/services/vmwaresolutions/services?topic=vmware-solutions-hcxclient-troubleshooting)
