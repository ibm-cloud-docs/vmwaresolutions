---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Ordering vCenter Server instances

To deploy a flexible and customizable VMware virtualized platform that best fits your workload needs, order a VMware vCenter Server
instance. You can order an instance with or without the [Zerto disaster recovery](../vmonic/addingzertodr.html) service.

VMware vCenter Server on IBM® Cloud is a hosted private cloud that delivers the VMware vSphere stack as a service. The VMware environment
is built on top of a minimum of two Bluemix® bare metal servers, shared file-level storage, and includes the automatic deployment and
configuration of an easy-to-manage logical edge firewall that is powered by VMware NSX.

The entire environment can be provisioned in a matter of hours, and the elastic bare metal infrastructure can scale out the compute
capacity rapidly when needed.

Post-deployment, you can order and manually attach additional NFS (Network File System) file shares across hosts. If you purchased
IBM-provided VMware licensing, you can upgrade the VMware NSX Base Edition to Advanced Edition or Enterprise Edition, and you can purchase
additional VMware software, such as VMware vRealize Operations.

IBM Cloud Professional Services and Managed Services are also available to help you accelerate your journey to the cloud with offerings
like migration, implementation, and onboarding services.

## Before you begin

Ensure that you completed the following tasks:
*  You configured the SoftLayer® credentials on the Settings page. For more information, see [User accounts and settings](../vmonic
/useraccount.html).
*  You meet the requirements and you reviewed the considerations in [vCenter Server requirements](vc_planning.html).

When you order a vCenter Server instance, you must specify the following settings under **System**.

**Important: Do not modify any values that are set during ordering and instance deployment. Doing so can result in your instance becoming unusable.**

* **Instance Name**: The instance name must meet the following requirements:
  *  Only alphanumeric and dash (-) characters are allowed.
  *  The instance name must start and end with an alphanumeric character.
  *  The maximum length of the instance name is 10 characters.
* **Bare Metal Server Configuration**: You can select a bare metal server specification depending on your requirements:
  *  Small (Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz / 128 GB RAM / 2 disks)
  *  Medium (Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz / 256 GB RAM / 2 disks)
  *  Large (Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz / 512 GB RAM / 2 disks)

  For guidance on what option to choose, see the _Bill of Materials_ document in the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtVCenterServerPlatform){:new_window}.

* **Number of Bare Metal Servers**: You can configure the number of ESXi servers in the range 2 - 20. All ESXi servers share the same configuration.
* **Data Center Location**: You must select the IBM Cloud data center where the instance is to be hosted. Only the data centers that meet the bare metal server specification you selected previously are displayed.

You can also add file-level shared storage for your instance and specify the following settings under **Storage**:
*  **Number of File Shares**: specify the number of file shares for the shared storage that you want to add. The number of file shares
must be in the range 1 - 7.
*  **Size**: select the capacity that meets your shared storage needs.
*  **Performance**: select the IOPS (input/output operations per second) per GB based on your workload requirements. The performance
levels available to you depend on the data center that you select.

Table 1. Performance level options

| Option        | Details       |
  |:------------- |:------------- |
  | 2 IOPS/GB | This option is designed for most general-purpose workloads. Example applications include: hosting small databases, backing up web applications, or virtual machine disk images for a hypervisor. |
  | 4 IOPS/GB | This option is designed for higher-intensity workloads that have a high percentage of active data at a time. Example applications include: transactional databases. |
  | 10 IOPS/GB | This option is designed for the most demanding workload types, such as analytics. This performance level is limited to a maximum capacity of 4 TB per file share, and it is supported only for the IBM Cloud data centers AMS03, DAL10, FRA02, LON02, MEL01, MON01, OSL01, SJC03, SYD01, TOR01, and WDC04. Example applications include: high-transaction databases and other performance-sensitive databases.  |

*  **NFS Version**: Select the appropriate NFS (Network File System) version according to your needs. NFS v4.1 includes multiple paths to the shared NAS (Network Attached Storage) array, but does not support SDRS (Storage Distributed Resource Scheduler) or SIOC (Storage I/O Control). NFS v3 supports SDRS and SIOC, but does not include NFS multipathing.

## Procedure

1. Click **Order Instance** from the left navigation pane.
2. On the **vCenter Server** card, click **Order Instance**.
3. On the **Basics** page, provide the following information:
   1. Enter the instance name.
   2. Select the bare metal server specification.
   3. Specify the number of bare metal servers.
   4. Select the IBM Cloud data center to host the instance.
   5. Under **Storage**, configure the file-level shared storage by selecting the number, size, performance, and NFS version.
   6. Click **Next**.
4. On the **Add Service** page, complete one of the following steps:
   *  To deploy an additional service into your instance, click **Add Service** on the service card.
   *  To proceed without deploying additional services, click **Continue**.
5. On the **Summary** page, verify the instance configuration before you place the order.
   1. Review the settings for the instance.
   2. Click the link or links of the terms that apply to your order, and ensure that you agree with these terms before you order the
   instance.
   3. Review the estimated cost of the instance by clicking the price link under **Estimated Cost**. To save or print your order
   summary,
   click the **Print** or **Download** icon on the upper right of the PDF window.
   4. Click **Place Order**.

## Results

The deployment of the instance starts automatically. You receive confirmation that the order is being processed and you can check the
status of the deployment by viewing the instance details.

When the instance is successfully deployed, the components that are described in [vCenter Server components](../vcenter/vc_vcenterserveroverview.html#vcenter-server-components) are installed on your VMware virtual platform. The ESXi servers that you ordered are grouped as **cluster1** by default. If you ordered the Zerto disaster recovery service, the deployment of the service is started after your order is completed.

When the instance is ready to use, the status of the instance is changed to **Ready to Use** and you receive a notification by email.

## What to do next

View and manage the vCenter Server instance that you ordered.

**Important**: You must manage the {{site.data.keyword.vmwaresolutions_full}} components that are created in your SoftLayer account only
from the {{site.data.keyword.vmwaresolutions_short}} console, not the SoftLayer Customer Portal or any other means outside of the console.
If you change these components outside of the {{site.data.keyword.vmwaresolutions_short}} console, the changes are not synchronized with
the console.

**CAUTION**: Managing any {{site.data.keyword.vmwaresolutions_short}} components (which were installed into your SoftLayer account when you ordered the instance) from outside the {{site.data.keyword.vmwaresolutions_short}} console can make your environment unstable. These
management activities include:
*  Adding, modifying, returning, or removing components
*  Expanding or contracting instance capacity through adding or removing ESXi servers
*  Powering off components
*  Restarting services

## Related links

* [Signing up for a SoftLayer account](../vmonic/signing_softlayer_account.html)
* [Viewing vCenter Server instances](vc_viewinginstances.html)
* [Adding and viewing clusters for vCenter Server instances](vc_addingviewingclusters.html)
* [Expanding and contracting capacity for vCenter Server instances](vc_addingremovingservers.html)
* [Ordering, viewing, and removing services for vCenter Server instances](vc_addingremovingservices.html)
* [Deleting vCenter Server instances](vc_deletinginstance.html)
