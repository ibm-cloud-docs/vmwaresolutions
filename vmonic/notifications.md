---

copyright:

  years:  2016, 2023

lastupdated: "2023-05-02"

keywords: notifications console, filter notifications, system notification

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Managing system notifications
{: #notifications}

You can check notifications for the status of system or user operations. You can also use the information to investigate problems that might occur.

## Viewing notifications
{: #notifications-view}

From the {{site.data.keyword.vmwaresolutions_full}} console, click **Notifications** from the left navigation pane to view a summary of all notifications. To view the details of a notification, click the notification row.

| Column | Description |
|:------ |:----------- |
| Severity | The severity of the event that is reported by the notification.  \n **Critical** - A critical event might impact the entire system or service.  \n **Error** - An error event occurs during an operation that might need intervention from the administrator or the user.  \n **Warning** - A component fails or is not working properly. However, the failure does not disrupt the ongoing process of the component.  \n **Informational** - A system or user operation is completed. Typically, the following events report informational notifications:  \n A service is installed.  \n A service is upgraded.  \n A service is removed.  \n All services are reconfigured for the added VMware ESXi™ servers.  \n All services are reconfigured for the removed ESXi servers. |
| Type | The type of component that the reported event is related to - VMware vCenter Server® instances, services, or system. |
| Resource | The name of the instance or service that sends the notification. |
| Title | The subject of the notification. |
| Creation time | The date and time when the notification is sent. |
{: caption="Table 1. Notification history" caption-side="bottom"}

## Filtering notifications
{: #notifications-filter}

By default, all unread notifications are displayed. You can filter the notifications by status, severity, and type. To filter the notifications, select the checkboxes only for the items that you want to display in the **Status**, **Severity**, or **Type** lists.

## Related links
{: #notifications-related}

* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [User account and settings](/docs/vmwaresolutions?topic=vmwaresolutions-useraccount)
