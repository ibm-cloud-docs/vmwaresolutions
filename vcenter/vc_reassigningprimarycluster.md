---

copyright:

  years:  2024, 2026

lastupdated: "2026-01-12"

keywords: reassign primary cluster, primary cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Reassigning primary clusters for {{site.data.keyword.vcf-auto-short}} instances
{: #vc_reassigningprimarycluster}

{{site.data.content.vms-deprecated-note}}

You can reassign a primary cluster to another cluster in your {{site.data.keyword.vcf-auto}} instance according to your business needs.

## Before you reassign a primary cluster
{: #vc_reassigningprimarycluster-prereq}

Review the following information before you reassign your primary cluster:

* Ensure that VMware NSX® is upgraded to the most recent version (4.1.2 or later).
* You must migrate the management virtual machines (VMs), deploy the NSX edge management VMs on the new cluster, and migrate the Usage Meter VM (if you deployed VMware vCloud Usage Meter).
* Do not migrate all VMs at the same time, as this action might cause failures.

The VM migration procedures are slightly different depending if any add-on services are installed on your instance.

| Add-on service | Migration procedures |
| :-------------- | :-------------------- |
| Juniper® vSRX | Complete the following procedures: \n 1. [Migrate management VMs (vSRX)](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm-vsrx) \n 2. [Deploy the NSX edge management VMs on the new cluster](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-deploy-new-nsx-edge-vm) |
| Caveonix RiskForesight™ | Complete the following procedures: \n 1. [Create corresponding port groups (RiskForesight)](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm-caveonix) \n 2. [Migrate management VMs](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm) \n 3. [Deploy the NSX edge management VMs on the new cluster](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-deploy-new-nsx-edge-vm) |
| Other services or no services | Complete the following procedures: \n 1. [Migrate management VMs](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm) \n 2. [Deploy the NSX edge management VMs on the new cluster](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-deploy-new-nsx-edge-vm) |
{: caption="VM migration procedures for add-on services" caption-side="bottom"}

### Procedure to migrate management VMs (vSRX)
{: #vc_reassigningprimarycluster-migrate-mgmt-vm-vsrx}

If the Juniper vSRX service is installed on your instance, complete the following procedure.

1. In the VMware vSphere® Web Client, create host groups on the target cluster:
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

If the Caveonix RiskForesight service is installed on your instance, complete the following procedure.

RiskForesight is installed with its own port group named **SDDC-DPortGroup-Caveonix**. Before you migrate the management VMs for instances with this service deployed, you must create a corresponding port group in the new (target) cluster.
{: requirement}

1. In the vSphere Web Client, click the **Networks** tab, right-click **SDDC-DPortGroup-Caveonix**, and click **Export Configuration**.
2. Under **Export Configuration**, click **OK**.
3. Right-click the private network subnet of the target cluster and click **Distributed Port Group** > **Import Distributed Port Group**.
4. Under **Import port group configuration**, click **Browse** and upload the exported configuration archive file that you created in **Step 2**. Click **Next**.
5. Under **Ready to complete**, verify the information and click **Finish**. Confirm that the subnet is to be renamed.
6. Complete [the procedure to migrate management VMs](/docs/vmwaresolutions?topic=vmwaresolutions-vc_reassigningprimarycluster#vc_reassigningprimarycluster-migrate-mgmt-vm).

### Procedure to migrate management VMs
{: #vc_reassigningprimarycluster-migrate-mgmt-vm}

1. In the vSphere Web Client, go to the **Virtual Machines** tab, select the VM that you want to migrate and click **Actions > Migrate**.
2. Under **Select a migration type**, choose **Change both compute resource and storage**.
3. Under **Select a compute resource**, choose a target cluster or host in the target cluster.

   If VMware HCX is installed on your instance, you might get a compatibility error, which you can ignore. For more information, see [vCenter vMotion error "Virtual Ethernet Card 'Network Adapter 1' is not supported"](https://knowledge.broadcom.com/external/article/332437/vcenter-vmotion-error-virtual-ethernet-c.html){: external}.
   {: note}

4. Under **Select storage**, choose the **vSAN** datastore name for the target cluster.

   If the target cluster has a higher version for the virtual switch than of the current cluster, you receive an error. For more information, see [Migrating a virtual machine between two different vDS versions](https://knowledge.broadcom.com/external/article?legacyId=79446){: external}.
   {: note}

5. Under **Select networks**, ensure that the `dpg` source networks are equivalent to their target cluster. Do not change the **edge-teps**, as added clusters cannot create their own networks. Also, the destination network that is marked as **none** is a known issue and can be ignored.
6. Under **Select vMotion priority**, choose a priority option.
7. Under **Ready to complete**, verify the information and click **Finish** to start the migration.

### Procedure to deploy the NSX edge management VMs on the new cluster
{: #vc_reassigningprimarycluster-deploy-new-nsx-edge-vm}

After you migrate the management VMs, you must deploy the NSX edge management VMs on the new (target) cluster.

Review the following information before you redeploy:
* Ensure that a new subnet is available on the same VLAN as the IP addresses assigned to the original (source) NSX edge.
* Obtain the DNS and NTP server details from [IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

Complete the following steps in NSX Manager:

1. Click the **System** tab and from the left navigation menu, click **Fabric > Nodes > Edge Transport Nodes** and click **Add Edge Node**.
2. Under **Name and Description**, enter a name for the new (target) edge, the hostname in FQDN format, and select the **Medium** option for **Form Factor**. Click **NEXT**.
3. Under **Credentials**, enter the passwords for both the `admin` and `root` users and toggle the **Allow SSH Login** and **Allow Root SSH Login** switches for debugging purposes. You can skip the **Audit Credentials** section. Click **NEXT**.
4. Under **Configure Deployment**, select the **Compute Manager**, **Cluster**, and **Datastore** values from the list. **Cluster** and **Datastore** refer to the new (target) cluster. Click **NEXT**.
5. Under **Configure Node Settings**, select **IPv4 Only** for **Management IP Assignment** and **Static** for **Type**. Enter the **Management IP** and **Default Gateway** values and click **Select Interface**.
6. Under **Select Interface**, choose the portgroup with the name that ends with `dpg-mgmt` and click **SAVE**.
7. Under **Configure Node Settings**, enter the DNS and NTP server details, previously obtained from IBM Support. Click **NEXT**.
8. Under **Configure NSX**, add the following NVDS (NSX Virtual Distributed Switch) switches with the indicated settings:
   1. For the `edge-teps` switch:
      * Transport Zone - `tz-vm-overlay`
      * Uplink Profile - `edge-tep-profile`
      * IP Address Type (TEP) - `IPv4`
      * IPv4 Assignment (TEP) - `Use IP Pool`
      * IPv4 Pool - Choose the pool with the name that matches the cluster to which you are deploying the new edge nodes.
      * Click **Select Interface** and choose **VLAN Segment** for **Type**, then select `edge-teps` and click **SAVE**.

   2. For the `edge-private` switch:
      * Transport Zone - `edge-private`
      * Uplink Profile - `edge-private-profile`
      * Click **Select Interface** for `uplink2` and choose **Virtual Switch/Distributed Virtual Portgroup** for **Type**, then select `dpg-edge-uplink` and click **SAVE**.

   3. For the `edge-public` switch:
      * Transport Zone - `edge-public`
      * Uplink Profile - `edge-public-profile`
      * Click **Select Interface** for `uplink2` and choose **Virtual Switch/Distributed Virtual Portgroup** for **Type**, then select `dpg-external` and click **SAVE**.

9. To complete the configuration and start the deployment of the edge node, click **FINISH**.
10. Repeat the previous steps to create an additional NSX edge node for replacing the original (source) node. By default, your configuration has a services edge and a customer edge, but it might include other edges that you deployed.

11. After all new edge nodes are deployed, replace the old nodes with new nodes. For each node pair:
    1. Click the **System** tab and from the left navigation menu, click **Fabric > Nodes > Edge Clusters**.
    2. Under **Actions**, click **Replace Edge Cluster Member**.
    3. Under **Replace**, select the old edge node and under **With**, select the newly deployed edge node.
    4. Click **Save**.

12. Verify that the newly added nodes are correctly configured:
    1. Go to **Networking > Tier-0 Gateways** or **Networking > Tier-1 Gateways** and to the cluster name where the new nodes were added.
    2. Click the active/standby configuration to confirm that the newly added nodes are listed in both the Active and Standby states.

13. After you confirm that all new nodes are working correctly, delete the original (source) nodes:
    1. Click the **System** tab and from the left navigation menu, click **Fabric > Nodes > Edge Transport Nodes**.
    2. Select each of the original nodes and delete them one by one. This step also deletes the old nodes from the vCenter Server cluster.

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
