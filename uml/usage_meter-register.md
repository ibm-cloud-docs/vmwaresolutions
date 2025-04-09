---

copyright:

  years:  2025

lastupdated: "2025-04-09"

keywords: usage meter, register, unregister

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Registering Usage Meter with IBM
{: #usage_meter-register}

Before you register Usage Meter with IBM, ensure that you have permission to access the Usage Meter instances. For more information, see [Managing IAM access for VCF as a Service](/docs/vmware-service?topic=vmware-service-vmaas-iam&interface=ui).

## Procedure to register Usage Meter
{: #usage_meter-register-reg}

In the {{site.data.keyword.vmwaresolutions_full}} console, complete the following steps:

1. Click **Licensing and metering > Usage Meters** from the left navigation panel.
2. On the **Usage Meters** page, click **Register** on the upper right of the **Usage Meters** table.
3. Enter the **Usage Meter ID#** value saved from the **Summary** page when you completed the Usage Meter configuration.
4. Enter a name for your Usage Meter. Use the same name as the virtual machine (VM).
5. Click **Register**.

## Procedure to check the Usage Meter registration
{: #usage_meter-register-check}

On the VMware vCloud Usage Meter web interface, complete the following steps:

1. From the **Usage Meter Initialization > Summary** window, click **Check registration**.

   The Usage Meter portal might log out quickly or request you to extend login time. In this case, repeat the initial **Welcome** and **Network Connectivity** steps. However, the **Registration** page might show success.
   {: note}

   Under **Summary**, a success message is displayed.

2. After you click **Finish**, you are redirected to the Usage Meter portal.

## Procedure to unregister Usage Meter
{: #usage_meter-register-unreg}

In the VMware Solutions console, complete the following steps:

1. Click **Licensing and metering > Usage Meters** from the left navigation panel.
2. In the **Usage Meters** table, locate the Usage Meter that you want to delete and click the **Delete** icon ![Delete icon](../../icons/delete.svg "Delete") next to the **Status** column.
3. In the **Unregister Usage Meter** window, click **Unregister**.

## Related links
{: #usage_meter-register-related}

* [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy)
* [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config)
* [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add)
