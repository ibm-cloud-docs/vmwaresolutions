---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-05"

---

# Adding and viewing clusters for vCenter Server instances

You can add clusters to your VMware vCenter Server instances to expand the compute and storage capacity. Within a cluster, you can manage ESXi servers for better resource allocation and high availability. Use this procedure to add or view clusters for the vCenter Server instances that you ordered.

## Before you begin

The ESXi servers that you configured when you ordered an instance are grouped as **cluster1** by default. You can add up to five clusters to an instance.

When you add a cluster for a vCenter Server instance, you must specify or review the following settings.

## System settings

### Cluster Name

The cluster name must meet the following requirements:
* Only alphanumeric and dash (-) characters are allowed.
* The cluster name must start and end with an alphanumeric character.
* The maximum length of the cluster name is 30 characters.
* The cluster name must be unique within the vCenter Server instance.

### Bare Metal Server Configuration

You can select a Bare Metal Server specification that is different from the specification of the default cluster. If you selected **User customized**, you must specify the CPU model and RAM for the bare metal server.

Table 1. CPU and RAM options

| Item        | Options       |
|:------------- |:------------- |
| CPU | <ul><li>Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.10 GHz</li><li>Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.20 GHz</li><li>Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.60 GHz</li></ul>|
| RAM | 64 GB, 128 GB, 256 GB, 384 GB, 512 GB, 768 GB, 1.5 TB|   

### Number of Bare Metal Servers

A minimum of 2 bare metal servers is required for a cluster. You can add up to 20 bare metal servers for a cluster. All bare metal servers share the same configuration.

### Data Center Location

By default, the data center location of the cluster is set to the data center of the vCenter Server instance.

For V1.9 and later, you can deploy the cluster to a different data center than the deployed instance. Ensure that there is less than a 150 ms network latency between the two data centers. If deploying to a different IBM Cloud data center, or Bluemix Infrastructure (SoftLayer) pod, three additional VLANs will be ordered for use with the ordered bare metal servers.

## Storage settings

You can add file-level shared storage for the cluster and specify the following settings.

### Number of File Shares

Specify the number of file shares for the shared storage that you want to add. The number of file shares must be in the range 1 - 32.

### Size

Select the capacity that meets your shared storage needs.

### Performance

Select the IOPS (Input/output Operations Per Second) per GB based on your workload requirements. The performance levels available to you depend on the size you selected and the data center location.

<!--### NFS Version

NFS (Network File System) v3 is set by default and you cannot change it. NFS v3 supports SDRS (Storage Distributed Resource Scheduler) and SIOC (Storage I/O Control), but does not include NFS multipathing.-->

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
   2. Select the bare metal server specification.
   3. If you selected **User customized**, select the CPU and RAM specifications based on your requirements.
   4. Specify the number of bare metal servers.
   5. Review the data center location that is automatically filled in.

   You can select a different data center other than the data center where the instance is deployed.  If you select a user-customized hardware configuration, you can deploy to a different Bluemix Infrastructure (SoftLayer) pod for data centers containing additional pods. This is useful if the default Bluemix Infrastructure (SoftLayer) pod where the initial instance is deployed has reached capacity. Pre-built, standardized **Small**, **Medium**, and **Large** bare metal server options use a default pod that cannot be changed.

   6. Under **Storage**, configure the file-level shared storage by selecting the number, size, and performance.
   7. Click **Calculate Price** under **Estimated Cost** to get the pricing of your order.
   8. Review the estimated cost of the cluster by clicking the price link under **Estimated Cost**. To save or print your order summary,
   click the **Print** or **Download** icon on the upper right of the PDF window.
   9. Click **Add**.

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
