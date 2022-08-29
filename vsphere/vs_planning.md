---

copyright:

  years:  2016, 2022

lastupdated: "2022-06-23"

keywords: planning vSphere, data center, vSphere data centers

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Planning for VMware vSphere
{: #vs_planning}

Review the following requirements before you order a VMware vSphere® cluster. Plan your VMware vSphere clusters based on the {{site.data.keyword.cloud}} data center location and your workload capacity requirements.

You are responsible for setting up the environment, installing, and configuring various VMware® components after the VMware ESXi™ servers are deployed. The following examples are VMware components: VMware vCenter Server®, VMware NSX®, and VMware vSAN™.
{: note}

## IBM Cloud account requirements
{: #vs_planning-account-req}

The {{site.data.keyword.cloud_notm}} account that you are using must meet certain requirements. For more information, see [Requirements for the {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).

## IBM Cloud data center availability
{: #vs_planning-dc-availability}

The vSphere deployment has strict requirements on the physical infrastructure. Therefore, you can deploy clusters only in {{site.data.keyword.cloud_notm}} data centers that meet the requirements. The following {{site.data.keyword.cloud_notm}} data centers are available for vSphere deployment.

Cascade Lake bare metal servers are available in [multizone region](#x9774820){: term}
{{site.data.keyword.cloud_notm}} data centers. For more information, see [Multizone region (MZR) overview](/docs/loadbalancer-service?topic=loadbalancer-service-multi-zone-region-mzr-overview).

If you select a vSAN component, the location list is filtered by SSD (Solid-State Disk) availability.
{: note}

| Geography | Data center | Pod | Server options[^vsphere-7] |
|:-----------|:----------|:---------------|:--------------|
| Asia-Pacific | CHE01 | 01 | Skylake, Cascade Lake, SAP-certified[^sap-che01] |
| Asia-Pacific | HKG02 | 02 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | OSA21 | 01 | Cascade Lake, SAP-certified |
| Asia-Pacific | OSA22 | 01 | Cascade Lake, SAP-certified |
| Asia-Pacific | OSA23 | 01 | Cascade Lake, SAP-certified |
| Asia-Pacific | SEO01 | 01 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SNG01 | 02 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SYD01 | 01-02 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SYD04 | 01 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SYD05 | 01 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | TOK02 | 01-02 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | TOK04 | 01 | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | TOK05 | 01 | Skylake, Cascade Lake, SAP-certified |
| Europe | AMS03 | 01-02 | Skylake, Cascade Lake, SAP-certified |
| Europe | FRA02 | 01-03 | Skylake, Cascade Lake, SAP-certified |
| Europe | FRA04 | 01 | Skylake, Cascade Lake, SAP-certified|
| Europe | FRA05 | 01 | Skylake, Cascade Lake, SAP-certified |
| Europe | LON02 | 01-02 | Skylake, Cascade Lake, SAP-certified |
| Europe | LON04 | 01 | Skylake, Cascade Lake, SAP-certified |
| Europe | LON05 | 01 | Skylake, Cascade Lake, SAP-certified |
| Europe | LON06 | 01 | Skylake, Cascade Lake, SAP-certified |
| Europe | MIL01  | 01 | Skylake, Cascade Lake, SAP-certified[^sap-mil01] |
| Europe | PAR01 | 01 | Skylake, Cascade Lake, SAP-certified[^sap-par01] |
| NA East | MON01 | 01-02 | Skylake, Cascade Lake, SAP-certified[^sap-mon01] |
| NA East | TOR01 | 01-02 | Skylake, Cascade Lake, SAP-certified |
| NA East | TOR04 | 01 | Cascade Lake |
| NA East | TOR05 | 01 | Cascade Lake |
| NA East | WDC04 | 01-05 | Skylake, Cascade Lake, SAP-certified |
| NA East | WDC 06 | 01 | Skylake, Cascade Lake, SAP-certified |
| NA East | WDC 07 | 01 | Skylake, Cascade Lake, SAP-certified |
| NA South | DAL09 | 01-06 | Skylake, Cascade Lake, SAP-certified |
| NA South | DAL10 | 01-04 | Skylake, Cascade Lake, SAP-certified 
| NA South | DAL12 | 01-02 | Skylake, Cascade Lake, SAP-certified |
| NA South | DAL13 |  01-03 | Skylake, Cascade Lake, SAP-certified |
| NA South | MEX01 | 01 | Skylake, Cascade Lake, SAP-certified[^sap-mex01] |
| NA West | SJC03 |  | Skylake, Cascade Lake, SAP-certified |
| NA West | SJC04 |  | Skylake, Cascade Lake, SAP-certified |
| South America | SAO01 | 01 | Skylake, Cascade Lake, SAP-certified |
| South America | SAO04 | 01 | Cascade Lake, SAP-certified |
| South America | SAO05 | 01 | Cascade Lake, SAP-certified |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for vSphere clusters" caption-side="bottom"}

[^vsphere-7]: Skylake is not supported for vSphere 7 instances

[^sap-che01]: Existing vSphere 6.5 clusters only

[^sap-mex01]: Existing vSphere 6.5 clusters only

[^sap-mil01]: Existing vSphere 6.5 clusters only

[^sap-mon01]: Existing vSphere 6.5 clusters only

[^sap-par01]: Existing vSphere 6.5 clusters only

## Related links
{: #vs_planning-related}

* [Ordering new vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-req)
* [Scaling existing clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_scalingexistingclusters)
* [Scaling existing clusters created outside of the console](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingforclustersoutside)
