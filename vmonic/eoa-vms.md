---

copyright:

  years:  2026

lastupdated: "2026-11-26"

keywords: end of access notice, eoa vmwaresolutions, end of access vcf for classic, end of access vcf for vpc, end of access vcf as a service, end of access ryo

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# End of Access for VMware on {{site.data.keyword.cloud_notm}}
{: #eoa-vms}

{{site.data.keyword.cloud}} is formally declaring the end of access to VMware on {{site.data.keyword.cloud_notm}}.

This notice applies if you have **not** received a notification from either {{site.data.keyword.IBM}} or 11:11 Systems that your VMware on {{site.data.keyword.cloud_notm}} usage has been assigned to 11:11 Systems. The notifications were distributed on 1 October 2026.

As a result of Broadcom’s decision to terminate its partnership contract with {{site.data.keyword.IBM}}, {{site.data.keyword.cloud_notm}} will no longer be an approved platform to run VMware software in March 2027.

You **must** migrate your VMware workloads, backups, and storage to other {{site.data.keyword.cloud_notm}} services or to a third-party cloud provider before 12 March 2027 00:00 hrs UTC. You **must** also stop deploying VMware licenses on {{site.data.keyword.cloud_notm}} before the same deadline.

If you want to continue using VMware software, you can contact [11:11 Systems](https://1111systems.com/){: external} to explore the available options.

After 12 March 2027 at 00:00 hrs UTC, {{site.data.keyword.cloud_notm}} **will cut off** access to customers who are still using VMware on IBM Cloud.

**Note:** 12:00 AM (00:00 hrs) UTC on 12 March 2027 corresponds to the following local times:

| Region | Timezone | Local Date and Time |
| ------------------ | ----------- | ------------------------ |
| US East Coast | EST | 11 March 2027, 7:00 PM |
| Central Europe | CET | 12 March 2027, 1:00 AM |
| Japan | JST | 12 March 2027, 9:00 AM |
{: caption="Local time equivalents" caption-side="bottom"}

## Impact to affected customers
{: #eoa-vms-impact}

VMware services that involve definitive consumption of VMware on {{site.data.keyword.cloud_notm}} will be inaccessible and permanently terminated. It also includes third-party add-on services that were bundled into {{site.data.keyword.cloud_notm}} for VMware Solutions offerings. However, stand-alone software and services that support VMware, and all other services and infrastructure in your account (including servers with other or no Operating Systems), will remain unaffected.

{{site.data.keyword.IBM_notm}} will delete only the VMware-specific resources that are associated with the account. Cleanup of all other resources is the customer's responsibility. Billing continues for associated non-VMware resources until you delete them.
{: important}

For more information, see the following table.

| Service name | Resource type | Impact of End of Access |
| :--- | :--- | :--- |
| {{site.data.keyword.cloud_notm}} for VCF as a Service | Virtual Machines and Backups | • Deletion of VCFaaS Orgs \n • Deletion of VDCs \n • Deletion of all data \n • Deletion of Veeam backups |
| VCF for Classic | VMware Virtual Machines, Bare Metals | • Deletion of Bare metal with VMware images \n • Deletion of data \n • Removing all automation, APIs and management functions |
| VCF for VPC | VMware Virtual Machines, Bare Metals | • Deletion of Bare metal with VMware images \n • Deletion of data \n • Removing all automation, APIs and management functions |
| {{site.data.keyword.cloud_notm}} Classic Bare metal with VMware image | VMware Virtual Machines, Bare Metals | • Deletion of Bare metal with VMware images \n • Deletion of data |
| VCF for Classic, VCF for VPC, and Bare metal with VMware image | Shared Storage | No impact (for example, NFS shares and Cloud Object Storage buckets will not be impacted) |
| {{site.data.keyword.cloud_notm}} Classic Bare metal with any other Operating System, including No Operating System | Bare Metals | No impact |
| Third-party add-ons (such as Veeam, Zerto, Caveonix, Juniper, F5, Entrust) for VCF for Classic and VCF for VPC | 1. Software licenses \n 2. Virtual appliances | 1. Revoking of license keys and customer must replace with their own license keys \n 2. Virtual appliances will be deleted, as stated earlier |
| VMware software licenses (stand-alone) | Software licenses | Revoking of license keys, and customer must replace with their own license keys |
| Veeam VSIs | Software licenses | No impact |
| Veeam add-on licenses (stand-alone) for PowerVS and VPC from the IC4V Licensing and Metering page | Software licenses | No impact |
| Zerto software (stand-alone) | Software licenses | No impact |
| Caveonix software (stand-alone) | Software licenses | No impact |
| Classic networking | N/A | No impact |
| {{site.data.keyword.cloud_notm}} Support (paid tiers) | N/A | No impact |
{: caption="Impact of End of Access by service" caption-side="bottom"}

## Next steps
{: #eoa-vms-next}

Contact your {{site.data.keyword.cloud_notm}} CSM, TAM, or seller, or your managed service provider (for example, Kyndryl) to plan your next steps immediately.

## Related links
{: #eoa-vms-related}

* [FAQ for EOA for VMware on {{site.data.keyword.cloud_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-faq-eoa-vms)
* [11:11 Systems](https://1111systems.com/){: external}
