---

copyright:

  years:  2020, 2024

lastupdated: "2024-10-04"

keywords: regulated workloads, regulated workloads order instance, order regulated workloads, regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Additional cluster for workloads
{: #vrw-orderinginstance-wkld-cluster}

For single-zone VMware® instances with a customizable consolidated cluster, you can toggle the **Deploy separate workload cluster** switch on to deploy a workload cluster. An extra cluster for workloads is required for a management-optimized cluster.

## Cluster name
{: #vrw-orderinginstance-wkld-cluster-name}

By default, the workload cluster name is set to **vrw-_xx_-workload**.

{{site.data.content.orderinginstance-cluster-name-list}}

## Workload capacity
{: #vrw-orderinginstance-wkld-capacity}

* For the **Customizable** capacity, you can choose a Cascade Lake CPU model and a RAM size according to your needs.
* For the **Medium** capacity, you get a Cascade Lake server with 32 cores, 2.3 GHz, and 384 GB RAM.
* For the **Large** capacity, you get a Cascade Lake server with 48 cores, 2.4 GHz, and 768 GB RAM.









## Number of bare metal servers
{: #vrw-orderinginstance-wkld-bare-metal}

You can order 4-59 servers. All servers have the same configuration.


## vSAN configuration
{: #vrw-orderinginstance-wkld-vsan}

* You can choose the type and number of capacity disks according to your requirements.
* If you are a BYOL user, provide your own vSAN license key. Toggle the **BYOL** switch to **Enabled** and enter your license key.

   {{site.data.content.attnnote-byol}}















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
