---

copyright:

  years:  2021, 2022

lastupdated: "2022-11-03"

keywords: planning vmware regulated workloads, data center vmware regulated workloads, vmware regulated workloads data centers

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Planning for VMware Regulated Workloads
{: #vrw-planning}

Review the following requirements before you order your VMware® Regulated Workloads instance. Plan your instance based on the {{site.data.keyword.cloud}} data center location, your capacity requirements, and services requirements.

## IBM Cloud account requirements
{: #vrw-planning-account-req}

The {{site.data.keyword.cloud_notm}} account that you are using must meet certain requirements. For more information, see [Requirements for the {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).

## IBM Cloud data center availability
{: #vrw-planning-dc-availability}

The VMware Regulated Workloads deployment has strict requirements on the physical infrastructure. Therefore, you can deploy instances only in {{site.data.keyword.cloud_notm}} data centers that meet the requirements.

### Data centers available for single-zone deployment
{: #vrw-planning-dc-single-zone}

The following {{site.data.keyword.cloud_notm}} data centers are available for VMware Regulated Workloads single-zone deployment.

| Geography | Data center | Pod |
|:--------- |:----------- |:--- |
| Asia-Pacific |CHE01 | 01 |
| Asia-Pacific | OSA21 | 01 |
| Asia-Pacific | OSA22 | 01 |
| Asia-Pacific | OSA23 | 01 |
| Asia-Pacific | SNG01| 02 |
| Asia-Pacific | SYD01 | 01-02 |
| Asia-Pacific | SYD04 | 01 |
| Asia-Pacific | SYD05 | 01 |
| Asia-Pacific | TOK02 | 01-02 |
| Asia-Pacific | TOK04 | 01 |
| Asia-Pacific | TOK05 | 01 |
| Europe | AMS03 | 01-02 |
| Europe | FRA02 | 01-03 |
| Europe | FRA04 | 01 |
| Europe | FRA05 | 01 |
| Europe | LON02 | 01-02 |
| Europe | LON04 | 01 |
| Europe | LON05 | 01 |
| Europe | LON06 | 01 |
| Europe | MIL01 | 01 |
| Europe | PAR01 | 01 |
| NA East | MON01 | 01-02 |
| NA East | TOR01 | 01-02 |
| NA East | TOR04 | 01 |
| NA East | TOR05 | 01 |
| NA East | WDC04 | 01-05 |
| NA East | WDC06 | 01 |
| NA East | WDC07 | 01 |
| NA South | DAL09 | 01-06 |
| NA South | DAL10 | 01-04 |
| NA South | DAL12 | 01-02 |
| NA South | DAL13 | 01-03 |
| NA West | SJC03 | 01-02 |
| NA West | SJC04 | 01 |
| South America | SAO01 | 01 |
| South America | SAO04 | 01 |
| South America | SAO05 | 01 |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for VMware Regulated Workloads single-zone deployment" caption-side="bottom"}

### Regions available for multizone deployment
{: #vrw-planning-reg-multizone}

The following regions are available for VMware Regulated Workloads multizone deployment.

| {{site.data.keyword.cloud_notm}} data centers | Mutizone region |
|:----------------------|:-------|
| Dallas, Sao Paulo, Toronto, and Washington DC | Americas |
| Frankfurt and London | Europe |
| Sydney, Tokyo, and Osaka | Asia Pacific |
{: caption="Table 2. Available regions for VMware Regulated Workloads multizone deployment" caption-side="bottom"}

## Services for VMware Regulated Workloads
{: #vrw-planning-addon-services}

The following services are required for the VMware Regulated Workloads:
* [Hyper Protect Crypto Services](https://cloud.ibm.com/catalog/services/hyper-protect-crypto-services)
* [KMIP for VMware](https://cloud.ibm.com/infrastructure/vmware-solutions/console/servicestandalonenew/KMIPAdapter)
* [Direct Link Dedicated](https://cloud.ibm.com/interconnectivity/direct-link)

The following services are included with VMware Regulated Workloads:
* [Veeam 11](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview)
* [Caveonix RiskForesight](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_considerations)
* [Entrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-entrust-cc_considerations)
* [Juniper vSRX](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-overview). This service is included when you choose **Edge services cluster with Juniper vSRX**. It is available for single-zone and multizone instances.
* [vRealize Operations and Log Insight](/docs/vmwaresolutions?topic=vmwaresolutions-vrops_overview)

The following services are optional for VMware Regulated Workloads and are available to single-zone VMware instances only:
* [VMware HCX](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_considerations)
* [F5 BIG-IP](/docs/vmwaresolutions?topic=vmwaresolutions-f5_considerations)

## Related links
{: #vrw-planning-related}

* [VMware Regulated Workloads overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-overview)
* [Ordering VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-req)
* [Viewing and deleting VMware Regulated Workloads](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-view-delete-instance)
* [VMware Regulated Workloads reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
