---

copyright:

  years:  2021, 2022

lastupdated: "2022-06-03"

keywords: vCenter Server add host, add server vCenter Server

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Adding ESXi servers to vCenter Server instances
{: #vc_addingservers}

You can expand the capacity of your VMware® vCenter Server® instance according to your business needs by adding VMware ESXi™ servers.

## Before you add ESXi servers to vCenter Server instances
{: #vc_addingservers-prereq}

* Adding ESXi servers to vCenter Server instances with VMware vSphere® 6.5 is not supported.
* For the edge services cluster, you cannot add or remove ESXi servers.
* For existing instances with vSphere 6.7u1, you can add ESXi servers with either vSphere 6.7u1 or vSphere 6.7u3.
* {{site.data.content.para-vcenteraddESXiservers}}
* A vCenter Server instance with NFS storage must have at least three ESXi servers. Each of the nondefault clusters can be expanded to have up to 59 ESXi servers.
* A vCenter Server instance with vSAN™ storage must have at least four ESXi servers.
* If your initial cluster has vSAN storage, adding one or more ESXi servers after deployment can increase the cluster storage capacity.
* If your initial cluster has vSAN storage, SED SSD disks are no longer available. Non-SED SSD disks are ordered.
* You can add 1 - 20 ESXi servers at a time. For more information about the minimum of ESXi servers, see [Is a two-node vCenter Server instance highly available?](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions#is-a-two-node-vcenter-server-instance-highly-available)

## Procedure to add ESXi servers to vCenter Server instances
{: #vc_addingservers-procedure}
{: help}
{: support}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server instances** table, click the instance for which you want to expand capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the **Clusters** table, click the cluster to which you want to add ESXi servers.
5. In the **ESXi servers** section, click **Add**.
6. On the **ESXi server** page, enter the number of bare metal servers that you want to add.
7. You can keep the **Maintenance mode** checkbox selected to add servers during maintenance mode.

   When you provision the new ESXi server, virtual machines (VMs) are immediately migrated to the new servers if you do not select the **Maintenance mode** checkbox. You do not receive a confirmation message before the migration begins.
   {: important}

8. Complete the bare metal server configuration.
   * Select an existing bare metal server configuration that is being used by the existing ESXi servers in the cluster. This option is not available under the following conditions:
      * The bare metal configuration that is used by the existing ESXi servers in the cluster is **Broadwell**.
      * The storage type of the cluster is **Local disks**.
   * Select a new bare metal server configuration. 
      * For vSphere 7.0, optionally select to change the bare metal server configuration. Then, select the VMware vSphere version.
      * For **Skylake** and **Cascade Lake**, select the **CPU model**, and the amount of **RAM**.
      * For **SAP-certified**, select the **CPU model and RAM**.
      * Complete the storage configuration. Specify the disk types for the capacity and cache disks, the number of disks, and the vSAN license edition. If you want more storage, select the **High performance Intel Optane** checkbox.
9. Complete the subnet settings.
    * Select to continue to use the previously selected primary subnets.
    * Select to specify primary subnets. Then, use the lists to select the **Public primary subnet** and **Private primary subnet**.
10. On the **Summary** pane, review the estimated pricing and click **Create**.

   You can also add the provisioned resources to the {{site.data.keyword.cloud_notm}} estimate tool, by clicking **Add to estimate**. This option is useful if you want to estimate the price of the selected {{site.data.keyword.vmwaresolutions_short}} resources together with other {{site.data.keyword.cloud_notm}} resources that you might consider to purchase.

## Results after you add ESXi servers to vCenter Server instances
{: #vc_addingservers-results}

1. You might experience a slight delay on the console while the instance status changes from **Ready to use** to **Modifying**. Allow the operation to complete before you make more changes to the instance.
2. You are notified by email that your request to add ESXi servers is being processed. On the console, the status of the cluster that is associated with the ESXi servers is changed to **Modifying**.
3. If you do not see the new ESXi servers added to the list in the cluster, check the email or console notifications to find more details about the failure.

If you are adding ESXi servers during maintenance mode, VMs are not migrated to the new servers until you remove maintenance mode.   
{: important}

## Related links
{: #vc_addingservers-related}

* [Deleting vCenter Server instances in a multisite configuration](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletinginstance_multi)
* [Ordering vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-req)
* [Viewing vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_viewinginstances)
* [Managing virtual servers](/docs/virtual-servers?topic=virtual-servers-managing-virtual-servers)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
