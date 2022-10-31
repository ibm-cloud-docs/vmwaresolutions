---

copyright:

  years:  2022

lastupdated: "2022-10-27"

keywords: vmware cloud foundation, IBM Cloud, vpc

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Deploying {{site.data.keyword.cloud_notm}} for VMware Cloud Foundation
{: #vpc-vcf-deployment}

{{site.data.keyword.cloud_notm}} for VCF is a self-managed solution. You are currently responsible for ordering the VPC, prefixes, subnets, bare metal servers for your VCF deployment.

For day two of operation, you are responsible to monitor and manage the VMware vCenter and NSX-T, including backups, patching, configuration, and monitoring of the VMware software and the underlying vSphere hypervisor. You can use SDDC manager to update your VCF environment, or add extra functions, such as vRealize Suite.

## {{site.data.keyword.cloud_notm}} account requirements
{: #vpc-vcf-deployment-account-req}

To order {{site.data.keyword.cloud_notm}} for VCF, you must have a **Pay As You Go** {{site.data.keyword.cloud_notm}} account. The cost of the resources that are ordered is billed to that {{site.data.keyword.cloud_notm}} account. For more information, see [Upgrading to a Pay-As-You-Go account](/docs/account?topic=account-upgrading-account#upgrade-paygo).

## Required permissions for managing {{site.data.keyword.cloud_notm}} resources
{: #vpc-vcf-deployment-permission}

Access to {{site.data.keyword.cloud_notm}} resources for users in your account is controlled by {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM). Every user that accesses infrastructure services resources in your account must be assigned one or more access policies that define their IAM roles. Each user must also have access to the resource group that contains the infrastructure resources. A resource group organizes account resources in customizable groupings so that you can quickly assign access to more than one resource at a time. Every resource that is managed by IAM belongs to a resource group within your account.
To manage users access and resource groups, your account must have permissions to [Managing resource groups](/docs/account?topic=account-rgs&interface=ui) and [Managing account](/docs/account?topic=account-groups&interface=ui#prereq-create-groups) permissions.

Ensure that the following requirements are met:

* Your account meets the [required IAM permissions](/docs/vpc?topic=vpc-resource-authorizations-required-for-api-and-cli-calls) to interact with VPC infrastructure objects.
* Your account meets the [required IAM permissions](/docs/vpc?topic=vpc-planning-for-bare-metal-servers&interface=ui) for Bare Metal Servers on VPC.
* Your account meets the required [IAM permissions](/docs/dns-svcs?topic=dns-svcs-iam) for {{site.data.keyword.cloud_notm}} DNS Services.

## Methods for deploying and managing {{site.data.keyword.cloud_notm}} resources
{: #vpc-vcf-deployment-methods}

To create and manage the required assets by following the VCF architectural principles, you can use the {{site.data.keyword.cloud_notm}} console (UI), the {{site.data.keyword.cloud_notm}} CLI, or Terraform on {{site.data.keyword.cloud_notm}}.
To get started, review the following tutorials:

* [Using the {{site.data.keyword.cloud_notm}} console to create VPC resources](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console)
* [Using the CLI to create VPC resources](/docs/vpc?topic=vpc-creating-vpc-resources-with-cli-and-api&interface=cli#creating-a-vpc-using-cli)
* [Getting started with Terraform on {{site.data.keyword.cloud_notm}}](/docs/ibm-cloud-provider-for-terraform?topic=ibm-cloud-provider-for-terraform-getting-started)

## Related links
{: #vpc-vcf-deployment-links}

* [Scaling capacity of VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-scaling)
* [How {{site.data.keyword.cloud_notm}} IAM works](/docs/account?topic=account-iamoverview)
* [Managing resource groups](/docs/account?topic=account-rgs)
* [Access management in {{site.data.keyword.cloud_notm}}](/docs/account?topic=account-cloudaccess)
