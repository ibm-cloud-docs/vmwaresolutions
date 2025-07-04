---

copyright:

  years:  2016, 2025

lastupdated: "2025-06-24"

keywords: vmware offering, vmware solutions functions, function support

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Offering comparison chart
{: #inst_comp_chart}

Review the following information to understand the differences in feature support between the various {{site.data.keyword.vmwaresolutions_full}} offerings.

## {{site.data.keyword.vcf-auto-short}} vs Flexible
{: #inst_comp_chart-vcs-vss}

Review the following table to understand the differences in feature support for {{site.data.keyword.vcf-auto}} and {{site.data.keyword.vcf-flex}} instances.

| Feature | {{site.data.keyword.vcf-auto-short}} | {{site.data.keyword.vcf-flex-short}} |
|:------- |:--------- |:-------- |
| Powered by {{site.data.keyword.IBM}} advanced automation[^automation] | Yes | No. Self-built and configured. |
| Storage options | * NFS or vSAN™ - available with automation \n * iSCSI - available with manual configuration | NFS, vSAN, or iSCSI - available with manual configuration |
| Number of ESXi™ servers in the initial cluster | For vSAN: 4 servers[^esxivsanvcs07] or 3 servers[^esxivsanvcs08] \n \n For NFS: \n * At least 3 servers for consolidated clusters \n * At least 2 servers for other clusters | No limitation. One or more ESXi servers are allowed on the console. For example, you can deploy a 3-node vSAN cluster with FTT=1. |
| Maximum number of ESXi servers | * 51 per consolidated cluster \n * 59 per workload cluster | 59 per cluster |
| Cloud automated multisite deployment | Supported for new instances | Supported. Automated configuration - not included. |
| Add or remove ESXi servers | Supported | Supported. Automated configuration - not included. |
| Multicluster support | The maximum number depends on VMware® by Broadcom sizing guidelines | Supported. Automated configuration - not included. |
| Client-managed updating and patching of VMware stack | Client-managed updates - Native VMware tools (VMware Update Manager™ or vSphere Lifecycle Manager) | Client-managed updates - Native VMware tools (VMware Update Manager or vSphere Lifecycle Manager) |
| Backup and restore | Manually, by using Veeam® | Backup and restore solution - not included |
| Add-on services | Supported[^services] | Not supported by the automation of this solution. You can bring and install your own software. |
| VMware components licensing | Automated for some VMware products | Not automated |
{: caption="Supported functions for Automated and Flexible instances" caption-side="bottom"}

[^automation]: According to a validated design and with verification during deployment

[^esxivsanvcs07]: Except for vSAN ESA

[^esxivsanvcs08]: For vSAN ESA on vSphere 8

[^services]: Add-on services that are supported might vary.

## {{site.data.keyword.vcf-auto-short}} vs {{site.data.keyword.rw}}
{: #inst_comp_chart-vcs-vrw}

Review the following table to understand the differences in feature support for {{site.data.keyword.vcf-auto}} and {{site.data.keyword.rw}}.

| Feature | {{site.data.keyword.vcf-auto-short}} | {{site.data.keyword.rw}} |
|:------- |:--------- |:-------- |
| NFS | Optional | Not allowed |
| Consolidated cluster | Optional | Optional |
| Separate management cluster | Supported | Supported |
| Minimum number of ESXi servers | * For vSAN, 4 servers[^esxivsanvrw07] or 3 servers[^esxivsanvrw08] \n * For NFS, 3 servers | 6 servers: \n * 4 for the consolidated cluster \n * 2 for the gateway cluster |
| Gateway cluster | Optional | Required. Juniper vSRX, FortiGate Virtual Appliance, Bring your own gateway, or FortiGate Security Appliance. |
| Logging and monitoring with VMware Aria® Operations™ and VMware Aria Operations™ for Logs | Optional | Required |
| Compliance with Caveonix | Optional | Required |
| Caveonix pricing | Per VM | Per host |
| Key encryption | Key Protect or Hyper Protect Crypto Services | Hyper Protect Crypto Services required |
| Direct Link | Optional | Required for private only instances |
| Backup | Veeam (opt out) | Veeam Backup and Replication 12 or later is required with option to remove on Day 2 |
| Veeam backup server | Optional (opt out) | Required with option to remove on Day 2 |
| Disaster recovery | Veeam or Zerto | Veeam |
| Migration | HCX™, Zerto, or PrimaryIO Migrations | HCX (optional) |
| Financial Services Cloud with policy framework | No | Yes |
| VMware components licensing | Automated for some VMware products | Not automated |
{: caption="Supported features for Automated instances and {{site.data.keyword.rw}}" caption-side="bottom"}

[^esxivsanvrw07]: Except for vSAN ESA

[^esxivsanvrw08]: For vSAN ESA on vSphere 8

## Related links
{: #inst_comp_chart-related}

* [{{site.data.keyword.vcf-auto-short}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview)
* [{{site.data.keyword.vcf-flex-short}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-vs_vsphereoverview)
* [{{site.data.keyword.vcf-auto-short}} BOM](/docs/vmwaresolutions?topic=vmwaresolutions-vc_bom)
* [{{site.data.keyword.vcf-flex-short}} BOM](/docs/vmwaresolutions?topic=vmwaresolutions-vs_bom)
* [General FAQ about VCF for Classic](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
