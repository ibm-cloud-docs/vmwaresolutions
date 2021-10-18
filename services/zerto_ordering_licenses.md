---

copyright:

  years:  2021

lastupdated: "2021-10-13"

keywords: Zerto, Zerto license, order Zerto license

subcollection: vmwaresolutions

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:download: .download}
{:preview: .preview}

# Ordering Zerto licenses
{: #zerto_ordering_licenses}

You can order a Zerto license without associating it to any VMware® vCenter Server® instance for licensing and activation of your on-premises workloads.

## Before you begin
{: #zerto_ordering_licenses-before-begin}

Ensure that you configured the {{site.data.keyword.cloud}} infrastructure credentials on the **Settings** page. For more information, see [Managing user accounts and settings](/docs/vmwaresolutions?topic=vmwaresolutions-useraccount).

You must have a billable {{site.data.keyword.cloud_notm}} account to order Zerto licenses and the account must be linked to the {{site.data.keyword.cloud_notm}} infrastructure account where your instance is deployed. For more information, see [Billing for Zerto replication](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering#zerto_ordering-billing).
{: important}

## Procedure to order Zerto licenses
{: #zerto_ordering_licenses_ordering-procedure}

1. In the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. Scroll down to the **Zerto licenses** table and click **Provision new**.
3. On the **Zerto license** page, specify the resource group.

   If **No resource group available** is displayed in this field, you currently do not have the permission to add the instance to any resource group in this account. Contact the account owner to be assigned an Editor or Administrator role on a resource group in the account. For more information, see [IAM access](/docs/account?topic=account-userroles).
   {: note}

4. Specify the name of the organization or company that the license is created for.
5. Specify a new license name or use the default name **zerto-_xx_** where _xx_ represents two randomly generated alphabetic characters.
6. In the **License notes** field, optionally enter a note. For example, you can enter a note to help you identify associated instances.
7. Specify the number of virtual machines (VMs) you want to license. The range is 1 - 1000.
8. Click the link or links of the terms that apply to your order. Ensure that you agree with these terms before you order the license.
9. Click **Add to estimate**, **Upgrade**, or **Create**.

**Upgrade** displays only if you must make your {{site.data.keyword.cloud_notm}} account a billable account.
{: note}

## Results
{: #zerto_ordering_licenses-results}

The status changes to **Ordering** when you submit your order.

When IBM Support receives your order, a license key request is sent to Zerto and the status changes to **Completed**.

IBM Support sends the key to the email address that is associated with the order, typically within two business days. 

The email address is added by default to the **Email address** field of the order.
{: note}

## Related links
{: #zerto_ordering_licenses-related}

* [Zerto overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Managing Zerto licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses)
* [Managed Disaster Recovery Services](/docs/vmwaresolutions?topic=vmwaresolutions-managing_zerto_services)
* [Zerto](https://www.zerto.com){: external}
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
