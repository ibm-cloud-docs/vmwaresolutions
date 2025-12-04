---

copyright:

  years:  2016, 2025

lastupdated: "2025-12-03"

keywords: troubleshooting, Zerto Virtual Replication, Zerto ESXi server

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Why aren't Zerto VRAs displaying for newly created ESXi servers?
{: #trbl_no_zerto_vra}
{: troubleshoot}
{: support}

{{site.data.content.vms-deprecated-note}}

Virtual Replication Appliances (VRAs) are not displayed on the Zerto Virtual Replication console after you add VMware ESXi™ servers to a {{site.data.keyword.vcf-auto}} instance with {{site.data.keyword.hpe-zerto}} disaster recovery installed.
{: tsSymptoms}

The {{site.data.keyword.hpe-zerto}} disaster recovery service is installed only on the ESXi server from the default cluster (**cluster1** for instances that are deployed in V3.1 or earlier). If new clusters are created in the same vCenter Server environment or if ESXi servers are added to new clusters, {{site.data.keyword.hpe-zerto}} disaster recovery is not installed on them. On those clusters, you must install {{site.data.keyword.hpe-zerto}} disaster recovery separately.
{: tsCauses}

Open an {{site.data.keyword.cloud}} Support ticket and work with IBM Support to obtain available IP addresses for you to install the VRAs from the {{site.data.keyword.hpe-zerto}} console, instead of the {{site.data.keyword.vmwaresolutions_short}} console.
{: tsResolve}

To access the {{site.data.keyword.hpe-zerto}} console, click the **Zerto** card from the **Services** tab of the instance and click **View details**. Then, click **View Zerto console**.

For more information about contacting IBM Support, see [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support#trbl_support).
