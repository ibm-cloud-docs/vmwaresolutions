---

copyright:

  years:  2022

lastupdated: "2022-10-27"

keywords: planning cyber recovery, cyber recovery, cyber recovery instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Planning for a Cyber Recovery instance
{: #cr_planning}

Review the following requirements before you order your Cyber Recovery instance. Plan your instance based on the {{site.data.keyword.cloud}} data center location, your capacity requirements, and services requirements.

## IBM Cloud account requirements
{: #cr_planning-account-req}

The {{site.data.keyword.cloud_notm}} account that you are using must meet certain requirements. For more information, see [Requirements for the {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).

## IBM Cloud data center availability
{: #cr_planning-dc-availability}

The Cyber Recovery deployment has strict requirements on the physical infrastructure. Therefore, you can deploy instances only in {{site.data.keyword.cloud_notm}} data centers that meet the requirements.

### Data centers available
{: #cr_planning-data-centers}

The following {{site.data.keyword.cloud_notm}} data centers are available for Cyber Recovery.

| Geography | Data center | Pod |
|:----------|:------------|:-------|
| Asia-Pacific |CHE01 | 01 |
| Asia-Pacific | HKG02 | 02 |
| Asia-Pacific | OSA21 | 01 |
| Asia-Pacific | OSA22 | 01 |
| Asia-Pacific | OSA23 | 01 |
| Asia-Pacific | SEO01 | 01 |
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
| NA East | WDC 07 | 01 |
| NA South | DAL09 | 01-06 |
| NA South | DAL10 | 01-04 |
| NA South | DAL12 | 01-02 |
| NA South | DAL13 | 01-03 |
| NA South | MEX01 | 01 |
| NA West | SJC03 | 01-02 |
| NA West | SJC04 | 01 |
| South America | SAO01 | 01 |
| South America | SAO04 | 01 |
| South America | SAO05 | 01 |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for Cyber Recovery" caption-side="bottom"}

## Services for a Cyber Recovery instance
{: #cr_planning-addon-services}

The following services are required for a Cyber Recovery instance.

* [Veeam® 11](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview) is required and also included in the Cyber Recovery instance. For Veeam 11, a Linux hardened repository is already chosen for you.
* An edge gateway is required. You can bring your own gateway appliance or choose from:
   * Edge services cluster with Juniper® vSRX
   * Edge services cluster with FortiGate® Virtual Appliance
   * Fortigate Security Appliance

The [Caveonix RiskForesight™](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_considerations) service is recommended.

The following services are optional for Cyber Recovery.

* [HCX™](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_considerations)
* [Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Entrust CloudControl™](/docs/vmwaresolutions?topic=vmwaresolutions-entrust-cc_considerations)
* [F5® BIG-IP®](/docs/vmwaresolutions?topic=vmwaresolutions-f5_considerations)
* [Red Hat® OpenShift® for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-ocp_overview)
* [vRealize Operations™ and Log Insight™](/docs/vmwaresolutions?topic=vmwaresolutions-vrops_overview)

## Related links
{: #cr_planning-related-links}

* [Cyber Recovery overview](/docs/vmwaresolutions?topic=vmwaresolutions-cr_overview)
* [Requirements for the Cyber Recovery offering](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance_reqs)
