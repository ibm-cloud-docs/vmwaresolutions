---

copyright:

  years:  2020, 2022

lastupdated: "2022-02-04"

keywords: vmware regulated workloads, vmware regulated workloads order instance, order vmware regulated workloads, vmware regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Management cluster (Multizone VMware instance only)
{: #vrw-orderinginstance-mgmt-cluster}

## Cluster name
{: #vrw-orderinginstance-mgmt-cluster-name}

The primary (management) cluster name is set to **mcv-_xx_-management** by default. You can also specify a new management cluster name, which must meet the following requirements.

### Management cluster name requirements
{: #vrw-orderinginstance-cluster-name-req}

* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The management cluster name must start with a lowercase alphabetic character.
* The management cluster name must end with a lowercase alphabetic or numeric character.
* The maximum length of the management cluster name is 30 characters.
* The management cluster name must be unique within the regulated workload instance.

## Management capacity
{: #vrw-orderinginstance-mngt-capacity}

* For the **Small** capacity, you get a Cascade Lake server with 20 cores, 2.2 GHz, and 384 GB RAM.
* For the **Customizable** capacity, you can choose the Cascade Lake server and RAM size according to your needs.

## Hosts per site
{: #vrw-orderinginstance-mngt-hosts}

Choose the number of management hosts to be deployed in two availability zones. The hosts are deployed and scaled in pairs (one per site) to ensure appropriate failover capacity. You can order 3 - 20 servers per site.

## vSAN configuration
{: #vrw-orderinginstance-mgmt-vsan}

* For the **Small** capacity, you get two vSAN™ capacity disks 1.9 TB SSD.
* For the **Customizable** capacity, you can choose the type and number of capacity disks according to your needs.

## Estimated resources available per cluster
{: #vrw-orderinginstance-mgmt-est}

Review the estimated resources available per cluster.

## Networking
{: #vrw-orderinginstance-mgmt-net}

Specify the networking type and uplink speed.

### Networking type
{: #vrw-orderinginstance-mgmt-net-type}

The networking type is set to **Private network only** by default.

### Uplink speed
{: #vrw-orderinginstance-mgmt-uplink}

{{site.data.content.uplink-speed-options-cascadelake-list}}

{{site.data.content.simpletable-uplink-speed-locations}}

## Related links
{: #vrw-orderinginstance-mgmt-related}

* [Workload cluster](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-wkld-cluster)
* [Procedure to order VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-procedure)
* [VMware Regulated Workloads reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
