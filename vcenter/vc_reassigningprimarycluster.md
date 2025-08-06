---

copyright:

  years:  2024, 2025

lastupdated: "2025-08-06"

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

The VM migration procedures are slightly different depending if any add-on services are installed on your instance.

| Add-on service | Migration procedures |
|:-------------- |:-------------------- |
| Juniper® vSRX | Complete [the procedure to migrate management VMs (vSRX)](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm-vsrx). |
| Caveonix RiskForesight™ | Complete [the procedure to create corresponding port groups (RiskForesight)](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm-caveonix), then complete [the procedure to migrate management VMs](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm). |
| Other services or no services | Complete [the procedure to migrate management VMs](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm). |
{: caption="VM migration procedures for add-on services" caption-side="bottom"}

### Procedure to migrate management VMs (Juniper vSRX)
{: #vc_reassigningprimarycluster-migrate-mgmt-vm-vsrx}

If the Juniper® vSRX service is installed on your instance, complete the following procedure.

1. In VMware vSphere Web Client, create host groups on the target cluster:
   1. Click the target cluster.
   2. On the **Configure** tab, under **Configuration**, click **VM/Host Groups**.
   3. Under **VM/Host Groups**, click **ADD**.
   4. Under **Add Group Member**, select the type as **Host Group** and click **ADD**.
   5. Select the host that you want to add as a member. Provide the same name as the hostname's fully qualified domain name (FQDN).
   6. Complete the previous 2 steps for the second hostname.

2. Disable affinity rules on the source cluster:
   1. Click the source cluster.
   2. On the **Configure** tab, under **Configuration**, click **VM/Host Rules**.
   3. For each of the following items: `<vm_nickname>_vSRX_edge_node1`, `<vm_nickname>_vSRX_edge_node2`, and `<vm_nickname>-affinity-rule`, click **Edit**, and clear the **Enable Rule** checkbox.

3. Export the network configurations of the source cluster:
   1. Go to the **Networks** tab of the source cluster.
   2. For each of the following switches: `<instance_name>-<source_clustername>-private`, `<vsrx_nickname>-vsrx-fab DVS`, and `<vsrx_nickname>-vsrx-private-transit`, right-click and click **Export Configuration**.
   3. Locate `<instance_name>--public`, right-click `<vsrx_nickname>-vsrx-public-transit` and click **Export Configuration**.

4. Import the port group configurations into the target cluster:
   1. Go to the **Networks** tab of the target cluster.
   2. Right-click the switch `<instance_name>-<target_cluster_name>` and click **Distributed Port Group > Import Distributed Port Group**.
   3. Under **Import port group configuration**, click **Browse** and upload the corresponding configuration file that you exported in **Step 3**. Click **Next**. Under **Ready to complete**, verify the information and click **Finish**. 
   4. Complete the previous 2 steps for `<instance_name>-<source_cluster_name>-public`.

5. Re-create the resource pool:
   1. On the source vSRX cluster, right-click its resource pool and click **Edit resource Settings**. Write down the reservation values for CPU and memory.
   2. On the target vSRX cluster, right-click **New Resource Pool** and create a resource pool with the same name as the source vSRX resource pool. Set the reservation values for CPU and memory to the same values as the source.

6. Migrate the vSRX edge nodes VMs:
   1. Right-click the `<vm_nickname>_vSRX_edge_node1` VM and click **Actions > Migrate**.
   2. Under **Select a migration type**, choose **Change both compute resource and storage**.
   3. Under **Select a compute resource**, choose the target cluster of the vSRX resource pool and click **Next**.
   4. Under **Select storage**, choose the **vSAN** datastore name for the target cluster.
   5. Under **Select networks**, choose the destination network by browsing to the appropriate DVS switch and click **Next**.
   6. Under **Select vMotion priority**, choose a priority option.
   7. Under **Ready to complete**, verify the information and click **Finish** to start the migration.
   8. Repeat the previous 7 steps for the `<vm_nickname>_vSRX_edge_node2` VM.

7. Create VM groups on the target cluster:
   1. Click the target cluster.
   2. On the **Configure** tab, under **Configuration**, click **VM/Host Groups**.
   3. Under **VM/Host Groups**, click **ADD**.
   4. Under **Add Group Member**, select the type as **VM Group** and click **ADD**.
   5. Select the vSRX node1 VM to add as member. Provide the same name as the vSRX node1.
   6. Complete the previous step for the vSRX node2 VM.

8. Map nodes to hosts on the target cluster:
   1. Click the target cluster.
   2. On the **Configure** tab, under **Configuration**, click **VM/Host Rules**.
   3. Under **VM/Host Rules**, click **ADD**.
   4. Under **Create VM/Host Rule**, select the type as **Virtual Machines to Hosts** and map `<vm_nickname>_vSRX_edge_node1` to the host where it is deployed. Assign the same name `<vm_nickname>_vSRX_edge_node1`.
   5. Complete the previous step for the `<vm_nickname>_vSRX_edge_node2` node.

9. Enable the affinity rule on the target cluster:
   1. Click the target cluster.
   2. On the **Configure** tab, under **Configuration**, click **VM/Host Rules**.
   3. Search for and locate `<vm_nickname>-affinity-rule`.
   4. Click **Edit** and select **Enable Rule**.

If you are migrating from a source vSAN OSA (Original Storage Architecture) to a target vSAN ESA (Express Storage Architecture) cluster, also configure the failover settings:
1. Click the target cluster.
2. Click the **Networks** tab, select the `vsrxnickname-vsrx-fab` DVS switch, and click the **Configure** tab.
3. Under **Policies**, click **Edit** and go to **Teaming and failover**.
4. Drag `uplink1` and `uplink2` to move them under **Unused uplinks** and `lag1` to move it under **Active uplinks**.
5. Repeat the previous 3 steps for the `vsrxnickname-vsrx-private-transit` and `vsrxnickname-vsrx-public-transit` DVS switches.

### Procedure to create corresponding port groups (RiskForesight)
{: #vc_reassigningprimarycluster-migrate-mgmt-vm-caveonix}

If the Caveonix RiskForesight™ service is installed on your instance, complete the following procedure.

RiskForesight is installed with its own port group named **SDDC-DPortGroup-Caveonix**. Before you migrate the management VMs for instances with this service deployed, you must create a corresponding port group in the new (target) cluster.
{: requirement}

1. In VMware vSphere Web Client, click the **Networks** tab, right-click **SDDC-DPortGroup-Caveonix**, and click **Export Configuration**.
2. Under **Export Configuration**, click **OK**.
3. Right-click the private network subnet of the target cluster and click **Distributed Port Group** > **Import Distributed Port Group**.
4. Under **Import port group configuration**, click **Browse** and upload the exported configuration archive file that you created in **Step 2**. Click **Next**.
5. Under **Ready to complete**, verify the information and click **Finish**. Confirm that the subnet is to be renamed.
6. Complete [the procedure to migrate management VMs](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm).

### Procedure to migrate management VMs
{: #vc_reassigningprimarycluster-migrate-mgmt-vm}

1. In VMware vSphere Web Client, go to the **Virtual Machines** tab, select the VM that you want to migrate and click **Actions > Migrate**.
2. Under **Select a migration type**, choose **Change both compute resource and storage**.
3. Under **Select a compute resource**, choose a target cluster or host in the target cluster.

   If VMware HCX is installed on your instance, you might get a compatibility error, which you can ignore. For more information, see [vCenter vMotion error "Virtual Ethernet Card 'Network Adapter 1' is not supported"](https://knowledge.broadcom.com/external/article/332437/vcenter-vmotion-error-virtual-ethernet-c.html){: external}.
   {: note}

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
