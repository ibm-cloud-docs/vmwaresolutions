---

copyright:

  years:  2022

lastupdated: "2022-09-28"

keywords: cyber recovery, cyber recovery workload cluster, workload cluster cyber recovery, cyber recovery order instance, order cyber recovery, cyber recovery instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Workload cluster
{: #cr_orderinginstance-wkld-cluster}

For VMware® instances with a customizable consolidated cluster, you can optionally select the **Include a separate, additional workload cluster** checkbox to deploy a workload cluster. An extra cluster for workloads is required for a management-optimized cluster.

## Cluster name
{: #cr_orderinginstance-wkld-cluster-cluster-name}

By default, the workload cluster name is set to **vcs-7w-workload**.

{{site.data.content.orderinginstance-cluster-name-list}}

## Workload capacity
{: #cr_orderinginstance-wkld-cluster-wkld-capacity}

* For the **Customizable** capacity, you can choose the Cascade Lake server and RAM size according to your needs.
* For the **Medium** capacity, you get a Cascade Lake server with 32 cores, 2.3 GHz, and 384 GB RAM.
* For the **Large** capacity, you get a Cascade Lake server with 48 cores, 2.4 GHz, and 768 GB RAM.

## Number of bare metal servers
{: #cr_orderinginstance-wkld-cluster-bare-metal-servers}

You can order 4 - 20 servers. All servers have the same configuration.

## vSAN configuration
{: #cr_orderinginstance-wkld-cluster-vsan}

* You can choose the type and number of capacity disks according to your needs.
* Use the IBM-provided VMware license for vSAN by selecting **Include with purchase** or Bring Your Own License (BYOL) by selecting **I will provide** and entering your own license key.

## Estimated resources available per cluster
{: #cr_orderinginstance-wkld-cluster-estimate-resources}

Review the estimated resources available per cluster.

## Networking
{: #cr_orderinginstance-wkld-cluster-networking}

Specify the networking type and uplink speed.

### Networking type
{: #cr_orderinginstance-wkld-cluster-network-type}

The networking type is set to **Private network only** by default.

### Uplink speed
{: #cr_orderinginstance-wkld-cluster-uplink}

{{site.data.content.uplink-speed-options-cascadelake-list}}

{{site.data.content.simpletable-uplink-speed-locations}}

## Related links
{: #cr_orderinginstance-wkld-cluster-related-links}

* [Firewall appliance](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-firewall-appl)
* Procedure to order Cyber recovery
