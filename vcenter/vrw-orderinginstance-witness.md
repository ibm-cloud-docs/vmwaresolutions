---

copyright:

  years:  2020, 2022

lastupdated: "2022-04-01"

keywords: vmware regulated workloads, vmware regulated workloads order instance, order vmware regulated workloads, vmware regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Witness cluster (Multizone VMware instance only)
{: #vrw-orderinginstance-witness-cluster}

## Cluster name
{: #vrw-orderinginstance-witness-cluster-name}

The witness cluster name is set to **mcv-_xx_-witness** by default, where _xx_ represents two randomly generated alphabetic characters. You can also specify a new witness cluster name, which must meet the following requirements.

## Witness cluster name requirements
{: #vrw-orderinginstance-witness-cluster-req}

* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The witness cluster name must start with a lowercase alphabetic character.
* The witness cluster name must end with a lowercase alphabetic or numeric character.
* The maximum length of the witness cluster name is 30 characters.
* The witness cluster name must be unique within the regulated workload instance.

## CPU model and RAM
{: #vrw-orderinginstance-witness-cluster-compute}

You can choose the following CPU models and a supported RAM size:

| CPU model | RAM |
|:--------- |:--- |
| Dual Intel® Xeon® Silver 4210 (Cascade Lake) / 20 cores, 2.2 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 (Cascade Lake) / 32 cores, 2.3 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 (Cascade Lake) / 40 cores, 2.5 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6250 (Cascade Lake) / 16 cores, 3.9 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Platinum 8260 (Cascade Lake) / 48 cores, 2.4 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 (Cascade Lake) / 80 cores, 2.5 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8260 (Cascade Lake) / 96 cores, 2.4 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 1. Options for Cascade Lake bare metal servers" caption-side="top"}

## Number of bare metal servers
{: #vrw-orderinginstance-witness-cluster-bare-metal}

You can order 3 - 30 servers. All servers have the same configuration.

## vSAN configuration
{: #vrw-orderinginstance-witness-cluster-vsan}

Specify the following settings for vSAN configuration.

### Size for vSAN capacity disks
{: #vrw-orderinginstance-witness-cluster-vsan-disktype}

Select an option for the capacity disks that you need.

### Number of vSAN capacity disks
{: #vrw-orderinginstance-witness-cluster-vsan-diskcount}

Specify the number of capacity disks that you want to add.

## Estimated resources available per cluster
{: #vrw-orderinginstance-witness-cluster-est}

Review the estimated resources available per cluster.

## Networking
{: #vrw-orderinginstance-witness-cluster-net}

Specify the networking type and uplink speed.

### Networking type
{: #vrw-orderinginstance-witness-cluster-net-type}

The networking type is set to **Private network only**.

### Uplink speed
{: #vrw-orderinginstance-witness-uplink}

{{site.data.content.uplink-speed-options-cascadelake-list}}

| Geography | Data center | Pod |
|:--------- |:----------- |:--- |
| Asia-Pacific | TOK02 | 02 |
| Asia-Pacific | TOK04 | 01 |
| Asia-Pacific | TOK05 | 01 |
| Europe | FRA02 | 02 |
| Europe | FRA05 | 01 |
| Europe | LON04 | 01 |
| Europe | LON06 | 01 |
| NA East | TOR04 | 01 |
| NA East | WDC04 | 05 |
| NA East | WDC06 | 01 |
| NA East | WDC07 | 01 |
| NA South | DAL10 | 03 |
| NA South | DAL12 | 01 |
| NA South | DAL13 | 02 |
{: caption="Table 2. Available locations for 25 Gb uplink speed" caption-side="top"}

## Related links
{: #vrw-orderinginstance-whitness-related}

* [Management cluster (Multizone VMware instance only)](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-mgmt-cluster)
* [Procedure to order VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-procedure)
* [VMware Regulated Workloads reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)