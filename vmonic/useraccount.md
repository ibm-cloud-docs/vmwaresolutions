---

copyright:

  years:  2016, 2017

lastupdated: "2017-09-28"

---

# Managing user accounts and settings

{{site.data.keyword.vmwaresolutions_full}} communicates with the IBM Bluemix Infrastructure (SoftLayer) through API calls. To access the Bluemix Infrastructure (SoftLayer) API securely, you must associate the credentials of your Bluemix Infrastructure (SoftLayer) user account to your {{site.data.keyword.vmwaresolutions_short}} user account. You can also specify whether you want to receive email notifications for instance updates.

## Before you begin

* You can associate only one Bluemix Infrastructure user account to your {{site.data.keyword.vmwaresolutions_short}} user account.
* The Bluemix Infrastructure account that you are using must meet certain requirements. For more information, see [Bluemix Infrastructure (SoftLayer) account requirements](slaccountrequirement.html).
* If the API key from your Bluemix Infrastructure account changes, you must update the key in your {{site.data.keyword.vmwaresolutions_short}} user account.

   **Important**: It is your responsibility to ensure that the API key that is saved on the **Settings** page is correct and up-to-date.
   Otherwise, operations that require API key validation might fail.

To associate the {{site.data.keyword.vmwaresolutions_short}} account with the Bluemix Infrastructure user account, enter the Bluemix Infrastructure (SoftLayer) credentials in the {{site.data.keyword.vmwaresolutions_short}} console.

After you associate the Bluemix Infrastructure account, the console automatically retrieves the Bluemix Infrastructure (SoftLayer) credentials to communicate with your VMware environment on IBM Cloud.

## Procedure

1. Click **Settings** from the left navigation pane.
2. If you want to be notified by email when events occur, select the **Enable email notifications** check box.
3. If you want to be notified on the console when events occur, select the **Enable console notifications** check box.
4. In the **Bluemix Infrastructure (SoftLayer) Credentials** area, enter the user name of your Bluemix Infrastructure account, and then follow the instructions on the console to enter the Bluemix Infrastructure API key.
5. Click **Save Credentials**.

## Results

The stored Bluemix Infrastructure credentials are used in future operations that require interaction with Bluemix Infrastructure (SoftLayer). If email or console notifications are enabled for certain instance events, you are notified by email or console messages when these events occur.

## Related links

* [FAQ](faq.html)
* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)
* [Notifications](notifications.html)
* [SoftLayer Development/API](http://knowledgelayer.softlayer.com/topic/developmentapi){:new_window}
