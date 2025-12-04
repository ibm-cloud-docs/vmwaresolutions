---

copyright:

  years:  2016, 2025

lastupdated: "2025-12-03"

keywords: Zerto, Zerto replication billing, order Zerto

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Ordering {{site.data.keyword.hpe-zerto}}
{: #zerto_ordering}

{{site.data.content.vms-deprecated-note}}

You can include the {{site.data.keyword.hpe-zerto}} service with a new {{site.data.keyword.vcf-auto}} instance or add the service to your existing instance.

## Billing for {{site.data.keyword.hpe-zerto}} replication
{: #zerto_ordering-billing}

VMs (virtual machines) that are replicated by using {{site.data.keyword.hpe-zerto}} are metered by {{site.data.keyword.hpe-zerto}} and {{site.data.keyword.cloud}}. Your bill for this usage is charged through an {{site.data.keyword.cloud_notm}} billable account instead of an {{site.data.keyword.cloud_notm}} infrastructure account.

Before you order {{site.data.keyword.hpe-zerto}}, ensure that your {{site.data.keyword.cloud_notm}} account is a billable account, and that it is linked to the same {{site.data.keyword.cloud_notm}} infrastructure account where your instance is deployed.

### Viewing {{site.data.keyword.hpe-zerto}} charges
{: #zerto_ordering-view-charge}

To view your {{site.data.keyword.hpe-zerto}} usage charges, follow these steps:

1. Go to the {{site.data.keyword.cloud_notm}} [Usage](/billing/usage) page.
2. From the **Filter by group** list, select **VMware Solutions**.

## Ordering {{site.data.keyword.hpe-zerto}} for a new instance
{: #zerto_ordering-new}

1. When you [order the instance](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure), scroll down to the **Add-on services** section. {{site.data.keyword.hpe-zerto}} is in the **Data resiliency and migration** category.
2. Open the category, locate {{site.data.keyword.hpe-zerto}}, and toggle its switch on.
3. Click **Edit** to review and specify the configuration information, then click **Save**.

## Ordering {{site.data.keyword.hpe-zerto}} for an existing instance
{: #zerto_ordering-existing}

1. On the instance details page, click the **Services** tab.
2. Click **Add** to add the service.
3. On the **Add services** page, locate the **{{site.data.keyword.hpe-zerto}}** service in the **Data resiliency and migration** section and toggle its switch on.
4. Click **Edit** to review and specify the configuration information, then click **Save**.

If you add {{site.data.keyword.hpe-zerto}} to a {{site.data.keyword.vcf-auto-short}} instance that has a VMware® ESXi™ server that is in maintenance mode, you must use the Zerto Virtual Manager (ZVM) console. Use the pre-populated Zerto Virtual Replication Appliance (VRA) IP address to manually deploy the VRA virtual machine (VM).
{: important}

## Considerations for ordering {{site.data.keyword.hpe-zerto}}
{: #zerto_ordering-private-only}

When you deploy {{site.data.keyword.hpe-zerto}}, you must configure your own proxy or NAT connection to the public network.

Within 15 days, you must configure the Call Home feature for {{site.data.keyword.hpe-zerto}}. If you do not complete the configuration in this time frame, the following issues might happen:
* {{site.data.keyword.hpe-zerto}} blocks certain management activities.
* You are charged for a full month of usage.

For more information about {{site.data.keyword.hpe-zerto}} Call Home, see [How to configure Zerto Reporting for Enterprise environments (Call Home)](https://help.zerto.com/bundle/z-kb-articles-zertokbs/page/4824.html){: external}.

## Related links
{: #zerto_ordering-related}

* [{{site.data.keyword.hpe-zerto}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing {{site.data.keyword.hpe-zerto}}](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Ordering {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses)
* [Managing {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses)
* [{{site.data.keyword.hpe-zerto}} product documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
