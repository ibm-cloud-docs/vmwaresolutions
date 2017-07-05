---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Ordering, viewing, and removing services for vCenter Server instances

You can order additional services for your VMware vCenter Server instances, such as a disaster recovery solution. When you no longer need these services, you can remove them from your instances.

You can order the Zerto disaster recovery service for your VMware vCenter Server instances, which provides replication and disaster
recovery capabilities to help protect your workloads. For more information, see [Zerto disaster recovery deployment](../vmonic/addingzertodr.html) and [Zerto disaster recovery removal](../vmonic/removingzertodr.html).

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Click the **vCenter Server** tab.
2. Click the instance on which you want to install a service, or from which you want to remove a service.
3. Click the **Services** tab.
4. To install a service, complete the following steps:
   1. On the **Available Services** tab, find the service that you want to install and click **Add Service** on the service card.
   2. In the **Your Order Summary** window, click the link of the terms that apply to the service, and ensure that you agree with the terms before you install the service.
   3. Review the estimated cost of the service by clicking the price link under **Estimated Cost of Service**.
   4. Click **Place Order**. After your request to install the service is accepted, the service status is changed to **Installing**.
5. To view details about a service, complete the following steps:
   1. On the **Installed Services** tab, find the service that you want to view details for and click **View Details** on the service card.
   2. Review the information about the selected service, such as the current version of the service, the service status, and so on.
   3. To log in to the Zerto console with your vCenter credentials to manage the Zerto disaster recovery service, click **View Zerto Console**.
6. To remove a service, complete the following steps:
   1. On the **Installed Services** tab, find the service that you want to remove.
   2. Click the overflow menu icon in the upper right of the service card, and then click **Remove Service**.
   3. In the **Remove Service** window, click **I Understand**. After your request for service removal is accepted, the service status is changed to **Removing**.

## Results

When the installation of the service is completed successfully, you are notified by email, and the service is displayed on the **Installed Services** tab with the **Installed** status.

When the removal of the service is completed successfully, you are notified by email, and the service is removed from the **Installed Services** tab.

**Attention**: You are billed until the end of the SoftLayer® billing cycle for the removed services.

## Related links

* [Zerto disaster recovery](../vmonic/addingzertodr.html)
* [Ordering vCenter Server instances](vc_orderinginstance.html)
