---

copyright:

  years:  2022

lastupdated: "2022-08-26"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# IBM Cloud for VMware Cloud Foundation architecture overview
{: #vpc-vcf-arch-overview}

The architecture for {{site.data.keyword.cloud}} for VMware Cloud Foundation is built upon {{site.data.keyword.vpc_short}} architecture and bare metal servers for {{site.data.keyword.vpc_short}}. The following information provides an overview of the VMware Cloud Foundation components and how the {{site.data.keyword.vpc_short}} assets are deployed for these components.

## VMware Cloud Foundation components
{: #vpc-vcf-arch-vcf-components}

The following items are the core components of VMware Cloud Foundation:

- VMware Cloud Builder
- SDDC Manager
- VMware vSphere® and VMware vCenter Server®
- VMware vSAN™
- VMware NSX-T™

The VMware Cloud Builder appliance is the first virtual appliance that is deployed on the {{site.data.keyword.cloud_notm}} bare metal servers for {{site.data.keyword.vpc_short}}. It automates the deployment of the entire VMware software-defined stack. VMware Cloud Foundation assumes that the underlying network infrastructure, required bare metal servers, and DNS are deployed before you start deploying it. VMware Cloud Builder deploys and configures the first cluster of the management domain and transfers the inventory and control to SDDC Manager. During the deployment process, the VMware Cloud Builder appliance validates network information that you provide in the deployment parameter workbook, such as DNS, network (VLANS, IP addresses, MTUs), and credentials.

SDDC Manager automates the entire system lifecycle, that is, from configuration and provisioning to upgrades and patching, including host firmware, and simplifies day-to-day management and operations.  

VMware vSphere running on bare metal servers for {{site.data.keyword.vpc_short}} uses virtualization to transform individual data centers into aggregated computing infrastructures that include CPU, storage, and networking resources. vCenter Server manages these infrastructures as a unified operating environment and provides you with the tools to administer the data centers that participate in that environment.

vSAN aggregates local or direct-attached data storage devices onbaremetal servers for {{site.data.keyword.vpc_short}} to create a single storage pool that is shared across all hosts in the vSAN cluster. By using vSAN, you don't need external shared storage and it also simplifies storage configuration and virtual machine provisioning. However, you can add {{site.data.keyword.vpc_short}} file shares to your virtual infrastructure (VI) workload clusters. Built-in policies allow for flexibility in data availability.

NSX-T Data Center is focused on providing networking, security, automation, and operational simplicity for emerging application frameworks and architectures that have heterogeneous endpoint environments and technology stacks. NSX-T Data Center supports cloud-native applications, bare metal workloads, multi-hypervisor environments, public clouds, and multiple clouds. NSX-T integrates with {{site.data.keyword.vpc_short}} capabilities, and your workloads are able to use networking and interconnectivity services that are provided by {{site.data.keyword.cloud_notm}}.

## VMware Cloud Foundation on {{site.data.keyword.vpc_short}}
{: #vpc-vcf-arch-vcf-vpc-arch}

Through the integration with the VPC platform, you can take full advantage of the network, storage, and security capabilities provided by the {{site.data.keyword.vpc_short}} with VMware Cloud Foundation deployments. {{site.data.keyword.cloud}} for VMware Cloud Foundation™ is deployed on {{site.data.keyword.vpc_short}} and uses the bare metal servers for {{site.data.keyword.vpc_short}} for compute resources. These fast provisioning {{site.data.keyword.cloud_notm}} bare metal servers and {{site.data.keyword.vpc_short}} network form the core for the deployment. An overview of the architecture is shown in the following diagram. 

![Architecture overview of {site.data.keyword.cloud_notm}} for VCF](../../images/vcf-on-vpc-vcf-arch.svg "The solution uses Virtual Private Cloud compute, network, storage resources, and VMware NSX-T for hosting VMware workloads."){: caption="Figure 1. Architecture overview of IBM Cloud for VCF" caption-side="bottom"}

To deploy {{site.data.keyword.vpc_short}} assets, you can use {{site.data.keyword.cloud_notm}} portal UI, command line interface (CLI), or {{site.data.keyword.cloud_notm}} Terraform provider with Schematics. For the required common services, such as NTP and DNS, you can use {{site.data.keyword.cloud_notm}} with provided services and solutions. {{site.data.keyword.cloud_notm}} bare metal servers are provisioned on VPC subnets. Bare metal server network PCI and VLAN interfaces are used for VMware vSphere Distributed Switch uplinks, VMkernel adapters, and required VMware Cloud Foundation appliances, such as NSX-T Tier 0 Gateway uplinks.

For connectivity needs, as your NSX-T deployment is integrated with VPC, you can use {{site.data.keyword.vpc_short}} connectivity services and {{site.data.keyword.cloud_notm}} interconnectivity solutions with your deployment. Public internet network access capabilities to the workloads are provided through floating IP addresses or Public Gateway configurations within your VPC. On-premises connectivity over public internet can be arranged by using {{site.data.keyword.vpc_short}} VPN services (site-to-site and client-to-site), or alternatively NSX-T built-in capabilities. For private networking, you can use {{site.data.keyword.cloud_notm}} interconnectivity services to connect your VMware workloads with {{site.data.keyword.cloud_notm}} classic infrastructure, other VPCs, and on-premises networks.

With VCF, you use VMware vSAN™ for storage and VMware NSX-T™ with your VMware workloads. You can easily and quickly add and remove ESXi hosts on to your deployment, or add new workload domains. If you want to increase your storage, you can add and attach {{site.data.keyword.vpc_short}} file shares (NFS) to your workload clusters.

For post initial deployment integrations, for example with Active Directory™, you can use {{site.data.keyword.vpc_short}} compute resources to build your Active Directory in {{site.data.keyword.vpc_short}}, or interconnect with your existing Active Directory infrastructure.

## Related links
{: #vpc-vcf-arch-overview-links}

* [{{site.data.keyword.cloud_notm}} for VMware Cloud Foundation cookbook](https://cloud.ibm.com/media/docs/downloads/vmware-cloud-foundation/IBMCloudForVMwareCloudFoundation-Cookbook.pdf)
* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} bare metal servers](/docs/vpc?topic=vpc-planning-for-bare-metal-servers)
* [{{site.data.keyword.dl_full_notm}} overview](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl)
* [{{site.data.keyword.tg_full_notm}} overview](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [{{site.data.keyword.vpc_short}} VPN overview](/docs/vpc?topic=vpc-vpn-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on bare metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)
