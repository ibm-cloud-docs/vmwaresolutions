---

copyright:

  years:  2020, 2025

lastupdated: "2025-06-23"

keywords: regulated workloads, regulated workloads order instance, order regulated workloads, regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Additional cluster for workloads
{: #vrw-orderinginstance-wkld-cluster}



For single-zone VMware® instances with a customizable consolidated cluster, you can toggle the **Include a separate cluster for workloads** switch on to deploy a workload cluster. An extra cluster for workloads is required for a management-optimized cluster.

## Cluster name
{: #vrw-orderinginstance-wkld-cluster-name}

By default, the workload cluster name is set to **vrw-_xx_-workload**.

{{site.data.content.orderinginstance-cluster-name-list}}

## Workload capacity
{: #vrw-orderinginstance-wkld-capacity}

* For the **Customizable** capacity, you can choose a Cascade Lake or a Sapphire Rapids CPU model and a RAM size according to your needs.
* For the **Medium** capacity, you get a Cascade Lake server with 32 cores, 2.3 GHz, and 384 GB RAM.
* For the **Large** capacity, you get a Cascade Lake server with 48 cores, 2.4 GHz, and 768 GB RAM.

## CPU model
{: #vrw-orderinginstance-wkld-cpumodel}

Select **Sapphire Rapids** or **Cascade Lake**.

### Sapphire Rapids
{: #vrw-orderinginstance-wkld-sapphire}

{{site.data.content.sapphire-para-intro}}

{{site.data.content.simpletabtable-sapphire}}

{{site.data.content.note-spr-rapids-byol}}

### Cascade Lake
{: #vrw-orderinginstance-wkld-cascade}

{{site.data.content.cascade-para-intro}}

{{site.data.content.simpletabtable-cascade}}

## RAM
{: #vrw-orderinginstance-wkld-cluster-ram}

Various RAM sizes are available depending on the CPU model.

## Number of bare metal servers
{: #vrw-orderinginstance-wkld-bare-metal}

For vSAN™ OSA storage, you can order 4-59 servers. For vSAN ESA storage, you can order 3-59 servers. All servers have the same configuration.

## vSAN configuration
{: #vrw-orderinginstance-wkld-vsan}

* You can choose the type and number of capacity disks according to your requirements.
* If you are a BYOL user, provide your own vSAN license key. Toggle the **BYOL** switch to **Enabled** and enter your license key.

   {{site.data.content.attnnote-byol}}

Review the following settings for vSAN storage.

### Storage architecture
{: #vrw-orderinginstance-wkld-vsan-storage-archi}

{{site.data.content.storage-arch-spr-intro}}

{{site.data.content.storage-arch-spr}}

### Size for vSAN capacity disks
{: #vrw-orderinginstance-wkld-vsan-storage-typesize-capdisks}

Select an option for the capacity disks that you need.

### Number of vSAN capacity disks
{: #vrw-orderinginstance-wkld-vsan-storage-number-capdisks}

Specify the number of capacity disks that you want to add.

### Size for vSAN cache disks
{: #vrw-orderinginstance-wkld-vsan-storage-size-cachedisks}

Review the **Size for vSAN cache disks** value.

### Number of vSAN cache disks
{: #vrw-orderinginstance-wkld-vsan-storage-number-cachedisks}

Review the **Number of vSAN cache disks** value.

## Summary
{: #vrw-orderinginstance-wkld-summary}

Review the vSAN details based on your selected configuration.

## Estimated resources available per cluster
{: #vrw-orderinginstance-wkld-est}

Review the estimated resources available per cluster.

## Networking
{: #vrw-orderinginstance-wkld-net}

Specify the networking type and uplink speed.

### Networking type
{: #vrw-orderinginstance-wkld-net-type}

The networking type is set to **Private network only** by default.

### Uplink speed
{: #vrw-orderinginstance-wkld-uplink}

{{site.data.content.uplink-speed-options-list}}

{{site.data.content.simpletable-uplink-speed-locations-ap}}

{{site.data.content.simpletable-uplink-speed-locations-eur}}

{{site.data.content.simpletable-uplink-speed-locations-naeast}}

{{site.data.content.simpletable-uplink-speed-locations-nasouth}}

## Related links
{: #vrw-orderinginstance-wkld-related}

* [Firewall appliance](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-firewall-appl)
* [Procedure to order {{site.data.keyword.rw}}](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-procedure)
* [{{site.data.keyword.rw}} reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
