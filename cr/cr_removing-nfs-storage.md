---

copyright:

  years:  2022, 2023

lastupdated: "2023-04-03"

keywords: Cyber Recovery remove NFS storage, remove NFS storage Cyber Recovery

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Removing NFS storage from Cyber Recovery instances
{: #cr_removingnfs}

You can contract the capacity of your Cyber Recovery instance according to your business needs by removing Network File System (NFS) storage.

## Before you remove NFS storage from Cyber Recovery instances
{: #cr_removingnfs-prereq}

* Do not remove NFS storage from the VMware vSphere® Web Client. The changes that you make on the vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_full}} console.
* Before you remove the NFS storage, ensure that you removed all the VMs from the storage.
* Ensure that the shares that you plan to remove are associated with the correct Cyber Recovery instance.
* The cluster status must be **Available**.
* You can remove NFS storage shares from an existing NFS or vSAN cluster.

## Procedure to remove NFS storage from Cyber Recovery instances
{: #cr_removingnfs-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources > Cyber Recovery** from the left navigation pane.
2. In the **Cyber Recovery** table, click the instance for which you want to contract capacity.
3. Click the **Infrastructure** tab.
4. In the applicable cluster table, click the cluster from which you want to remove NFS storage.
5. In the **Storage** section, select the storage share that you want to remove and click **Delete**.
6. Click **Remove** in the **Remove storage** window.

## Results after you remove NFS storage from Cyber Recovery instances
{: #cr_removingnfs-results}

1. You might experience a slight delay on the console, while the instance status changes from **Available** to **Modifying**. Allow the operation to complete before you make more changes to the instance.
2. You are notified by email that your request to remove NFS storage is being processed. On the console, the status of the cluster that is associated with the NFS storage is changed to **Modifying**.
3. The NFS storage is fully reclaimed by {{site.data.keyword.cloud_notm}} infrastructure at the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle, which is typically 30 days.

   You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the removed NFS storage.
   {: note}

## Related links
{: #cr_removingnfs-related}

* [Planning for Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_planning)
* [Requirements for Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance_reqs)
* [Adding clusters to Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingclusters)
