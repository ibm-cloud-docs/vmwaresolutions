---

copyright:

  years:  2019, 2022

lastupdated: "2022-10-10"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Adding ESXi servers to vCenter Server multizone instances
{: #mcv_addingremovingservers}

New deployments of vCenter Server multizone instances are no longer supported. You can still add and delete clusters, add and remove ESXi servers, and add and delete storage for existing multizone instances.
{: deprecated}

You can expand the capacity of your VMware vCenter Server® multizone instances by adding VMware® ESXi servers to your witness, consolidated, extra workload, and edge services clusters.

## Procedure to add ESXi servers to vCenter Server multizone instances
{: #mcv_addingremovingservers-adding-procedure}

1. From the {{site.data.keyword.vmwaresolutions_full}} console, click **Resources** > **vCenter Server** from the left navigation pane.
2. In the **vCenter Server instances** table, click the instance for which you want to expand capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the applicable cluster table, click the cluster to which you want to add ESXi servers.
5. In the **ESXi servers** section, click **Add**.
6. In the **ESXi server** window, enter the number of servers that you want to add.
7. Optionally, select the checkbox to add servers during maintenance mode.

   When you provision the new ESXi server, virtual machines (VMs) are immediately migrated to the new servers if you do not select the **Maintenance Mode** checkbox. You do not receive a confirmation message before the migration begins.
   {: important}

8. Review the estimated price and click **Create**.

## Results after you add ESXi servers to vCenter Server multizone instances
{: #mcv_addingremovingservers-adding-results}

1. You might experience a slight delay on the console while the instance status changes from **Ready to use** to **Modifying**. Allow the operation to complete before you make more changes to the instance.
2. You are notified by email that your request to add ESXi servers is being processed. On the console, the status of the cluster that is associated with the ESXi servers is changed to **Modifying**.
3. If you do not see the new ESXi servers added to the list in the cluster, check the email or console notifications to find more details about the failure.

   If you are adding ESXi servers during maintenance mode, VMs are not migrated to the new servers until you remove maintenance mode.
   {: important}
