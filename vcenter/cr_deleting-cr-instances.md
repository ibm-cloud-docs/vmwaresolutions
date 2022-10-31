---

copyright:

  years:  2022

lastupdated: "2022-10-21"

keywords: Cyber Recovery delete instance, delete Cyber Recovery, remove Cyber Recovery

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Deleting Cyber Recovery instances
{: #cr_deletinginstance}

To release the components that you ordered in a Cyber Recovery instance, delete the instance.

{{site.data.content.deletinginstance-components-list}}

{{site.data.content.deletinginstance-delete-vlans}}

{{site.data.content.deletinginstance-delete-info}}

{{site.data.content.deletinginstance-important-note}}

The instance remains in **Deleting** status and the monthly ESXi servers are available for the remainder of the account monthly billing cycle. After the billing cycle ends, the status of the device changes from **ACTIVE** to **RECLAIM** until the reclaim process completes which can take days or weeks into the following month.

After the ESXi server reclaim process completes, the subnets and VLANs are deleted and the instance deletion is completed.

You can review the next account invoice to confirm that you are no longer billed for this instance. From the {{site.data.keyword.cloud_notm}} console, click **Manage > Billing and usage**, then click **Invoices**.

## Procedure to delete Cyber Recovery instances from the Resources page
{: #cr_deletinginstance-procedure1}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources > Cyber Recovery** from the left navigation pane.
2. In the **Cyber Recovery instances** table, find the instance to delete.
3. Click the vertical overflow menu next to the **Status** column, and then click **Delete instance**.
   The status of the instance is changed to **Deleting**. When the instance is deleted successfully, the components of the instance are released, and the status of the instance is changed to **Deleted**.
4. If you want to delete the instance record from the {{site.data.keyword.vmwaresolutions_short}} console, complete the following steps:
   1. Click the vertical overflow menu next to the **Status** column, and then click **Delete from the console**.
   2. In the **Delete instance** window, click **Delete**.

## Procedure to delete Cyber Recovery instances from the instance details page
{: #cr_deletinginstance-procedure2}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources > Cyber Recovery** from the left navigation pane.
2. In the **Cyber Recovery instances** table, click the instance to delete.
3. Click **Actions** next to **vCenter console**, and then click **Delete instance**.
   The status of the instance is changed to **Deleting**. When the instance is deleted successfully, the components of the instance are released, and the status of the instance is changed to **Deleted**.
4. If you want to delete the instance record from the {{site.data.keyword.vmwaresolutions_short}} console, complete the following steps:
   1. Click **Actions** again and then click **Delete from the console**.
   2. In the **Delete instance** window, click **Delete**.

## Related links
{: #cr_deletinginstance-related}

* [Ordering Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance_reqs)
* [Viewing Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_viewinginstances)
* [Managing virtual servers](/docs/virtual-servers?topic=virtual-servers-managing-virtual-servers)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
