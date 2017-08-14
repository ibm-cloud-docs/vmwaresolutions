---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-08"

---

# Deleting vCenter Server instances

To release the components that you ordered in a VMware vCenter Server instance, delete the instance.

When you delete a vCenter Server instance, the following components are released sequentially:
1. All deployed services
2. Support and Services fee
3. VMware product licenses
4. ESXi servers
5. Subnets
6. VLANs

Because of resource dependencies, the components in your instance are not released immediately when you delete the instance. For example, the subnets and VLANs cannot be deleted until the ESXi servers are fully reclaimed by SoftLayer®, which happens at the end of the SoftLayer 
billing cycle. At the end of the SoftLayer billing cycle, which is typically 30 days, the subnets and VLANsare deleted and the instance 
deletion is completed.

**Attention:** You are billed until the end of the SoftLayer billing cycle for the deleted instance.

## Procedure

To delete a vCenter Server instance on the **Deployed Instances** page, use the following procedure:
   1. Click **Deployed Instances** from the left navigation pane. Ensure that you are on the **vCenter Server** tab.
   2. Locate the instance to delete.
   3. In the **Actions** column, click the delete icon. The status of the instance is changed to **Deleting**.
   4. When the instance is deleted successfully and its status is changed to **Deleted**, click the delete icon in the **Actions** 
   column again.
   5. In the **Delete Instance** window, click **OK** to remove the instance from the {{site.data.keyword.vmwaresolutions_short}} 
   console.

To delete a vCenter Server instance on the instance details page, use the following procedure:
   1. Click **Deployed Instances** from the left navigation pane. Ensure that you are on the **vCenter Server** tab.
   2. Click the instance to delete.
   3. Click the overflow menu icon to the right of **vCenter console**.
   4. Click **Delete Instance**.

## Related links

* [Ordering vCenter Server instances](vc_orderinginstance.html)
* [Viewing vCenter Server instances](vc_viewinginstances.html)
* [Expanding and contracting capacity for vCenter Server instances](vc_addingremovingservers.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
