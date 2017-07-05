---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-30"

---

# Ordering Cloud Foundation instances

If you want to deploy a unified software-defined data center (SDDC) platform with standard compute, storage, and network configuration, order a VMware Cloud Foundation instance. You can order an instance with or without the [Zerto disaster recovery](../vmonic/addingzertodr.html) service.

When you order a VMware Cloud Foundation instance, an entire VMware environment is deployed automatically. The base deployment consists of four IBM® Cloud bare metal servers with the VMware Cloud Foundation stack preinstalled and configured to provide a unified software-defined data center (SDDC) platform. Cloud Foundation natively integrates VMware vSphere, VMware NSX, VMware Virtual SAN, and is architected based on VMware Validated Designs.

## Before you begin

Ensure that you completed the following tasks:

*  You configured the SoftLayer® credentials on the **Settings** page. For more information, see [User accounts and settings](../vmonic/useraccount.html).
*  You meet the requirements and you reviewed the considerations in [Cloud Foundation requirements](sd_planning.html).

When you order a Cloud Foundation instance, you must specify the following settings.

**Important: Do not modify any values that are set during ordering and instance deployment. Doing so can result in your instance becoming unusable. In addition, do not change the instance name or the domain name after the instance is deployed.**

* **Instance type**: You can deploy the instance as a primary (single) instance in your environment, or deploy the instance in a multi-site configuration by linking it with an existing primary instance for high availability. For more information, see [Multi-site configuration for Cloud Foundation instances](sd_multisite.html).
* **Domain name**: The root domain name must meet the following requirements:
   *  The name must consist of two or more strings that are separated by period (.)
   *  Only alphanumeric and dash (-) characters are allowed.
   *  Each string must start with an alphabetic character and end with an alphanumeric character, and the last string can contain only
   alphabetic characters.
   *  The length of the last string must be in the range 2 - 24 characters.
   *  The length of other strings must be in the range 1 - 63 characters.
   *  The maximum length of the domain name is 189 characters.
* **Instance name**: The instance name must meet the following requirements:
   *  Only alphanumeric and dash (-) characters are allowed.
   *  The instance name must start and end with an alphanumeric character.
   *  The maximum length of the instance name is 10 characters.
   *  The instance name must be unique within your account.

  The Cloud Foundation instance name and the root domain name use the format in the following table.

  Table 1. Value format for instance and domain names

| Name        | Value Format      |
  |:------------- |:------------- |
  | Single Sign-On (SSO) site name | `instancename` |
  | vCenter Server login user name | `userid@rootdomain` (Active Directory user) or `administrator@vsphere.local` |
  | Domain name | `rootdomain` |  
  | Platform Services Controller (PSC) host name | `PSC-instancename` or `PSC-instancename.rootdomain`. The maximum length is 50 characters. |  
  | vCenter Server fully qualified domain name (FQDN) | `vcenter-1.instancename.rootdomain` |  
  | SDDC Manager FQDN name | `sddcmanager.instancename.rootdomain`. The maximum length is 50 characters. |
  | Fully qualified ESXi host name | `hostn.instancename.rootdomain`, where n is the sequence of the ESXi server. The maximum length is 50 characters. |  
  | PSC fully qualified FQDN name | `psc-instancename.instancename.rootdomain`. The maximum length is 50 characters. |   

  The SDDC Manager FQDN cannot be publicly resolvable. Otherwise, the Cloud Foundation instance configuration fails and is not recoverable.
  Before you specify a domain name, review the [Considerations while choosing a root domain name](../vmonic/trbl_limitations.html#considerations-when-choosing-a-root-domain-name-for-cloud-foundation-instances).

* **Bare Metal Server Configuration**: You can select a bare metal server specification depending on your requirements:
  *  Standard (Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz / 256 GB RAM / 12 disks)
  *  Small (Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz / 128 GB RAM / 12 disks)

  For guidance on what option to choose, see the _Bill of Materials_ document in the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtCloudFoundationPlatform){:new_window}.

* **Data center location**: You must select the IBM Cloud data center where the instance is to be hosted. Only the data centers that meet the bare metal server specification are displayed.

## Procedure

1. Click **Order Instance** from the left navigation pane.
2. On the **Cloud Foundation** card, click **Order Instance**.
3. On the **Order a Cloud Foundation instance** page, select the instance type:
   *  To deploy a single instance in the environment or to deploy the first instance in a multi-site topology, click **Primary**.
   *  To connect the instance with an existing (primary) instance in the environment for high availability, click **Secondary**.
4. If you selected the **Primary** instance type, provide the following information on the **Basics** page:
   1. Enter the root domain name.
   2. Enter the instance name.
   3. Select the bare metal server specification.
   4. Select the IBM Cloud data center to host the instance.
   5. Click **Next**.
5. If you selected the **Secondary** instance type, provide the following information on the **Basics** page:
   1. Select the primary site that you want the instance to be connected with.
   2. Review the root domain name that is automatically filled in.
   3. Enter the instance name.
   4. Select the bare metal server specification.
   5. Select the IBM Cloud data center to host the instance.
   6. Click **Next**.
6. If you selected the **Secondary** instance type, review the following information on the **Primary instance authentication** page:
   1. In the **Primary Instance PSC Administrator Password** field, the Platform Services Controller (PSC) password of the selected primary instance is automatically filled in.
   2. Click **Next** to validate the password.
   3. If the password validation fails, enter the correct PSC password, and click **Next** again.
7. On the **Add Service** page, complete one of the following steps:
   *  To deploy an additional service into your instance, click **Add Service** on the service card.
   *  To proceed without deploying additional services, click **Continue**.
8. On the **Summary** page, verify the instance configuration before you place the order.
   1. Review the settings for the instance.
   2. Click the link or links of the terms that apply to your order, and ensure that you agree with these terms before you order the
   instance.
   3. Review the estimated cost of the instance by clicking the price link under **Estimated Cost**. To save or print your order summary,
   click the **Print** or **Download** icon on the upper right of the PDF window.
   4. Click **Place Order**.

## Results

The deployment of the instance starts automatically. You receive confirmation that the order is being processed and you can check the status of the deployment by viewing the instance details.

When the instance is successfully deployed, the components that are described in [Cloud Foundation components](../sddc/sd_cloudfoundationoverview.html#cloud-foundation-components) are installed on your VMware virtual platform. If you ordered the Zerto disaster recovery service, the deployment of the service is started after your  order is completed.

When the instance is ready to use, the status of the instance is changed to **Ready to Use** and you receive a notification by email.

## What to do next

View and manage the Cloud Foundation instance that you ordered.

**Important**: You must manage the {{site.data.keyword.vmwaresolutions_full}} components that are created in your SoftLayer account only from the {{site.data.keyword.vmwaresolutions_short}} console, not the SoftLayer Customer Portal or any other means outside of the console. If you change these components outside of the {{site.data.keyword.vmwaresolutions_short}} console, the changes are not synchronized with the console.

**CAUTION**: Managing any {{site.data.keyword.vmwaresolutions_short}} components (which were installed into your SoftLayer account when you ordered the instance) from outside the {{site.data.keyword.vmwaresolutions_short}} console can make your environment unstable. These management activities include:

*  Adding, modifying, returning, or removing components
*  Expanding or contracting instance capacity through adding or removing ESXi servers
*  Powering off components
*  Restarting services

## Related links

* [Signing up for a SoftLayer account](../vmonic/signing_softlayer_account.html)
* [Viewing Cloud Foundation instances](sd_viewinginstances.html)
* [Expanding and contracting capacity for Cloud Foundation instances](sd_addingremovingservers.html)
* [Ordering and removing services for Cloud Foundation instances](sd_addingremovingservices.html)
* [Deleting Cloud Foundation instances](sd_deletinginstance.html)
