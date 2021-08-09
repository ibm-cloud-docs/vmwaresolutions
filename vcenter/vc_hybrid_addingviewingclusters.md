---

copyright:

  years:  2016, 2021

lastupdated: "2021-07-26"

keywords: vCenter Server Hybridity add cluster, view cluster vCenter Server Hybridity, delete cluster vCenter Server Hybridity

subcollection: vmwaresolutions

---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Adding, viewing, and deleting clusters for vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingviewingclusters}

The VMware ESXi™ servers that you configured when you ordered an instance are grouped as **cluster1** by default.

You can add clusters to your VMware vCenter Server® with Hybridity Bundle instance to expand the compute and storage capacity. Within a cluster, manage the ESXi servers for better resource allocation and high availability. When no longer needed, delete the added clusters from your instance.

## Adding clusters to vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingviewingclusters-adding}

### Before you add clusters
{: #vc_hybrid_addingviewingclusters-before-add}

* Whenever possible, add clusters by using the {{site.data.keyword.vmwaresolutions_full}} console because changes that you make on the VMware vSphere® Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. Therefore, add clusters to vCenter Server only for on-premises clusters or clusters that you cannot or do not plan to manage in the {{site.data.keyword.vmwaresolutions_short}} console.
* For instances that were deployed in (or upgraded to) V2.5 and later, the number of clusters, hosts, and VMs determines the maximum limit for the number of clusters you can add. You must remain within the VMware sizing guidelines and limits for your deployment. For more information about maximum limits, see [VMware Configuration Maximums](https://configmax.vmware.com/home){:external}.
* For instances that were deployed in (or upgraded to) V2.3 and V2.4, you can add up to 10 clusters.

### System settings
{: #vc_hybrid_addingviewingclusters-adding-sys-settings}

When you add a cluster for a vCenter Server with Hybridity Bundle instance, you must specify the following settings.

#### Cluster name
{: #vc_hybrid_addingviewingclusters-adding-cluster-name}

The cluster name must meet the following requirements:
* Only alphanumeric and dash (-) characters are allowed.
* The cluster name must start and end with an alphanumeric character.
* The maximum length of the cluster name is 30 characters.
* The cluster name must be unique within the vCenter Server with Hybridity Bundle instance.

#### Data center location
{: #vc_hybrid_addingviewingclusters-adding-dc-location}

The {{site.data.keyword.cloud_notm}} data center location of the cluster is set to the {{site.data.keyword.cloud_notm}} data center of the vCenter Server instance by default. You can deploy the cluster to a different {{site.data.keyword.cloud_notm}} data center than the deployed instance, but you must ensure that the network latency between the two {{site.data.keyword.cloud_notm}} data centers is less than 150 ms. To check the network latency, use a tool such as [Looking Glass](http://lg.softlayer.com/){:external}.

If you deploy the cluster to a different {{site.data.keyword.cloud_notm}} data center or {{site.data.keyword.cloud_notm}} infrastructure pod, three more VLANs are ordered for use with the ordered {{site.data.keyword.cloud_notm}} bare metal servers.

### Bare metal server settings
{: #vc_hybrid_addingviewingclusters-adding-bare-metal}

You can choose **Skylake** or **Cascade Lake**. Options might differ depending on the version that your instance was initially deployed in.

#### Skylake
{: #vc_hybrid_addingviewingclusters-adding-skylake}

When you select **Skylake**, you have options for the **CPU model** and **RAM**.

| CPU model options        | RAM options       |
|:------------- |:------------- |
| Dual Intel® Xeon® Silver 4110 processor / 16 cores total, 2.1 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5120 processor / 28 cores total, 2.2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6140 processor / 36 cores total, 2.3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
{: caption="Table 1. Options for Skylake bare metal servers" caption-side="top"}

#### Cascade Lake
{: #vc_hybrid_addingviewingclusters-adding-cascade}

For the **Cascade Lake** setting, you have options for the **CPU model** and **RAM**.

Cascade Lake bare metal servers are available only for VMware vSphere Enterprise Plus 6.7u3 instances.
{:note}

| CPU model options        | RAM options       |
|:------------- |:------------- |
| Dual Intel Xeon Silver 4210 processor / 20 cores total, 2.2 GHz |64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 processor / 32 cores total, 2.3 GHz |64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 processor / 40 cores total, 2.5 GHz |64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Platinum 8260 processor / 48 cores total, 2.4 GHz |64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 processor / 80 cores total, 2.5 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8260 processor / 96 cores total, 2.4 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 2. Options for Cascade Lake bare metal servers" caption-side="top"}

The Quad Intel Xeon Gold 6248 processor is available if you add new clusters or new ESXi servers for existing hybridity instances.
{:note}

#### Number of bare metal servers
{: #vc_hybrid_addingviewingclusters-adding-bare-metal-number}

* All servers that you order have the same configuration.
* You can order in the range 4 - 59 servers.

### vSAN storage settings
{: #vc_hybrid_addingviewingclusters-adding-vsan-storage-settings}

VMware vSAN™ 6.6 is included with your vCenter Server with Hybridity Bundle instance order. Specify the following vSAN options:
* **Size for vSAN capacity disks**: Select an option for the capacity disks that you need.
* **Number of vSAN capacity disks**: Specify the number of capacity disks that you want to add.
* If you want to add more capacity disks, select the **High performance with Intel Optane** checkbox. This option provides two extra capacity disk bays that are useful for workloads that require less latency and higher IOPS throughput.

  The **High performance with Intel Optane** option is available only for Skylake and Cascade Lake CPU models.
  {:note}

* Review the **Disk Type for vSAN Cache Disks** and **Number of vSAN cache disks** values. These values depend on whether you selected the **High performance with Intel Optane** checkbox.
* **vSAN license**: Select the VMware vSAN 6.6 license edition (Advanced or Enterprise).

### Licensing settings
{: #vc_hybrid_addingviewingclusters-adding-licensing-settings}

IBM-provided licenses for the following VMware components:
  * vSphere Enterprise Plus 6.5u3 or 6.7u3, depending on the cluster that is ordered, which is 6.5 or 6.7
  * vCenter Server 6.5
  * VMware NSX® Service Providers 6.4 (Advanced or Enterprise edition)

### Network interface settings
{: #vc_hybrid_addingviewingclusters-adding-network-interface-settings}

Network interface card (NIC) settings are based on your selection of either **Public and private network** or **Private network only**. The following add-on services require public NICs and aren't available with the private option:

* F5® BIG-IP®
* FortiGate® Virtual Appliance

### Summary
{: #vc_hybrid_addingviewingclusters-adding-order-summary}

Based on your selected configuration for the cluster, the estimated price is instantly generated and displayed in the **Summary** right pane. Click **Pricing details** to generate a PDF document with the price summary for the {{site.data.keyword.vmwaresolutions_short}} resources.

You can also add the provisioned resources to the {{site.data.keyword.cloud_notm}} estimate tool, by clicking **Add to estimate**. The tool is useful if you want to estimate the price of the selected {{site.data.keyword.vmwaresolutions_short}} resources together with other {{site.data.keyword.cloud_notm}} resources that you might consider to purchase.

## Procedure to add clusters to vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingviewingclusters-adding-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server instances** table, click the instance to view the clusters in it.

   Ensure that the instance status is **Ready to use**. Otherwise, you can't add clusters to the instance.
   {:note}

3. Click **Infrastructure** on the left navigation pane and click **Add** at the upper right of the **CLUSTERS** table.
4. On the **Add cluster** page, enter the cluster name.
5. You can host the cluster in a different {{site.data.keyword.cloud_notm}} data center than the one that the instance is hosted in. To do so, under **Bare metal server**, select the **Select a different location** checkbox and choose the {{site.data.keyword.cloud_notm}} data center to host the instance.
6. Select the **CPU model**, the amount of **RAM**, and the **Number of bare metal servers** for the bare metal configuration.
7.  Select **vSAN storage** and specify the disk types for the capacity and cache disks and the number of disks. If you want more storage, select the **High performance with Intel Optane** checkbox.
8. Select the license edition for VMware vSAN for the license configuration.
9. Select the network setting of either **Public and private network** or **Private network only**.
10. On the **Summary** pane, verify the cluster configuration before you add the cluster.
   1. Review the settings for the cluster.
   2. Review the estimated price of the cluster. Click **Pricing details** to generate a PDF summary. To save or print your order summary, click the **Print** or **Download** icon on the upper right of the PDF window.
   3. Click the link or links of the terms that apply to your order, and confirm that you agree with these terms before you add the cluster.
   4. Click **Create**.

### Results after you add clusters to vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingviewingclusters-adding-results}

1. The deployment of the cluster starts automatically and the status of the cluster is changed to **Initializing**. You can check the status of the deployment by viewing the deployment history on the **Summary** page of the instance.
2. When the cluster is ready to use, its status changes to **Ready to use**. The newly added cluster is enabled with vSphere High Availability (HA) and vSphere Distributed Resource Scheduler (DRS).

You can't change the cluster name. Changing the cluster name might cause the add or remove ESXi servers operations in the cluster to fail.
{:important}

## Procedure to view clusters in vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingviewingclusters-viewing-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server instances** table, click the instance to view the clusters in it.
3. Click **Infrastructure** on the left navigation pane. In the **CLUSTERS** table, view the summary about the clusters:
  * **Name**: The name of the cluster.
  * **ESXi servers**: The number of ESXi servers in the cluster.
  * **CPU**: The CPU specification of the ESXi servers in the cluster.
  * **Customized vSAN disks**: The number of vSAN disks in the cluster, including the disk type and capacity.
  * **Memory**: The total memory size of the ESXi servers in the cluster.
  * **Data center location**: The {{site.data.keyword.cloud_notm}} data center where the cluster is hosted.
  * **Pod**: The pod where the cluster is deployed.
  * **Status**: The status of the cluster. The status can have one of the following values:
    * Initializing: The cluster is being created and configured.
    * Modifying: The cluster is being modified.
    * Ready to use: The cluster is ready to use.
    * Deleting: The cluster is being deleted.
    * Deleted: The cluster is deleted.
4. Click a cluster name to view the ESXi servers, storage, and network interface details:

  * ESXi servers details:
     * **Name**: The name of the ESXi server is in the format `<host_prefix><n>.<subdomain_label>.<root_domain>`, where:

       `host_prefix` is the hostname prefix,

       `n` is the sequence of the server,

       `subdomain_label` is the subdomain label, and

       `root_domain` is the root domain name.

     * **Version**: The version of the ESXi server.
     * **Credentials**: The username and password to access the ESXi server.
     * **Private IP**: The private IP address of the ESXi server.
     * **Status**: The status of the ESXi server, which can be one of the following values:
       * Added: The ESXi server is added and is ready for use.
       * Adding: The ESXi server is being added.
       * Deleting: The ESXi server is being deleted.

  * Storage details:
    * **Name**: The data store name.
    * **Size**: The capacity of the storage.
    * **IOPS/GB**: The performance level of the storage.
    * **NFS protocol**: The NFS version of the storage.
  * Network Interface - VLAN details:
    * **VLAN number**: The unique VLAN number.
    * **Description**: The description of the VLAN.
    * **Location**: The data center location.
    * **Primary route**: The primary route of the VLAN.
    Click **View resource** to access the VLAN details.
  * Network Interface - Subnet details:
    * **Name**: The subnet name. Click the name to access the subnet details.
    * **Type**: The type of subnet: primary or portable.
    * **Description**: The description of the subnet.
  * Network Interface - IP details:
    * **IP**: The IP address.
    * **Status**: The status of the IP address.
    * **Description**: The description of the IP address.

## Deleting clusters from vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingviewingclusters-deleting}

You might want to delete a cluster from an instance when it's no longer needed.

### Before you delete
{: #vc_hybrid_addingviewingclusters-deleting-prereq}

* Whenever possible, delete clusters by using the {{site.data.keyword.vmwaresolutions_short}} console because changes that you make on the VMware vSphere Web Client are not synchronized with the {{site.data.keyword.vmwaresolutions_short}} console. Therefore, delete clusters from vCenter Server only for on-premises clusters or clusters that you can't or don't plan to manage in the {{site.data.keyword.vmwaresolutions_short}} console.
* You can delete a single cluster at a time. To delete multiple clusters, you must do it in sequence; waiting for the previous cluster to be deleted before you delete the next cluster.
* Ensure that all nodes in a cluster are powered on and operational before you delete the cluster.
* When you delete a cluster, all VMs (virtual machines) from the cluster are also deleted and they can't be recovered. If you want to keep the VMs, migrate them to other clusters.
* The default cluster can't be deleted.

## Procedure to delete clusters from vCenter Server with Hybridity Bundle instances
{: #vc_hybrid_addingviewingclusters-deleting-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources** from the left navigation pane.
2. In the **vCenter Server instances** table, click the instance that you want to delete clusters from.

   Ensure that the instance is in the **Ready to use** status. Otherwise, you cannot delete clusters from the instance.
   {:note}

3. Click **Infrastructure** on the left navigation pane. In the **CLUSTERS** table, locate the cluster that you want to delete and click the **Delete** icon in the **Actions** column.

## Related links
{: #vc_hybrid_addingviewingclusters-related}

* [Viewing vCenter Server with Hybridity Bundle instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_hybrid_viewinginstances)
* [Expanding and contracting capacity for vCenter Server with Hybridity Bundle instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_hybrid_addingremovingservers)
