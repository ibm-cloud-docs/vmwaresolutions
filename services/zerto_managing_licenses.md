---

copyright:

  years: 2021, 2023

lastupdated: "2023-02-01"

keywords: Zerto, Zerto license, manage Zerto license

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Managing Zerto licenses
{: #zerto_managing_licenses}

You can view and delete the Zerto licenses that you ordered for stand-alone use.

## Procedure to view Zerto licenses
{: #zerto_managing_licenses-procedure-view}

1. From the {{site.data.keyword.vmwaresolutions_full}} console, click **Licenses** from the left navigation pane.
2. Scroll down to the **Zerto licenses** table to view the license name, creation time, and status.
3. To view more details of a specific license, click the license.

The following information is displayed for the Zerto license:
* License notes
* Number of VMs licensed
* Creation date
* Email address
* Status

The status is one of the following items.
* Ordering - the order is submitted to IBM Support.
* Completed - IBM Support receives your order and a license key request is sent to Zerto.

## Procedure to delete Zerto licenses
{: #zerto_managing_licenses-procedure-delete}

Deleting a Zerto license does not delete the Zerto service that is installed on a vCenter Server instance. To delete the service, you must do so in the {{site.data.keyword.vmwaresolutions_short}} console.

For more information, see [Deleting services from vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices).

Use the following steps to delete a Zerto license.

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Licenses** from the left navigation pane.
2. Scroll down to the **Zerto licenses** table and select the license that you want to delete.
3. From the **Actions** menu, click **Delete license**.
4. In the **Notes** field, optionally enter a reason for license deletion.
5. Enter the license name to confirm deletion and click **Delete**. The status of the license is changed to **Removing**.

When the license deletion is complete, the license is no longer listed in the **Zerto licenses** table and you receive an email that confirms the license deletion.

The license charge is reflected on your account until the end of the billing cycle, which is typically 30 days.
{: note}

## Related links
{: #zerto_managing_licenses-related}

* [Zerto overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Ordering Zerto licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses)
* [Managed Disaster Recovery Services by Kyndryl](https://www.kyndryl.com/us/en/services/cyber-resilience){: external}
* [Zerto](https://www.zerto.com){: external}
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
