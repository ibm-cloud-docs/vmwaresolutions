---

copyright:

  years:  2021, 2025

lastupdated: "2025-05-02"

keywords: Zerto, Zerto license, order Zerto license

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Ordering Zerto stand-alone licenses
{: #zerto_ordering_licenses}

You can order a Zerto license without associating it to any {{site.data.keyword.vcf-auto}} instance for licensing and activation of your on-premises workloads.

## Before you begin
{: #zerto_ordering_licenses-before-begin}

Ensure that you configured the {{site.data.keyword.cloud}} infrastructure credentials on the **Settings** page. For more information, see [Managing user accounts and settings](/docs/vmwaresolutions?topic=vmwaresolutions-useraccount).

You must have a billable {{site.data.keyword.cloud_notm}} account to order Zerto licenses and the account must be linked to the {{site.data.keyword.cloud_notm}} infrastructure account where your instance is deployed. For more information, see [Billing for Zerto replication](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering#zerto_ordering-billing).
{: important}

## Procedure to order Zerto stand-alone licenses
{: #zerto_ordering_licenses_ordering-procedure}

1. {{site.data.content.ol-intro-ui-licenses}}
2. Scroll down to the **Zerto licenses** table and click **Create new**.
3. On the **Zerto license** page, specify the resource group.

   {{site.data.content.note-orderinginstance-resource-group}}

4. Specify the name of the organization or company that the license is created for.
5. Specify a new license name or use the default name **zerto-_xx_** where _xx_ represents two randomly generated alphabetic characters.
6. In the **License notes** field, optionally enter a note. For example, you can enter a note to help you identify associated instances.
7. Specify the number of virtual machines (VMs) you want to license. The range is 1 - 1000.
8. Click the link or links of the license agreements that apply to your order and ensure that you agree with them before you order the license.
9. Click **Add to estimate**, **Upgrade**, or **Create**. The **Upgrade** option is displayed only if you must make your {{site.data.keyword.cloud_notm}} account a billable account.

Within 15 days, you must configure the Call Home feature for Zerto. If you do not complete the configuration in this time frame, Zerto blocks certain management activities. For more information about the Call Home feature for Zerto, see [Considerations for ordering Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering#zerto_ordering-private-only).
{: attention}

## Results
{: #zerto_ordering_licenses-results}

1. The status changes to **Ordering** when you submit your order.
2. When IBM Support receives your order, a license key request is sent to Zerto and the status changes to **Completed**.
3. IBM Support sends the key to the email address that is associated with the order, typically within two business days.

   The email address is added by default to the **Email address** field of the order.
   {: note}

## Related links
{: #zerto_ordering_licenses-related}

* [Zerto overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Managing Zerto stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses)
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
