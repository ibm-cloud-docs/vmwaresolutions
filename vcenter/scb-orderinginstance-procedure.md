---

copyright:

  years:  2021, 2022

lastupdated: "2022-01-20"

keywords: order Security and Compliance Readiness Bundle, order scb instances, order vcs scb
subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Procedure to order VMware Security and Compliance Readiness Bundle
{: #scb-orderinginstance-procedure}

1. In the {{site.data.keyword.vmwaresolutions_full}} console, click the **VMware Solutions Dedicated - Security & Compliance Readiness Bundle** card.
2. On the **VMware Security and Compliance Readiness Bundle** page, review the service prerequisites and confirm that you ordered the mandatory services listed.
3. Under **Resource details**, complete the following settings.
   1. Specify the instance configuration:
      * If you want to create a new configuration, select **New configuration**.
      * If you want to update a saved configuration or create a new configuration based on a saved one, select a saved configuration.
   2. Specify the instance name.
   3. Select the resource group.
   4. Review the properties of the included VMware components.
4. Under **Licensing**, complete the license settings for the listed components.
    * To use IBM-provided licenses, ensure that the option **Include with purchase** is selected.
    * To use your own licenses, click **I will provide** and enter the license key.
5. For data center location, click the **Edit** icon ![Edit icon](../../icons/edit-tagging.svg "Edit") and select the geography, data center, and pod where the consolidated cluster (or management cluster) and the workload cluster are to be hosted.
6. Under **Consolidated cluster**, complete the following settings:
   1. Specify the consolidated cluster name.
   2. Select the CPU model, RAM size, and the number of bare metal servers.
   3. If you select to use vSAN™ storage, complete the following settings:
      1. Specify the disk type and size for the vSAN capacity disks, and the number of vSAN capacity disks.
      2. Review the predefined disk size for vSAN cache disks and the predefined number of vSAN cache disks.
      3. If you want to enable vSAN deduplication and compression, select the **Enable vSAN deduplication and compression** checkbox.
      4. Specify whether to include the vSAN Enterprise license with your purchase or to use your own license.
   4. If you select to use NFS storage, complete the following settings:
      * To add and configure same settings for all file shares, select the **Number of shares**, **Size (GB)**, and **Performance**.
      * To add and configure file shares individually, select the **Configure shares individually** checkbox. Then, click **Add shared storage** and select the **Size (GB)** and **Performance** for each file share. You must select at least one file share.
   5. Select the private NICs enablement.
   6. Select the uplink speed. The 25 Gb option is available for specific data centers only.
   7. Select the VLAN settings:
      * If you want to order new public and private VLANs, click **Order new VLANs**.
      * If you want to reuse the existing public and private VLANs when they are available, click **Select existing VLANs** and specify the VLANs and the subnets.
      * Optionally click **Portable subnets settings**. Then, select the portable subnet for each purpose and click **Save**.

       If the consolidated or management cluster and the workload clusters are in the same location, you cannot use existing VLANs. Instead, the workload clusters reuse the VLANs from the management cluster.
       {: note}

7. (Optional) Under **Workload cluster**, select the **Include a separate, additional workload cluster** checkbox, and then specify the workload cluster settings. The configuration options are the same as the options for the consolidated cluster.

8. Choose the firewall appliance for your instance and follow the steps, depending on your selection:
   1. Specify the edge services [cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance#vrw-orderinginstance-cluster-name-req), the CPU model, the RAM size, the uplink speed, and the networking type.
   2. For **Edge services cluster with Juniper vSRX** and **Edge services cluster with FortiGate Virtual Appliance**, you must also specify the corresponding service settings in a later step.

9. Under **Network interface**, complete the following settings:
   1. Specify the hostname prefix and the root domain name.
   2. Review the deployment type.

10. Under **Included services**, review the add-on services to be deployed into the instance. If a service requires configuration, complete the service-specific settings by clicking **Edit** on the service card. Then, complete your edits and click **Save**. For more information about specific settings for a service, see the corresponding topic for ordering the service.

11. Under **Recommended services** and **Optional services**, review the service options. If you want to deploy an add-on service, toggle the switch on and review the service settings. If configuration is required, click **Edit**, then complete the edits and click **Save**. For more information about specific settings for a service, see the corresponding topic for ordering the service.

12. On the **Summary** pane, review the instance settings and the estimated price.
    * To save the settings as a new configuration template without placing an order, click **Save configuration**, enter a name for the configuration, and click **Continue**.
    * To save the updates to a saved configuration, click **Save configuration**, select **Modify current configuration**, and click **Continue**.
    * To save the updates to a new saved configuration, click **Save configuration**, select **Create new configuration**, enter a new name for the configuration, and click **Continue**.

13. To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Results if you saved a configuration
{: #scb_orderinginstance-results-config}

You get a console notification that the configuration is saved successfully, and then you can find the template in the **Instance configurations** list. Next, you can manage the configuration template by viewing or deleting it in the **Instance configurations** list.

## Results if you placed an order
{: #scb-orderinginstance-results-order}

The deployment of the Security and Compliance Readiness Bundle instance starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the **Deployment history** tab on the instance details page.

When the instance is successfully deployed, the ordered components are installed on your VMware virtual platform. The deployment of the services starts after your order is completed. When the instance is ready to use, the status of the instance is changed to **Ready to use** and you receive a notification by email.

Next, you can view and manage the Security and Compliance Readiness Bundle instance that you ordered.

You must manage the {{site.data.keyword.vmwaresolutions_short}} components that are created in your {{site.data.keyword.cloud_notm}} account only from the {{site.data.keyword.vmwaresolutions_short}} console, not the {{site.data.keyword.slportal}}, or any other means outside of the console.
If you change these components outside of the {{site.data.keyword.vmwaresolutions_short}} console, the changes are not synchronized with the console.
{: important}

**CAUTION:** Managing any {{site.data.keyword.vmwaresolutions_short}} components (which were installed into your {{site.data.keyword.cloud_notm}} account when you ordered the instance) from outside the {{site.data.keyword.vmwaresolutions_short}} console can make your environment unstable. These management activities include:
*  Adding, modifying, returning, or removing components
*  Expanding or contracting instance capacity through adding or removing VMware ESXi™ servers
*  Powering off components
*  Restarting services

## Related links
{: #scb-orderinginstance-related}

* [Signing up for an {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts#signing_required_accounts-cloud)
* [Requirements and planning Security and Compliance Readiness Bundle](/docs/vmwaresolutions?topic=vmwaresolutions-scb-planning)
* [Viewing and deleting Security and Compliance Readiness Bundle instances](/docs/vmwaresolutions?topic=vmwaresolutions-scb-view-delete-instance)
