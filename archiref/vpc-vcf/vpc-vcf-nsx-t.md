---

copyright:

  years:  2022

lastupdated: "2022-08-09"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# VMware Cloud Foundation NSX-T design on {{site.data.keyword.vpc_short}}
{: #vpc-vcf-nsx-t}

The topic provides an introduction to VMware® NSX-T™ deployment architecture that uses {{site.data.keyword.cloud}} bare metal server for {{site.data.keyword.vpc_short}}. An overview of this architecture is shown in the following diagram. 

![Architecture overview of VMware with NSX-T on {{site.data.keyword.vpc_short}}](../../images/vpc-ryo-diagrams-aod-nsx-t-based.svg "Architecture overview of VMware with NSX-T."){: caption="Figure 1. Architecture overview of VMware with NSX-T on {{site.data.keyword.vpc_short}}" caption-side="bottom"}

Compared to the roll-your-own deployments, the NSX-T is deployed in a slightly different way in VMware Cloud Foundation™ (VCF) deployments. The topic provides an overview of how {{site.data.keyword.vpc_short}} resources are used in VCF deployments.

## VCF NSX-T deployment architecture
{: #vpc-vcf-nsx-t-dplarch-managers}

### VMware vSphere distributed switch deployment
{: #vpc-vcf-nsx-t-dplarch-vds}

In the VCF architecture for {{site.data.keyword.vpc_short}}, each {{site.data.keyword.cloud_notm}} bare metal server has two PCI interfaces and one vSphere Distributed Switch with two uplinks.

When you create {{site.data.keyword.cloud_notm}} bare metal server VLAN interfaces for NSX-T components that are attached to a VPC subnet, your Distributed Switch must contain a port group that matches the used VLAN IDs.
{: note}

Each physical host has redundant 1611 Gb network connection for network access to {{site.data.keyword.vpc_short}}. The 1611 Gb bandwidth is shared by the network interfaces that are on the bare metal server.
{: note}

The high availability for physical network connectivity is handled by {{site.data.keyword.cloud_notm}}, which manages the aggregation. The multiple PCI interfaces, as seen in VCF deployment, do not add redundancy, but are required in VCF deployments and they are up the uplink migrations from vSphere Standard Switch to vSphere Distributed Switch. 
{: note}

### NSX-T manager deployment
{: #vpc-vcf-nsx-t-dplarch-managers-depl}

NSX Manager Node hosts the API services, the management plane, and the agent services. It provides a graphical user interface (GUI) and REST APIs for creating, configuring, and monitoring NSX-T Data Center components, such as logical switches, logical routers, and firewalls. It also provides a system view and it is the management component of NSX-T Data Center. For high availability, VCF deploys a management cluster of three NSX Manager virtual machines (VMs) and a virtual IP.

A VLAN interface is provisioned for each NSX-T manager in the management subnet (`vpc-mgmt-subnet`) of the VPC. This VPC subnet is designated for VMware management components of your solution. If you deploy the NSX-T managers on the same VPC subnet in a zone, and you plan to use the NSX-T internal network load balancer, you need an extra VLAN interface for this virtual IP (VIP). All created VLAN interfaces are allowed to float, which means that they can be vMotioned between the ESXi hosts. The following table summarizes the required VLAN interfaces in {{site.data.keyword.vpc_short}}.

Interface name        | Interface type | VLAN ID | Subnet              | Allow float  | NSX-T interface   | Distributed port group name
----------------------|----------------|---------|---------------------|--------------|-------------------|------------------------------
vlan-nic-nsx-0        | vlan           | 1611    | vpc-mgmt-subnet     | true         | NSX-T Manager 1   | pg-mgmt
vlan-nic-nsx-1        | vlan           | 1611    | vpc-mgmt-subnet     | true         | NSX-T Manager 2   | pg-mgmt
vlan-nic-nsx-2        | vlan           | 1611    | vpc-mgmt-subnet     | true         | NSX-T Manager 3   | pg-mgmt
vlan-nic-nsx-vip      | vlan           | 1611    | vpc-mgmt-subnet     | true         | NSX-T Manager VIP | pg-mgmt
{: caption="Table 1. VLAN interfaces for NSX-T Managers" caption-side="bottom"}

When the initial NSX Manager is deployed into the host and cluster, you must register the vCenter as the compute manager to facilitate the deployment of other NSX Managers. You can use the Public Gateway that is attached to the management subnet to download updates for the NSX Managers through SDDC manager.

### Host transport nodes
{: #vpc-vcf-nsx-t-dplarch-hosts}

For NSX-T, each ESXi host must be set as a Transport Node so that it becomes capable of participating in an NSX-T Data Center overlay or NSX-T Data Center VLAN networking. Cloud builder and SDDC manager handle the deployment in VCF. However, you need VLAN interfaces prepared for the TEP vmks in the hosts.

The following table lists the required VLAN interfaces for NSX-T VMKs for each host. These interfaces are always local to the host and do not need to move, but are allowed to float to facilitate the use in NSX-T pools. They are provisioned on the `vpc-tep-subnet`. 

Interface name         | Interface type | VLAN ID | Subnet              | Allow float  | VMkernel adapter | Distributed port group name
----------------------|----------------|---------|---------------------|--------------|------------------|------------------------------
vlan-nic-tep-pool-<1>  | vlan           | 1614    | vpc-tep-subnet      | false        | vmk10            | none - set in NSX-T profile
vlan-nic-tep-pool-<2>  | vlan           | 1614    | vpc-tep-subnet      | false        | vmk11            | none - set in NSX-T profile
{: caption="Table 2. Host management networks and VMkernel adapters" caption-side="bottom"}

Host TEP VLAN ID is defined in the host transport profile.
{: note}

### Edge transport nodes and edge services cluster
{: #vpc-vcf-nsx-t--dplarch-edges}

In addition to NSX Managers, NSX-T edge services cluster and NSX Edge Nodes are required in an NSX-T deployment. The Edge Nodes are specific service appliances that are dedicated to running centralized network services. They cannot be distributed to the ESXi hypervisors, such as Network Address Translation or north-south traffic between NSX-T Geneve Segments and VPC subnets. NSX Edge Nodes are transport nodes that run local control plane daemons and forwarding engines that implement the NSX-T data plane.

VM form factor Edge Nodes are used in this architecture. Edge Nodes can be grouped in one or several clusters, representing a pool of capacity. NSX-T Logical Routers, Tier-0 (also referred as T0) and Tier-1 (also referred as T1) can be hosted in the same or different edge services clusters. Also, in this architecture, a single edge services cluster is created for all T0 and T1 Logical Routers. A T0 Logical Router provides north-south connectivity and connects to a VPC subnet. A T1 logical router connects to one T0 logical router, and it provides northbound connectivity to the NSX-T segments attached to it.

The following table summarizes the requirements for a Medium Form Factor Edge environment, which is the starting size for production workloads.

| Attribute            | Medium edge node |
|----------------------|------------------|
| NSX Edges            | 2 VMs            |
| Number of vCPUs      | 4                |
| Memory               | 8 GB             |
| Disk                 | 200 GB           |
| Network - Management | vpc-mgmt-subnet  |
{: caption="Table 3. NSX-T Edge Node specifications" caption-side="bottom"}

As for the other NSX-T components, VLAN interfaces must be created in {{site.data.keyword.vpc_short}} for connectivity. The following table lists the required VLAN interfaces for Edge Nodes.

Interface name           | Interface type | VLAN ID | Subnet              | Allow float  | NSX-T interface    | DPG/Segment name
-------------------------|----------------|---------|---------------------|--------------|--------------------|------------------------------
vlan-nic-nsx-edge-1      | vlan           | 1611    | vpc-mgmt-subnet     | true         | NSX-T Edge 1 Mgmt  | pg-mgmt
vlan-nic-nsx-edge-2      | vlan           | 1611    | vpc-mgmt-subnet     | true         | NSX-T Edge 2 Mgmt  | pg-mgmt
vlan-nic-edge-tep-pool-1 | vlan           | 1614    | vpc-tep-subnet      | true         | NSX-T Edge 1 TEP 1 | none - set in NSX-T profile
vlan-nic-edge-tep-pool-2 | vlan           | 1614    | vpc-tep-subnet      | true         | NSX-T Edge 1 TEP 2 | none - set in NSX-T profile
vlan-nic-edge-tep-pool-3 | vlan           | 1614    | vpc-tep-subnet      | true         | NSX-T Edge 2 TEP 1 | none - set in NSX-T profile
vlan-nic-edge-tep-pool-4 | vlan           | 1614    | vpc-tep-subnet      | true         | NSX-T Edge 2 TEP 2 | none - set in NSX-T profile
{: caption="Table 4. Host management networks and VMkernel adapters" caption-side="bottom"}

Edge TEP VLAN ID is defined in the edge transport profile.
{: note}

This action provides the base for each NSX-T edge. NSX-T T0 Logical Router needs its own VLAN interfaces for its uplinks.
{: note}

## Related links
{: #vpc-vcf-nsx-t-links}

* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} bare metal servers](/docs/vpc?topic=vpc-planning-for-bare-metal-servers)
* [{{site.data.keyword.vpc_short}} RYO VMware reference architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-ryo-arch-overview)
* [{{site.data.keyword.dl_full_notm}} overview](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl)
* [{{site.data.keyword.tg_full_notm}} overview](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [{{site.data.keyword.vpc_short}} VPN overview](/docs/vpc?topic=vpc-vpn-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on bare metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)
