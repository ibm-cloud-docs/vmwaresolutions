---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Deleting Cloud Foundation instances

To release the components that you ordered in a VMware Cloud Foundation instance, you can delete the instance. 

When you delete a Cloud Foundation instance, the following components are released sequentially:
1. Support and Services fee
2. VMware product licenses
3. ESXi servers
4. Subnets
5. VLANs

Because of resource dependencies, the components in your instance are not released immediately when you delete the instance. For example, the subnets and VLANs cannot be deleted until the ESXi servers are fully reclaimed by SoftLayer®, which happens at the end of the SoftLayer billing cycle. At the end of the SoftLayer billing cycle, which is typically 30 days, the subnets and VLANs are deleted and the instance deletion is completed.

**Attention**: You are billed until the end of the SoftLayer billing cycle for the deleted instance.

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Ensure that you are on the **Cloud Foundation** tab.
2. Locate the instance to delete.
3. In the **Actions** column, click the delete icon. The status of the instance is changed to **Deleting**.
4. When the instance is deleted successfully and its status is changed to **Deleted**, click the delete icon in the **Actions** column again.
5. In the **Delete Instance** window, click **OK** to remove the instance from the {{site.data.keyword.vmwaresolutions_short}} console.

## Related links

* [Ordering Cloud Foundation instances](sd_orderinginstance.html)
* [Viewing Cloud Foundation instances](sd_viewinginstances.html)
* [Expanding and contracting capacity for Cloud Foundation instances](sd_addingremovingservers.html)
* [Deleting multi-site configurations](sd_deletinginstance_multi.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
