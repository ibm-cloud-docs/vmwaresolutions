---

copyright:

  years:  2022

lastupdated: "2022-11-21"

keywords: cyber recovery, cyber recovery cluster, cyber recovery cluster type, cyber recovery instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Primary cluster
{: #cr_orderinginstance-consldt-cluster}

## Cluster name
{: #cr-orderinginstance-consldt-cluster-name}

By default, the primary cluster name is set to **vrw-_xx_-management**.

{{site.data.content.orderinginstance-cluster-name-list}}

## Cluster type
{: #cr_orderinginstance-consldt-capacity}

You can start with a smaller footprint by deploying a consolidated management and workload cluster, or you can deploy a management cluster and a separate cluster for workloads.

* **Management-optimized cluster** supports separate management and workload clusters.

   If you don't want workloads to run on the primary cluster, select this option. With this option, you get a 2-CPU Intel® Cascade Lake processor with 20 cores, 2.2 GHz, and 192 GB RAM per bare metal server. You must include a separate cluster for workloads. Under **Additional cluster for workloads**, complete the settings to customize the bare metal hardware based on your workload capacity requirements.

* **Customizable consolidated cluster** supports a range of CPU and RAM options to optimize capacity for both management and workload clusters.

   You can choose the Cascade Lake server and RAM size according to your needs. This option brings down the entry price point by enabling workloads to run alongside VMware® management components in the same cluster. You can start with only 6 hosts instead of 10. This option is helpful for proof of concepts (POCs) or if you want to start small and grow over time.

## Number of bare metal servers
{: #cr_orderinginstance-consldt-bare-metal}

You can order 4 - 20 servers. All servers have the same configuration.

## vSAN configuration
{: #cr_orderinginstance-consldt-vsan}

* For the **Small** capacity, you get two vSAN™ capacity disks 1.9 TB SSD.
* For the **Customizable** capacity, you can choose the type and number of capacity disks according to your needs.
* You can use the IBM-provided VMware license for vSAN by selecting **Include with purchase**, or Bring Your Own License (BYOL) by selecting **I will provide** and entering your own license key.

## Estimated resources available per cluster
{: #cr_orderinginstance-consldt-est}

Review the estimated resources available per cluster.

## Networking
{: #cr_orderinginstance-consldt-net}

Specify the networking type and uplink speed.

### Networking type
{: #cr_orderinginstance-consldt-net-type}

The networking type is set to **Private network only** by default.

### Uplink speed
{: #cr_orderinginstance-consldt-uplink}

{{site.data.content.uplink-speed-options-cascadelake-list}}

{{site.data.content.simpletable-uplink-speed-locations}}
