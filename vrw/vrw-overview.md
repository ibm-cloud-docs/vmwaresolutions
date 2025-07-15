---

copyright:

  years:  2020, 2025

lastupdated: "2025-07-15"

keywords: vmware regulated workloads, regulated workloads, workloads instance, regulated instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.rw}} overview
{: #vrw-overview}

{{site.data.content.vrw-deprecated-note}}

The {{site.data.keyword.rw}} offering includes a secure-by-default architecture that follows the {{site.data.keyword.IBM}} unique policy controls framework. It also includes continuous compliance monitoring and the highest level of data encryption FIPS 140-2 Level 4.

Review the following specifications:
* {{site.data.keyword.rw}} is available only for single-zone topology.
* {{site.data.keyword.rw}} are based on VMware NSX-T™ and VMware vSphere® 7.
* [Hyper Protect Crypto Services](/catalog/services/hyper-protect-crypto-services), [KMIP for VMware](/infrastructure/vmware-solutions/console/servicestandalonenew/KMIPAdapter), and [Direct Link](/interconnectivity/direct-link) are required for {{site.data.keyword.rw}}. Ensure that you order these services before you start your {{site.data.keyword.rw}} order.
* Some of the services require configuration setup. Review each service and ensure that you configure its settings properly, as indicated.
* The **Private network only** option is available for all clusters. The **Public and private network** option is available only for the gateway cluster.

## Options not available for {{site.data.keyword.rw}}
{: #vrw-overview-before-not-avail-options}

The following options or settings are not available for {{site.data.keyword.rw}}:
* Local disks
* High performance with Intel® Optane
* vSAN™ deduplication and compression
* Selection of existing VLANs
* Single public Windows® VSI for Active Directory™ DNS configuration
