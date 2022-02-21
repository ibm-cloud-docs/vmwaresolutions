---

copyright:

  years:  2016, 2022

lastupdated: "2022-01-24"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Cluster name
{: #vc_orderinginstance-mngt-workload-cluster-settings}

VMware vCenter Server® instances are deployed with a consolidated cluster (for VMware vSphere® 7) or a management cluster (for vSphere 6.7), in which all the VMware® management components and user workloads run.

Optionally, for vSphere 7, you can order an additional workload cluster.

For both vSphere 7 and vSphere 6.7, you can order an edge services cluster.

By default, the cluster names are set to the following values:
* For the consolidated cluster (vSphere 7) - **_instance name_-consolidated**
* For the management cluster (vSphere 6.7) - **_instance name_-cluster**
* For the workload cluster (vSphere 6.7) - **_instance name_-workload**
* For the edge services cluster (vSphere 6.7) - **_instance name_-edge**

You can also specify a new name for your clusters. The names must meet the requirements that are listed in [Initial cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance#vc_orderinginstance-cluster-name).

## Related links
{: #vc_orderinginstance-cluster-related}

* [Bare metal server settings](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-bare-metal-settings)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
