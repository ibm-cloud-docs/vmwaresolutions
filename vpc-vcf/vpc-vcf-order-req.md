---

copyright:

  years:  2023, 2025

lastupdated: "2025-03-04"

keywords: vmware cloud foundation, IBM Cloud, vpc

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Requirements for {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-order-req}

With the bare metal server infrastructure provided in {{site.data.keyword.vpc_full}} ({{site.data.keyword.vpc_short}}), you can quickly deploy {{site.data.keyword.vcf-vpc}} on {{site.data.keyword.cloud_notm}}.

Ensure that the following requirements are met:
* [{{site.data.keyword.cloud_notm}} account requirements](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-plan#vpc-vcf-plan-acc)
* [Required permissions for managing {{site.data.keyword.cloud_notm}} resources](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-plan#vpc-vcf-plan-permission)
* [Requirements for the list of allowed IP addresses](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_vcf_vpc_allowlist_ip)

The installation of {{site.data.keyword.vcf-vpc-short}} on {{site.data.keyword.cloud_notm}} uses the Terraform IBM Provider to create the necessary infrastructure resources and services.

Do not modify any values that are set during resource deployment and {{site.data.keyword.vcf-vpc-short}} instance order from the Schematics workspace. After the instance is provisioned, do not add or remove hosts manually.
{: attention}

## Related links
{: #vpc-vcf-order-req-related}

* [The {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts#signing_required_accounts-cloud)
* [Getting started with {{site.data.keyword.vpc_short}}](/docs/vpc?topic=vpc-getting-started)
* [VPC network design](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-vpc-deployment)
* [IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
