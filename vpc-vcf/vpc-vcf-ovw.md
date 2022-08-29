---

copyright:

  years:  2022

lastupdated: "2022-08-22"

keywords: vmware cloud foundation, IBM Cloud, vpc

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.cloud_notm}} for VMware Cloud Foundation overview
{: #vpc-vcf-ovw}

VMware Cloud Foundation™ (VCF) provides a ubiquitous hybrid cloud platform for both traditional enterprise apps and modern apps. VCF is based on a comprehensive software-defined stack, which includes VCF with VMware Tanzu™, VMware vSAN™, VMware NSX-T™ Data Center, and VMware vRealize® Suite. It provides a complete set of software-defined services for compute, storage, network security, Kubernetes management, and cloud management. The VMware Cloud Builder automates the initial deployment of the entire software-defined stack, and it is managed then with SDDC manager. The result is agile, reliable, and efficient. The cloud infrastructure offers consistent operations across private and public clouds.

The {{site.data.keyword.vpc_full}} provides the underlying infrastructure for running VCF in {{site.data.keyword.cloud_notm}}. The {{site.data.keyword.cloud_notm}} bare metal servers for {{site.data.keyword.vpc_short}} provide you compute capacity provisioned in minutes for your VCF deployment. The VCF provisioning is done in a similar way that you deploy at on-premises. However, it happens in a much more agile way in a secure and isolated virtual network inside your {{site.data.keyword.vpc_short}}.

![{{site.data.keyword.cloud_notm}} for VCF overview](../images/vcf-on-vpc-vcf-overview.svg "{{site.data.keyword.cloud_notm}} for VCF overview"){: caption="Figure 1. {{site.data.keyword.cloud_notm}} for VCF overview" caption-side="bottom"}

## Key benefits
{: #vpc-vcf-ovw-benefits}

The VCF architecture provides you the fundamental building blocks, which include VMware vSphere, vCenter Server, VMware NSX-T, VMware vSAN, and SDDC manager to manage your VCF deployment. The VMware Cloud Builder appliance automates the deployment of the entire VMware software-defined stack and you have the same architecture and user experience as in on-premises VCF deployments.

VMware Solutions in {{site.data.keyword.vpc_short}} have the following key benefits:

* {{site.data.keyword.vpc_short}} gives you the ability to easily and rapidly define and control a virtual network, which is logically isolated from all other tenants. The logical isolation is implemented by using virtual network functions and security that is built into the platform.
* Provisioning the {{site.data.keyword.cloud_notm}} bare metal server on {{site.data.keyword.vpc_short}} takes minutes instead of hours when compared to {{site.data.keyword.cloud_notm}} bare metal server on {{site.data.keyword.cloud_notm}} classic.
* VMware workloads by running in {{site.data.keyword.vpc_short}} can take advantage of all original functions for VPC networking capabilities and other {{site.data.keyword.cloud_notm}} interconnectivity services.

With this single-tenant {{site.data.keyword.cloud_notm}} bare metal server infrastructure that is provided in {{site.data.keyword.vpc_short}}, you can quickly deploy network, compute, and storage capacity for your VCF to the {{site.data.keyword.cloud_notm}}.

Unlike the managed service offerings, VCF on {{site.data.keyword.vpc_short}} gives you flexibility to design a solution for your needs, and it provides you full and complete access to all components.

## Supported VMware Cloud Foundation architectures in {{site.data.keyword.cloud_notm}} VPC
{: #vpc-vcf-ovw-supported-arch}

VMware Cloud Foundation (VCF) supports two architecture models - standard and consolidated, according to the requirements of your organization and the resource capabilities of your environment. Implement a standard architecture for workload provisioning and mobility across VMware Cloud Foundation instances according to production best practices. If you plan to deploy a small-scale environment and extend it according to customer adoption, or if you are working on an SDDC proof-of-concept, implement a consolidated architecture.

For more information, see [Supported VMware Cloud Foundation architectures in {{site.data.keyword.vpc_short}}](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-architectures).

## VMware Cloud Foundation Bill of Materials
{: #vpc-vcf-ovw-bom}

VMware Cloud Foundation software product is composed of the following software Bill-of-Materials (BOM). The components in the BOM are interoperable and compatible. For more information, see [VMware Cloud Foundation 4.4.1.x Bill of Materials](https://docs.vmware.com/en/VMware-Cloud-Foundation/4.4.1/rn/vmware-cloud-foundation-441-release-notes/index.html){: external}.

The following components are the initial ones for {{site.data.keyword.cloud_notm}} for VMware Cloud Foundation:
* Cloud Builder VM 4.4.1 Build Number 19766960
* SDDC Manager 4.4.1 Build Number 19766960
* VMware vCenter Server Appliance 7.0 Update 3d Build Number 19480866
* VMware ESXi 7.0 Update 3d Build Number 19482537. VMware vSAN is included in the VMware ESXi bundle
* VMware NSX-T Data Center 3.1.3.7.4 Build Number 19762317

## Related links
{: #vpc-vcf-ovw-links}

* [{{site.data.keyword.cloud_notm}} for VMware Cloud Foundation cookbook](https://cloud.ibm.com/media/docs/downloads/vmware-cloud-foundation/IBMCloudForVMwareCloudFoundation-Cookbook.pdf)
* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} design for VMware deployment](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-vpc-deployment)
* [{{site.data.keyword.vpc_short}} RYO VMware reference architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-ryo-arch-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on bare metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)
