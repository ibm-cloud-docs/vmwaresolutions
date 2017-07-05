---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-29"

---

# Managing user accounts and settings

{{site.data.keyword.vmwaresolutions_full}} communicates with the SoftLayer® infrastructure through API calls. To access the SoftLayer API securely, you must associate the credentials of your SoftLayer user account to your {{site.data.keyword.vmwaresolutions_short}} user account. You can also specify whether you want to receive email notifications for instance updates.

## Before you begin

* You can associate only one SoftLayer user account to your {{site.data.keyword.vmwaresolutions_short}} user account.
* The SoftLayer account that you are using must meet certain requirements. For more information, see [SoftLayer account requirements](slaccountrequirement.html).
* If the API key from your SoftLayer account changes, you must update the key in your {{site.data.keyword.vmwaresolutions_short}} user account.

   **Important**: It is your responsibility to ensure that the API key that is saved on the Settings page is correct and up-to-date. 
   Otherwise, operations that require API key validation might fail.

To associate the {{site.data.keyword.vmwaresolutions_short}} account with the SoftLayer user account, enter the SoftLayer credentials in the {{site.data.keyword.vmwaresolutions_short}} console.

After you associate the SoftLayer account, the console automatically retrieves the SoftLayer credentials to communicate with your VMware environment on IBM Cloud.

## Procedure

1. Click **Settings** from the left navigation pane.
2. If you want to be notified by email when the following events occur, select one or more check boxes under **Notifications**:
   * A new instance deployment is completed successfully.
   * An instance is deleted successfully.
   * ESXi servers are added or removed successfully.
   * An instance service is installed or removed successfully.
3. If you want to be notified on the console when events occur in the following areas, select one or more check boxes under **Notifications**:
   * Cloud Foundation instances
   * vCenter Server instances
   * Services
   * System
4. In the **SoftLayer Credentials** area, enter the user name of your SoftLayer account, and then follow the instructions on the console 
to enter the SoftLayer API key.
5. Click **Save Credentials**.

## Results

The stored SoftLayer credentials are used in future operations that require interaction with SoftLayer. If email or console notifications are enabled for certain instance events, you are notified by email or console messages when these events occur.

## Related links

* [FAQ](faq.html)
* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)
* [Notifications](notifications.html)
* [SoftLayer Development/API](http://knowledgelayer.softlayer.com/topic/developmentapi){:new_window}
