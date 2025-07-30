---

copyright:

  years:  2024, 2025

lastupdated: "2025-07-30"

keywords: reassign primary cluster, primary cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Reassigning primary clusters for {{site.data.keyword.vcf-auto-short}} instances
{: #vc_reassigningprimarycluster}

You can reassign a primary cluster to another cluster in your {{site.data.keyword.vcf-auto}} instance according to your business needs.

Reassigning primary clusters for instances that are deployed with VMware vSphere® 6 is not supported.
{: restriction}

## Before you reassign a primary cluster
{: #vc_reassigningprimarycluster-prereq}

Review the following information before you reassign your primary cluster:

* Ensure that VMware NSX® is upgraded to the most recent version (4.1.2 or later).
* You must migrate the management virtual machines (VMs), the NSX edge management VMs, and the Usage Meter VM (if you deployed VMware vCloud Usage Meter).
* Do not migrate all VMs at the same time, as this action might cause failures.

To migrate your VMs, complete the following procedures in VMware vSphere Web Client.

### Procedure to migrate management VMs
{: #vc_reassigningprimarycluster-migrate-mgmt-vm}

1. In VMware vSphere Web Client, go to the **Virtual Machines** tab, select the VM that you want to migrate and click **Actions > Migrate**.
2. Under **Select a migration type**, choose **Change both compute resource and storage**.
3. Under **Select a compute resource**, choose a target cluster or host in the target cluster.

4. Under **Select storage**, choose the **vSAN** datastore name for the target cluster.

   If the target cluster has a higher version for the virtual switch than of the current cluster, you receive an error. For more information, see [Migrating a virtual machine between two different vDS versions](https://knowledge.broadcom.com/external/article?legacyId=79446){: external}.
   {: note}

5. Under **Select networks**, ensure that the **dpg** source networks are equivalent to their target cluster. Do not change the **edge-teps**, as added clusters cannot create their own networks. Also, the destination network that is marked as **none** is a known issue and can be ignored.
6. Under **Select vMotion priority**, choose a priority option.
7. Under **Ready to complete**, verify the information and click **Finish** to start the migration.

### Procedure to migrate NSX edge management VMs
{: #vc_reassigningprimarycluster-migrate-nsx-edge-vm}

After you migrate the management VMs, complete the following steps in NSX Manager:

1. Click the **System** tab.
2. From the left navigation menu, click **Fabric > Nodes**.
3. On the **Edge Transport Nodes** tab, click **Edit** to change the vMotion nodes.
4. Update the **IPv4 Pool** value so that it targets the cluster TEP pool. The IPv4 Pool value must be in the format `<instance name>-<cluster name>-tep-pool`.
5. Click **Save**.

   In the **Edge Transport Nodes** table, wait until the edge node **Configuration Status** shows **Mismatch**. This action happens when NSX identifies that the VM changed its cluster and datastore. Because it might be triggered from the NSX refresh of vCenter Server resources, it takes some time before the inconsistency is identified.

6. Select the edge node that has the **Mismatch** configuration status.
7. In the **Resolve Sync Errors** window, select the **vSphere/Edge Appliance** source.

   Do not select **NSX**, as the migration will be reverted.
   {: important}

8. Click **Resolve**.
9. Refresh the table.

The validated configuration status changes to **Success**.

## Procedure to reassign primary clusters for Automated instances
{: #vc_reassigningprimarycluster-procedure}
{: help}
{: support}

1. {{site.data.content.ol-intro-ui-vcfclassic}}
2. In the **{{site.data.keyword.vcf-classic}}** table, click the instance that contains the primary cluster that you want to reassign.
3. Click the **Infrastructure** tab and click **Reassign primary cluster** on the upper right of the **Clusters** table.
4. On the **Reassign primary cluster** pane, the original primary cluster is preselected. Verify that both the new primary cluster and the original primary cluster show a status of **Available**.
5. Select the new cluster that you want to assign as the primary cluster. The list shows only the new clusters that meet the following conditions, which are required for a successful reassignment:
    * Must have vSAN storage.
    * Must be on the same VLANs as the original primary cluster.
    * Must have the same version of vSphere and the same networking type as the original primary cluster.
6. Click **Reassign**.

The reassignment of the new primary cluster can take up to one hour.
{: note}

## Results after you reassign the primary cluster
{: #vc_reassigningprimarycluster-results}

The status of the original and new primary clusters changes from **Available** to **Modifying**. After the reassignment is complete, the **primary** tag is shown on the new primary cluster and the status of both clusters changes to **Available**.

## Related links
{: #vc_reassigningprimarycluster-related}

* [Viewing Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_viewinginstances)
* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
