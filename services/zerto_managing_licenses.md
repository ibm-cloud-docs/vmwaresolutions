---

copyright:

  years: 2021, 2025

lastupdated: "2025-12-03"

keywords: Zerto, Zerto license, manage Zerto license

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Managing {{site.data.keyword.hpe-zerto}} stand-alone licenses
{: #zerto_managing_licenses}

{{site.data.content.vms-deprecated-note}}

You can view and delete the {{site.data.keyword.hpe-zerto}} licenses that you ordered for stand-alone use.

## Procedure to view {{site.data.keyword.hpe-zerto}} stand-alone licenses
{: #zerto_managing_licenses-procedure-view}

1. {{site.data.content.ol-intro-ui-licenses}}
2. Scroll down to the **{{site.data.keyword.hpe-zerto}} licenses** table to view the license name, creation time, and status.
3. To view more details of a specific license, click the license. The following information is displayed for the {{site.data.keyword.hpe-zerto}} license:

* License notes
* Number of VMs licensed
* Creation date
* Email address
* Status

   The status can have one of the following values:
   * **Ordering** - the order is submitted to IBM Support.
   * **Completed** - IBM Support received your order and a license key request was sent to {{site.data.keyword.hpe-zerto}}.

## Procedure to renew {{site.data.keyword.hpe-zerto}} stand-alone licenses
{: #zerto_managing_licenses-procedure-renew}

Your {{site.data.keyword.hpe-zerto}} license expires annually. Before it expires, you must request a new license and delete your existing one.

To renew your license, complete the following steps:

1. Order a new license with your required quantity. For more information, see [Ordering {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses).
2. Wait to receive your new license key from IBM Support.
3. After you receive the new license key, delete your existing license. For more information, see [Procedure to delete {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses#zerto_managing_licenses-procedure-delete).

## Procedure to delete {{site.data.keyword.hpe-zerto}} stand-alone licenses
{: #zerto_managing_licenses-procedure-delete}

Deleting a {{site.data.keyword.hpe-zerto}} license does not delete the {{site.data.keyword.hpe-zerto}} service that is installed on a {{site.data.keyword.vcf-auto-short}} instance. To delete the service, you must do so in the {{site.data.keyword.vmwaresolutions_short}} console.

For more information, see [Deleting services from {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices).

To delete a {{site.data.keyword.hpe-zerto}} license:

1. In the VMware Solutions console, click **Licensing and metering > Add-on services** from the left navigation panel.
2. Scroll down to the **{{site.data.keyword.hpe-zerto}} licenses** table and select the license that you want to delete.
3. From the **Actions** menu, click **Delete license**.
4. In the **Notes** field, optionally enter a reason for license deletion.
5. Enter the license name to confirm deletion and click **Delete**.

   The status of the license is changed to **Removing**. When the license deletion is complete, the license is no longer listed in the **{{site.data.keyword.hpe-zerto}} licenses** table and you receive an email that confirms the license deletion.

The license charge is reflected on your account until the end of the billing cycle, which is typically 30 days.
{: note}

## Related links
{: #zerto_managing_licenses-related}

* [{{site.data.keyword.hpe-zerto}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing {{site.data.keyword.hpe-zerto}}](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Ordering {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses)
* [{{site.data.keyword.hpe-zerto}} technical documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
