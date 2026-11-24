---

copyright:

  years:  2026

lastupdated: "2026-11-24"

keywords: FAQ end of access for vmwaresolutions, vmware solutions, end of access, end of access

subcollection: vmwaresolutions

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQ for End of access for VMware on {{site.data.keyword.cloud_notm}}
{: #faq-eoa-vms}

{{site.data.content.vms-deprecated-note}}

Find answers to frequently asked questions about the End of Access for VMware on {{site.data.keyword.cloud}}.

## Why is {{site.data.keyword.IBM_notm}} announcing the End of Access for VMware on {{site.data.keyword.cloud_notm}}?
{: #faq-eoa-vms-11-11-reason}
{: faq}

As a result of Broadcom’s decision to not renew the partnership contract with {{site.data.keyword.cloud_notm}}, {{site.data.keyword.cloud_notm}} will no longer be an approved platform to run VMware software in March 2027.

You **must** migrate your VMware workloads, backups, and storage to other {{site.data.keyword.cloud_notm}} services or to a third-party cloud provider before 12 March 2027 00:00 hrs UTC[^timezone]. You **must** also stop deploying VMware licenses on {{site.data.keyword.cloud_notm}} before the same deadline.

[^timezone]: For reference, 12:00 AM (00:00 hrs) UTC on 12 March 2027 is equivalent to **7:00 PM EST (11 March 2027)**, **1:00 AM CET (12 March 2027)**, and **9:00 AM JST (12 March 2027)**.

If you want to continue using VMware software, you can contact [11:11 Systems](https://1111systems.com/){: external} to explore the available options.

**Note:** 00:00 hrs UTC on 12 March 2027 corresponds to the following local times:

| Region | UTC Offset | Local Date | Local Time |
| ---------------------------- | ------------ | --------------- | ------------------ |
| US East Coast | UTC−5 | 11 March 2027 | 7:00 PM |
{: caption="Local time equivalents" caption-side="bottom"}
{: tab-title="EST"}
{: tab-group="Timezone"}
{: class="simple-tab-table"}
{: #table-timezone-equiv}

| Region | UTC Offset | Local Date | Local Time |
| ---------------------------- | ------------ | --------------- | ------------------ |
| Central Europe | UTC+1 | 12 March 2027 | 1:00 AM |
{: caption="Local time equivalents" caption-side="bottom"}
{: tab-title="CET"}
{: tab-group="Timezone"}
{: class="simple-tab-table"}
{: #table-timezone-equiv}

| Region | UTC Offset | Local Date | Local Time |
| ---------------------------- | ------------ | --------------- | ------------------ |
| Japan | UTC+9 | 12 March 2027 | 9:00 AM |
{: caption="Local time equivalents" caption-side="bottom"}
{: tab-title="JST"}
{: tab-group="Timezone"}
{: class="simple-tab-table"}
{: #table-timezone-equiv}

## Who does the End of Access apply to?
{: #faq-eoa-vms-11-11-applies}
{: faq}

This notice applies if you have **not** received a notification from either {{site.data.keyword.IBM}} or 11:11 Systems that your VMware on {{site.data.keyword.cloud_notm}} usage has been assigned to 11:11 Systems. The notifications were distributed on 1 October 2026.

## I was notified about the End of Access. What should I do next?
{: #faq-eoa-vms-11-11-nextsteps}
{: faq}

Customers who are notified about the End of Access for VMware on {{site.data.keyword.cloud_notm}} must migrate their VMware workloads, backups, and storage to other {{site.data.keyword.cloud_notm}} services or to a third-party cloud provider. Customers must stop deploying VMware licenses on {{site.data.keyword.cloud_notm}} before 12 March 2027 00:00 hrs UTC. No extensions or exceptions are allowed to this announcement.

## What is going to happen to VMware workloads, storage and backups on {{site.data.keyword.cloud_notm}} on 12 March 2027 for impacted customers?
{: #faq-eoa-vms-11-11-deadline}
{: faq}

Access to the VMware workloads, storage, and backups, as described in the next answer, will end for you on 12 March 2027 at 00:00 hrs UTC. Workloads will be shut down and network access to the VMware environment will be disabled. No migration activity will be permitted beyond this deadline, so you must complete any migration activities before 12 March 2027 at 00:00 hrs UTC.

## Are there services that remain unaffected by this development? I would like to know more about which of my services will be impacted, and which ones will remain operational.
{: #faq-eoa-vms-11-11-unaffected}
{: faq}

VMware services that involve definitive consumption of VMware on {{site.data.keyword.cloud_notm}} will be inaccessible and permanently terminated. It also includes third-party add-on services that were bundled into {{site.data.keyword.cloud_notm}} for VMware Solutions offerings. However, stand-alone software and services that support VMware services (including multiple other offerings) will remain unaffected.

{{site.data.keyword.IBM_notm}} will delete only the VMware-specific resources that are associated with the account. Cleanup of all other resources is the customer's responsibility. Billing will continue for associated non-VMware resources until you delete them.
{: note}

For more information, see the following table.

| Service name | Resource type | Impact of End of Access |
| :--- | :--- | :--- |
| {{site.data.keyword.cloud_notm}} for VCF as a Service | Virtual Machines and Backups | • Deletion of VCFaaS Orgs \n • Deletion of VDCs \n • Deletion of all data \n • Deletion of Veeam backups |
| VCF for Classic | VMware Virtual Machines, Bare Metals | • Deletion of Bare metal with VMware images \n • Deletion of data \n • Removing all automation, APIs and management functions |
| VCF for VPC | VMware Virtual Machines, Bare Metals | • Deletion of Bare metal with VMware images \n • Deletion of data \n • Removing all automation, APIs and management functions |
| {{site.data.keyword.cloud_notm}} Classic Bare metal with VMware image | VMware Virtual Machines, Bare Metals | • Deletion of Bare metal with VMware images \n • Deletion of data |
| VCF for Classic, VCF for VPC, and Bare metal with VMware image | Shared Storage | No impact (for example, NFS shares and Cloud Object Storage buckets will not be impacted) |
| {{site.data.keyword.cloud_notm}} Classic Bare metal with no Operating System | Bare Metals | No impact |
| Third-party add-ons (such as Veeam, Zerto, Caveonix, Juniper, F5, Entrust) for VCF for Classic and VCF for VPC | 1. Software licenses \n 2. Virtual appliances | 1. Revoking of license keys and customer must replace with their own license keys \n 2. Virtual appliances will be deleted, as stated earlier |
| VMware software licenses (stand-alone) | Software licenses | Revoking of license keys, and customer must replace with their own license keys |
| Veeam VSIs | Software licenses | No impact |
| Veeam add-on licenses (stand-alone) for PowerVS and VPC from the IC4V Licensing and Metering page | Software licenses | No impact |
| Zerto software (stand-alone) | Software licenses | No impact |
| Caveonix software (stand-alone) | Software licenses | No impact |
| Classic networking | N/A | No impact |
| {{site.data.keyword.cloud_notm}} Support (paid tiers) | N/A | No impact |
{: caption="Impact of End of Access by service" caption-side="bottom"}
{: #table-eoa-impact}

## What happens to my data if I fail to complete the migration by the End of Access deadline?
{: #faq-eoa-vms-11-11-dataloss}
{: faq}

Starting 12 March 2027, the actions that are listed [earlier](#table-eoa-impact) will be carried out regardless of the status of your migration.

## Related links
{: #faq-eoa-vms-related}

* [End of access for VMware on {{site.data.keyword.cloud_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-eoa-vms)
