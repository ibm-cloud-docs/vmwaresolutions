---

copyright:

  years: 2021, 2025

lastupdated: "2025-04-04"

keywords: Zerto, Zerto license, manage Zerto license

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Managing Zerto stand-alone licenses
{: #zerto_managing_licenses}

You can view and delete the Zerto licenses that you ordered for stand-alone use.

## Procedure to view Zerto stand-alone licenses
{: #zerto_managing_licenses-procedure-view}

1. {{site.data.content.ol-intro-ui-licenses}}
2. Scroll down to the **Zerto licenses** table to view the license name, creation time, and status.
3. To view more details of a specific license, click the license. The following information is displayed for the Zerto license:

* License notes
* Number of VMs licensed
* Creation date
* Email address
* Status

   The status can have one of the following values:
   * **Ordering** - the order is submitted to IBM Support.
   * **Completed** - IBM Support received your order and a license key request was sent to Zerto.

## Procedure to renew Zerto stand-alone licenses
{: #zerto_managing_licenses-procedure-renew}

Your Zerto license expires annually. Before it expires, you must request a new license and delete your existing one.

To renew your license, complete the following steps:

1. Order a new license with your required quantity. For more information, see [Ordering Zerto stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses).
2. Wait to receive your new license key from IBM Support.
3. After you receive the new license key, delete your existing license. For more information, see [Procedure to delete Zerto stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses#zerto_managing_licenses-procedure-delete).

## Procedure to delete Zerto stand-alone licenses
{: #zerto_managing_licenses-procedure-delete}

Deleting a Zerto license does not delete the Zerto service that is installed on a {{site.data.keyword.vcf-auto-short}} instance. To delete the service, you must do so in the {{site.data.keyword.vmwaresolutions_short}} console.

For more information, see [Deleting services from {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices).

To delete a Zerto license:

1. In the VMware Solutions console, click **Licensing and metering > Add-on services** from the left navigation panel.
2. Scroll down to the **Zerto licenses** table and select the license that you want to delete.
3. From the **Actions** menu, click **Delete license**.
4. In the **Notes** field, optionally enter a reason for license deletion.
5. Enter the license name to confirm deletion and click **Delete**.

   The status of the license is changed to **Removing**. When the license deletion is complete, the license is no longer listed in the **Zerto licenses** table and you receive an email that confirms the license deletion.

The license charge is reflected on your account until the end of the billing cycle, which is typically 30 days.
{: note}

## Related links
{: #zerto_managing_licenses-related}

* [Zerto overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Ordering Zerto stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses)
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
