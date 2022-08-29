---

copyright:

  years:  2016, 2022

lastupdated: "2022-07-26"

keywords: vSphere order cluster, order vSphere, order vSphere cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Bare metal server
{: #vs_orderinginstances-bare-metal-settings}

When you size the capacity of your servers, consider your current requirements, and include extra capacity to accommodate anticipated growth. For more information about sizing properly, see [Exporting VMware inventory](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-inventory-export).

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

## CPU model and RAM size
{: #vs_orderinginstances-cpumodelram}

### Skylake
{: #vs_orderinginstances-skylake}

For **Skylake** servers, you can choose the following CPU models and a supported RAM size. Options available depend on whether you selected the vSAN component.

Skylake servers are not supported for VMware vSphere® Enterprise Plus 7.0 instances.
{: note}

| CPU model     | Cores     | GHz     | RAM sizes     |
|:------------- |:----------|:--------|:------------- |
| Dual Intel® Xeon® Silver 4110 processor | 16 | 2.1 | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5120 processor | 28 | 2.2 | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6140 processor | 36 | 2.3 | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
{: caption="Table 1. Options for Skylake bare metal servers" caption-side="bottom"}

### Cascade Lake
{: #vs_orderinginstance-cascade}

For **Cascade Lake** servers, you can choose the following CPU models and a supported RAM size.

| CPU model     | Cores     | GHz     | RAM sizes     |
|:------------- |:----------|:--------|:------------- |
| Dual Intel Xeon Silver 4210 processor | 20 | 2.2 | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 processor | 32 | 2.3 | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 processor | 40 | 2.5 | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6250 processor | 16 | 3.9 | 64 GB, 96 GB, 128 GB, 192 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Platinum 8260 processor | 48 | 2.4 | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 processor | 80 | 2.5 | 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8260 processor | 96 | 2.4 | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 2. Options for Cascade Lake bare metal servers" caption-side="bottom"}

### SAP-certified
{: #vs_orderinginstances-sap}

The **SAP-certified** servers are not available if you selected VMware vSAN previously.
{: note}

For **SAP-certified** servers, you have the following options:
* **NetWeaver**, for which the CPU and RAM size are preset.
* **HANA**, for which you can choose the CPU model and a supported RAM size.

| CPU model     | Cores     | GHz     | RAM sizes |
|:------------- |:----------|:--------|:--------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW192) | 32 | 2.3 | 192 GB |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW384) | 32 | 2.3 | 384 GB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake, BI.S4.NW768) | 40 | 2.5 | 768 GB |
| Dual Intel Xeon Platinum 8280 M processor (Cascade Lake, BI.S4.NW1500) | 56 | 2.7 | 1.5 TB |
| Dual Intel Xeon Platinum 8280 M processor (Cascade Lake, BI.S4.NW3000) | 56 | 2.7 | 3 TB |
{: caption="Table 3. Options for SAP-certified bare metal servers - NetWeaver" caption-side="bottom"}
{: class="simple-tab-table"}
{: tab-title="NetWeaver"}
{: tab-group="SAP-certified Intel servers"}
{: #simpletabtable_netweaver}

| CPU model     | Cores     | GHz     | RAM sizes |
|:------------- |:----------|:--------|:--------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake) | 32 | 2.3 | 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake) | 40 | 2.5 | 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Dual Intel Xeon Platinum 8280 M processor (Cascade Lake) | 56 | 2.7 | 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8280 M processor (Cascade Lake) | 112 | 2.7 | 3 TB, 6 TB |
{: caption="Table 3. Options for SAP-certified bare metal servers - HANA" caption-side="bottom"}
{: tab-title="HANA"}
{: tab-group="SAP-certified Intel servers"}
{: class="simple-tab-table"}
{: #simpletabtable_hana}

## Number of bare metal servers
{: #vs_orderinginstances-bare-metal-number}

The number of VMware ESXi™ servers that you want add to the vSphere cluster. All the ESXi servers have the same configuration.

## Related links
{: #vs_orderinginstances-bare-metal-related}

* [Storage](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-storage-settings)
* [Procedure to order vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-procedure#vs_orderinginstances-procedure-related)
