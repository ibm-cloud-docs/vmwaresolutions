---

copyright:

  years:  2016, 2025

lastupdated: "2025-08-20"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# VMware NSX-T design
{: #nsx-t-design}

VMware® NSX-T™ is designed to address application frameworks and architectures that have heterogeneous endpoints and technology stacks. In addition to VMware vSphere®, these environments can include other hypervisors, KVM, containers, and bare metal servers. NSX-T is designed to span a software-defined network and security infrastructure across platforms other than just vSphere alone. While it is possible to deploy NSX-T components without needing vSphere, this design focuses on NSX-T and its integration primarily within a vCenter Server vSphere automated deployment.

NSX-T version 3 or later can run on the vSphere virtual distributed switch (VDS) version 7.0. All new deployments of VMware NSX and vSphere use NSX-T on VDS (N-VDS is not used). For NSX-T version 2.4 or later, the manager VM and the controller VM functions are combined. As a result, three controller or manager VMs are deployed. If on the same subnet, they use an internal network load balancer. If across different subnets, an external load balancer is required.

NSX-T brings many advanced features, such as firewall policies, inclusion of guest introspection within firewall policies, and advanced netflow tracking. Describing these features is beyond the scope of this document. In this design, the NSX-T Management Infrastructure is deployed during the initial vCenter Server® cluster deployment. For more information about NSX-T, see the [VMware NSX documentation](https://techdocs.broadcom.com/us/en/vmware-cis/nsx.html){: external}.

## Resource requirements
{: #nsx-t-design-resource-req}

In this design, the NSX-T controller Manager VMs are deployed on the management cluster. Additionally, each controller manager is assigned to a VLAN–backed IP address from the private portable address block. The address block is designated for management components and configured with the DNS and NTP servers that are discussed in section 0. A summary of the NSX Manager installation is shown in the following table.

| Attribute | Specification |
|:--------- |:------------- |
| **NSX managers or controllers** | Three Virtual Appliances |
| **Number of vCPUs** | 6 |
| **Memory** |  24 GB |
| **Disk** | 300 GB |
| **Disk type** | Thin provisioned |
| **NetworkPrivate A** | Private A |
{: caption="NSX-T Manager - controller specifications" caption-side="bottom"}

The following figure shows the placement of the NSX managers in relation to the other components in this architecture.

![NSX-T Manager network overview](../../images/nsx-t-3-ra-diagrams-overview-vcs-v7-t3.svg "NSX-T Manager network overview"){: caption="NSX-T Manager network overview" caption-side="bottom"}

## Deployment considerations
{: #nsx-t-design-deployment}

With NSX-T v3.x on vSphere VDS switch version 7.0, N-VDS is no longer required on the ESXi hosts. When configured as transport nodes, you can use the v7 VDS, which makes the consolidated cluster a more optimal design.

After initial deployment, the {{site.data.keyword.cloud}} automation deploys three NSX-T Manager virtual appliances within the management cluster. The controllers are assigned to a VLAN–backed IP address from the Private A portable subnet that is designated for management components. Additionally, VM–VM anti–affinity rules are created such that controllers are separated among the hosts in the cluster.

You must deploy the management cluster with a minimum of three nodes to ensure high availability for the managers or controllers. In addition to the managers, the {{site.data.keyword.cloud_notm}} automation prepares the deployed workload cluster as NSX-T transport nodes. The ESXi transport nodes are assigned to a VLAN–backed IP address from the **Private A** portable IP address range that is specified by an NSX IP pool ranged derived from the VLAN and subnet summary. Transport node traffic resides on the untagged VLAN and is assigned to the private NSX-T VDS.

Depending on the NSX-T topology that you choose, you can deploy an NSX-T gateway cluster either as a pair of VMs or as software deployed on bare metal cluster nodes. Bare metal edges are not supported by the {{site.data.keyword.cloud_notm}} automation and must be manually deployed and configured. Regardless of whether the cluster pair is virtual or physical, uplinks are configured to VDS switches for both {{site.data.keyword.cloud_notm}} private and (if present) public networks.

The following table summarizes the requirements for a medium size environment, which is the recommended starting size for production workloads.

| Resources | Manager x3 | Edge services \n cluster x4 |
|:--------- |:---------- |:--------------- |
| Medium size | Virtual appliance | Virtual appliance |
| Number of vCPUs | 6 | 4 |
| Memory | 24 GB | 8 GB |
| Disk | 300 GB vSAN or management NFS | 200 GB vSAN or management NFS |
| Disk type | Thin provisioned | Thin provisioned |
| Network | Private A | Private A |
{: caption="NSX-T component specification" caption-side="bottom"}

## Distributed switch design
{: #nsx-t-design-distr-switch}

The design uses a minimum number of VDS switches. The hosts in the management cluster are connected to the private and (optionally) public networks. The hosts are configured with two distributed virtual switches. The use of two switches follows the practice of {{site.data.keyword.cloud_notm}} network that separates the public and private networks. All new deployments of NSX and vSphere take advantage of running the vSphere VDS switch version 7.0., which allows for a converged NSX-T architecture.

![Distributed switch design Private ](../../images/nsx-t-3-ra-diagrams-v7-vds-private.svg "Distributed switch design Private"){: caption="NSX-T Distributed switch design Private" caption-side="bottom"}

![Distributed switch design Public](../../images/nsx-t-3-ra-diagrams-v7-vds-public.svg "Distributed switch design Public"){: caption="NSX-T Distributed switch design Public" caption-side="bottom"}

As shown in the previous diagrams, the public VDS `*instancename*-*clustername*-public` is configured for public network connectivity and the public VDS `*instancename*-*clustername*-private` is configured for private network connectivity. Separating different types of traffic is required to reduce contention and latency and increase security.

VLANs are used to segment physical network functions. This design uses three VLANs: two for private network traffic and one for public network traffic. The following table shows the traffic separation.

| VLAN  | Designation | Traffic type |
|:----- |:----------- |:------------ |
| VLAN 1 | Private A   | ESXi management, management, Geneve (TEP), edge uplinks |
| VLAN 2 | Private B   | vSAN, NFS, and vMotion|
| VLAN 3 | Public      | Available for internet access |
{: caption="VLAN mapping to traffic types" caption-side="bottom"}

For the optional two host gateway clusters, this design uses two VLANs: one for private network traffic and one for public network traffic. This cluster type uses local disks as data store. Therefore, you don't need separate storage traffic. Also, according to the design, the NSX-T Geneve (TEP) traffic is left out. The following table shows the traffic separation between VLANs for this cluster type.

| VLAN   | Designation       | Traffic type                                       |
|:-------|:------------------|:---------------------------------------------------|
| VLAN 1 | Private Transit   | Private transit VLAN, ESXi management, and vMotion |
| VLAN 2 | Public Transit    | Public transit VLAN                                |
{: caption="VLAN mapping to Gateway traffic types" caption-side="bottom"}

## Naming conventions
{: #nsx-t-design-naming}

The following naming conventions are used for deployment. For readability, only the specific naming is used. For example, `instancename-dcname-clustername-tz-edge-private` is referred to as `tz-edge-private`.

| Description | Naming Standard |
|:----------- |:--------------- |
| Management VMs | `instancename-nsxt-ctrlmgr0` \n `instancename-nsxt-ctrlmgr1` \n `instancename-nsxt-ctrlmgr2` |
| Uplink profiles | `instancename-esxi-private-profile` \n `instancename-esxi-public-profile` \n `instancename-edge-private-profile` \n `instancename-edge-public-profile` \n `instancename-edge-tep-profile` \n `instancename-mgmt-edge-private-profile` \n `instancename-mgmt-edge-public-profile` \n `instancename-mgmt-edge-tep-profile` |
| NIOC profiles | `instancename-clustername-nioc-private-profile` \n `instancename-clustername-nioc-public-profile` |
| Gateway cluster profiles | `instancename-dcname-clustername-service-edge-cluster-profile` \n `instancename-dcname-clustername-service-edge-cluster-profile` |
| Transport zones | `instancename-tz-esxi-private` \n `instancename-tz-esxi-public` \n `instancename-tz-vm-overlay` \n `instancename-tz-edge-private` \n `instancename-tz-edge-public` |
| Segments | `instancename-podname.dcname-customer-t0-172-16-16-0` \n `instancename-podname.dcname-customer-t1-192-168-0-0` \n `instancename-podname.dcname-customer-t1-192-168-1-0` \n `instancename-podname.dcname-customer-to-private` \n `instancename-podname.dcname-customer-to-public` \n `instancename-podname.dcname-service-to-private` \n `instancename-podname.dcname-service-to-public` \n `instancename-clustername-edge-teps` |
| IP address pools | `instancename-clustername-tep-pool` |
| Transport nodes profiles | `instancename-podname.dcname-clustername-esxi-tpn-profile` |
| Tier-0 and Tier-1 gateways | `instancename-podname.dcname-clustername-T0-function` (where `function` includes `services`, `workload`, `openshift`) \n `instancename-podname.dcname-clustername-T1-function` |
{: caption="NSX-T design naming convention" caption-side="bottom"}

## Transport nodes
{: #nsx-t-design-transport-nodes}

Transport nodes define the physical server objects or VMs that participate in the virtual network fabric. Review the following table to understand the design.

| Transport node type   | Uplink profile | IP assignment |
|:-------------------  |:-------------- |:------------- |
| ESXi | `esxi-private-profile` \n `esxi-public-profile` | `tep-pool` |
| Gateway cluster | `edge-private-profile` \n `edge-public-profile` \n `edge-tep-profile` \n `mgmt-edge-private-profile` \n `mgmt-edge-public-profile` \n `mgmt-edge-tep-profile` | `tep-pool` |
{: caption="NSX-T transport nodes" caption-side="bottom"}

## Uplink profiles and teaming
{: #nsx-t-design-uplink-profiles}

An uplink profile defines policies for the links from hypervisor hosts to NSX-T logical switches or from NSX Edge nodes to TOR (top-of-rack) switches.

| Uplink profile name | VLAN | Teaming policy | Active uplinks | Standby links | MTU |
|:------------------- |:---- |:-------------- |:-------------- |:------------- |:--- |
| `esxi-private-profile` | Default | Default - Loadbalance source | uplink-1 \n uplink-2 |   | Managed by vCenter Server |
| `esxi-private-profile` | Default | TEP - Failover order | uplink-1 | uplink-2 | Managed by vCenter Server |
| `esxi-public-profile`  | Default | Default - Loadbalance source | uplink-1 \n uplink-2 |   | Managed by vCenter Server |
| `edge-private-profile` | Default |   | uplink-1 |  | 9000 |
| `edge-public-profile`  | Default |   | uplink-1 |  | 1500 |
| `edge-tep-profile`     | Default | Failover order | uplink-1 |   | 9000 |
| `mgmt-edge-private-profile` | Default |   | uplink-1 |  | 9000 |
| `mgmt-edge-public-profile`  | Default |   | uplink-1 |  | 1500 |
| `mgmt-edge-tep-profile`     | Default | Failover order | uplink-1 |   | 9000 |
{: caption="NSX-T uplink profiles" caption-side="bottom"}

## VNI pools
{: #nsx-t-design-vni-pools}

Virtual Network Identifiers (VNIs) are similar to VLANs to a physical network. They are automatically created when a logical switch is created from a pool or range of IDs. This design uses the default VNI pool that is deployed with NSX-T.

## Segments
{: #nsx-t-design-logical-switches}

An NSX-T segment reproduces switching functions, broadcast, unknown unicast, multicast (BUM) traffic, in a virtual environment that is decoupled from the underlying hardware.

| Segment name | VLAN |Transport zone | Uplink teaming policy |
|:------------ |:---- |:------------- |:--------------------- |
| `edge-teps` | Default | `tz-esxi-private` | TEP - Failover order |
| `service-to-private` | Default | `tz-edge-private` |   |
| `service-to-public` | Default | `tz-edge-public` |   |
| `customer-to-private` | Default | `tz-edge-private` |   |
| `customer-to-public` | Default | `tz-edge-public` |   |
| `customer-t0-172-16-16-0` |   | `tz-vm-overlay` |   |
| `customer-t1-192-168-0-0` |   | `tz-vm-overlay` |   |
| `customer-t1-192-168-1-0` |   | `tz-vm-overlay` |   |
{: caption="NSX-T logical switches" caption-side="bottom"}

### Gateway cluster
{: #nsx-t-design-edge-cluster}

Within this design, two virtual edge node clusters are provisioned, one for management and the other for customer workloads. A limitation of one T0 per Edge Transport Node exists, which means that a single Edge Node Cluster can support one T0 Gateway (in either active-standby or active-active).

The following figures show the functional components of an NSX-T gateway cluster.

![Topology for the customer gateway cluster](../../images/nsx-t-3-ra-diagrams-customer-edge-cluster-t0-t1.svg "Topology for the customer gateway cluster"){: caption="Topology for the customer gateway cluster" caption-side="bottom"}

![Gateway cluster topology](../../images/nsx-t-3-ra-diagrams-management-edge-cluster-t0.svg "Gateway cluster topology"){: caption="Gateway cluster topology" caption-side="bottom"}

#### Tier 0 logical gateway
{: #nsx-t-design-tier-0}

An NSX-T Tier-0 logical gateway provides a gateway service between the logical and physical networks (for north-south traffic). In this design, two highly available T0 gateways are deployed in two separate NSX-T gateway clusters, one for customer and one for services or management needs. More services and products are optional for customer-chosen topologies and they use the services T0 for their inbound or outbound connectivity needs. Each T0 logical gateway is configured with two uplinks for private and two for public. Additionally, VIPs are assigned to both public and private uplinks.

#### Tier 1 logical gateway
{: #nsx-t-design-tier-1}

An NSX-T Tier-1 logical gateway has downlink ports to connect to NSX-T Data Center logical switches and uplink ports to connect to NSX-T Data Center Tier-0 logical gateways. They run in the kernel level of the hypervisor that they are configured for, and they are virtual router instances (vrf) of the NSX-T gateway cluster. In this design, one or more T1 logical gateways can be created for the needs of customer-chosen topologies.

#### Tier 1 to Tier 0 route advertisement
{: #nsx-t-design-tier-1-tier-0}

To provide Layer 3 connectivity between VMs connected to logical switches that are attached to different tier-1 logical gateways, it is necessary to enable tier-1 route advertisement toward tier-0. No need to configure a routing protocol or static routes between tier-1 and tier-0 logical routers. NSX-T creates static routes automatically when you enable route advertisement. For this design, route advertisement is always enabled for any {{site.data.keyword.vmwaresolutions_full}} automation created T1 gateways.

### Preconfigured topologies
{: #nsx-t-design-preconfig-topo}

Workload to T1 to T0 gateway – virtual gateway cluster

![NSX-T deployed topology virtual T0 Edge Gateway](../../images/nsx-t-3-ra-diagrams-preconfigured-topology.svg "NSX-T deployed topology virtual T0 Edge Gateway"){: caption="NSX-T deployed topology virtual T0 Edge Gateway" caption-side="bottom"}

With NSX-T, no dynamic routing protocol configuration between T1 and T0. RFC-1891 IP address space is used for the workload overlay network and transit overlay network. A customer private and public portable IP space is assigned for customer use. A customer designated {{site.data.keyword.cloud_notm}} private and public portable IP space is assigned to the T0 for customer use.
