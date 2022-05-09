---

copyright:

  years:  2020, 2022

lastupdated: "2022-04-01"

keywords: vmware regulated workloads, vmware regulated workloads order instance, order vmware regulated workloads, vmware regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Edge services cluster
{: #vrw-orderinginstance-edge}

The **Edge services cluster** section is available for all firewall appliances except for **FortiGate Security Appliance**.

## Cluster name
{: #vrw-orderinginstance-edge-cluster-name}

By default, the edge services cluster name is set to **mcv-_xx_-edge**. You can also specify a new name for the edge services cluster. The edge services cluster name must meet the requirements that are listed in [Cluster name requirements](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance#vrw-orderinginstance-cluster-name-req).

## Data center location (multizone VMware instance only)
{: #vrw-orderinginstance-edge-dc}

The edge services clusters are colocated with the witness and consolidated clusters.

## Compute capacity
{: #vrw-orderinginstance-edge-compute}

For compute capacity, you get a Cascade Lake server with 20 cores, 2.2 GHz, and you also get two cluster hosts and 2 * 3.8 TB SSD storage.

## RAM
{: #vrw-orderinginstance-edge-ram}

You can select a RAM size from 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, and 1.5 TB.

## Uplink speed
{: #vrw-orderinginstance-edge-uplink}

{{site.data.content.uplink-speed-options-cascadelake-list}}

{{site.data.content.simpletable-uplink-speed-locations}}

## Networking type
{: #vrw-orderinginstance-edge-net}

Select either **Public and private network** or **Private network only** for the edge services cluster.

## Related links
{: #vrw-orderinginstance-edge-related}

* [Network interface](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-network-interface)
* [Procedure to order VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-procedure)
* [VMware Regulated Workloads reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)