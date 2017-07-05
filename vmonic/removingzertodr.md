---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Removal process of Zerto disaster recovery

The removal process of Zerto disaster recovery is automated. The following steps are completed for the successful removal of the Zerto disaster recovery service.

## Procedure

1. Click **Deployed Instances** from the left navigation pane and click the instance from which you want to remove the service.
2. Click the **Services** tab.
3. On the **Installed Services** tab, click **Delete Service** on the **Zerto disaster recovery** card.
4. The service status changes to **Removing** and the following removal steps are completed:   
   1. Remove the Zerto Virtual Replication Appliances that were deployed to all ESXi servers.
   2. Uninstall Zerto Virtual Replication.
   3. Delete the Windows VSI (Virtual Service Instance) on which Zerto Virtual Replication was installed.
   4. Return the private portable subnet that was ordered for Zerto Virtual Replication communication to SoftLayer®.   
   5. Remove the charges of the Zerto disaster recovery service from your IBM Bluemix® billing statement. 
     **Note**: You are billed until the end of the billing cycle for the removed Zerto disaster recovery service.
     
## Results

After the service removal is completed successfully, you are notified by email and the service entry is deleted from the **Installed Services** tab.

## Related links

* [Zerto disaster recovery deployment](addingzertodr.html)
* [Managing Zerto disaster recovery](managingzertodr.html)
* [Cloud Foundation instances](../sddc/sd_cloudfoundationoverview.html)
* [vCenter Server instances](../vcenter/vc_vcenterserveroverview.html)
* [zerto.com website](https://www.zerto.com){:new_window}
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){:new_window}
