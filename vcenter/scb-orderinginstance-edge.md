---

copyright:

  years:  2021, 2022

lastupdated: "2022-02-01"

keywords: order Security and Compliance Readiness Bundle, order scb instances, order vcs scb
subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Edge services cluster
{: #scb-orderinginstance-edge}

You must order a dedicated cluster for the network edge and you can select any custom firewall component of your choice.

Review the following restrictions for edge services clusters:
* The data center of the consolidated cluster must be available for edge services cluster deployment. Edge services cluster deployment is not supported for **Dallas 09** and **Hong Kong 02**.
* You cannot add more than one edge services cluster in the same data center pod. If you are adding multiple edge services clusters in the same pod, the clusters would share a transit VLAN, which might cause subsequent issues with the Juniper® vSRX installation.

## Cluster name
{: #scb-orderinginstance-edge-cluster-name}

The edge service cluster name must meet the requirements that are listed in [Cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance#vc_orderinginstance-cluster-name).

## Data center location
{: #scb-orderinginstance-edge-dc}

The edge services cluster is deployed in the consolidated cluster.

## Compute capacity
{: #scb-orderinginstance-edge-compute}

* Cores - 20
* RAM - 64 GB
* Cluster hosts - 2

## Networking type
{: #scb-orderinginstancee-edge-private-nics}

Select either **Public and private network** or **Private network only** for the edge services cluster.

## Related links
{: #scb-orderinginstance-edge-related}

* [Network interface settings](/docs/vmwaresolutions?topic=vmwaresolutions-scb-orderinginstance-services)
* [Procedure to order VMware Security and Compliance Readiness Bundle](/docs/vmwaresolutions?topic=vmwaresolutions-scb-orderinginstance-procedure)
