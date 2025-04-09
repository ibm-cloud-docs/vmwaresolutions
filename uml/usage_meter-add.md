---

copyright:

  years:  2025

lastupdated: "2025-04-09"

keywords: usage meter, adding products

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Adding VMware products to Usage Meter 
{: #usage_meter-add}

To add various VMware products to Usage Meter, complete the following procedures from the VMware vCloud Usage Meter web interface.

## Adding vCenter Server to Usage Meter 
{: #usage_meter-add-vcenter}

To add vCenter Server to Usage Meter, complete the following steps:

1. Under **Products**, select **vCenter/Cloud Foundation** and click **Add**.
2. Enter the following information:
   * **Endpoint**: The IP address or the hostname (recommended in case of IP address reassignment) of the vCenter Server virtual machine (VM). The port number is 443.
   * **Username**: A vCenter Server username with administrator privileges.
   * **Password**: The user password.
   * If you have an external PSC, select the **Use External Platform Services Controller (PSC)** checkbox.
   * **PSC Endpoint**: The external PSC IP address or hostname. The port number is 7444.
   * Leave the default values for all other fields.

3. Click **Add**. The endpoint is displayed in the vCenter/Cloud Foundation table with a status of **Please accept certificate**.
4. Click the status, accept the certificate, and verify that the status changes to **OK**.

## Adding NSX to Usage Meter 
{: #usage_meter-add-nsx}

To add VMware NSX to Usage Meter, complete the following steps:

1. Under **Products**, select **NSX-T** if you have VMware NSX-T or **NSX-V** if you have VMware NSX-V. NSX-T is a separate UI, while NSX-V is typically accessed within vCenter Server.
2. Click **Add** and enter the following information:
   * **Endpoint**: The IP address or the hostname (recommended in case of IP address reassignment) of the vCenter Server VM. The port number is 443.
   * **Username**: A vCenter Server username with administrator privileges.
   * **Password**: The user password.

3. Click **Add**. The endpoint is displayed in the NSX-T or NSX-V table, respectively, with a status of **Please accept certificate**.
4. Click the status, accept the certificate, and verify that the status changes to **OK**.

## Adding Aria Operations to Usage Meter 
{: #usage_meter-add-aria}

To add VMware Aria Operations to Usage Meter, complete the following steps:

1. Under **Products**, select **Aria Operations** and click **Add**.
2. Enter the following information:
   * **Endpoint**: The IP address or the hostname (recommended in case of IP address reassignment) of the vCenter Server VM. The port number is 443.
   * **Username**: A vCenter username with administrator privileges.
   * **Password**: The user password.

3. Click **Add**. The endpoint is displayed in the Aria Operations table with a status of **Please accept certificate**.
4. Click the status, accept the certificate, and verify that the status changes to **OK**.

## Adding other VMware products to Usage Meter 
{: #usage_meter-add-other}

Use the previous procedures to add the following products to Usage Meter:
* Horizon DaaS (Desktop as a Service)
* Tanzu Kubernetes Grid Multi-Cloud
* VMware Aria® Automation™
* VMware Aria Operations™ for Networks
* VMware Aria Suite Lifecycle
* VMware Avi Load Balancer (formerly NSX Advanced Load Balancer)
* VMware Cloud Director™
* VMware Cloud Director Availability (VCDA)
* VMware Horizon®
* vRealize Automation 7 (legacy) - applicable only for environments with vRealize 7 and that do not have Aria.

## Related links
{: #usage_meter-add-related}

* [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy)
* [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config)
* [Registering Usage Meter with IBM](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register)
