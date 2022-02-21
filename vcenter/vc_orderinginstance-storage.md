---

copyright:

  years:  2016, 2022

lastupdated: "2022-01-24"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Storage settings
{: #vc_orderinginstance-storage-settings}

Storage settings are based on your selection of bare metal server configuration and the storage type.

For deployed instances, you can add NFS storage shares to an existing NFS or vSAN™ cluster. For more information, see [Adding NFS storage to vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingnfs).

## vSAN storage
{: #vc_orderinginstance-vsan-storage}

vSAN is available for the **Skylake** and **Cascade Lake** bare metal configurations only.

### Size for vSAN capacity disks
{: #vc_orderinginstance-vsan-storage-typesize-capdisks}

Select an option for the capacity disks that you need.

### Number of vSAN capacity disks
{: #vc_orderinginstance-vsan-storage-number-capdisks}

Specify the number of capacity disks that you want to add.

* For VMware vSphere® 7.0, order up to 10 disks for Dual CPU models and order up to 8 disks for Quad CPU models.
* For vSphere 6.3, order up to 12 disks with Intel Optane for Dual CPU models and order up to 8 disks for Quad CPU models.

If you want to add more capacity disks, select the **High performance with Intel Optane** checkbox. This option provides two extra capacity disk bays, which are useful for workloads that require less latency and higher IOPS throughput.

The **High performance with Intel Optane** option is available only for vSphere 6 instances.
{: note}

### Size for vSAN cache disks
{: #vc_orderinginstance-vsan-storage-size-cachedisks}

Review the **Size for vSAN cache disks** value. The value depends on whether you selected the **High performance with Intel Optane** checkbox.

### Number of vSAN cache disks
{: #vc_orderinginstance-vsan-storage-number-cachedisks}

Review **Number of vSAN cache disks**. The value depends on whether you selected the **High performance with Intel Optane** checkbox.

### Enable vSAN deduplication and compression
{: #vc_orderinginstance-vsan-storage-enable-comp}

vSAN storage depends on the number of servers and your total disk capacity, and the use of deduplication and compression.

The amount of storage reduction from deduplication and compression depends on many factors, including the type of data stored and the number of duplicate blocks. Larger disk groups tend to provide a higher deduplication ratio. For more information, see [Using deduplication and compression](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.vsan.doc/GUID-3D2D80CC-444E-454E-9B8B-25C3F620EFED.html){: external}.
{: note}

### vSAN license
{: #vc_orderinginstance-vsan-storage-license}

Use the IBM-provided VMware license for the vSAN component by selecting **Include with purchase**, or Bring Your Own License (BYOL) by selecting **I will provide** and entering your own license key.

If your initial cluster is a vSAN cluster, any additional vSAN clusters use the same vSAN license and have the same configuration as the initial one. This statement is also true for any initial or additional clusters in the instance for which you select vSAN. The first time you're prompted for the vSAN license (BYOL or purchased) and the edition. The next time that you select vSAN for a new cluster, the license that is chosen initially is reused.

## NFS storage
{: #vc_orderinginstance-nfs-storage}

When you select **NFS storage**, you can add file-level shared storage for your instance where all shares use the same settings or you can specify different configuration settings for each file share. The number of file shares must be in the range 1 - 100.

Specify the following NFS options:
* **Configure shares individually** - Select to specify different configuration settings for each file share.
* **Number of shares** - When you use the same configuration setting for each file share, specify the number of file shares for the NFS shared storage that you want to add.
* **Size (GB)** - Select the capacity that meets your shared storage needs.
* **Performance** - Select the IOPS (input/output operations per second) per GB based on your workload requirements.
* **Add shared storage** - Select to add individual file shares that use different configuration settings.

Choose performance level options according to your needs.

| Option       | Details       |
|:------------ |:------------- |
| 0.25 IOPS/GB | This option is designed for workloads that are not used often. For example, vaulted data, hosting large databases with legacy data, or virtual disk images of virtual memory system as backup. |
| 2 IOPS/GB | This option is designed for most general-purpose workloads. For example, hosting small databases, backing up web applications, or virtual machine disk images for a hypervisor. |
| 4 IOPS/GB | This option is designed for higher-intensity workloads that have a high percentage of active data at a time. For example, transactional databases. |
| 10 IOPS/GB | This option is designed for the most demanding workload types, such as analytics. For example, high-transaction databases and other performance-sensitive databases. This performance level is limited to a maximum capacity of 4 TB per file share. |
{: caption="Table 1. NFS performance level options" caption-side="top"}

## Local disks (NSX-V SAP-certified HANA only)
{: #vc_orderinginstance-local-disks}

The **Local disks** option is enabled for the **SAP-certified** - **HANA** CPU generation only.
{: note}

Specify the following settings:
* **Local disk count** - Select the number of disks that you want to add. The first two disks are reserved, so a minimum of four disks is required.
* **Local disk type** - Select an option for the disk type that you need.

## Related links
{: #vc_orderinginstance-storage-related}

* [Edge services cluster](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-edge-services-cluster)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
