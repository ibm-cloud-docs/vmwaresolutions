---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-11"

---

# Ordering, viewing, and removing services for vCenter Server instances

You can order additional services for your VMware vCenter Server instances, such as a disaster recovery solution. When you no longer need these services, you can remove them from your instances.

## Before you begin

The following services are available to vCenter Server instances:
* **Veeam on IBM® Cloud**: this service seamlessly integrates directly with your VMware hypervisors to help your enterprise achieve high availability. It can provide recovery points and time objectives of less than 15 minutes upon configuration for your applications and data. When you order this service, you must configure the following settings for it:
   * **Number of VMs to License**: select the number of VMs to license. A minimum of 4 VMs for licenses is required for management.
   * **Storage Size**: select the capacity that meets your storage needs. A minimum of 2000 GB of storage is required for management.
   For considerations when estimating storage size, see [Estimating Repository Capacity](https://bp.veeam.expert/resource_planning/repository_planning_sizing.html).
    * **Storage Performance**: select the IOPS (Input/output Operations Per Second) per GB based on your workload requirements.

  This service is initially configured to back up the management virtual machines (VMs) immediately upon deployment for your instance. If you do not order this service, there is no backup of the management VMs. For more information, see [Managing Veeam on IBM Cloud](../vmonic/managingveeam.html).
* **Fortinet on IBM Cloud**: this service deploys an HA-pair of FortiGate Security Appliance (FSA) 300 series devices that can provide firewall, routing, NAT, and VPN services to protect the public network connection to your environment. For more information, see [Managing Fortinet on IBM Cloud](../vmonic/managingfsa.html).
* **Zerto on IBM Cloud**: this service provides replication and disaster recovery capabilities to help protect your workloads. For more information, see [Managing Zerto on IBM Cloud](../vmonic/managingzertodr.html).

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Click the **vCenter Server** tab.
2. Click the instance on which you want to install services, or from which you want to remove services.
3. Click the **Services** tab.
4. To install services, complete the following steps:
   1. On the **Add Services** tab, find the services that you want to install and click **Select Service** on the service cards.
   2. If you selected the Veeam on IBM Cloud service, specify the number of VMs to license, storage size and performance in the **Configure Veeam** area.
   3. Click **Install**.
   4. In the **Order Summary** window, click the link or links of the terms that apply to the services, and ensure that you agree with the terms before you install the services.
   5. Review the estimated cost of the services by clicking the price link under **Estimated Cost**.
   6. Click **Place Order**. After your request to install the services is accepted, the status of the services is changed to **Installing**.
5. To view details about a service, complete the following steps:
   1. On the **Installed Services** tab, find the service that you want to view details for and click **View Details** on the service
   card.
   2. Review the information about the selected service, such as the service status and so on.
   3. If you are viewing the details of the Veeam on IBM Cloud service, you can access the Veeam console with the credentials provided on this page by using Remote Desktop Protocol (RDP). For more information, see the _Accessing the Veeam console by using RDP_ section in [Managing Veeam on IBM Cloud](../vmonic/managingveeam.html).
   4. If you are viewing the details of the Fortinet on IBM Cloud service, you can log in to the FortiGate 300 series console with the credentials provided on this page to manage the service by clicking **View FortiGate Console**.
   5. If you are viewing the details of the Zerto on IBM Cloud service, you can log in to the Zerto console with your vCenter
   credentials to manage the service by clicking **View Zerto Console**.
6. To remove a service, complete the following steps:
   1. On the **Installed Services** tab, find the service that you want to remove.
   2. Click the overflow menu icon in the upper right of the service card, and then click **Remove Service**.
   3. In the **Remove Service** window, review the considerations or warnings if there are any. Click **I Understand**. After your
   request for service removal is accepted, the service status is changed to **Removing**.

## Results

When the installation of the service is completed successfully, you are notified by email, and the service is displayed on the **Installed Services** tab with the **Installed** status.

**Important**: After the Fortinet on IBM Cloud service is installed successfully, you can manage and configure firewall
rules for the FSA from the FortiGate console. You must ensure that the FSA firewall rules are defined to allow outbound HTTPS (TCP port 443) communications that are initiated by management components such as the IBM CloudDriver virtual machine or Zerto Virtual Manager to
communicate with the external management database on IBM Bluemix over the Internet. The outbound HTTPS (TCP port 443) communications originate from the public IP address of the management services VMware NSX Edge Services Gateway (ESG) in your instance.

When the removal of the service is completed successfully, you are notified by email, and the service is removed from the **Installed Services** tab.

**Attention**: You are billed until the end of the SoftLayer® billing cycle for the removed services.

## Related links

* [Ordering vCenter Server instances](vc_orderinginstance.html)
* [FAQ](../vmonic/faq.html)
