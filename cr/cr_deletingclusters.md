---

copyright:

  years:  2022, 2023

lastupdated: "2023-02-08"

keywords: Cyber Recovery delete clusters, delete clusters, delete Cyber Recovery clusters, delete Cyber Recovery clusters

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Deleting clusters from Cyber Recovery instances
{: #cr_deletingclusters}

You can delete clusters from Cyber Recovery instances when you do not need them.

## Before you delete clusters from Cyber Recovery instances
{: #cr_deletingclusters-before}

* Whenever possible, delete clusters by using the {{site.data.keyword.vmwaresolutions_full}} console because changes that you make on the VMware vSphere® Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. Therefore, delete clusters from Cyber Recovery only for on-premises clusters or clusters that you don't plan to manage in the {{site.data.keyword.vmwaresolutions_short}} console.
* You can delete only clusters that are added as part of Day 2 operations. Clusters that are created during initial deployment can't be deleted.
* You can delete a single cluster at a time. To delete more than one cluster, you must do it in sequence. Wait for the previous cluster to be deleted before you delete the next cluster.
* Ensure that all nodes in a cluster are powered on and operational before you delete the cluster.
* You can add or delete a cluster while another cluster is being created or deleted.
* When you delete a cluster, all virtual machines (VMs) from the cluster are also deleted, and they can't be recovered. If you want to keep the VMs, migrate them to other clusters.
* You do not have to delete any services that are installed on the cluster, including services on an edge gateway cluster. The services are automatically deleted when you delete the cluster.

## Procedure to delete clusters from Cyber Recovery instances
{: #cr_deletingclusters-procedure}
{: help}
{: support}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources > Cyber Recovery** from the left navigation pane.
2. In the **Cyber Recovery** table, click the instance that you want to delete clusters from.

   Ensure that the instance is in the **Ready to use** status. Otherwise, you can't delete clusters from the instance.
   {: note}

3. Click **Infrastructure** on the left navigation pane. In the **Clusters** table, locate the cluster that you want to delete and click the **Delete** icon ![Delete icon](../../icons/delete.svg "Delete") next to the **Status** column.
4. In the **Delete cluster** window, confirm that you completed the migration of VMs to other clusters, if needed, and that you want to delete the cluster. Click **Delete**.

## Related links
{: #cr_deletingclusters-related}

* [Viewing services for Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_viewingservices)
* [Expanding and contracting capacity for Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingservers)
