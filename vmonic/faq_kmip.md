---

copyright:

  years:  2025

lastupdated: "2025-07-16"

keywords: FAQ kmip for vmware, kmip for vmware questions

subcollection: vmwaresolutions

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQ about KMIP for VMware migration
{: #faq-kmip}

{{site.data.content.kmip-deprecated-note}}

{{site.data.content.kmip-imp-note}}

Find answers to frequently asked questions about the Key Management Interoperability Protocol (KMIP™) for VMware® service.

## What does the End of Support announcement mean?
{: #faq-kmip-eos-kp}
{: faq}

Support for the Key Protect service as part of the Key Management Interoperability Protocol (KMIP™) for VMware® will end on 16 July 2026 after which the service will no longer be available. Customers must migrate to the native [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect) offering, or an alternative key management service of your choice by 16 July 2026.

This announcement is applicable only to customers who are using the KMIP for VMware support for Key Protect.

## I am a user of KMIP for VMware support for HPCS. What does this announcement mean for me?
{: #faq-kmip-eos-hpcs}
{: faq}

This announcement is applicable only to customers who are using the KMIP for VMware support for Key Protect. Customers who are using KMIP for VMware support for Hyper Protect Crypto Services (HPCS) remain unaffected by this announcement. The KMIP for VMware support for HPCS continues to function as usual without any impact.

## Why is the support for Key Management Interoperability Protocol (KMIP™) for VMware® service ending?
{: #faq-kmip-eos-reason}
{: faq}

The new key provider, [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect), offers various advantages over the KMIP for VMware adapter that supports the existing Key Protect. The decision to end support was taken due to the following reasons:

* Reduced risk of failure to recover VMs.
* Improved performance due to the shorter network distance for calls from KMIP to key provider.
* Improved visibility and management of KMIP keys.
* No change in pricing when you shift to the new and improved key provider.

## What are the next steps?
{: #faq-kmip-eos-next}
{: faq}

Customers must migrate to the native [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect) offering, or an alternative key management service of your choice by 16 July 2026. For more information about the migration steps, see [Migrating from KMIP for VMware to {{site.data.keyword.cloud_notm}} native KMIP providers](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_migration).

The KMIP for VMware support for Key Protect is not going to be available from 17 July 2026.
{: important}

For any questions or assistance, send an email to clouddigitalsales@us.ibm.com, or [open a support ticket](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) in the VMware Solutions console.

## Are there any challenges that are anticipated during the migration?
{: #faq-kmip-eos-challenges}
{: faq}

Customers who are using vSphere version 7.x can encounter an issue in vSphere HA that results in the restart of virtual machines with vSphere encryption during the rekeying process. However, you can work around this issue. For more information, see [Encrypted VM with Change Block Tracking (CBT) enabled unexpectedly powers off after shallow rekey operation](https://knowledge.broadcom.com/external/article?articleNumber=387897){: external}.

For any questions or assistance, send an email to clouddigitalsales@us.ibm.com, or [open a support ticket](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) in the VMware Solutions console.

## Is there a price change? Does it cost more?
{: #faq-kmip-eos-price}
{: faq}

No, the price of adopting the new key provider, [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect), remains the same as what customers are currently paying for KMIP for VMware support for Key Protect. The existing KMIP adapter for VMware is not chargeable, and the customers are only charged monthly for per key version. The pricing remains the same in the new key provider.

## Related links
{: #faq-kmip-related}

* [End of Support for KMIP for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-eos-kmip)
* [Migrating from KMIP for VMware to {{site.data.keyword.cloud_notm}} native KMIP providers](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_migration)
* [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect)
