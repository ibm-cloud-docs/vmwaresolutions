---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-11"

---

# Adding and viewing clusters for vCenter Server instances

You can add clusters to your VMware vCenter Server instances to expand the compute and storage capacity. Within a cluster, you can manage ESXi servers for better resource allocation and high availability. Use this procedure to add or view clusters for the vCenter Server instances that you ordered.

## Before you begin

The ESXi servers that you configured when you ordered an instance are grouped as **cluster1** by default. You can add up to five clusters to an instance.

When you add a cluster for a vCenter Server instance, you must specify or review the following settings:
* **Cluster Name**: The cluster name must meet the following requirements:
  * Only alphanumeric and dash (-) characters are allowed.
  * The cluster name must start and end with an alphanumeric character.
  * The maximum length of the cluster name is 30 characters.
  * The cluster name must be unique within the vCenter Server instance.
* **Bare Metal Server Configuration**: The bare metal server specification options available to you depend on the data center location of the vCenter Server instance. You can select a specification that is different from the specification of the default cluster.
* **Number of Bare Metal Servers**: A minimum of 2 bare metal servers is required for a cluster. You can add up to 20 bare metal servers for a cluster. All bare metal servers share the same configuration.
* **Data Center Location**: The data center location of the cluster is same with the one of the vCenter Server instance. You cannot change it.
* **Storage**: You can add file-level shared storage for the cluster and specify the following settings:
  * **Number of File Shares**: Specify the number of file shares for the shared storage that you want to add. The number of file shares
  must be in the range 1 - 32. <!-- the range to change to 1 - 32 per github 3545 -->
  * **Size**: Select the capacity that meets your shared storage needs.
  * **Performance**: Select the IOPS (Input/output Operations Per Second) per GB based on your workload requirements. The performance
  levels available to you depend on the size you selected and the data center location.
  * **NFS Version**: Select the appropriate NFS (Network File System) version according to your needs. NFS v4.1 includes multiple paths
  to the shared NAS (Network Attached Storage) array, but does not support SDRS (Storage Distributed Resource Scheduler) or SIOC
  (Storage I/O Control). NFS v3 supports SDRS and SIOC, but does not include NFS multipathing.

## Procedure

1. Click **Deployed Instances** from the left navigation pane. Click the **vCenter Server** tab.
2. Click the instance to view the clusters in it or to add clusters to it.

   **Note**: If you want to add clusters to this instance, ensure that the instance is in the **Ready to Use** status. Otherwise, you cannot add clusters to the instance.
3. Click the **Infrastructure** tab. View the summary about the clusters:
   * **Name**: The name of the cluster.
   * **ESXi servers**: The number of ESXi servers in the cluster.
   * **CPU**: The CPU specification of the ESXi servers in the cluster.
   * **Memory**: The total memory size of the ESXi servers in the cluster.
   * **Status**: The status of the cluster. The status can have one of the following values:
     <dl class="dl">
         <dt class="dt dlterm">Initializing</dt>
         <dd class="dd">The cluster is being created and configured.</dd>
         <dt class="dt dlterm">Modifying</dt>
         <dd class="dd">The cluster is being modified.</dd>
         <dt class="dt dlterm">Ready to Use</dt>
         <dd class="dd">The cluster is ready to use.</dd>
     </dl>
4. To add a cluster, click **Add**, and then complete the following steps in the **Add Cluster** area:
   1. Enter the cluster name.
   2. Select the bare metal server specification. If selecting **User customized**, enter the CPU and RAM specifications based on your requirements.
   3. Specify the number of bare metal servers.
   4. Review the data center location that is automatically filled in.
   5. Under **Storage**, configure the file-level shared storage by selecting the number, size, performance, and NFS version.
   6. Click **Calculate Price** under **Estimated Cost** to get the pricing of your order.
   7. Review the estimated cost of the cluster by clicking the price link under **Estimated Cost**. To save or print your order summary,
   click the **Print** or **Download** icon on the upper right of the PDF window.
   8. Click **Add**.

5. After the cluster is ready to use, you can click the cluster name to view its details:
   * The list of ESXi servers with their details:
     * **Name**: The name of the ESXi server is in the format `hostname.vmonic.local`, where:

       `hostname` is the host name in the format `instancename-esxn`, where `instancename` is the name of the instance and `n` is the sequence of the server.

       `vmonic.local` is the domain name.
     * **Version**: The version of the ESXi server.
     * **Credentials**: The user name and password to access the ESXi server.
     * **Private IP**: The private IP address of the ESXi server.
     * **Status**: The status of the ESXi server, which can be one of the following values:
        <dl class="dl">
        <dt class="dt dlterm">Active</dt>
        <dd class="dd">The ESXi server is ready for use. </dd>
        <dt class="dt dlterm">Deleting</dt>
        <dd class="dd">The ESXi server is being deleted.</dd>
        </dl>
   * The storage details:
     * **Name**: The data store name.
     * **Size**: The capacity of the storage.
     * **IOPS/GB**: The performance level of the storage.
     * **NFS protocol**: The NFS version of the storage.

## Results

The deployment of the cluster starts automatically and the status of the cluster is changed to **Initializing**. You can check the status of the deployment by viewing the deployment history from the **Summary** tab on the instance details page. When the cluster is ready to use, its status changes to **Ready to Use**. The newly added cluster is enabled with vSphere High Availability (HA) and vSphere Distributed Resource Scheduler (DRS).

**Important**: You cannot change the cluster name. Changing the cluster name might cause the add or remove ESXi servers operations in the cluster to fail.

## Removing clusters

**Important**: You cannot remove a cluster from the instance it was added to. To remove clusters, you must delete the vCenter Server instance in which they are located.

## Related links

* [Viewing vCenter Server instances](vc_viewinginstances.html)
* [Expanding and contracting capacity for vCenter Server instances](vc_addingremovingservers.html)
