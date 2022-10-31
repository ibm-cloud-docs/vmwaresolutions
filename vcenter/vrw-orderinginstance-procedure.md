---

copyright:

  years:  2020, 2022

lastupdated: "2022-09-27"

keywords: vmware regulated workloads, vmware regulated workloads order instance, order vmware regulated workloads, vmware regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Procedure to order VMware Regulated Workloads
{: #vrw-orderinginstance-procedure}

1. In the {{site.data.keyword.vmwaresolutions_full}} console, click the **VMware Regulated Workloads** card.
2. On the **VMware Regulated Workloads** page, select a deployment topology according to your needs.
3. Review the service prerequisites and confirm that you ordered the mandatory services listed.
4. Specify the instance configuration:
     * If you want to create a new configuration, select **New configuration**.
     * If you want to update a saved configuration or create a new configuration based on a saved one, select a saved configuration.
5. Under **Licensing**, complete the license settings for the listed components.
   * To use IBM-provided licenses, ensure that the option **Include with purchase** is selected.
   * To use your own licenses, click **I will provide**, and enter the license key.
6. For data center location, click the **Edit** icon ![Edit icon](../../icons/edit-tagging.svg "Edit") and select the geography, data center, and pod to host the clusters.
7. (Single-zone VMware® instance only) Specify the primary cluster settings.
   1. Specify the cluster name.
   2. Select the primary cluster type. For the **Customizable consolidated** cluster, select the CPU model and RAM size.
   3. Select the number of bare metal servers.
   4. Under **vSAN configuration**, select the disk type and size for the vSAN™ capacity disks, the number of vSAN capacity disks, and the vSAN licensing option.
   5. Review the estimated resources available per cluster.
   6. Review the networking type and select the uplink speed.

8. (Multizone VMware instance only) Specify the witness cluster settings.
   1. Specify the witness cluster name.
   2. Select the CPU model, RAM size, and the number of bare metal servers.
   3. Select the disk type and size for the vSAN capacity disks and the number of vSAN capacity disks.
   4. Review the estimated resources available per cluster.
   5. Review the networking configuration.
   6. Select the uplink speed. The 25 Gb option is available for specific data centers only.

9. (Multizone VMware instance only) Specify the management cluster settings.
   1. Specify the cluster name.
   2. Select the management cluster capacity. For the **Customizable** capacity, select the CPU model and RAM size.
   3. Select the hosts per site.
   4. Select the disk type and size for the vSAN capacity disks, the number of vSAN capacity disks, and complete the vSAN license configuration. The available options depend on your deployment topology and capacity configurations. For small capacity instances, disk type and size for the vSAN capacity disks and the number of vSAN capacity disks are predefined.
   5. Review the estimated resources available per cluster.
   6. Review the networking type and select the uplink speed.

10. Specify the settings for the workload cluster. For single-zone VMware instances with a customizable consolidated cluster, optionally select the **Include a separate cluster for workloads** checkbox and complete the settings.
    1. Specify the cluster name.
    2. Select the workload capacity. For the **Customizable** capacity, select the CPU model and RAM size.
    3. (Single-zone VMware instance only) Select the number of bare metal servers.
    4. (Multizone VMware instance only) Select the hosts per site.
    5. Select the disk type and size for the vSAN capacity disks, and the number of vSAN capacity disks. For single-zone VMware virtual data centers, also select the vSAN licensing option.
    6. Review the estimated resources available per cluster.
    7. Review the networking type and select the uplink speed.

11. Choose the firewall appliance for your instance and follow the steps, depending on your selection:
    1. For **Edge services cluster with Juniper vSRX**, **Edge services cluster with FortiGate Virtual Appliance**, and **Bring your own gateway appliance**, specify the edge services [cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-edge#vrw-orderinginstance-edge-cluster-name), the CPU model, the RAM size, the uplink speed, and the networking type.
    2. For **Edge services cluster with Juniper vSRX** and **Edge services cluster with FortiGate Virtual Appliance**, you must also specify the corresponding service settings in a later step.
    3. For **FortiGate Security Appliance**, you must order the **FortiGate Security Appliance 10 Gbps** service from the [IBM Cloud catalog](https://cloud.ibm.com/catalog/infrastructure/fortigate-security-appliance-10gb). Confirm that you ordered the service and continue with the following steps.

12. Under **Network interface**, enter the hostname prefix for the regulated workload and the root domain name. If you want to customize the hostnames prefix individually, select **Configure hostnames individually**.
13. Under **Resource details**, enter the instance name and select a resource group.
14. Under **Included services**, review the add-on services to be deployed into the instance. If a service requires configuration, complete the service-specific settings by clicking **Edit** on the service card. Then, complete your edits and click **Save**. For more information about specific settings for a service, see the corresponding topic for ordering the service.
15. (Single-zone VMware instance only) Under **Optional services**, select the add-on service to be deployed into the instance. To deploy an add-on service, toggle the switch on and review the service settings. If configuration is required, click **Edit**, then complete the edits and click **Save**. For more information, see [VMware HCX configuration](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_ordering#hcx_ordering-config) or [Considerations when you install F5 BIG-IP](/docs/vmwaresolutions?topic=vmwaresolutions-f5_considerations#f5_considerations-install).
16. On the **Summary** pane, review the regulate workload instance settings and the estimated price.
    * To save the settings as a new configuration template without placing an order, click **Save configuration**, enter a name for the configuration, and click **Continue**.
    * To save the updates to a saved configuration, click **Save configuration**, select **Modify current configuration**, and click **Continue**.
    * To save the updates to a new saved configuration, click **Save configuration**, select **Create new configuration**, enter a new name for the configuration, and click **Continue**.
17. To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

## Results if you saved a configuration
{: #vrw-orderinginstance-results-config}

You get a console notification that the configuration is saved successfully, and then you can find the template in the **Instance configurations** list. Next, you can manage the configuration template by viewing or deleting it in the **Instance configurations** list.

## Results if you placed an order
{: #vrw-orderinginstance-results-order}

1. The deployment of the regulated workload instance starts automatically and you receive confirmation that the order is being processed. You can check the deployment status, including any issues that might require your attention, by viewing the **Deployment history** section of the instance details.
2. When the instance is successfully deployed, the ordered components are installed on your VMware virtual platform. The deployment of the services starts after your order is completed. When the instance is ready to use, the status of the instance is changed to **Ready to use**, and you receive a notification by email.

You must manage the {{site.data.keyword.vmwaresolutions_short}} components that are created in your {{site.data.keyword.cloud_notm}} account only from the VMware Solutions console, not the {{site.data.keyword.slportal}}, or any other means outside of the console.
If you change these components outside of the VMware Solutions console, the changes are not synchronized with the console.
{: important}

{{site.data.content.caution-component-management}}

### Known issue for multizone deployment
{: #vrw-orderinginstance-results-order-issue}

Some public networking components might be displayed as inactive in VMWare vCenter Server®. These components do not indicate a problem and you can either ignore the issue or delete the components.

## Related links
{: #vrw-orderinginstance-procedure-related}

* [Signing up for an {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts#signing_required_accounts-cloud)
* [Planning for VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-planning)
* [Viewing and deleting VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-view-delete-instance)
* [VMware Regulated Workloads reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
