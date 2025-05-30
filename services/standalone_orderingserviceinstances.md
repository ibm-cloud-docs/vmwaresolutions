---

copyright:

  years:  2016, 2025

lastupdated: "2025-05-02"

keywords: VMware HCX standalone, HCX on-premises, order HCX

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Ordering on-premises VMware HCX instances
{: #standalone_orderingserviceinstances}

You can order an on-premises VMware® HCX™ instance without associating it to any {{site.data.keyword.vcf-auto}} instance for licensing and activation of your on-premises HCX installation.

## Before you begin
{: #standalone_orderingserviceinstances-reqs}

Ensure that you completed the following tasks:
*  You configured the {{site.data.keyword.cloud}} infrastructure credentials on the **Settings** page. For more information, see [Managing user accounts and settings](/docs/vmwaresolutions?topic=vmwaresolutions-useraccount).
*  You reviewed the [considerations for on-premises HCX instances](/docs/vmwaresolutions?topic=vmwaresolutions-standalone_considerations).

## Procedure to order on-premises VMware HCX instances
{: #standalone_orderingserviceinstances-procedure}

1. {{site.data.content.ol-intro-ui-licenses}}
2. Scroll down to the **On-premises HCX activation keys** table and click **Create new**.
3. Specify the resource group.

   {{site.data.content.note-orderinginstance-resource-group}}

4. Specify a new on-premises instance name, or use the default one **hcx-_xx_** where _xx_ represents two randomly generated alphabetic characters.
5. Click the link or links of the license agreements that apply to your order and ensure that you agree with them before you order the license.
6. Click **Add to estimate** or **Create**.

## Results
{: #standalone_orderingserviceinstances-results}

The ordering of the service activation key starts automatically. You receive confirmation that the order is being processed and you can check the status of the order by viewing the instance details.

When the activation key is ready to use, the status of the instance is changed to **Installed** and you receive a notification by email.

## What to do next
{: #standalone_orderingserviceinstances-next}

View and manage the on-premises HCX instance that you ordered.

## Related links
{: #standalone_orderingserviceinstances-related}

* [Viewing on-premises HCX instances](/docs/vmwaresolutions?topic=vmwaresolutions-standalone_viewingserviceinstances)
* [Deleting on-premises HCX instances](/docs/vmwaresolutions?topic=vmwaresolutions-standalone_deletingserviceinstances)
* [Glossary of HCX terms](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_glossary)
* [VMware HCX documentation](https://techdocs.broadcom.com/us/en/vmware-cis/hcx.html){: external}
