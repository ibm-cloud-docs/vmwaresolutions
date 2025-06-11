---

copyright:

  years:  2020, 2025

lastupdated: "2025-06-10"

keywords: Veeam, Veeam standalone license, order Veeam standalone license

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Ordering Veeam stand-alone licenses
{: #veeam_ordering_licenses}

You can order a Veeam® stand-alone license without associating it to any {{site.data.keyword.vcf-auto}} instance for licensing and activation of your on-premises workloads.

## Considerations for installing and deleting Veeam licenses
{: #managingveeam-install-delete-consid}

For Veeam 10 and later versions, Veeam licenses are installed and deleted in a different way than previous Veeam versions:
* After you place an order for Veeam, a Veeam stand-alone license is deployed. The Veeam service installation begins only after the stand-alone license order completed successfully. After that, depending on what you ordered, Veeam is installed on the bare metal server, VM, or VSI.
* When you uninstall Veeam, the stand-alone license instance is not deleted. To avoid being charged for the stand-alone license, you must delete it separately.

If you have an existing Veeam 9.5u4b installation that comes with a license and you want more coverage, you can keep your license that came with the installation and order a new license to upgrade your usage. Later, if you delete Veeam 9.5u4b, you must delete separately any stand-alone licenses that you ordered. Otherwise, you continue to be charged for them.
{: attention}

When you plan to upgrade your Veeam usage, you might be charged for licenses for Veeam 9.5, which is deprecated, and for the currently supported Veeam version. Therefore, order a new license for your Veeam installation toward the end of a month, so you aren’t charged for both licenses for most of the month.
{: tip}

## Procedure to order Veeam stand-alone licenses
{: #veeam_ordering_licenses_ordering-procedure}

1. In the VMware Solutions console, click **Licensing and metering > Add-on services** from the left navigation panel.
2. Scroll down to the **Veeam licenses** table and click **Create new**.
3. Enter the required information for the fields.
4. Click the link or links of the license agreements that apply to your order and ensure that you agree with them before you order the license.
5. Click **Add to estimate** or **Create**.

## Results
{: #veeam_ordering_licenses-results}

The ordering process starts automatically and an email is sent to confirm the license order. For more information, see [Managing Veeam stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_managing_licenses).

A license key is generated to whomever placed the order.

## Related links
{: #veeam_ordering_licenses-related}

* [Veeam on {{site.data.keyword.cloud_notm}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview)
* [Ordering Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering)
* [Managing Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam)
* [Managing Veeam stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_managing_licenses)
* [Ordering and configuring {{site.data.keyword.cloud_notm}} Object Storage with Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering)
