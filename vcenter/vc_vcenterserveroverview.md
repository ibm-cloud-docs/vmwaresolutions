---

copyright:

  years:  2016, 2025

lastupdated: "2025-06-06"

keywords: vcf automated, vcf classic architecture, tech specs vmware cloud foundation

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Overview of {{site.data.keyword.vcf-auto-short}}
{: #vc_vcenterserveroverview}

{{site.data.keyword.vcf-auto}} is a hosted private cloud that delivers the {{site.data.keyword.vcf-flex}} stack as a service. The VMware® environment is built in addition to a minimum of three {{site.data.keyword.cloud}} bare metal servers and it offers shared network-attached storage and dedicated software-defined storage options. It also includes the automatic deployment and configuration of an easy-to-manage logical edge firewall, which VMware NSX® powers.
{: shortdesc}

In many cases, the entire environment can be provisioned in less than a day and the bare metal infrastructure can rapidly and elastically scale the compute capacity up and down as needed.

After initial instance deployment, you can increase shared storage by ordering more Network File System (NFS) file shares from the {{site.data.keyword.slportal}}. You can attach them manually to all VMware ESXi™ servers in a cluster. You can also take advantage of VMware vSAN™ as a storage option. To increase the vSAN-based storage capacity of a vSAN cluster, you can add more ESXi servers post-deployment.

## Architecture of {{site.data.keyword.vcf-auto-short}}
{: #vc_vcenterserveroverview-nsx-t-archi}

The following graphic depicts the high-level architecture and components of a three node {{site.data.keyword.vcf-auto-short}} deployment.

![{{site.data.keyword.vcf-auto-short}} architecture](../images/vc_nsx-t_architecture.svg "{{site.data.keyword.vcf-auto-short}} architecture"){: caption="{{site.data.keyword.vcf-auto-short}} high-level architecture for a three-node cluster" caption-side="bottom"}

## Physical infrastructure
{: #vc_vcenterserveroverview-physical-infras}

This layer provides the physical infrastructure (compute, storage, and network resources) to be used by the virtual infrastructure.

## Virtualization infrastructure (Compute and Network)
{: #vc_vcenterserveroverview-virtualization-infras}

This layer virtualizes the physical infrastructure through different VMware products:
* VMware vSphere virtualizes the physical compute resources.
* VMware NSX is the network virtualization platform that provides logical networking components and virtual networks.

## Virtualization management
{: #vc_vcenterserveroverview-virtualization-mgmt}

This layer consists of the following components:
* vCenter Server Appliance with embedded Platform Services Controller (PSC)
* Three NSX Manager or Controller nodes in total
* Two VMware NSX Edge™ clusters
* IBM CloudDriver virtual server instance (VSI). The CloudDriver VSI is deployed on demand as needed for certain operations such as adding hosts to the environment.

The base offering is deployed with a vCenter Server appliance that is sized to support an environment with up to 400 hosts and up to 4,000 VMs. The same vSphere API-compatible tools and scripts can be used to manage the IBM-hosted VMware environment.

In total, the base offering requires 42 vCPU and 128 GB vRAM, which are reserved for the virtualization management layer. The remaining host capacity for your virtual machines (VMs) depends on several factors, such as oversubscription rate, VM sizing, and workload performance requirements.

For more information about the architecture, see [Overview of VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-solution_overview).

## Technical specifications for {{site.data.keyword.vcf-auto-short}}
{: #vc_vcenterserveroverview-specs}

The availability and pricing of standardized hardware configurations might vary based on the {{site.data.keyword.cloud_notm}} data center that is selected for deployment.
{: note}

The following components are included in your {{site.data.keyword.vcf-auto-short}} instance.

### Bare metal server
{: #vc_vcenterserveroverview-bare-metal}

You can order three or more bare metal servers on the consolidated or management cluster, and optionally two or more bare metal servers on the workload cluster.

If you plan to use vSAN storage, the configuration requires a minimum of four bare metal servers.
{: note}

The following configurations are available:
* **Sapphire Rapids** - Intel® Sapphire Rapids generation servers (Dual Intel Xeon® 6400/8400 series) with your selected RAM size.
* **Cascade Lake** - Intel Cascade Lake generation servers (Dual Intel Xeon 4200/5200/6200/8200 series or Quad Intel Xeon 6200/8200 series) with your selected RAM size.
* **SAP-certified Cascade Lake** - Intel Cascade Lake generation servers (Dual Intel Xeon 5200/6200/8200 series or Quad Intel Xeon 8200 series) with a preset RAM size.

### Networking
{: #vc_vcenterserveroverview-networking}

The following networking components are ordered:
* 10 Gbps dual public and private network uplinks
* Three VLANs (Virtual LANs) - one public and two private
* One overlay network with a T1 and T0 router for potential east-west communication between local workloads that are connected to layer 2 (L2) networks. This network is deployed as a sample routing topology, which you can modify, build on, or remove.
* Two VMware NSX Edge clusters:
   * One secure management service VMware NSX Edge cluster for outbound traffic for add-on services, which is deployed by IBM as part of the management networking typology. This edge cluster is used by add-on services such as Zerto, FortiGate® Virtual Appliance, and F5 BIG-IP® to communicate with external licensing and billing components.

      These edge nodes are named **service-edgeNN**. Do not modify or customize them. Otherwise, some of your add-on services might stop working."
      {: important}

   * Secure customer-managed edge cluster for your application traffic. The edge cluster is deployed by IBM as a template that can be modified by you to provide VPN access or public access. For more information, see [Configuring your network to use the customer-managed NSX edge cluster with your VMs](/docs/vmwaresolutions?topic=vmwaresolutions-vc_esg_config).

   For more information, see [Does the customer-managed NSX Edge pose a security risk?](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions#faq-customer-nsx)

### Virtual Server Instances
{: #vc_vcenterserveroverview-vsi}

The following virtual server instances (VSIs) are ordered:
* A VSI for IBM CloudDriver, which is deployed as needed for initial deployment and for Day 2 operations.
* Choose to deploy a single Microsoft® Windows® Server VSI for Microsoft Active Directory™ (AD) or two high availability (HA) Microsoft Windows VMs on the management cluster to help enhance security and robustness.

### Storage
{: #vc_vcenterserveroverview-storage}

During initial deployment, you can choose between NFS and vSAN storage options.

After deployment, you can add NFS storage shares to an existing NFS or vSAN cluster. For more information, see [Adding NFS storage to Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingnfs).
{: note}

#### NFS storage
{: #vc_vcenterserveroverview-nfs-storage}

The NFS option offers customized shared file-level storage for workloads with various options for size and performance:
* Size - 20 GB to 24 TB
* Performance - 0.25, 2, 4, or 10 IOPS/GB. The 10 IOPS/GB performance level is limited to a maximum capacity of 4 TB per file share.
* Individual configuration of file shares

#### vSAN storage
{: #vc_vcenterserveroverview-vsan-storage}

The vSAN option offers customized configurations, with various options for disk type, size, and quantity:
* Disk quantity - various options depending on the CPU model and storage architecture.
* Storage disk - 960 GB SSD, 1.9 TB SSD, 3.8 TB SSD, or 7.68 TB SSD. In addition, two cache disks of 960 GB are also ordered per host.

   3.8 TB SSD (solid-state disk) drives are supported when they are made available in a data center.
   {: note}

## Technical specifications for expansion nodes for {{site.data.keyword.vcf-auto-short}}
{: #vc_vcenterserveroverview-expansion-node-specs}

Each expansion node deploys and incurs charges for the following components in your {{site.data.keyword.cloud_notm}} account.

### Hardware for expansion nodes
{: #vc_vcenterserveroverview-expansion-node-hardware}

One bare metal server with the configuration presented in [Technical specifications for Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview#vc_vcenterserveroverview-specs).

## Technical specifications for multizone instances
{: #vc_vcenterserveroverview-mcv-specs}

This information is provided as reference for existing multizone instances. New deployments of multizone instances are not supported.
{: deprecated}

The {{site.data.keyword.vcf-auto-short}} multizone architecture is an end-to-end reference architecture that provides automated failover for customer workloads. It uses an {{site.data.keyword.cloud_notm}} [multizone region](#x9774820){: term} with an IBM-managed service that covers the following components:
* Compute architecture (VMware vSphere®)
* Network architecture (NSX-T™)
* Storage architecture (VMware vSAN or NFS)
* Integration with IBM Services Platform with Watson to enable the consumption of services
* Tools for monitoring, troubleshooting, performance, and capacity management.
   * VMware Aria Suite pattern (VMware Aria Operations, VMware Aria Operations™ for Logs, and VMware Aria Operations™ for Networks)
   * Active Directory pattern
   * Integration with IBM Netcool and IBM Bluecare for auto-ticketing, alerting, and event enrichment
   * Resiliency patterns (backup and recovery)

Multizone instances are available in the following regions:
* America - Washington DC, Dallas, Sao Paulo, and Toronto
* Europe - London and Frankfurt
* Asia Pacific - Sydney, Tokyo, and Osaka

### Base infrastructure architecture specifications
{: #vc_vcenterserveroverview-mcv-base-specs}

The base infrastructure has the following specifications:
* Each site has its own dedicated gateway and management cluster.
* The resource cluster is a vSphere + vSAN stretched cluster.
* The witness site contains two VMware ESXi™ hosts that provide quorum for both vSAN and vCenter.
* Single vCenter Server and NSX Manager architecture.
* vCenter Server Appliance with embedded Platform Services Controller (PSC) that uses vCenter Server HA over an L3 network architecture.
* NSX Manager recovery is using a Hot Standby method that syncs up backup files.

### Tools and technology architecture specifications
{: #vc_vcenterserveroverview-mcv-tooling-specs}

The tools and technology architecture has the following specifications:
* VMware Aria Operations, VMware Aria Operations for Logs, and VMware Aria Operations for Networks to provide operations and management capabilities specific to the VMware products that are used, for example NSX, vSAN, and vSphere.
* IBM Software Defined Environment (SDE) automation tool health check for validating deployments against best practices and security policies.
* Optional Disaster Recovery (DR) to an out of Region {{site.data.keyword.cloud_notm}} site.
* FortiGate Security Appliance or similar to secure any internet access and to facilitate active-active network integration with the on-premises network.

### vSphere + vSAN stretched cluster architecture specifications
{: #vc_vcenterserveroverview-mcv-stretched-cluster-specs}

The vSphere + vSAN stretched cluster architecture has the following specifications:
* Provides storage and compute capabilities, which span two sites for enhanced availability.
* Write requests from VMs are synchronously written to both sites, which incur site-to-site network latency.
* Read requests from VMs are fulfilled locally to the physical location of where the VM is located, thus avoiding extra latency.
* The witness site and witness host act as the split brain or quorum.
* vSAN native encryption (for at rest encryption) can be used in combination with this architecture.

### Network architecture specifications
{: #vc_vcenterserveroverview-mcv-network-specs}

The network architecture has the following specifications:
* Edge/DLR/VXLANs in combination with BGP metric-based routing to facilitate an active-active site design with automated failover.
* Each site has the concept of their own set of Edges, DLRs, and VXLANs.
* Under normal circumstances, any VMs connected to DLR-A, for example VM-A, are in {{site.data.keyword.cloud_notm}} availability zone #1 and traffic is both ingress and egress locally.
* During a vMotion activity for VM-A, traffic still ingresses and egresses through the {{site.data.keyword.cloud_notm}} availability zone #1.
* During a site or edge failure, traffic routes out of the remaining available site.

## Related links
{: #vc_vcenterserveroverview-related}

* [{{site.data.keyword.vcf-auto-short}} BOM](/docs/vmwaresolutions?topic=vmwaresolutions-vc_bom)
* [Planning for Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_planning)
* [Ordering Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-req)
* [Attached storage for Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-storage-benefits#storage-benefits)
* [Expanding File Share capacity](/docs/FileStorage?topic=FileStorage-expandCapacity#expandCapacity)
