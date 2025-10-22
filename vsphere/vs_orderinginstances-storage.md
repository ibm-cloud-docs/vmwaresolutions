---

copyright:

  years:  2016, 2025

lastupdated: "2025-10-21"

keywords: flexible order instance, order vSphere, order flexible instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Storage (vSAN only)
{: #vs_orderinginstances-storage-settings}



The **Storage** section of your {{site.data.keyword.vcf-flex}} instance order is applicable only if you select the VMware vSAN™ component.

* New instances are provisioned with mirrored M.2 boot drives.
* VMware ESXi™ servers are ordered with a 12-disk chassis and two disks are ordered for caching. The ESXi OS is placed on a single M.2 solid-state drive that does not use a disk bay. These settings are configured by default and cannot be changed.
* You can order more capacity disks by specifying values for **Size for vSAN capacity disks** and **Number of vSAN capacity disks**.

If you do not select the vSAN component for your order, the ESXi servers are ordered with a 12-disk chassis, with two disks for the ESXi operating system (OS).
{: note}

## Storage architecture
{: #vs_orderinginstances-storage-archi}

{{site.data.content.storage-arch-spr-intro}}

{{site.data.content.storage-arch-spr}}

Specify the following settings for the vSAN component:
* **Size for vSAN capacity disks** - Select an option for the capacity disks that you need.
* **Number of vSAN capacity disks** - Specify the number of capacity disks that you want to add.
* Review the **Size for vSAN cache disks** and **Number of vSAN cache disks** values.

## Enable vSAN deduplication and compression
{: #vs_orderinginstance-storage-enable-comp}

vSAN storage depends on the number of servers and your total disk capacity, and the use of deduplication and compression.

The amount of storage reduction from deduplication and compression depends on many factors, including the type of data stored and the number of duplicate blocks. Larger disk groups tend to provide a higher deduplication ratio. For more information, see [Using deduplication and compression](https://techdocs.broadcom.com/us/en/vmware-cis/vsan/vsan/7-0/vsan-adminstration-7-0/increasing-space-efficiency-in-a-vsan-cluster/using-deduplication-and-compression-in-vsan-cluster.html){: external}.
{: note}

## Enable vSAN compression (vSAN ESA only)
{: #vs_orderinginstance-storage-enable-comp-esa}

vSAN storage depends on the number of servers and your total disk capacity, and the use of deduplication. For Sapphire Rapids servers, both vSAN ESA and vSAN OSA are available. However, the **Enable vSAN compression** option is available only for vSAN ESA. For more information, see [Storage architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-storage-settings#vs_orderinginstances-storage-archi).

## Related links
{: #vs_orderinginstances-storage-related}

* [Network interface](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-network-interface-settings)
* [Procedure to order Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-procedure)
