---

copyright:

  years:  2016, 2025

lastupdated: "2025-02-14"

keywords: planning flexible, data center, vSphere data centers

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Planning for {{site.data.keyword.vcf-flex-short}}
{: #vs_planning}

Review the following requirements before you order a {{site.data.keyword.vcf-flex}} instance. Plan your {{site.data.keyword.vcf-flex-short}} based on the {{site.data.keyword.cloud}} data center location and your workload capacity requirements.

You are responsible for setting up the environment, installing, and configuring various VMware® components after the VMware ESXi™ servers are deployed. The following examples are VMware components: VMware vCenter Server®, VMware NSX®, and VMware vSAN™.
{: note}

## Account requirements
{: #vs_planning-account-req}

The account that you are using must meet certain requirements. For more information, see [Signing up for required accounts](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts).

## Licensing considerations
{: #vs_planning-licensing}

{{site.data.content.vmware-licensing}}

## {{site.data.keyword.cloud_notm}} data center availability
{: #vs_planning-dc-availability}

The VMware vSphere deployment has strict requirements on the physical infrastructure. Therefore, you can deploy instances only in {{site.data.keyword.cloud_notm}} data centers that meet the requirements. The following {{site.data.keyword.cloud_notm}} data centers are available for vSphere deployment.

Cascade Lake bare metal servers are available in [multizone region](#x9774820){: term}
{{site.data.keyword.cloud_notm}} data centers. For more information, see [Creating a VPC in a different region](/docs/vpc?topic=vpc-creating-a-vpc-in-a-different-region&interface=cli).

If you select a vSAN component, the location list is filtered by SSD (Solid-State Disk) availability.
{: note}

| Data center | Pod | Server options |
|:----------- |:--- |:-------------- |
| CHE01 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| OSA21 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| OSA22 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| OSA23 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| SNG01 | 02 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| SYD01 | 01-02 | Cascade Lake, SAP-certified Cascade Lake |
| SYD04 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| SYD05 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| TOK02 | 01-02 | Cascade Lake, SAP-certified Cascade Lake |
| TOK04 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| TOK05 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for Flexible instances - Asia Pacific" caption-side="bottom"}
{: tab-title="Asia Pacific"}
{: tab-group="Data centers for Flexible instances"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-ap}

| Data center | Pod | Server options |
|:----------- |:--- |:-------------- |
| AMS03 | 01-02 | Cascade Lake, SAP-certified Cascade Lake |
| FRA02 | 01-03 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| FRA04 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| FRA05 | 01 | Cascade Lake |
| LON02 | 01-02 | Cascade Lake, SAP-certified Cascade Lake |
| LON04 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| LON05 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| LON06 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| MAD02 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| MAD04 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| MAD05 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| MIL01 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| PAR01 | 01 | Cascade Lake, SAP-certified Cascade Lake |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for Flexible instances - Europe" caption-side="bottom"}
{: tab-title="Europe"}
{: tab-group="Data centers for Flexible instances"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-eur}

| Data center | Pod | Server options |
|:----------- |:--- |:-------------- |
| MON01 | 01-02 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| TOR01 | 01-02 | Cascade Lake, SAP-certified Cascade Lake |
| TOR04 | 01 | Cascade Lake |
| TOR05 | 01 | Cascade Lake, Sapphire Rapids |
| WDC04 | 01-05 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| WDC06 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| WDC07 | 01 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for Flexible instances - NA East" caption-side="bottom"}
{: tab-title="NA East"}
{: tab-group="Data centers for Flexible instances"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-naeast}

| Data center | Pod | Server options |
|:----------- |:--- |:-------------- |
| DAL09 | 01-02, 05-06 | Cascade Lake, SAP-certified Cascade Lake |
| DAL10 | 01-04 | Cascade Lake, SAP-certified Cascade Lake |
| DAL12 | 01-02 | Cascade Lake, SAP-certified Cascade Lake |
| DAL13 | 01-03 | Cascade Lake, SAP-certified Cascade Lake, Sapphire Rapids |
| DAL14 | 01 | Cascade Lake, Sapphire Rapids |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for Flexible instances - NA South" caption-side="bottom"}
{: tab-title="NA South"}
{: tab-group="Data centers for Flexible instances"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-nasouth}

| Data center | Pod | Server options |
|:----------- |:--- |:-------------- |
| SJC03 | 01-02 | Cascade Lake, Sapphire Rapids |
| SJC04 | 01 | Cascade Lake, Sapphire Rapids |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for Flexible instances - NA West" caption-side="bottom"}
{: tab-title="NA West"}
{: tab-group="Data centers for Flexible instances"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-nawest}

| Data center | Pod | Server options |
|:----------- |:--- |:-------------- |
| SAO01 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| SAO04 | 01 | Cascade Lake, SAP-certified Cascade Lake |
| SAO05 | 01 | Cascade Lake, SAP-certified Cascade Lake |
{: caption="Available {{site.data.keyword.cloud_notm}} data centers for Flexible instances - South America" caption-side="bottom"}
{: tab-title="South America"}
{: tab-group="Data centers for Flexible instances"}
{: class="simple-tab-table"}
{: #simpletabtable-cr-sa}

## Related links
{: #vs_planning-related}

* [Ordering Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-req)
* [Adding ESXi servers to Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_addingservers)
