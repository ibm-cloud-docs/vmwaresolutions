---

copyright:
  years: 2022

lastupdated: "2022-04-20"

keywords: IBM Cloud for VMware Solutions, getting started, vmware solutions offerings, services for vmwaresolutions, vmwaresolutions use cases

subcollection: vmwaresolutions

content-type: conref

---

{{site.data.keyword.attribute-definition-list}}

# Content references for vmwaresolutions subcollection
{: #conref-vmwaresolutions}

Conref section START.

INFORMATION:
The section is referenced by the following files:
- vcenter\vc_orderinginstance-bare-metal.md
- vcenter\vc_addingclusters.md

CONTENT:

For **Skylake** servers, you can choose the following CPU models and a supported RAM size, which depends on the NSX networking solution.
{: #skylake-para-intro}

Skylake servers are not supported for VMware vSphere® Enterprise Plus 7.0u1 instances.
{: note}
{: #skylake-note}

| CPU model     | RAM sizes   |
|:------------- |:----------- |
| Dual Intel® Xeon® Silver 4110 processor / 16 cores, 2.1 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5120 processor / 28 cores, 2.2 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6140 processor / 36 cores, 2.3 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
{: caption="Table 1. Options for Skylake bare metal servers - NSX-T instances" caption-side="top"}
{: class="simple-tab-table"}
{: tab-title="NSX-T instances"}
{: tab-group="SkyLake Intel servers"}
{: #simpletabtable-skylake-nsxt}


| CPU model     | RAM sizes   |
|:------------- |:----------- |
| Dual Intel® Xeon® Silver 4110 processor / 16 cores, 2.1 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5120 processor / 28 cores, 2.2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6140 processor / 36 cores, 2.3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
{: caption="Table 1. Options for Skylake bare metal servers - NSX-V instances" caption-side="top"}
{: class="simple-tab-table"}
{: tab-title="NSX-V instances"}
{: tab-group="SkyLake Intel servers"}
{: #simpletabtable-skylake-nsxv}


For **Cascade Lake** servers, you can choose the following CPU models and a supported RAM size, which depends on the NSX networking solution.
{: #cascade-para-intro}

| CPU model     | RAM sizes   |
|:------------- |:----------- |
| Dual Intel Xeon Silver 4210 processor / 20 cores, 2.2 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 processor / 32 cores, 2.3 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 processor / 40 cores, 2.5 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6250 processor / 16 cores, 3.9 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Platinum 8260 processor / 48 cores, 2.4 GHz | 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 processor / 80 cores, 2.5 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8260 processor / 96 cores, 2.4 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 2. Options for Cascade Lake bare metal servers - NSX-T instances" caption-side="top"}
{: class="simple-tab-table"}
{: tab-title="NSX-T instances"}
{: tab-group="Cascade Lake Intel servers"}
{: #simpletabtable-cascade-nsxt}


| CPU model     | RAM sizes   |
|:------------- |:----------- |
| Dual Intel Xeon Silver 4210 processor / 20 cores, 2.2 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 5218 processor / 32 cores, 2.3 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6248 processor / 40 cores, 2.5 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Gold 6250 processor / 16 cores, 3.9 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Dual Intel Xeon Platinum 8260 processor / 48 cores, 2.4 GHz | 64 GB, 96 GB, 128 GB, 192 GB, 384 GB, 768 GB, 1.5 TB |
| Quad Intel Xeon Gold 6248 processor / 80 cores, 2.5 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8260 processor / 96 cores, 2.4 GHz | 384 GB, 768 GB, 1.5 TB, 3 TB |
{: caption="Table 2. Options for Cascade Lake bare metal servers - NSX-V instances" caption-side="top"}
{: class="simple-tab-table"}
{: tab-title="NSX-V instances"}
{: tab-group="Cascade Lake Intel servers"}
{: #simpletabtable-cascade-nsxv}


For **SAP-certified** servers, you have the following options:
* **NetWeaver**, for which the CPU and RAM size are preset.
* **HANA**, for which you can choose the CPU model and a supported RAM size, which depends on the NSX networking solution.
{: #sap-para-intro}

| CPU model     | RAM sizes   |
|:------------- |:----------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW192) / 32 cores, 2.3 GHz | 192 GB |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake, BI.S4.NW384) / 32 cores, 2.3 GHz | 384 GB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake, BI.S4.NW768) / 40 cores, 2.5 GHz | 768 GB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.NW1500) / 56 cores, 2.7 GHz | 1.5 TB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake, BI.S4.NW3000) / 56 cores, 2.7 GHz | 3 TB |
{: caption="Table 3. Options for SAP-certified bare metal servers - NetWeaver" caption-side="top"}
{: class="simple-tab-table"}
{: tab-title="NetWeaver"}
{: tab-group="SAP-certified Intel servers"}
{: #simpletabtable-sap-netweaver}


| CPU model     | RAM sizes |
|:------------- |:--------- |
| Dual Intel Xeon Gold 5218 processor (Cascade Lake) / 32 cores, 2.3 GHz | 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Dual Intel Xeon Gold 6248 processor (Cascade Lake) / 40 cores, 2.5 GHz| 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Dual Intel Xeon Platinum 8280M processor (Cascade Lake) / 56 cores, 2.7 GHz | 192 GB, 384 GB, 768 GB, 1.5 TB, 3 TB |
| Quad Intel Xeon Platinum 8280M processor (Cascade Lake) / 112 cores, 2.7 GHz | 3 TB, 6 TB |
{: caption="Table 3. Options for SAP-certified bare metal servers - HANA" caption-side="top"}
{: tab-title="HANA"}
{: tab-group="SAP-certified Intel servers"}
{: class="simple-tab-table"}
{: #simpletabtable-sap-hana}


Conref section END.

Conref section START.

INFORMATION:
The section is referenced by the following files:
- vcenter\vc_addingclusters.md
- vcenter\vc_orderinginstance-network.md
- vcenter\scb-orderinginstance-cons-work-cluster.md
- vcenter\vrw-orderinginstance-edge.md
- vcenter\vrw-orderinginstance-mgmt.md
- vcenter\vrw-orderinginstance-primary.md
- vcenter\vrw-orderinginstance-witness.md
- vcenter\vrw-orderinginstance-wkld.md
- vsphere\vs_orderinginstances-network.md

CONTENT:

The uplink speed provides two options:
* 10 Gb, which is selected by default.
* 25 Gb, which is available only for **Cascade Lake** and **SAP-certified** bare metal servers and for specific data center locations. The following table shows the available locations for the 25 Gb uplink speed.
{: #uplink-speed-options-list}

The uplink speed provides two options:
* 10 Gb, which is selected by default.
* 25 Gb, which is available only for specific locations. The following table shows the available {{site.data.keyword.cloud}} data centers for the 25 Gb uplink speed.
{: #uplink-speed-options-cascadelake-list}

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
{: caption="Table 1. Available locations for 25 Gb uplink speed" caption-side="top"}
{: #simpletable-uplink-speed-locations}


Conref section END.

Conref section START.

INFORMATION:
The section is referenced by the following files:
- vcenter\scb-orderinginstance-procedure.md
- vcenter\vc_orderinginstance-procedure.md
- vcenter\vrw-orderinginstance-procedure.md

CONTENT:

**CAUTION** Managing any {{site.data.keyword.vmwaresolutions_short}} components (which were installed into your {{site.data.keyword.cloud_notm}} account when you ordered the instance) from outside the VMware Solutions console can make your environment unstable. The following activities are considered management activities:
*  Adding, modifying, returning, or removing components
*  Expanding or contracting instance capacity through adding or removing ESXi servers
*  Powering off components
*  Restarting services
{: #caution-component-management}

Conref section END.

Conref section START.

INFORMATION:
The section is referenced by the following files:
- services\vrops_overview.md
- services\veeamvm_overview.md
- services\managing-ss-sap.md
- services\htcc_considerations.md
- services\hcx_considerations.md
- services\f5_considerations.md
- services\caveonix_considerations.md

CONTENT:

{{site.data.keyword.vmwaresolutions_full}} offers promotions for some services. Promotional pricing offers a number of months free of charge for a service’s licenses, if the service has license charges. For more information, see [Promotions for VMware Solutions services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-service-promotions).
{: #para-promotion-services}


Conref section END.

Conref section START.

INFORMATION:
The section is referenced by the following files:
- services\juniper_overview.md
- services\addingzertodr.md

CONTENT:

{{site.data.keyword.vmwaresolutions_full}} offers promotions for some add-on services. Promotional pricing offers a number of months free of charge for a service’s licenses, if the service has license charges. For more information, see [Promotions for VMware Solutions add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-service-promotions).
{: #para-promotion-add-on-services}


Conref section END.


For details about the conref.md file template, see [Using conrefs to reuse chunks of content within your subcollection](https://test.cloud.ibm.com/docs/writing?topic=writing-conrefs).
