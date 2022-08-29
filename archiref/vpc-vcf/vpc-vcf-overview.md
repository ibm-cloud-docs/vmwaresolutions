---

copyright:

  years:  2022

lastupdated: "2022-08-22"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.cloud_notm}} for VMware Cloud Foundation overview
{: #vpc-vcf-overview}

VMware Cloud Foundation™ (VCF) provides a ubiquitous hybrid cloud platform for both traditional enterprise apps and modern apps. The {{site.data.keyword.vpc_full}} provides the underlying infrastructure for running VCF in {{site.data.keyword.cloud_notm}}.

![{{site.data.keyword.cloud_notm}} for VCF overview](../../images/vcf-on-vpc-vcf-overview.svg "{{site.data.keyword.cloud_notm}} for VCF overview"){: caption="Figure 1. {{site.data.keyword.cloud_notm}} for VCF overview" caption-side="bottom"}

VCF is based on a comprehensive software-defined stack, which includes VCF with VMware Tanzu™, VMware vSAN™, VMware NSX-T™ Data Center, and VMware vRealize® Suite. It provides a complete set of software-defined services for compute, storage, network security, Kubernetes management, and cloud management. The VMware Cloud Builder automates the initial deployment of the entire software-defined stack, and it is managed then with SDDC manager. The result is agile, reliable, and efficient. The cloud infrastructure offers consistent operations across private and public clouds. 

The {{site.data.keyword.cloud_notm}} bare metal servers for {{site.data.keyword.vpc_short}} provide you compute capacity provisioned in minutes for your VCF deployment. The VCF provisioning is done in a similar way that you deploy at on-premises. However, it happens in a much more agile way in a secure and isolated virtual network inside your {{site.data.keyword.vpc_short}}.


## Key responsibilities
{: #vpc-vcf-overview-responsibilities}

{{site.data.keyword.cloud_notm}} for VCF is a self-managed solution. You are currently responsible for ordering the VPC, prefixes, subnets, bare metal servers for your VCF deployment.

For day two of operation, you are responsible to monitor and manage the VMware vCenter and NSX-T, including backups, patching, configuration, and monitoring of the VMware software and the underlying vSphere hypervisor. You can use SDDC manager to update your VCF environment, or add extra functions, such as vRealize Suite.

At the moment, only the Bring Your Own License (BYOL) model is supported by VCF deployments.

## Key benefits
{: #vpc-vcf-overview-benefits}

The VCF architecture provides you the fundamental building blocks, which include VMware vSphere, vCenter Server, VMware NSX-T, VMware vSAN, and SDDC manager to manage your VCF deployment. The VMware Cloud Builder appliance automates the deployment of the entire VMware software-defined stack and you have the same architecture and user experience as in on-premises VCF deployments.

VMware Solutions in {{site.data.keyword.vpc_short}} have the following key benefits:

* {{site.data.keyword.vpc_short}} gives you the ability to easily and rapidly define and control a virtual network, which is logically isolated from all other tenants. The logical isolation is implemented by using virtual network functions and security that is built into the platform.
* Provisioning the {{site.data.keyword.cloud_notm}} bare metal server on {{site.data.keyword.vpc_short}} takes minutes instead of hours when compared to the {{site.data.keyword.cloud_notm}} bare metal server on {{site.data.keyword.cloud_notm}} classic.
* VMware workloads by running in {{site.data.keyword.vpc_short}} can take advantage of all original functions for VPC networking capabilities and other {{site.data.keyword.cloud_notm}} interconnectivity services.

With this single-tenant {{site.data.keyword.cloud_notm}} bare metal server infrastructure that is provided in {{site.data.keyword.vpc_short}}, you can quickly deploy network, compute, and storage capacity for your VCFn to the {{site.data.keyword.cloud_notm}}.

Unlike the managed service offerings, VCF on {{site.data.keyword.vpc_short}} gives you flexibility to design a solution for your needs, and it provides you full and complete access to all components.

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
