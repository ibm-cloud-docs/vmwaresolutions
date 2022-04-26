---

copyright:

  years:  2021, 2022

lastupdated: "2022-04-11"

keywords: planning vcs Security and Compliance Readiness Bundle, data centers for Security and Compliance Readiness Bundle, services for security and compliance bundle, vcs scb

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Requirements and planning for Security and Compliance Readiness Bundle
{: #scb-planning}

Review the following requirements before you order your Security and Compliance Readiness Bundle instance. Plan your instance based on the {{site.data.keyword.cloud}} data center location, your workload capacity requirements, and services requirements.

## IBM Cloud account requirements
{: #scb-planning-account-req}

The {{site.data.keyword.cloud_notm}} account that you are using must meet certain requirements. For more information, see [Requirements for the {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).

## IBM Cloud data center availability
{: #scb-planning-dc-availability}

The Security and Compliance Readiness Bundle deployment has strict requirements on the physical infrastructure. Therefore, you can deploy instances only in {{site.data.keyword.cloud_notm}} data centers that meet the requirements. The following {{site.data.keyword.cloud_notm}} data centers are available for Security and Compliance Readiness Bundle deployment.

| Geography | Data center | Pod |
|:----------|:------------|:-------|
| Asia-Pacific | OSA21 | 01 |
| Asia-Pacific | OSA22 | 01 |
| Asia-Pacific | OSA23 | 01 |
| Asia-Pacific | SEO01 | 01 |
| Asia-Pacific | SNG01| 02 |
| Asia-Pacific | SYD01 | 01, 02 |
| Asia-Pacific | SYD04 | 01 |
| Asia-Pacific | SYD05 | 01 |
| Asia-Pacific | TOK02 | 01, 02 |
| Asia-Pacific | TOK04 | 01 |
| Asia-Pacific | TOK05 | 01 |
| Europe | AMS03 | 01, 02 |
| Europe | FRA02 | 01, 02, 03 |
| Europe | FRA04 | 01 |
| Europe | FRA05 | 01 |
| Europe | LON02 | 01, 02 |
| Europe | LON04 | 01 |
| Europe | LON05 | 01 |
| Europe | LON06 | 01 |
| Europe | MIL01 | 01 |
| Europe | PAR01 | 01 |
| NA East | MON01 | 01-02 |
| NA East | TOR01 | 01, 02 |
| NA East | TOR04 | 01 |
| NA East | TOR05 | 01 |
| NA East | WDC04 | 01-05 |
| NA East | WDC06 | 01 |
| NA East | WDC07 | 01 |
| NA South | DAL10 | 01-04 |
| NA South | DAL12 | 01-02 |
| NA South | DAL13 | 01-03 |
| NA South | MEX01 | 01 |
| NA West | SJC03 | 01-02 |
| NA West | SJC04 | 01 |
| South America | SAO01 | 01 |
| South America | SAO04 | 01 |
| South America | SAO05 | 01 |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for Security and Compliance Readiness Bundle" caption-side="top"}

## Services for Security and Compliance Readiness Bundle
{: #scb-planning-addon-services}

The following services are required for Security and Compliance Readiness Bundle instances.
* [Hyper Protect Crypto Services](https://cloud.ibm.com/catalog/services/hyper-protect-crypto-services)
* [KMIP for VMware](https://cloud.ibm.com/infrastructure/vmware-solutions/console/servicestandalonenew/KMIPAdapter)

The following services are included with Security and Compliance Readiness Bundle instances.
* [Caveonix RiskForesight](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_considerations)
* [Entrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-htcc_considerations)
* [vRealize Operations and Log Insight](/docs/vmwaresolutions?topic=vmwaresolutions-vrops_overview)

The following services are recommended for Security and Compliance Readiness Bundle instances.
* [Veeam 11](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview)
* [Juniper vSRX](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-overview)

The following services are optional for Security and Compliance Readiness Bundle instances.
* [VMware HCX](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_considerations)
* [F5 BIG-IP](/docs/vmwaresolutions?topic=vmwaresolutions-f5_considerations)
* [{{site.data.keyword.redhat_openshift_notm}} for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-ocp_ordering)

## Related links
{: #scb-planning-related}

* [Security and Compliance Readiness Bundle overview](/docs/vmwaresolutions?topic=vmwaresolutions-scb-overview)
* [Ordering Security and Compliance Readiness Bundle instances](/docs/vmwaresolutions?topic=vmwaresolutions-scb-orderinginstance-req)
* [Viewing and deleting Security and Compliance Readiness Bundle instances](/docs/vmwaresolutions?topic=vmwaresolutions-scb-view-delete-instance)
