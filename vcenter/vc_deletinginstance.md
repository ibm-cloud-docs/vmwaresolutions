---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Deleting vCenter Server instances

To release the components that you ordered in a VMware vCenter Server instance, delete the instance.

When you delete a vCenter Server instance, only the ESXi servers are released.

Because of resource dependencies, the components in your instance are not released immediately when you delete the instance. For example, the subnets and VLANs cannot be deleted until the ESXi servers are fully reclaimed by SoftLayer®, which happens at the end of the SoftLayer 
billing cycle. At the end of the SoftLayer billing cycle, which is typically 30 days, the subnets and VLANsare deleted and the instance 
deletion is completed.

**Attention:** You are billed until the end of the SoftLayer billing cycle for the deleted instance.

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Click the **vCenter Server** tab.
2. Locate the instance to delete.
3. In the **Actions** column, click the delete icon. The status of the instance is changed to **Deleting**.
4. When the instance is deleted successfully and its status is changed to **Deleted**, click the delete icon in the **Actions** column again.
5. In the **Delete Instance** window, click **OK** to remove the instance from the {{site.data.keyword.vmwaresolutions_short}} console.

## Related links

* [Ordering vCenter Server instances](vc_orderinginstance.html)
* [Viewing vCenter Server instances](vc_viewinginstances.html)
* [Expanding and contracting capacity for vCenter Server instances](vc_addingremovingservers.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
