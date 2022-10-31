---

copyright:

  years:  2016, 2022

lastupdated: "2022-10-14"

keywords: Zerto, Zerto replication billing, order Zerto

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Ordering Zerto
{: #zerto_ordering}

You can include the Zerto service with a new VMware vCenter Server® instance or add the service to your existing vCenter Server instance.

Zerto v9.5u1 no longer supports vSphere 6.5 and 6.7. However, you can still order stand-alone licenses for existing vSphere 6.x instances.
{: note}

## Billing for Zerto replication
{: #zerto_ordering-billing}

VMs that are replicated by using Zerto are metered by Zerto and {{site.data.keyword.cloud}}. Your bill for this usage is charged through an {{site.data.keyword.cloud_notm}} billable account instead of an {{site.data.keyword.cloud_notm}} infrastructure account.

Before you order Zerto, ensure that your {{site.data.keyword.cloud_notm}} account is a billable account, and that it is linked to the same {{site.data.keyword.cloud_notm}} infrastructure account where your instance is deployed.

### Viewing Zerto charges
{: #zerto_ordering-view-charge}

To view your Zerto usage charges, follow these steps:

1. Go to the [IBM Cloud Billing and Usage](https://cloud.ibm.com/billing/usage) page.
2. From the **Filter by group** list, select **VMware Solutions**.

### Zerto installations from V3.0 or earlier
{: #zerto_ordering-30-install}

If you have a Zerto installation from V3.0 or earlier, your VM replication costs are still being billed by using {{site.data.keyword.cloud_notm}} infrastructure billing. If your accounts and billing settings meet the requirements that are listed previously, you can convert your Zerto billing method to billable.

On the {{site.data.keyword.vmwaresolutions_short}} console, you are prompted to convert from the {{site.data.keyword.cloud_notm}} infrastructure plan to a billable plan and to upgrade your {{site.data.keyword.cloud_notm}} account to a billable account, if needed.

* For more information about free and billable accounts, see [Account types](/docs/account?topic=account-accounts).
* For more information about upgrading to a billable account, see [Upgrading your account](/docs/account?topic=account-upgrading-account).
* For more information about linking your {{site.data.keyword.cloud_notm}} and your {{site.data.keyword.cloud_notm}} infrastructure accounts, see [Enabling MFA for your account](/docs/account?topic=account-enablemfa).

## Ordering Zerto for a new instance
{: #zerto_ordering-new}

1. When you [order the instance](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure), scroll down to the Add-on services section. Zerto is in the Business continuity and migration category. 
2. Open the category, locate Zerto, and toggle its switch on.
3. Select **Edit** to review and specify the information. 
4. If you enter or change information, click **Save**.

## Ordering Zerto for an existing instance
{: #zerto_ordering-existing}

1. On the instance details page, click **Services** on the left navigation pane.
2. Click **Add** to add the service.
3. On the **Services** page, locate the **Zerto** service and toggle its switch on.
4. Follow the steps to configure and add the service to your instance.

If you add Zerto to a vCenter Server instance that has a VMware® ESXi™ server that is in maintenance mode, you must use the Zerto Virtual Manager (ZVM) console. Use the pre-populated Zerto Virtual Replication Appliance (VRA) IP address to manually deploy the VRA virtual machine (VM).
{: note}

## Considerations for ordering Zerto
{: #zerto_ordering-private-only}

When you deploy Zerto, you must configure your own proxy or NAT connection to the public network.

Within 15 days, you must configure the Call Home feature for Zerto. If you do not complete the configuration in this timeframe, Zerto blocks certain management activities.

For more information about Zerto Call Home, see [How to configure Zerto Reporting for Enterprise environments (Call Home)](https://www.zerto.com/myzerto/knowledge-base/zerto-reporting-for-enterprise-environments-call-home/){: external}.

## Related links
{: #zerto_ordering-related}

* [Zerto overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Ordering Zerto licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses)
* [Managing Zerto licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses)
* [Managed Disaster Recovery Services by Kyndryl](/docs/vmwaresolutions?topic=vmwaresolutions-managing_zerto_services)
* [Zerto](https://www.zerto.com){: external}
* [Zerto product documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
