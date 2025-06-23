---

copyright:

  years:  2020, 2025

lastupdated: "2025-06-23"

keywords: regulated workloads, regulated workloads order instance, order regulated workloads, regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Primary cluster
{: #vrw-orderinginstance-consldt-cluster}



## Cluster name
{: #vrw-orderinginstance-consldt-cluster-name}

By default, the primary cluster name is set to **vrw-_xx_-management**.

{{site.data.content.orderinginstance-cluster-name-list}}

## Cluster type
{: #vrw-orderinginstance-consldt-capacity}

You can start with a smaller footprint by deploying a consolidated management and workload cluster, or you can deploy a management cluster and a separate cluster for workloads.

* **Management-optimized cluster** supports separate management and workload clusters.

   If you don't want workloads to run on the primary cluster, select this option. With this option, you get a 2-CPU Intel® Cascade Lake processor with 20 cores, 2.2 GHz, and 192 GB RAM per bare metal server. You must include a separate cluster for workloads. Under **Additional cluster for workloads**, complete the settings to customize the bare metal hardware based on your workload capacity requirements.

* **Customizable consolidated cluster** supports a range of CPU and RAM options to optimize capacity for both management and workload clusters.

   You can choose a Cascade Lake CPU model and a RAM size according to your needs. This option brings down the entry price point by enabling workloads to run alongside VMware® management components in the same cluster. You can start with only 6 hosts instead of 10. This option is helpful for proof of concepts (POCs) or if you want to start small and grow over time.

## CPU model
{: #vrw-orderinginstance-consldt-cpumodel}

Select **Sapphire Rapids** or **Cascade Lake**.

### Sapphire Rapids
{: #vrw-orderinginstance-consldt-sapphire}

{{site.data.content.sapphire-para-intro}}

{{site.data.content.simpletabtable-sapphire}}

{{site.data.content.note-spr-rapids-byol}}

### Cascade Lake
{: #vrw-orderinginstance-consldt-cascade}

{{site.data.content.cascade-para-intro}}

{{site.data.content.simpletabtable-cascade}}

## RAM
{: #vrw-orderinginstance-consldt-cluster-ram}

Various RAM sizes are available depending on the CPU model.

## Number of bare metal servers
{: #vrw-orderinginstance-consldt-bare-metal}

For vSAN™ OSA storage, you can order 4-59 servers. For vSAN ESA storage, you can order 3-59 servers. All servers have the same configuration.

## vSAN configuration
{: #vrw-orderinginstance-consldt-vsan}

Review the following settings for vSAN storage.

### Storage architecture
{: #vrw-orderinginstance-consldt-vsan-storage-archi}

{{site.data.content.storage-arch-spr-intro}}

{{site.data.content.storage-arch-spr}}

### Size for vSAN capacity disks
{: #vrw-orderinginstance-consldt-vsan-storage-typesize-capdisks}

Select an option for the capacity disks that you need.

### Number of vSAN capacity disks
{: #vrw-orderinginstance-consldt-vsan-storage-number-capdisks}

Specify the number of capacity disks that you want to add.

### Size for vSAN cache disks
{: #vrw-orderinginstance-consldt-vsan-storage-size-cachedisks}

Review the **Size for vSAN cache disks** value.

### Number of vSAN cache disks
{: #vrw-orderinginstance-consldt-vsan-storage-number-cachedisks}

Review the **Number of vSAN cache disks** value.

## Summary
{: #vrw-orderinginstance-consldt-summary}

Review the vSAN details based on your selected configuration.

## Estimated resources available per cluster
{: #vrw-orderinginstance-consldt-est}

Review the estimated resources available per cluster.

## Networking
{: #vrw-orderinginstance-consldt-net}

Specify the networking type and uplink speed.

### Networking type
{: #vrw-orderinginstance-consldt-net-type}

The networking type is set to **Private network only** by default.

### Uplink speed
{: #vrw-orderinginstance-consldt-uplink}

{{site.data.content.uplink-speed-options-list}}

{{site.data.content.simpletable-uplink-speed-locations-ap}}

{{site.data.content.simpletable-uplink-speed-locations-eur}}

{{site.data.content.simpletable-uplink-speed-locations-naeast}}

{{site.data.content.simpletable-uplink-speed-locations-nasouth}}

## Related links
{: #vrw-orderinginstance-primary-related}

* [Procedure to order {{site.data.keyword.rw}}](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-procedure)
* [{{site.data.keyword.rw}} reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
