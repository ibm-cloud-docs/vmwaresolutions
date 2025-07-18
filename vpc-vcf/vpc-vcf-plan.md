---

copyright:

  years:  2023, 2025

lastupdated: "2025-07-10"

keywords: vmware cloud foundation, IBM Cloud, vpc

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Planning for {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-plan}

## {{site.data.keyword.cloud_notm}} account requirements
{: #vpc-vcf-plan-acc}

To order a {{site.data.keyword.vcf-vpc}} instance, you must have a Pay-As-You-Go {{site.data.keyword.cloud}} account. The cost of the resources that are ordered are billed to that {{site.data.keyword.cloud}} account. For more information, see [Upgrading to a Pay-As-You-Go account](/docs/account?topic=account-upgrading-account#upgrade-paygo).

## Required permissions for managing {{site.data.keyword.cloud_notm}} resources
{: #vpc-vcf-plan-permission}

Access to {{site.data.keyword.cloud_notm}} resources for users in your account is controlled by {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM). Every user that accesses infrastructure services resources in your account must be assigned one or more access policies that define their IAM roles. Each user must also have access to the resource group that contains the infrastructure resources.

A resource group organizes account resources in customizable groupings so that you can quickly assign access to more than one resource at a time. Every resource that is managed by IAM belongs to a resource group within your account.
To manage users access and resource groups, your account must have permissions to [manage resource groups](/docs/account?topic=account-rgs&interface=ui) and to [manage accounts](/docs/account?topic=account-groups&interface=ui#prereq-create-groups).

Ensure that the following requirements are met:
* You have an Editor or Administrator role on a resource group in the account. For more information, see [{{site.data.keyword.cloud_notm}} IAM roles](/docs/account?topic=account-userroles).
* You have permission to [create an {{site.data.keyword.bplong_notm}} workspace](/docs/schematics?topic=schematics-access#access-roles).
* Your account meets the [required IAM permissions](/docs/vpc?topic=vpc-iam-getting-started&interface=ui) to interact with {{site.data.keyword.vpc_full}} ({{site.data.keyword.vpc_short}}) infrastructure objects.
* Your account meets the [required IAM permissions](/docs/vpc?topic=vpc-planning-for-bare-metal-servers&interface=ui) for Bare Metal Servers on {{site.data.keyword.vpc_short}}.
* Your account meets the [required IAM permissions](/docs/dns-svcs?topic=dns-svcs-iam) for {{site.data.keyword.cloud_notm}} DNS Services.

## {{site.data.keyword.cloud_notm}} region and zone availability for {{site.data.keyword.vcf-vpc-short}} deployment
{: #vpc-vcf-plan-region}

The ESXi servers in {{site.data.keyword.vcf-vpc-short}} are built on Bare Metal Servers on {{site.data.keyword.vpc_short}}. Therefore, you can deploy instances only in {{site.data.keyword.cloud}} data centers that meet the requirements for {{site.data.keyword.vpc_short}} [bare metal profiles](/docs/vpc?topic=vpc-bare-metal-servers-profile&interface=ui) that are supported by {{site.data.keyword.vcf-vpc-short}}.

The following bare metal profiles are supported:
* `bx3d-metal-192x1024`
* `mx3d-metal-64x512`
* `mx3d-metal-192x2048` (available only in the Sao Paulo region)

For more information about {{site.data.keyword.vpc_short}} bare metal servers by region, see [Generation 3 (x3 and x3d) bare metal profiles availability by region](/docs/vpc?topic=vpc-bare-metal-servers-profile&interface=ui#bare-metal-profile-availability-by-region-gen3).

## {{site.data.keyword.cloud_notm}} quotas and service limits
{: #vpc-vcf-plan-limits}

When you plan your {{site.data.keyword.vcf-vpc-short}} deployment, you also need to consider [quotas and service limits](/docs/vpc?topic=vpc-quotas) for {{site.data.keyword.vpc_short}} and the resources available. For example, for bare metal server on {{site.data.keyword.vpc_short}}, the limitation is 25 per account by default. To increase a quota for a resource, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

## Configuration updates for {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-plan-configchanges}

You cannot download configuration updates for some {{site.data.keyword.vcf-vpc-short}} components from the Broadcom public repositories.

For existing {{site.data.keyword.vcf-vpc-short}} instances, you must complete the following steps:

1. To obtain a download token, open an [IBM Support ticket](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).
2. Configure the download URL for each component manually. For more information, see [VCF authenticated downloads configuration update instructions](https://knowledge.broadcom.com/external/article/390098){: external}.
3. Apply the configuration changes to the following components yourself:

   * VMware SDDC Manager. For more information, see [SDDC fails to download the updates from online repositories - Apply the Token (Manual method)](https://knowledge.broadcom.com/external/article/389871){: external}.
   * VMware vCenter Server. For more information, see [vCenter Server patching through VAMI fails to download the updates from online repositories - Resolution](https://knowledge.broadcom.com/external/article/390120){: external}.
   * VMware vSphere ESXi. For more information, see [vLCM fails to download the ESXi patches and images from online repositories - Resolution](https://knowledge.broadcom.com/external/article/390121){: external}.

For new {{site.data.keyword.vcf-vpc-short}} instances, take note of the configuration links listed previously, as you might need them for future upgrades.
{: tip}

## Related links
{: #vpc-vcf-plan-links}

* [{{site.data.keyword.vpc_short}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-ovw)
* [Requirements for {{site.data.keyword.vpc_short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-order-req)
