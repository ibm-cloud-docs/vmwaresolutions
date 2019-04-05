---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-05"

subcollection: vmware-solutions


---

# Network stretching and virtual machine migration
{: #vcshcx-stretching}

## Network stretching
{: #vcshcx-network-stretching}

### Concepts and best practices for network stretching
{: #vcshcx-stretching-best-practices-network}

The glue that bridges the client-side network to the cloud side VXLAN is a sophisticated multi-tunnel VPN that consists of proprietary HCX technology. It is not based on NSX, but does work with NSX and extend its capability. This process is controlled by the client-side vCenter web user interface (UI) and automates the deployment and bring up of both endpoints on the client and cloud side. Selecting the network to stretched is done individually or in batch.

Additionally, as part of the network stretching workflow, NSX on the cloud side is authorized to build a VXLAN that is then connected to an interface created on the specified cloud side L3 device (DLR or ESG left in an unconnected state) and the cloud side L2C appliance.

Typically, when you migrate a particular application, all the networks in use by the applicable virtual machines (VMs) must get stretched across the {{site.data.keyword.cloud}} instance.

Why typically and not always? It can be advantageous to disconnect certain traffic from the client side after the VM is migrated. For example, VM guest backup clients, which might cause high-bandwidth use when moved to the cloud. The in-guest backup client is not required when the VM is migrated as it is automatically picked up by a more modern block level backup on the cloud side.

The client’s backup network adapter is not being accessed, because this would mean accessing each VM to shut off the in-guest client backup schedule. Therefore, if a backup network is used, the backup might fail. This is a temporary situation until all the VMs can be reached post migration to disable the in-guest backup client.

Bandwidth of a single L2C is theoretically 4 Gbps, however this can be the limit for all stretched networks within a single L2C pair and is not achievable by a single stretched network. A single stretched network can achieve ~1 Gbps given there is enough underlay bandwidth allotted and latency is low (<~10 ms).

### Process to stretch a network
{: #vcshcx-stretching-process-stretch}

To stretch a network (VLAN or VXLAN) with HCX, complete the following steps from the client-side vCenter web UI.

1. For individual selection of port groups, navigate to the **Networks** tab within the vCenter web UI, right-click the network to be stretched, and select **Hybridity Actions-> Extend Networks to the Cloud**.
2. Select the cloud side L3 device to connect to and the L2C appliance that will be used. Type the current default gateway and subnet mask in CIDR format.
3. Click **Stretch** at the bottom of the screen to begin the network stretch workflow.

Network progress is monitored in the vCenter client tasks pane.

### Proximity Routing option
{: #vcshcx-stretching-prox-routing}

Without any type of route optimization, extended networks route back to the client side for any L3 access. This trombone-ing introduces an inefficient traffic pattern as packets need to travel back and forth between client (source) and cloud even for cases where both source and destination VMs are within the cloud. The Proximity Routing feature of HCX was designed to address this and local egress of traffic.

## vMotion
{: #vcshcx-stretching-vmotion}

The vMotion capability within HCX extends the vSphere vMotion capability to work across differing versions of vSphere, separate SSO domains, and various types of network connectivity across the internet. HCX assumes the network it uses to connect across is not secure and always moves traffic through encrypted tunnels regardless of the type of connectivity.

### Concepts and best practices for vMotion
{: #vcshcx-stretching-best-practices-vmotion}

HCX is essentially a vMotion two-way proxy. Each instance of HCX emulates a single ESXi host within the vSphere data center, outside any clusters that is itself a “front” for the cloud gateway fleet component (CGW). A proxy host appears for each HCX site that is linked to the currently viewed site. When a vMotion is initiated to a remote host, the local ESXi host will vMotion that VM to the local proxy ESXi host that fronts the CGW that also is maintaining an encrypted tunnel with the CGW on the remote side.

At the same time, a vMotion migration is initiated from the remote ESXi proxy host to the destination vSphere physical ESXi host, while it receives data from the source CGW across the tunnel. When vMotion is employed, unlike bulk migration option, only a single VM migration operation runs at a time. Because of this, for large amounts of VMs to be migrated, it is recommended it only be used where downtime is not an option or there is risk in rebooting the VM. However, like standard vMotion, the VM can be live during the process.

It has been observed that a single vMotion will top out at around 1.7 Gbps on the LAN and 300 to 400 Mbps on the WAN through the WAN Optimizer. This does not mean that 1.7 Gbps on the LAN equals to 400 Mbps on the WAN through the WAN Optimizer, but rather that these maximums were observed on specific  environments. Such an environment consisted of 10 GB LAN vMotion Network and 1GB internet uplink, shared with production web traffic.

Use vMotion when:
- The VM is troublesome to shut down, start, or uptime can be long and would introduce risk by shutting it down.
- For any cluster type application that requires disk UUIDs, such as Oracle RAC clusters. Note that vMotion does not changed the disk UUIDs on the destination.
- You want to move a single VM as quickly as possible.
- Scheduled migration is not required.

### Operation
{: #vcshcx-stretching-operation}

Use the HCX web UI snap-in portal or the vSphere web client contextual extension menus to initiate a cross cloud vMotion. In either case, the same migration wizard comes up. For the contextual menus, only a single VM is selected for migration operations. For the portal, multiple VMs can be selected.

Reverse migrating VMs is only possible from the web UI portal that uses the **Reverse migration** check box in the HCX Migration wizard.

## Bulk migration
{: #vcshcx-stretching-bulk-mig}

### Concepts and best practices for bulk migration
{: #vcshcx-stretching-best-practices-bulk-mig}

The bulk migration capability of HCX uses vSphere replication to migrate disk data while re-creating the VM on the destination vSphere HCX instance. A migration of a VM incurs the following workflow:
- Creation of a new VM on the destination side and its corresponding virtual disks.
- Replication of VM data to the new VM. Replication starts as soon as the wizard is completed regardless of switch over scheduling.
- Power down of the original VM.
- During the power off period, final replication of any data changes occurs.
- Powering on the new VM on the destination side.
- Rename and move of the original VM to the cloud folder to which it was moved.

The following are advantages of bulk migration over vMotion:
- Migration of multiple VMs concurrently.
- More consistent bandwidth use. vMotion can generate fluctuations in bandwidth use that would be visible as peaks and valleys within network monitoring tools or the WAN Opt UI.
- Use bulk migration to obtain higher overall use of a network bandwidth capability than a single vMotion is capable of.
- Schedule bulk migration to switch to the newly migrated VMs during a scheduled outage window.
- Allow migration of VMs that are currently using virtual CPU features which differ from the cloud side. vMotion migration could fail in these cases.

The following are disadvantages of bulk migration over vMotion:
- Individual VMs migrate much more slowly than with vMotion.
- The VM incurs downtime briefly as the new clone VM is brought up on the destination side.
- VMs that depend on disk ordering and disk UUIDs (Oracle RAC) can have issues and have disks that show up differently as the UUIDs are changed, which might change the OS paths to the virtual disk devices.

## Migration type best practices
{: #vcshcx-stretching-mig-type-best-practices}

### Shared disk clusters
{: #vcshcx-stretching-shared-disk-clusters}

Oracle RAC, MS Exchange, and MS-SQL clusters are examples of applications where two or more VMs participate in a cluster that requires shared disk across all VMs or cluster nodes. The VMware multi-writer flag needs to be enabled on all of the VM nodes for disks that are part of the application cluster (non-OS virtual disks). VMs with the multi-writer flag enabled for any virtual disk are not supported.

Migrating a multi-writer virtual disk enabled cluster:
- Uses vMotion as the original VM disk and UUID mappings are maintained.
- The cluster remains up in a degraded state (single node) during migration.
- The cluster incurs downtime before the start of the migration and after the migration is complete to reassemble the multi-writer configuration across cluster VMs.

Complete the following steps to migrate a multi-writer disk enabled cluster:
1. Power off the cluster and all nodes per the application best practice.
2. Take note of the disk order, if the application requires it, in each node VM for the multi-writer configured virtual disks.
3. For Oracle and any other application that uses the virtual disk UUID feature, login to a particular ESXi host and run the `vmkfstools -J getuuid /vmfs/volumes/datastore/VM/vm.vmdk` command to get the UUID of each virtual disk file that requires the multi-writer flag set for
the cluster.
  This is necessary if best practice aligns disk orders with how the path displays in the operating system. vMotion can reorder the disks (disk1, disk2, disk3) but the UUIDs remain the same.
  When the migration completes, use the noted UUID to map the disk information, to re-create the disk naming order, and the SCSI ID, if necessary. The application should function either way. This is used where an Oracle instance has many virtual disks that are mapped for troubleshooting of the application.
4. Remove the virtual disks from all cluster VMs except the one deemed primary.
5. Remove the multi writer-flag from the primary cluster VM that should be the only one owning the cluster disks currently.
6. Power on the primary cluster, if required for minimal downtime.
7. Migrate all cluster nodes with vMotion. Migrate the primary cluster first. Migrate all other nodes after they are powered off.
8. When the primary disk owning node completes migration, power it off.
9. If required, remap the disk order with the proper disk UUID and scsi ID. Remapping is not required for the application to function.
10. Re-enable the multi-writer flag on the primary node.
11. Start the primary node and verify operation.
12. Map disk / enable multi-writer flag on all other cluster VMs and power them on.
13. Verify other cluster operation.

### General VMs
{: #vcshcx-stretching-general-vms}

After confidence is built around the function of HCX, bulk migration must be employed. Bulk migration is necessary where redundant applications are concerned. For example, web servers and where many 100s or 1000s VMs are to be migrated.

### VMs using direct attached NAS
{: #vcshcx-stretching-vms-direct-nas}

NFS is typically employed for use to share data across many servers, such as web server content. iSCSI can be employed across VM nodes that comprise of an application cluster such as email or RDBMS and is typically more latency sensitive than NFS.

In either case, if latency can be kept low to the {{site.data.keyword.CloudDataCent_notm}} (< ~7 ms for iSCSI and whatever the application tolerates for NFS) and allowing that the application can operate with bandwidth of ~1 Gbps or less, then the NAS network can be stretched with HCX into an {{site.data.keyword.cloud_notm}} location. After this is done the VMs can be migrated / vMotioned with HCX as normal.

Post migration, iSCSI volumes can be mirrored with the OS to another local cloud storage solution and NFS data can be replicated to any cloud solution. The considerations are:
- Latency (iSCSI or application tolerance for NFS)
- Bandwidth (~1 Gbps per stretched network)
- Underlay link bandwidth

After the the migration lifecycle, test Development or staging applications before attempting on production. QoS can be employed for the underlay tunnel traffic (udp 500 / 4500) between the L2C HCX appliances that support latency sensitive stretched L2 networks.

## Network swing
{: #vcshcx-stretching-network-swing}

If the goal is data center evacuation into the {{site.data.keyword.cloud_notm}}, then the next to last step before HCX removal is the network swing. Network swing achieves a migration of the network subnet that houses the migrated VMs from the source data center to an NSX overlay network within the {{site.data.keyword.cloud_notm}}.

Swinging the network involves the following steps:
- Verify that the network is evacuated of all workloads and any non-VM networked devices are either moved to another network, functionally migrated to cloud, or deprecated.
- Verify any NSX topology or {{site.data.keyword.cloud_notm}} supporting network topology is completed to support the network swing. For example, dynamic routing protocols and firewalls.
- Run an HCX unstretch network workflow in the UI and select the appropriate routing NSX device to take control of the default gateway of the unstretched network.
- Run any external routing changes, which can include: insert changed routing for networks that were migrated, remove routes to source site from the migrated network, and ensure that routing to the migrated subnet across the WAN still works for applications that were not migrated.
- Application owner testing of migrated applications from all possible access points: internet, intranet, and VPN.

Let's say you want to network swing a particular application that has all VMs completely migrated to cloud. For example:
- You are using a vyatta on the private network side to insert routes into your MPLS cloud and to tunnel to the edge routing devices on the MPLS so you can avoid the {{site.data.keyword.cloud_notm}} IP space.
- You have your account set with an {{site.data.keyword.cloud_notm}} VRF.
- Some applications are behind a network load balanced virtual IP (vIP). Those vIPs are on your owned subnet that resides on a virtual F5 behind the vyatta.

While adding more specific routing into the MPLS for networks that are swung over to {{site.data.keyword.cloud_notm}} through HCX works fine for other networks, it does not work for the individual vIPs because a /32 route is being added.

Solution: It is common for WAN providers to filter out /32 routes that are added. Work with the WAN vendor to allow.

The following are considerations and implications:
- Applications that share subnet, vLAN, and VXLAN need to move together.
- Applications behind a load balancer that uses an internal routable IP can require routing changes if they cannot be moved together or it is not desirable to do so. For example, if there is too much perceived risk by involving too many applications in one swing.
- VMware admins, network admins (including customers and WAN vendors), and application owners need to be involved, even if even if there's no planned impact on a particular system or network equipment.

## Related links
{: #vcshcx-stretching-related}

* [vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle overview](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)   
