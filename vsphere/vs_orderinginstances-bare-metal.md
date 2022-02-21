---

copyright:

  years:  2016, 2022

lastupdated: "2022-02-01"

keywords: vSphere order cluster, order vSphere, order vSphere cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Bare metal server settings
{: #vs_orderinginstances-bare-metal-settings}

When you size the capacity of your servers, consider your current requirements and include extra capacity to accommodate anticipated growth. For more information about sizing properly, see [Exporting VMware inventory](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-inventory-export).

## Data center location
{: #vs_orderinginstances-dc}

Select the {{site.data.keyword.cloud}} data center settings. For more information, see [Region and data center locations for resource deployment](/docs/overview?topic=overview-locations).

### Geography
{: #vs_orderinginstances-dc-region}

Select the region where the cluster is to be hosted.

### Data center
{: #vs_orderinginstance-dc-location}

Select the {{site.data.keyword.cloud_notm}} data center where the cluster is to be hosted. If you select a VMware vSAN™ component, the location list is filtered by SSD availability.

### Pod
{: #vs_orderinginstance-dc-pod}

Select the {{site.data.keyword.cloud_notm}} data center pod where you want to deploy your resources. Keep the default pod selection if you do not have reasons to prefer a different pod.

## Skylake
{: #vs_orderinginstances-skylake}

For **Skylake** servers, you can choose the following CPU models and a supported RAM size. Options available depend on whether you selected the vSAN component.

Skylake servers are not supported for vSphere® Enterprise Plus 7.0 instances.
{: note}

| CPU model     | RAM sizes     |
|:------------- |:------------- |
| Dual Intel® Xeon® Silver 4110 processor / 16 cores, 2.1 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5120 processor / 28 cores, 2.2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6140 processor / 36 cores, 2.3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
{: caption="Table 1. Options for Skylake bare metal servers" caption-side="top"}

## Cascade Lake
{: #vs_orderinginstance-cascade}

For **Cascade Lake** servers, you can choose the following CPU models and a supported RAM size.

| CPU model     | RAM sizes     |
|:------------- |:------------- |
| Dual Intel Xeon Silver 4210 processor / 20 cores, 2.2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 processor / 32 cores, 2.3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 processor / 40 cores, 2.5 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6250 processor / 16 cores, 3.9 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Platinum 8260 processor / 48 cores, 2.4 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 processor / 80 cores, 2.5 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8260 processor / 96 cores, 2.4 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 2. Options for Cascade Lake bare metal servers" caption-side="top"}

## SAP-certified
{: #vs_orderinginstances-sap}

The **SAP-certified** servers are not available if you selected VMware vSAN previously.
{: note}

For **SAP-certified** servers, you have the following options:
* **NetWeaver**, for which the CPU and RAM size are preset.
* **HANA**, for which you can choose the CPU model and a supported RAM size.

| CPU model     | RAM sizes |
|:------------- |:--------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW192) / 32 cores, 2.3 GHz | 192 GB |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW384) / 32 cores, 2.3 GHz | 384 GB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake, BI.S4.NW768) / 40 cores, 2.5 GHz | 768 GB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.NW1500) / 56 cores, 2.7 GHz | 1.5 TB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.NW3000) / 56 cores, 2.7 GHz | 3 TB |
{: caption="Table 3. Options for SAP-certified bare metal servers - NetWeaver" caption-side="top"}
{: class="simple-tab-table"}
{: #simpletabtable1}
{: tab-title="NetWeaver"}
{: tab-group="SAP-certified Intel servers"}

| CPU model     | RAM sizes |
|:------------- |:--------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake) / 32 cores, 2.3 GHz | 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake) / 40 cores, 2.5 GHz| 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake) / 56 cores, 2.7 GHz | 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8280M processor (Cascade Lake) / 112 cores, 2.7 GHz | 3 TB, 6 TB |
{: caption="Table 3. Options for SAP-certified bare metal servers - HANA" caption-side="top"}
{: #simpletabtable2}
{: tab-title="HANA"}
{: tab-group="SAP-certified Intel servers"}
{: class="simple-tab-table"}

## Number of bare metal servers
{: #vs_orderinginstances-bare-metal-number}

The number of ESXi servers that you want add to the vSphere cluster. All the ESXi servers have the same configuration.

## Related links
{: #vs_orderinginstances-bare-metal-related}

* [Storage settings](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-storage-settings)
* [Procedure to order vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-procedure#vs_orderinginstances-procedure-related)
