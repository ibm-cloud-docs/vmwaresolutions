---

copyright:

  years:  2020, 2022

lastupdated: "2022-12-19"

keywords: planning VMware Solutions Shared, data center, VMware Solutions Shared data centers

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Requirements and planning for VMware Shared
{: #shared_planning}

Review the following requirements before you order your VMware Shared virtual data centers. Plan for your order by considering the {{site.data.keyword.cloud_notm}} data center location, your workload capacity requirements, and services requirements.

Price calculations are automatically generated when you access the VMware Shared instance order page. Default selections for on-demand virtual data centers include public and private networking, 2000 vCPU, and 40960 RAM. Default selections for reserved virtual data centers include public and private networking, and customizable vCPU and RAM limits.

## IBM Cloud account requirements
{: #shared_ordering-account-req}

To order VMware Shared, you must have a **Pay As You Go** or **Subscription** {{site.data.keyword.cloud_notm}} account. The cost of the resources that are ordered is billed to that {{site.data.keyword.cloud_notm}} account.

## Virtual data center name requirements
{: #shared_ordering-vdc-name-req}

The virtual data center name must meet the following requirements:

* Maximum length is 128 characters.
* Only alphanumeric, dash (-), and underscore (_) characters are allowed.
* The name must be unique from active virtual data centers within your account. You can create a virtual data center that has the same name as a previously deleted virtual data center.

## IBM Cloud data center availability
{: #shared_planning-dc-availability}

The VMware Shared deployment has strict requirements on the physical infrastructure. Therefore, you can deploy your virtual data centers only in {{site.data.keyword.cloud_notm}} data centers that meet the requirements.

The following {{site.data.keyword.cloud_notm}} data centers are available for VMware Shared deployment.

| Geography | Site | Location | vSAN support | Multizone support |
|:----------|:----------|:----------|:-------|:-------|
| Europe | Frankfurt Director 01 | Frankfurt 02 | None | No |
| Europe | Frankfurt Director 01 | Frankfurt 04 | None | No |
| Europe | Frankfurt Director 01 | Frankfurt 05 | None | No |
| North America | Dallas Director 01 | Dallas 10 | vSAN | Yes |
| North America | Dallas Director 01 | Dallas 12 | vSAN | Yes |
| North America | Dallas Director 01 | Dallas 13 | vSAN | No |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for deployment" caption-side="bottom"}

## Services for VMware Shared instances
{: #shared_planning-addon-services}

The following preinstalled services are available for your virtual data center based on your needs.
* [Managing Veeam for VMware Shared](/docs/vmwaresolutions?topic=vmwaresolutions-shared_veeam)
* [Managing Zerto for VMware Shared](/docs/vmwaresolutions?topic=vmwaresolutions-shared_zerto-portal)

Service charges are incurred only if you choose to use the service.
{: note}

## Related links
{: #shared_planning-related}

* [Ordering virtual data centers](/docs/vmwaresolutions?topic=vmwaresolutions-shared_ordering)
* [Viewing and managing virtual data centers](/docs/vmwaresolutions?topic=vmwaresolutions-shared_viewing-vdc-summary)
* [Operating VMware Shared](/docs/vmwaresolutions?topic=vmwaresolutions-shared_vcd-ops-guide)
* [VMware Cloud Director](https://www.vmware.com/ca/products/cloud-director.html){: external}
