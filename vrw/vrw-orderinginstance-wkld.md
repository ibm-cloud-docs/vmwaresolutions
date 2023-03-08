---

copyright:

  years:  2020, 2023

lastupdated: "2023-02-17"

keywords: vmware regulated workloads, vmware regulated workloads order instance, order vmware regulated workloads, vmware regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Workload cluster
{: #vrw-orderinginstance-wkld-cluster}

For single-zone VMware® instances with a customizable consolidated cluster, you can optionally select the **Include a separate cluster for workloads** checkbox to deploy a workload cluster. An extra cluster for workloads is required for a management-optimized cluster.

## Cluster name
{: #vrw-orderinginstance-wkld-cluster-name}

By default, the workload cluster name is set to **vrw-_xx_-workload** for single-zone VMware virtual data centers and is set to **mcv-_xx_-workload** for multizone VMware virtual data centers.

{{site.data.content.orderinginstance-cluster-name-list}}

## Workload capacity
{: #vrw-orderinginstance-wkld-capacity}

* For the **Customizable** capacity, you can choose the Cascade Lake server and RAM size according to your needs.
* For the **Medium** capacity, you get a Cascade Lake server with 32 cores, 2.3 GHz, and 384 GB RAM.
* For the **Large** capacity, you get a Cascade Lake server with 48 cores, 2.4 GHz, and 768 GB RAM.

## Number of bare metal servers (Single-zone VMware instance only)
{: #vrw-orderinginstance-wkld-bare-metal}

You can order 4 - 20 servers. All servers have the same configuration.

## Hosts per site (Multizone VMware instance only)
{: #vrw-orderinginstance-wkld-hosts}

Choose the number of vSAN™ stretched cluster resource hosts to be deployed in two availability zones. The hosts must be deployed and scaled in pairs (one per site).

## vSAN configuration
{: #vrw-orderinginstance-wkld-vsan}

* You can choose the type and number of capacity disks according to your needs.
* For single-zone VMware instance only - Use the IBM-provided VMware license for vSAN by selecting **Include with purchase**. 

Bring Your Own License (BYOL) is no longer supported except for migrations or upgrades of existing BYOL clusters. Select **I will provide** and enter your own license key only if you are performing an upgrade or migration of an existing BYOL cluster.
{: important}

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

{{site.data.content.uplink-speed-options-cascadelake-list}}

{{site.data.content.simpletable-uplink-speed-locations}}

## Related links
{: #vrw-orderinginstance-wkld-related}

* [Firewall appliance](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-firewall-appl)
* [Procedure to order VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-procedure)
* [VMware Regulated Workloads reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
