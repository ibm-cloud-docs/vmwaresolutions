---

copyright:

  years:  2025

lastupdated: "2025-10-24"

keywords: end of support notice, kmip for vmware service, end of support kmip for vmware, kmip for vmware deprecated, kmip for vmware support

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# End of Support for KMIP for VMware for Key Protect
{: #eos-kmip}

{{site.data.content.vms-deprecated-note}}

{{site.data.content.kmip-deprecated-note}}

Support for Key Protect service as part of the Key Management Interoperability Protocol (KMIP™) for VMware® will end on 16 July 2026 after which the service will no longer be available. You must migrate to the native [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect) offering, or an alternative key management service of your choice by 16 July 2026.

{{site.data.content.kmip-imp-note}}

If you are using the KMIP for VMware support for Key Protect, you must plan and start migration to [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect) services at the earliest.

The new key provider offering, [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect), has the following advantages over the KMIP for VMware adapter:
- Improved performance because the calls from KMIP to key provider are closer in network distance and no longer cross the service-to-service authorization boundaries.
- Improved visibility and management for the KMIP keys.
- No change in pricing.

To experience an improved performance at no additional cost, you must migrate to {{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}} from KMIP for VMware service. For more information about KMIP migration, see [Migrating from KMIP for VMware to IBM Cloud native KMIP providers](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_migration).

Customers who are using vSphere version 7.x can encounter a Broadcom bug in vSphere HA that results in restart of virtual machines with vSphere encryption during the rekeying process. However, Broadcom provides a workaround for this issue. For more information about the workaround, see [Encrypted VM with Change Block Tracking (CBT) enabled unexpectedly powers off after shallow rekey operation](https://knowledge.broadcom.com/external/article?articleNumber=387897){: external}.
{: attention}

{{site.data.content.eol-ibm-cloud}}

## Related links
{: #eos-kmip-related}

* [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect)
* [Migrating from KMIP for VMware to IBM Cloud native KMIP providers](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_migration)
* [FAQ for KMIP for VMware migration](/docs/vmwaresolutions?topic=vmwaresolutions-faq-kmip)
