---

copyright:

  years:  2016, 2025

lastupdated: "2025-12-03"

keywords: Zerto, Zerto components, tech specs Zerto

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.hpe-zerto}} on {{site.data.keyword.cloud_notm}} overview
{: #addingzertodr}

{{site.data.content.vms-deprecated-note}}

{{site.data.keyword.hpe-zerto}} on {{site.data.keyword.cloud}} integrates replication and disaster recovery capabilities into the deployment offerings to protect and recover data in your VMware® virtual environment on {{site.data.keyword.cloud}}. {{site.data.keyword.hpe-zerto}} on {{site.data.keyword.cloud_notm}} is a non-IBM product that is offered under terms and conditions from {{site.data.keyword.hpe-zerto}}, not IBM.

{{site.data.keyword.hpe-zerto}} is supported on {{site.data.keyword.vcf-auto}} instances that meet the following requirements:

* VMware NSX-T™ 3.1 or later
* VMware vSphere® 7.0 or later
{: shortdesc}

{{site.data.content.para-promotion-services}}


The {{site.data.keyword.hpe-zerto}} version available for deployment is 10.0u7. To upgrade from {{site.data.keyword.hpe-zerto}} versions that are earlier than 10.0u7, you must migrate from a Microsoft Windows® Virtual Service Instance (VSI) to a Linux® virtual machine (VM).
{: note}

## Before you begin
{: #addingzertodr-req}

Ensure that your {{site.data.keyword.cloud_notm}} account is a billable account, and that it is linked to the {{site.data.keyword.cloud_notm}} infrastructure account where your instance is deployed. For more information, see [Billing for {{site.data.keyword.hpe-zerto}} replication](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering#zerto_ordering-billing).

## Technical specifications for {{site.data.keyword.hpe-zerto}}
{: #addingzertodr-specs}

For more information about resource requirements and capacity checking for some services, see [Resource requirements for services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-resource-requirements).

The following components are ordered and included in the {{site.data.keyword.hpe-zerto}} service.

Zerto Virtual Replication Appliance (VRA) components are deployed only into the default cluster.
{: note}

### Storage
{: #addingzertodr-specs-storage}

100 GB (SAN) disk

### {{site.data.keyword.hpe-zerto}} Networking
{: #addingzertodr-specs-network}

* One portable private IP address
* Virtual replication appliances (VRAs) - One private portable subnet for VRA deployment

The {{site.data.keyword.hpe-zerto}} service is not configured with an {{site.data.keyword.cloud_notm}} infrastructure public IP address or with a NAT connection to the public network, even if you have public interfaces in your instance. This implementation helps to avoid the possibility of asymmetric routing when it uses a network gateway appliance.

When you deploy {{site.data.keyword.hpe-zerto}}, you must configure your own proxy or NAT connection to the public network. If you do not complete the configuration, {{site.data.keyword.hpe-zerto}} blocks management activities in 15 days.

For more information, see [Considerations for ordering {{site.data.keyword.hpe-zerto}}](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering#zerto_ordering-private-only).

### Licenses and fees
{: #addingzertodr-specs-licenses}

{{site.data.keyword.hpe-zerto}} Replication version 10.0u7 license. You must use the license for disaster recovery purposes only. The license key cannot be used for migrating existing instances.

## Related links
{: #addingzertodr-related}

* [Ordering {{site.data.keyword.hpe-zerto}}](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering)
* [Managing {{site.data.keyword.hpe-zerto}}](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Ordering {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses)
* [Managing {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses)
* [{{site.data.keyword.hpe-zerto}} product documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
