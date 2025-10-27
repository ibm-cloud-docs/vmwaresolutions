---

copyright:

  years:  2025

lastupdated: "2025-10-24"

keywords: end of marketing notice, eom vmwaresolutions, end of marketing vcf for classic, end of marketing vcf for vpc, end of marketing vcf as a service

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# End of Marketing for VMware on {{site.data.keyword.cloud_notm}}
{: #eos-vms}

{{site.data.content.vms-deprecated-note}}

Effective 31 October 2025, {{site.data.keyword.cloud_notm}} will no longer sell VMware on {{site.data.keyword.cloud_notm}} offerings to customers who do not have at least one active VMware workload that is running on {{site.data.keyword.cloud_notm}} before that date.

Due to changes to the Broadcom VSCP (VMware Cloud Services Provider) partner program, {{site.data.keyword.IBM}} is no longer permitted to sell VMware licenses to customers who do not have at least one active VMware workload that is running on {{site.data.keyword.cloud_notm}} before 31 October 2025.

Existing customers can continue to use and expand their VMware environments, but the following restrictions apply beginning on 31 October 2025:

* Existing customers cannot order a different VMware offering than what they currently use.
* The following restrictions apply only to the {{site.data.keyword.vcf-aas-full}} offering:
   * Workload expansion is limited to your current regions or resource pools.
   * The consumption model is limited to your existing model: on-demand or reserved.
   * Using the Veeam® Backup service for virtual machine (VM) backup is not available if you are not already using the service to actively back up your VMs.
   * Existing usage of the Veeam Backup service cannot be expanded beyond your current regions.
   * New dedicated Veeam Scale-out Backup Repositories (SOBRs) are limited to Cloud Object Storage (COS) only storage.

*Existing customer* is defined as an {{site.data.keyword.cloud_notm}} account (or Enterprise child account) with at least one active VMware workload on {{site.data.keyword.cloud_notm}} before 31 October 2025. If an existing customer has multiple {{site.data.keyword.cloud_notm}} accounts, only those accounts that have the VMware offerings before 31 October 2025 are allowed to expand their environments based on the restrictions that are stated earlier.

*VMware workload* is defined as:

* At least one deployed host machine on the following {{site.data.keyword.cloud_notm}} offerings:
   * VMware on Bare Metal Servers for Classic, including {{site.data.keyword.cloud_notm}} for Government environments
   * {{site.data.keyword.vcf-auto-short}}
   * {{site.data.keyword.vcf-flex-short}}
   * {{site.data.keyword.vcf-vpc-short}}
   * {{site.data.keyword.vcf-aas}} single-tenant
* At least one deployed or migrated VM on {{site.data.keyword.vcf-aas}} multitenant

This notice addresses End of Marketing only and it does not reflect End of Support.
{: note}

For more information, see [FAQ for EOM for VMware on {{site.data.keyword.cloud_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-faq-eos-vms).
