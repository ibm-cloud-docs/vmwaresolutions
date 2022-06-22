---

copyright:

  years:  2016, 2022

lastupdated: "2022-05-24"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Bare metal server settings
{: #vc_orderinginstance-bare-metal-settings}

Bare metal settings are based on your data center selection and bare metal server configuration. When you size the capacity of your servers, consider your current requirements and include extra capacity to accommodate anticipated growth. For more information about sizing, see [Exporting VMware inventory](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-inventory-export).

## Data center location
{: #vc_orderinginstance-dc}

Select the {{site.data.keyword.cloud}} data center settings. For more information, see [Region and data center locations for resource deployment](/docs/overview?topic=overview-locations).

### Geography
{: #vc_orderinginstance-dc-region}

Select the region where your consolidated cluster or instance is hosted.

### Data center
{: #vc_orderinginstance-dc-location}

Select the {{site.data.keyword.cloud_notm}} data center where the consolidated cluster is hosted.

### Pod
{: #vc_orderinginstance-dc-pod}

Select the {{site.data.keyword.cloud_notm}} data center pod where you want to deploy your resources. Keep the default pod selection if you do not have reasons to prefer a different pod.

## Skylake
{: #vc_orderinginstance-skylake}

{{site.data.content.skylake-para-intro}}

{{site.data.content.skylake-note}}

{{site.data.content.simpletabtable-skylake-nsxt}}

VMware vCenter Server® with NSX-V instances are available for V4.7 and earlier deployments.
{: note}

{{site.data.content.simpletabtable-skylake-nsxv}}


## Cascade Lake
{: #vc_orderinginstance-cascade}

{{site.data.content.cascade-para-intro}}

{{site.data.content.simpletabtable-cascade-nsxt}}

vCenter Server with NSX-V instances are available for V4.7 and earlier deployments.
{: note}

{{site.data.content.simpletabtable-cascade-nsxv}}

## SAP-certified
{: #vc_orderinginstance-sap}

{{site.data.content.sap-para-intro}}

{{site.data.content.simpletabtable-sap-netweaver}}

{{site.data.content.simpletabtable-sap-hana}}


## Number of bare metal servers
{: #vc_orderinginstance-bare-metal-number}

* All servers that you order have the same configuration.
* If you are planning to use vSAN™ storage, you can order 4 - 20 servers.
* If you are planning to use NFS storage, you can order 2 - 20 servers. A limit of three servers applies for VMware NSX-T™ consolidated clusters.
* If you select two bare metal servers for the consolidated cluster, the minimum RAM size for the instance to function properly is 192 GB.
* For production workloads, a minimum of three servers is recommended. For more information, see [Is a two node vCenter Server instance highly available?](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions#is-a-two-node-vcenter-server-instance-highly-available)

## Related links
{: #vc_orderinginstance-bare-metal-related}

* [Storage settings](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-storage-settings)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
