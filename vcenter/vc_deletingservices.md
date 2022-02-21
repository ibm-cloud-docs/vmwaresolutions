---

copyright:

  years:  2021, 2022

lastupdated: "2022-02-18"

keywords: remove services vCenter Server

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Deleting services from vCenter Server instances
{: #vc_deletingservices}

You can delete the services that were provisioned for your VMware vCenter Server® instances when you no longer need these services.

## Before you delete services from vCenter Server instances
{: #vc_deletingservices-prereq}

* Deleting services from vCenter Server instances with VMware vSphere® 6.5 is not supported.
* You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the deleted services.

## Procedure to delete services from vCenter Server instances
{: #vc_deletingservices-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server instances** table, click the instance for which you want to delete services.
3. Click **Services** on the left navigation pane.
4. On the **Services** page, locate the service instance that you want to delete, click the vertical overflow menu next to the **Status** column, and then click **Delete service**.
5. In the **Remove service** window, review the considerations or warnings if there are any and select **I Understand**. Click **Delete**.

## Results after you delete services from vCenter Server instances
{: #vc_deletingservices-results}

After your request to delete a service is accepted, the service status is changed to **Removing**.

When the service deletion is completed successfully, you are notified by email, and the service is deleted from the **Services** page of the instance.

You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the deleted services.
{: note}

## Manually removing the DNS entries for specific services
{: #vc_deletingservices-DNS-entries}

For specific services, if you installed the service in a VMware Solutions release earlier than V4.0 and you delete that service, you must manually remove the DNS entries.

After you delete the service, unused DNS entries remain in Active Directory™. These entries do not cause any problems. However, in the future, they might create conflicts with reverse lookups. It is recommended that you remove the entries as soon as possible.

The following table shows the services that are affected. The table also shows the pattern for hostnames for various service offerings. The actual hostname might differ from the pattern in various ways. Use the pattern to locate all of the registered DNS hostnames associated with a service. Many services have more than one registered hostname.

| Service | Hostname Pattern | Example |
|:-------- |:--------------------- | :----------- |
| Caveonix RiskForesight | `riskforesight` | `riskforesight`   \n `inst01-riskforesight` |
| F5 BIG-IP | `nickname-bigip1`   \n `nickname-bigip2` | `edgefw-bigip1` |
| FortigateVM | `nickname-fortigate` | `edgefw-fortigate01` |
| HyTrust CloudControl | `htccnn-id` | `htcc02-GY67239` |
| HyTrust DataControl | `htdcnn-id` | `htcc02-GY67239` |
| HyTrust KeyControl | `htkcnn-id` | `htcc02-GY67239` |
| vRealize Operations | `vrli`   \n `vrops`   \n `vrlog` | `vrli-master`   \n `vrops-data1`   \n `vrlog-master` |
{: caption="Table 1. Hostname patterns and examples for affected services" caption-side="top"}

To remove the DNS entires, complete the following steps:

1. Log in to the Active Directory appliance and open the DNS tools.
2. Go to the instance subdomain, which is the subdomain under the root domain. Its name resembles the name of the vCenter Server instance.
3. Remove the hostname entries for the specific deleted service appliances.
4. Open the associated reverse lookup table and remove the DNS entries from the table.

## Related links
{: #vc_deletingservices-related}

* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
