---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-18"

---

# Ordering vCenter Server instances

To deploy a flexible and customizable VMware virtualized platform that best fits your workload needs, order a VMware vCenter Server
instance. You can order an instance with or without additional services, such as [Zerto on IBM Cloud](../vmonic/addingzertodr.html).

VMware vCenter Server on IBM® Cloud is a hosted private cloud that delivers the VMware vSphere stack as a service. The VMware environment is built on top of a minimum of two Bluemix® bare metal servers, shared file-level storage, and includes the automatic deployment and configuration of an easy-to-manage logical edge firewall that is powered by VMware NSX.

The entire environment can be provisioned in a matter of hours, and the elastic bare metal infrastructure can scale out the compute
capacity rapidly when needed.

Post-deployment, you can order and manually attach additional NFS (Network File System) file shares across hosts. If you purchased
IBM-provided VMware licensing, you can upgrade the VMware NSX Base Edition to Advanced Edition or Enterprise Edition, and you can purchase additional VMware software, such as VMware vRealize Operations.

IBM Cloud Professional Services and Managed Services are also available to help you accelerate your journey to the cloud with offerings
like migration, implementation, and onboarding services.

## Requirements

Ensure that you completed the following tasks:
*  You configured the SoftLayer® credentials on the Settings page. For more information, see [User accounts and settings](../vmonic/useraccount.html).
*  You meet the requirements and you reviewed the considerations in [vCenter Server requirements](vc_planning.html).

## System settings

When you order a vCenter Server instance, you must specify the following settings under **System**:

**Important: Do not modify any values that are set during ordering and instance deployment. Doing so can result in your instance becoming unusable.**

### Instance name

The instance name must meet the following requirements:
* Only alphanumeric and dash (-) characters are allowed.
* The instance name must start and end with an alphanumeric character.
* The maximum length of the instance name is 10 characters.

### Bare Metal Server configuration

You can select a bare metal server specification depending on your requirements:
* Small (Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz / 128 GB RAM / 2 disks)
* Medium (Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz / 256 GB RAM / 2 disks)
* Large (Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz / 512 GB RAM / 2 disks)
* User customized: you can specify the CPU model and RAM for the bare metal server.

  The following CPU Model options are available:
    * Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz
    * Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz
    * Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz

  The following RAM options are available:
    * 64 GB
    * 128 GB
    * 256 GB
    * 512 GB

For guidance on what bare metal server configuration to choose, see the _Bill of Materials_ document in the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtVCenterServerPlatform){:new_window}.

### Number of Bare Metal Servers

You can configure the number of ESXi servers in the range 2 - 20. All ESXi servers share the same configuration.

### Data center location

You must select the IBM Cloud data center where the instance is to be hosted. Only the data centers that meet the bare metal server specification you selected previously are displayed.

## Storage settings

You can also add file-level shared storage for your instance and specify the following settings under **Storage**:

### Number of File Shares

Specify the number of file shares for the shared storage that you want to add. The number of file shares must be in the range 1 - 32.

### Size

Select the capacity that meets your shared storage needs.

### Performance

Select the IOPS (Input/output Operations Per Second) per GB based on your workload requirements. The performance levels available to you depend on the data center that you select.

Table 1. Performance level options

| Option        | Details       |
  |:------------- |:------------- |
  | 2 IOPS/GB | This option is designed for most general-purpose workloads. Example applications include: hosting small databases, backing up web applications, or virtual machine disk images for a hypervisor. |
  | 4 IOPS/GB | This option is designed for higher-intensity workloads that have a high percentage of active data at a time. Example applications include: transactional databases. |
  | 10 IOPS/GB | This option is designed for the most demanding workload types, such as analytics. This performance level is limited to a maximum capacity of 4 TB per file share, and it is supported only for the IBM Cloud data centers DAL10, SJC03, and WDC04. Example applications include: high-transaction databases and other performance-sensitive databases.  |

### NFS version

Select the appropriate NFS (Network File System) version according to your needs. NFS v4.1 includes multiple paths to the shared NAS (Network Attached Storage) array, but does not support SDRS (Storage Distributed Resource Scheduler) or SIOC (Storage I/O Control). NFS v3 supports SDRS and SIOC, but does not include NFS multipathing.

## Services

When you order a vCenter Server instance, you can add the following services:
### Veeam on IBM Cloud

This service seamlessly integrates directly with your VMware hypervisors to help your enterprise achieve high availability. It can provide recovery points and time objectives of less than 15 minutes upon configuration for your applications and data.

This service is initially configured to back up the management virtual machines (VMs) immediately upon deployment for your instance. If you do not order this service, there is no backup of the management VMs. For more information, see [Managing Veeam on IBM Cloud](../vmonic/managingveeam.html).

When you order this service, you must configure the following settings for it:
* **Number of VMs to License**: select the number of VMs to license. A minimum of 4 VMs for licenses is required for management.
* **Storage Size**: select the capacity that meets your storage needs. A minimum of 2000 GB of storage is required for management. For considerations when estimating storage size, see [Estimating Repository Capacity](https://bp.veeam.expert/resource_planning/repository_planning_sizing.html).
* **Storage Performance**: select the IOPS (Input/output Operations Per Second) per GB based on your workload requirements.

### Fortinet on IBM Cloud

This service deploys an HA-pair of FortiGate Security Appliance (FSA) 300 series devices that can provide firewall, routing, NAT, and VPN services to protect the public network connection to your environment. For more information, see [Managing Fortinet on IBM Cloud](../vmonic/managingfsa.html).

### Zerto on IBM Cloud

This service provides replication and disaster recovery capabilities to help protect your workloads. For more information, see [Managing Zerto on IBM Cloud](../vmonic/managingzertodr.html).

## Procedure

1. Click **Getting Started** or **Order Instance** from the left navigation pane.
2. On the **vCenter Server** card, click **Order Instance**.
3. On the **Basics** page under **System**, provide the following information:
   1. Enter the instance name.
   2. Select the bare metal server configuration.
   3. If you selected **User customized** for the bare metal server configuration, specify the **CPU Model** and the amount of **RAM**.
   4. Specify the number of bare metal servers.
   5. Select the IBM Cloud data center to host the instance.
4. On the **Basics** page under **Storage**, configure the file-level shared storage by selecting the number, size, performance, and NFS version.
   6. Click **Next**.
5. On the **Add Service** page, complete one of the following steps:
   *  To deploy additional services into your instance, click **Select Service** on the service cards. If you selected the Veeam on IBM Cloud service, specify the number of VMs to license, storage size and performance in the **Configure Veeam** area. Click
   **Next**.
   *  To proceed without deploying any service, including the Veeam on IBM Cloud service, click **Selected Service** on the Veeam service card, and then click **Next**.
6. On the **Summary** page, verify the instance configuration before you place the order.
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

When the instance is successfully deployed, the components that are described in [vCenter Server instance components](../vcenter/vc_vcenterserveroverview.html#vcenter-server-components) are installed on your VMware virtual platform. The ESXi servers that you ordered are grouped as **cluster1** by default. If you ordered additional services, the deployment of the services is started after your order is completed.

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
