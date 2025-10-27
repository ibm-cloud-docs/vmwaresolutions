---

copyright:

  years:  2025

lastupdated: "2025-10-24"

keywords: usage meter, adding products, vmware products usage meter, add nsx usage meter, add vcenter usage meter, add aria operations usage meter

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Adding VMware products to Usage Meter 
{: #usage_meter-add}

{{site.data.content.vms-deprecated-note}}

To add various VMware products to Usage Meter, complete the following procedures from the VMware vCloud Usage Meter web interface.

## Adding vCenter Server to Usage Meter 
{: #usage_meter-add-vcenter}

To add vCenter Server to Usage Meter, complete the following steps:

1. Under **Products**, select **vCenter/Cloud Foundation** and click **Add**.
2. Enter the following information:
   * **Endpoint**: The IP address or the hostname (recommended if the IP address was reassigned) of the vCenter Server virtual machine (VM). The port number is 443.
   * **Username**: A vCenter Server username with administrator privileges.
   * **Password**: The user password.
   * If you have an external PSC, select the **Use External Platform Services Controller (PSC)** checkbox.
   * **PSC Endpoint**: The external PSC IP address or hostname. The port number is 7444.
   * Keep default values for all the other fields.

3. Click **Add**. The endpoint is displayed in the vCenter/Cloud Foundation table with a status of **Please accept certificate**.
4. Click the status, accept the certificate, and verify that the status changes to **OK**.

## Adding NSX to Usage Meter 
{: #usage_meter-add-nsx}

To add VMware NSX to Usage Meter, complete the following steps:

1. Under **Products**, select **NSX-T**. Click **Add** and enter the following information:
   * **Endpoint**: The IP address or the hostname (recommended if the IP address was reassigned) of the NSX-T Manager instance. The port number is 443. For more information, see [Add an NSX-T Data Center Instance for Metering in vCloud Usage Meter](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/vcloud-usage-meter-4-8-deployment-and-administration-guide-4-8/managing-the-metering-in-um/add-nsx-t.html){: external}.
   * **Username**: An NSX username with administrator privileges.
   * **Password**: The user password.

2. Click **Add**. The endpoint is displayed in the NSX-T table, with a status of **Please accept certificate**.
3. Click the status, accept the certificate, and verify that the status changes to **OK**.

## Adding Aria Operations to Usage Meter 
{: #usage_meter-add-aria}

To add VMware Aria Operations to Usage Meter, complete the following steps:

1. Under **Products**, select **Aria Operations** and click **Add**.
2. Enter the following information:
   * **Endpoint**: The IP address or the hostname (recommended if the IP address was reassigned) of your Aria Operations for Networks instance. The port number is 443. For more information, see [Add an Aria Operations for Networks Instance for Metering in vCloud Usage Meter](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/vcloud-usage-meter-4-8-deployment-and-administration-guide-4-8/managing-the-metering-in-um/add-vrni.html){: external}.
   * **Username**: An Aria Operations for Networks username with administrator privileges.
   * **Password**: The user password.

3. Click **Add**. The endpoint is displayed in the Aria Operations table with a status of **Please accept certificate**.
4. Click the status, accept the certificate, and verify that the status changes to **OK**.

## Adding other VMware products to Usage Meter 
{: #usage_meter-add-other}

Use the previous procedures to add the following products to Usage Meter:
* Tanzu Kubernetes Grid Multi-Cloud
* VMware Aria® Automation™
* VMware Aria Operations™ for Networks
* VMware Aria Suite Lifecycle
* VMware Avi Load Balancer (formerly NSX Advanced Load Balancer)
* VMware Cloud Director™
* VMware Cloud Director Availability (VCDA)
* vRealize Automation 7 (legacy) - applicable only for environments with vRealize 7 and that do not have Aria.

## Related links
{: #usage_meter-add-related}

* [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy)
* [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config)
* [Registering Usage Meter with IBM](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register)
