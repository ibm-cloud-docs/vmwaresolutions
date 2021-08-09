---

copyright:

  years:  2021

lastupdated: "2021-07-16"

keywords: vCenter Server view clusters, vmware multizone, vCenter Server multizone view clusters, view vCenter Server cluster

subcollection: vmwaresolutions

---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:help: data-hd-content-type='help'}
{:support: data-reuse='support'}

# Viewing clusters for vCenter Server instances
{: #vc_viewingclusters}

You can view the summary and detailed information of the clusters that are provisioned in VMware vCenter Server® instances.

## Procedure to view clusters for vCenter Server instances
{: #vc_viewingclusters-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server instances** table, click an instance to view the clusters in it.
3. Click **Infrastructure** on the left navigation pane. In the **Clusters** table, view the summary about the clusters:
  * **Cluster name/type**: The name and type of the cluster. Types include witness, consolidated, workload, and edge services.
  * **ESXi servers**: The number of ESXi servers in the cluster.
  * **Storage**: The type of storage that the cluster uses.
  * **Data center location**: The {{site.data.keyword.cloud_notm}} data center where the cluster is hosted.
  * **Pod**: The pod where the cluster is deployed.
  * **Networking**: Whether **Public and private network** or **Private network only**.
  * **Uplink speed**: Whether 10 Gb or 25 Gb.
  * **Status**: The status of the cluster. The status can have one of the following values:
     * Initializing: The cluster is being created and configured.
     * Modifying: The cluster is being modified.
     * Ready to use: The cluster is ready to use.
     * Deleting: The cluster is being deleted.
     * Deleted: The cluster is deleted.
  * **Actions**: Click the **Delete** icon to delete the cluster.
4. Click a cluster name to view the ESXi server, storage, and network interface details.

| Item | Description |
|:---- |:----------- |
| Name | The name of the ESXi server is in the following format: `<host_prefix><n>.<root_domain>`, where `n` is the sequence of the ESXi server. |
| Hardware | The hardware specification. |
| Credentials | The user name and password to access the ESXi server. |
| Private IP | The private IP address of the ESXi server. |
| Status | The status of the ESXi server, which can be one of the following values:<br> **Added** The ESXi server is added and is ready for use.<br> **Adding** The ESXi server is being added.<br> **Deleting** The ESXi server is being deleted. |
{: caption="Table 1. ESXi server details" caption-side="top"}
{: class="simple-tab-table"}
{: #table1}
{: tab-title="ESXi server details"}
{: tab-group="Cluster details"}

| Item | Description |
|:---- |:----------- |
| CPU | The CPU specification of the ESXi servers in the cluster. |
| Memory | The total memory size of the ESXi servers in the cluster. |
| Customized vSAN disks | The number of vSAN disks in the cluster, including the disk type and capacity. |
| vSAN cache disks | The type and number of vSAN cache disks. |
| Networking |The network interface card (NIC) enablement settings of either Public and Private Network or Private Network Only. |
{: caption="Table 1. Additional ESXi server details" caption-side="top"}
{: class="simple-tab-table"}
{: #table2}
{: tab-title="Additional ESXi server details"}
{: tab-group="Cluster details"}

| Item | Description |
|:---- |:----------- |
| Name | The data store name. |
| Size | The capacity of the storage. |
| IOPS/GB | The performance level of the storage. |
| NFS protocol | The NFS version of the storage. |
| Status | The storage status, which can be one of the following values:<br> **Added** The storage is added and is ready for use.<br> **Adding** The storage is being added.<br> **Deleting** The storage is being deleted. |
{: caption="Table 1. Storage details" caption-side="top"}
{: class="simple-tab-table"}
{: #table3}
{: tab-title="Storage details"}
{: tab-group="Cluster details"}

| Item | Description |
|:---- |:----------- |
| VLAN number | The unique VLAN number.  |
| Description | The description of the VLAN.  |
| Location | The data center location. |
| Primary route | The primary route of the VLAN. |
{: caption="Table 1. Network interface - VLAN details" caption-side="top"}
{: class="simple-tab-table"}
{: #table4}
{: tab-title="Network interface details"}
{: tab-group="Cluster details"}

Click **View resource** to access the VLAN details, including the subnet details and IP details.

| Item | Description |
|:---- |:----------- |
| Name | The subnet name. Click the name to access the subnet details. |
| Type | The type of subnet: primary or portable. |
| Description | The description of the subnet. |
{: caption="Table 2. Network interface - Subnet details" caption-side="top"}
{: class="simple-tab-table"}
{: #vlan-table1}
{: tab-title="Subnet details"}
{: tab-group="Network interface VLAN details"}

| Item | Description |
|:---- |:----------- |
| IP | The IP address. |
| Status | The status of the IP address. |
| Description |The description of the IP address.  |
{: caption="Table 2. Network interface - IP details" caption-side="top"}
{: class="simple-tab-table"}
{: #vlan-table2}
{: tab-title="IP details"}
{: tab-group="Network interface VLAN details"}

## Related links
{: #vc_viewingclusters-related}

* [Viewing vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_viewinginstances)
* [Expanding and contracting capacity for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservers)
