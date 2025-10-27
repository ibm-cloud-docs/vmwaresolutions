---

copyright:

  years:  2025

lastupdated: "2025-10-24"

keywords: usage meter, register, unregister

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Registering Usage Meter with IBM
{: #usage_meter-register}

{{site.data.content.vms-deprecated-note}}

Before you register VMware vCloud Usage Meter with {{site.data.keyword.IBM}}, verify that you have the appropriate service roles to access the Usage Meter instances. For more information, see [Service roles](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui#iamrolesservice) in [Managing IAM access](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui).
{: important}

## Procedure to register Usage Meter
{: #usage_meter-register-reg}

In the {{site.data.keyword.vmwaresolutions_full}} console, complete the following steps:

1. Click **Licensing and metering > Usage Meters** from the left navigation panel.
2. On the **Usage Meters** page, click **Register** on the upper right of the **Usage Meters** table.
3. Enter the **Usage Meter ID#** value saved from the **Summary** page when you completed the Usage Meter configuration.
4. Enter a custom name for your Usage Meter. It must meet the following requirements:
   * Only alphanumeric and hyphen (-) characters are allowed.
   * The Usage Meter custom name must start with an alphabetic character and end with an alphanumeric character.

   It is recommended to use the same name as the virtual machine (VM).
   {: tip}

5. Click **Next** to register your Usage Meter.
6. Copy the **Access token** value to use when you configure the Usage Meter in the VMware vSphere® Web Client. For more information, see [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config).

   You can also copy the **Access token** by clicking the vertical overflow menu next to the **Status** column on the **Usage Meters** page and selecting **Copy Access token**.
   {: tip}

7. Click **Done**.

## Procedure to check the Usage Meter registration
{: #usage_meter-register-check}

On the VMware vCloud Usage Meter web interface, complete the following steps:

1. From the **Usage Meter Initialization > Summary** window, click **Check registration**.

   The Usage Meter portal might log out quickly or request you to extend login time. In this case, repeat the initial **Welcome** and **Network Connectivity** steps. However, the **Registration** page might show success.

   Under **Summary**, a success message is displayed.

2. After you click **Finish**, you are redirected to the Usage Meter portal.

## Procedure to unregister Usage Meter
{: #usage_meter-register-unreg}

In the VMware Solutions console, complete the following steps:

1. Click **Licensing and metering > Usage Meters** from the left navigation panel.
2. In the **Usage Meters** table, locate the Usage Meter that you want to unregister. Click the vertical overflow menu next to the **Status** column and then click **Unregister**.
3. In the **Unregister Usage Meter** window, click **Unregister**.

## Related links
{: #usage_meter-register-related}

* [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy)
* [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config)
* [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add)
