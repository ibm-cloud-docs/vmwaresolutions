---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-05"

---

# Ordering vCenter Server instances

To deploy a flexible and customizable VMware virtualized platform that best fits your workload needs, order a VMware vCenter Server
instance. During the initial order, you can also add services, such as [Zerto on IBM Cloud](../services/addingzertodr.html).

VMware vCenter Server on IBM® Cloud is a hosted private cloud that delivers the VMware vSphere stack as a service. The VMware environment is built on top of a minimum of three Bluemix® bare metal servers, shared file-level storage, and includes the automatic deployment and configuration of an easy-to-manage logical edge firewall that is powered by VMware NSX.

The entire environment can be provisioned in a matter of hours, and the elastic bare metal infrastructure can scale out the compute
capacity rapidly when needed.

Post-deployment, you can order additional NFS (Network File System) file shares from the IBM Bluemix Infrastructure (SoftLayer) portal and manually attach them across hosts. If you require dedicated storage, [NetApp ONTAP Select on IBM Cloud](../netapp/np_netappoverview.html) is offered in both high-performance (all SSD) and high-capacity (all SATA) configurations.

If you purchased IBM-provided VMware licensing, you can upgrade the VMware NSX Base edition to Advanced or to Enterprise edition, and you can purchase additional VMware components, such as VMware vRealize Operations.

IBM Cloud Professional Services and Managed Services are also available to help you accelerate your journey to the cloud with offerings
like migration, implementation, and onboarding services.

## Requirements

Ensure that you completed the following tasks:
*  You configured the IBM Bluemix Infrastructure (SoftLayer) credentials on the **Settings** page. For more information, see [User accounts and settings](../vmonic/useraccount.html).
*  You meet the requirements and you reviewed the considerations in [vCenter Server requirements](vc_planning.html).

## System settings

When you order a vCenter Server instance, you must specify the following settings under **System**:

**Important: Do not modify any values that are set during ordering and instance deployment. Doing so can result in your instance becoming unusable.**

### Domain name

The root domain name must meet the following requirements:
*  The name must consist of two or more strings that are separated by period (.)
*  Only alphanumeric and dash (-) characters are allowed.
*  Each string must start with an alphabetic character and end with an alphanumeric character, and the last string can contain only alphabetic characters.
*  The length of the last string must be in the range 2 - 24 characters.
*  The length of other strings must be in the range 1 - 63 characters.
*  The maximum length of the domain name is 189 characters.

### Instance name

The instance name must meet the following requirements:
* Only alphanumeric and dash (-) characters are allowed.
* The instance name must start and end with an alphanumeric character.
* The maximum length of the instance name is 10 characters.
* The instance name must be unique within your account.

### Instance and domain name format

The vCenter Server instance name and the root domain name use the format in the following table.

Table 1. Value format for instance and domain names

| Name        | Value Format      |
  |:------------- |:------------- |
  | Domain name | `rootdomain` |  
  | vCenter Server login user name | `userid@rootdomain` (Microsoft Active Directory user) or `administrator@vsphere.local` |
  | vCenter Server fully qualified domain name (FQDN) | `vcenter.instancename.rootdomain` |
  | Single Sign-On (SSO) site name | `instancename` |
  | Fully qualified ESXi host name | `hostn.instancename.rootdomain`, where n is the sequence of the ESXi server. The maximum length is 50 characters. |  
  | PSC fully qualified FQDN name | `psc-instancename.instancename.rootdomain`. The maximum length is 50 characters. |   

### Bare metal server configuration

You can select a bare metal server specification depending on your requirements:
* Small (Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz / 128 GB RAM / 2 disks)
* Medium (Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz / 256 GB RAM / 2 disks)
* Large (Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz / 512 GB RAM / 2 disks)
* User customized: you can specify the CPU model and RAM for the bare metal server.

Table 2. CPU and RAM options for the user-customized configuration

| Item          | Options       |
|:------------- |:------------- |
| CPU | <ul><li>Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz</li><li>Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz</li><li>Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz</li></ul>|
| RAM | 64 GB, 128 GB, 256 GB, 384 GB, 512 GB, 768 GB, 1.5 TB|

For guidance on what bare metal server configuration to choose, see the _Bill of Materials_ document in the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtVCenterServerPlatform){:new_window}.

### Number of bare metal servers

For the initial cluster in the instance, you can configure the number of ESXi servers in the range 2 - 20. All ESXi servers share the same configuration. Post-deployment, you can create up to four more clusters. For more information about minimum of ESXi servers, see [Is a two-node vCenter Server instance highly available?](../vmonic/faq.html#is-a-two-node-vcenter-server-instance-highly-available-)

### Data center location

You must select the IBM Cloud data center where the instance is to be hosted. Only the data centers that meet the bare metal server specification you selected previously are displayed.

## Storage settings

You can also add file-level shared storage for your instance and specify the following settings under **Storage**:

### Number of file shares

Specify the number of file shares for the shared storage that you want to add. The number of file shares must be in the range 1 - 32.

### Size

Select the capacity that meets your shared storage needs.

### Performance

Select the IOPS (Input/output Operations Per Second) per GB based on your workload requirements. The performance levels available to you depend on the data center that you select.

Table 3. Performance level options

| Option        | Details       |
  |:------------- |:------------- |
  | 2 IOPS/GB | This option is designed for most general-purpose workloads. Example applications include: hosting small databases, backing up web applications, or virtual machine disk images for a hypervisor. |
  | 4 IOPS/GB | This option is designed for higher-intensity workloads that have a high percentage of active data at a time. Example applications include: transactional databases. |
  | 10 IOPS/GB | This option is designed for the most demanding workload types, such as analytics. This performance level is limited to a maximum capacity of 4 TB per file share, and it is supported only for the IBM Cloud data centers DAL10, SJC03, and WDC04. Example applications include: high-transaction databases and other performance-sensitive databases.  |

<!--### NFS version

NFS (Network File System) v3 is set by default and you cannot change it. NFS v3 supports SDRS (Storage Distributed Resource Scheduler) and SIOC (Storage I/O Control), and it does not include NFS multipathing.-->

## Services

When you order a vCenter Server instance, you can also order additional services. For more information about the available services, see [Services for vCenter Server instances](vc_planning.html#services-for-vcenter-server-instances).

## Procedure

1. Click **Getting Started** or **Order Instance** from the left navigation pane.
2. On the **vCenter Server** card, click **Order Instance**.
3. On the **Basics** page under **System**, provide the following information:
   1. Enter the domain name.
   2. Enter the instance name.
   3. Select the bare metal server configuration.
   4. If you selected **User customized** for the bare metal server configuration, specify the **CPU Model** and the amount of **RAM**.
   5. Specify the number of bare metal servers.
   6. Select the IBM Cloud data center to host the instance.
4. On the **Basics** page under **Storage**, configure the file-level shared storage by selecting the number, size, and performance. Click **Next**.
5. On the **Add Service** page, complete the following steps:
   1. To deploy a service into your instance, click **Select Service** on the corresponding service card.
   2. If you accepted the default selection for Veeam on IBM Cloud, specify the following settings in the **Configure Veeam** area:
      * **Number of VMs to License**: A minimum of 4 VMs for licenses is required for management.
      * **Storage Size**: The capacity that meets your storage needs. A minimum of 2,000 GB of storage is required for management. For considerations when estimating storage size, see [Estimating Repository Capacity](https://bp.veeam.expert/resource_planning/repository_planning_sizing.html).
      * **Storage Performance**: The IOPS (Input/output Operations Per Second) per GB based on your workload requirements.
  3. If you want to install F5 on IBM Cloud, specify the following settings in the **Configure F5 on IBM Cloud** area:
     * **License Model**: Select **Good**, **Better**, or **Best** according to your requirements. For more information about what is provided for each license option, click **Learn More** on the **F5 on IBM Cloud** service card.
     * **Maximum Bandwidth**:  The maximum data transfer rate for the network connection.
  4. Select any other services that you want to install, or, to proceed without deploying any service, including Veeam on IBM Cloud, click **Selected Service** on the service card. Click **Next**.

6. On the **Summary** page, verify the instance configuration before you place the order.
   1. Review the settings for the instance.
   2. Click the link or links of the terms that apply to your order, and ensure that you agree with these terms before you order the
   instance.
   3. Review the estimated cost of the instance by clicking the price link under **Estimated Cost**. To save or print your order
   summary, click the **Print** or **Download** icon on the upper right of the PDF window.
   4. Click **Place Order**.

## Results

The deployment of the instance starts automatically. You receive confirmation that the order is being processed and you can check the
status of the deployment by viewing the instance details.

When the instance is successfully deployed, the components that are described in [vCenter Server instance components](../vcenter/vc_vcenterserveroverview.html#vcenter-server-components) are installed on your VMware virtual platform. The ESXi servers that you ordered are grouped as **cluster1** by default. If you ordered additional services, the deployment of the services is started after your order is completed.

When the instance is ready to use, the status of the instance is changed to **Ready to Use** and you receive a notification by email.

## What to do next

View and manage the vCenter Server instance that you ordered.

**Important**: You must manage the {{site.data.keyword.vmwaresolutions_full}} components that are created in your Bluemix Infrastructure (SoftLayer) account only
from the {{site.data.keyword.vmwaresolutions_short}} console, not the Bluemix Infrastructure (SoftLayer) portal or any other means outside of the console.
If you change these components outside of the {{site.data.keyword.vmwaresolutions_short}} console, the changes are not synchronized with
the console.

**CAUTION**: Managing any {{site.data.keyword.vmwaresolutions_short}} components (which were installed into your Bluemix Infrastructure (SoftLayer) account when you ordered the instance) from outside the {{site.data.keyword.vmwaresolutions_short}} console can make your environment unstable. These management activities include:
*  Adding, modifying, returning, or removing components
*  Expanding or contracting instance capacity through adding or removing ESXi servers
*  Powering off components
*  Restarting services

   Exceptions to these activities include managing the shared storage file shares from the Bluemix Infrastructure (SoftLayer) portal. Such activities include: ordering, deleting (which might impact data stores if mounted), authorizing, and mounting shared storage file shares.

## Related links

* [Signing up for an IBM Bluemix Infrastructure (SoftLayer) account](../vmonic/signing_softlayer_account.html)
* [Viewing vCenter Server instances](vc_viewinginstances.html)
* [Adding and viewing clusters for vCenter Server instances](vc_addingviewingclusters.html)
* [Expanding and contracting capacity for vCenter Server instances](vc_addingremovingservers.html)
* [Ordering and removing services for vCenter Server instances](vc_addingremovingservices.html)
* [Deleting vCenter Server instances](vc_deletinginstance.html)
