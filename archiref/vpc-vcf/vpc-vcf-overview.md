---

copyright:

  years:  2022, 2023

lastupdated: "2023-09-11"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# VMware Cloud Foundation overview
{: #vpc-vcf-overview}

{{site.data.keyword.cloud_notm}} for VMware Cloud Foundation™ provides a ubiquitous hybrid cloud platform for both traditional enterprise apps and modern apps. {{site.data.keyword.vpc_full}} provides the underlying infrastructure for running VMware Cloud Foundation in {{site.data.keyword.cloud_notm}} and {{site.data.keyword.cloud}} for VMware Cloud Foundation automation deploys the required infrastructure assets inside your own {{site.data.keyword.cloud}} account.

![{{site.data.keyword.cloud_notm}} for VMware Cloud Foundation overview](../../images/vcf-vpc-v2-overview.svg "{{site.data.keyword.cloud_notm}} for VMware Cloud Foundation overview"){: caption="Figure 1. {{site.data.keyword.cloud_notm}} for VMware Cloud Foundation overview" caption-side="bottom"}

VMware Cloud Foundation deployments provide a complete set of software-defined services for compute, storage, network security, Kubernetes management, and cloud management. It includes VMware vSphere® with VMware Tanzu™, VMware vSAN™, VMware NSX™ Data Center and is managed though vCenter, SDDC manager, HCX, and VMware Aria® Suite (formerly known as VMware vRealize® Suite). The VMware Cloud Foundation management capabilities offer consistent VMware operations across private and public cloud deployments. To select an optimal {{site.data.keyword.cloud_notm}} for VMware Cloud Foundation solution for your needs, you can select between VMware Cloud Editions Advanced or Enterprise that provide you access to a unique set of VMware Cloud Foundation capabilities in a bundled form.

{{site.data.keyword.cloud}} for VMware Cloud Foundation automation provisions the required underlying infrastructure components in your own {{site.data.keyword.vpc_short}}, which is under your own control. The {{site.data.keyword.cloud_notm}} bare metal servers for {{site.data.keyword.vpc_short}} provide you with compute capacity provisioned in minutes. By using {{site.data.keyword.vpc_full}} as the underlying infrastructure, the deployment happens in an agile way inside a secure and logically isolated virtual network by using a private IP address space that you can define.

The VMware Cloud Foundation provisioning is done in a similar way that you would deploy on-premises, where the VMware Cloud Builder is responsible for the initial start of the entire software-defined stack. The combined deployment process is handled by {{site.data.keyword.cloud}} for VMware Cloud Foundation automation. Post VMware Cloud Foundation provisioning, you can manage the environment by using SDDC manager, vCenter, and NSX manager - the same tools and interfaces you would use on-premises. Adding or removing compute capacity is done by using {{site.data.keyword.cloud}} for VMware Cloud Foundation automation.

## Key responsibilities
{: #vpc-vcf-overview-responsibilities}

{{site.data.keyword.cloud_notm}} for VMware Cloud Foundation is a self-managed solution. This means that the {{site.data.keyword.cloud}} for VMware Cloud Foundation automation provisions a new VPC, prefixes, subnets, several security groups, a public gateway, and the required bare metal servers for your VMware Cloud Foundation deployment, and an {{site.data.keyword.cloud_notm}} DNS service instance. For day two of operation, you are responsible to monitor and manage the VMware vCenter and NSX, including backups, patching, configuration, and monitoring of the VMware software and the underlying vSphere hypervisor. You can use SDDC manager to update your VMware Cloud Foundation environment, or add extra functions and capabilities, such as other Aria Suite components by using the deployed Aria Lifecycle.

## Key benefits
{: #vpc-vcf-overview-benefits}

The VMware Cloud Foundation architecture provides you with the fundamental building blocks for a software-defined data center. These blocks include VMware vSphere, vCenter Server, VMware NSX, VMware vSAN, and SDDC manager to manage your VMware Cloud Foundation deployment. The VMware Cloud Foundation automation and the VMware Cloud Builder appliance automate the deployment of the entire underlying infrastructure and VMware software-defined stack and you have the same architecture and user experience as in on-premises VMware Cloud Foundation deployments.

{{site.data.keyword.cloud_notm}} provides the VMware Cloud Foundation licensing based on the selection between VMware Cloud Editions - Advanced or Enterprise. Each of these provide you access to a unique set of VMware Cloud Foundation capabilities in a bundle.

VMware Solutions in {{site.data.keyword.vpc_short}} have the following key benefits:

- {{site.data.keyword.vpc_short}} gives you the ability to easily and rapidly define and control a virtual network, which is logically isolated from all other tenants. The logical isolation is implemented by using virtual network functions and security that is built into the platform. You can freely select the private IP address space that is used in your VPC. 
- Provisioning the {{site.data.keyword.cloud_notm}} bare metal server on {{site.data.keyword.vpc_short}} takes minutes instead of hours when compared to the {{site.data.keyword.cloud_notm}} bare metal server on {{site.data.keyword.cloud_notm}} classic.
- VMware workloads by running in {{site.data.keyword.vpc_short}} can take advantage of all functions for VPC networking capabilities and other {{site.data.keyword.cloud_notm}} interconnectivity services.

Unlike the managed service offerings, {{site.data.keyword.cloud}} for VMware Cloud Foundation gives you flexibility to control, manage, and update the solution based on your needs, and it provides you full and complete access to all components.

## Related links
{: #vpc-vcf-overview-links}

* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} bare metal servers](/docs/vpc?topic=vpc-planning-for-bare-metal-servers)
* [{{site.data.keyword.vpc_short}} RYO VMware reference architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-arch-overview)
* [{{site.data.keyword.dl_full_notm}} overview](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl)
* [{{site.data.keyword.tg_full_notm}} overview](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [{{site.data.keyword.vpc_short}} VPN overview](/docs/vpc?topic=vpc-vpn-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on bare metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)