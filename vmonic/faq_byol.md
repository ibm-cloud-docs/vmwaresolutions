---

copyright:

  years:  2016, 2025

lastupdated: "2025-05-24"

keywords: FAQ, license, BYOL

subcollection: vmwaresolutions

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQ about BYOL for VMware
{: #faq_byol}

## What is BYOL and is it supported for VMware perpetual licenses?
{: #faq_byol-def}
{: faq}
{: support}

BYOL (Bring Your Own License) was a feature available to {{site.data.keyword.vcf-classic}} instances in version 2.0 and later. Previously, {{site.data.keyword.cloud}} allowed customers to bring their own licenses (BYOL) when moving their existing on-premises VMware® workloads to {{site.data.keyword.cloud_notm}}.

BYOL is no longer allowed by VMware. You cannot bring your own licenses for any new hosts. This restriction applies to all VMware products that are available through {{site.data.keyword.cloud_notm}}.

For existing BYOL servers, you can complete upgrades and migrations to refresh the software and hardware.

## How is BYOL affected by the new packaging and pricing on 1 May 2024?
{: #faq_byol-new-pack}
{: faq}
{: support}

If you are using BYOL (Bring Your Own License) for all VMware software licenses in your instance, this change does not impact you. However, if you are using VMware licenses that are provided by IBM or a mix of IBM-provided licenses and BYOL, you are updated to VMware Cloud Foundation™ on 1 May 2024 and billed at its pricing.

## Can you use the BYOL feature for some VMware components and purchase monthly licenses for others?
{: #faq_byol-mthly-license}
{: faq}

Yes. You can continue to use the BYOL feature for clusters that already have BYOL. You must purchase licenses from IBM for any new combination of the four VMware components. The {{site.data.keyword.vmwaresolutions_short}} console makes it straightforward for you to select the licensing option when you order your instance. Select **I will provide**, and enter your own license key only if you are performing an upgrade or migration of an existing BYOL cluster.

## For a specific VMware component, can you use BYOL for some licenses and buy the rest of licenses from IBM?
{: #faq_byol-purchase}
{: faq}

Yes. If you selected BYOL for a specific VMware component when you created a cluster, you have the following options:

* Continue to use an existing BYOL key.
* Purchase IBM-provided licensing for any new clusters.

Currently, only VMware vSphere Enterprise and VMware vSAN can be licensed per cluster.

You cannot mix and match BYOL and IBM-provided licensing for any VMware component within a cluster.
{: note}

## Can you use BYOL when you create a cluster?
{: #faq_byol-cluster}
{: faq}

No. BYOL is no longer supported except for migrations or upgrades of existing BYOL clusters. Select **I will provide**, and enter your own license key only if you are performing an upgrade or migration of an existing BYOL cluster.

## How do you manage BYOL licenses?
{: #faq_byol-mgmt}
{: faq}

You can manage your BYOL licenses by using the VMware vSphere Web Client.

## Does IBM provide support if you select the BYOL licensing option?
{: #faq_byol-support}
{: faq}

IBM Support continues to be your first point of contact for any {{site.data.keyword.vmwaresolutions_short}} offering. However, if the reported concern is determined to be for a BYOL VMware component, you are instructed to raise a service request directly to Broadcom Support.

## Can you renew BYOL?
{: #faq_byol-renew}
{: faq}

No. If the contract that is providing BYOL ends and is up for renewal, new licenses must be purchased from IBM.

## What happens if the license key you provided is not correct?
{: #faq_licensing-incorrect-license}
{: faq}

All license keys that you provide are validated to ensure that the following conditions are met:
* They are correct for the corresponding VMware components.
* They meet the minimum edition and CPU requirements of the VMware components.

If the validation of any license key fails, you get a notification and you cannot proceed with the instance order.

## Can you provide a license key with more than 8 CPUs?
{: #faq_licensing-license-key}
{: faq}

Yes. For each VMware component, one license per CPU is required. Currently, all VMware vCenter Server® servers have two CPUs. Therefore, two licenses are required for each server. It is recommended that you provide a license key that can support the base instance and any expansion nodes that you want to add to the instance in the future.

## Related links
{: #faq_byol-related}

* [FAQ about licensing and metering](/docs/vmwaresolutions?topic=vmwaresolutions-faq_usage-meter)
* [Accessing the console](/docs/vmwaresolutions?topic=vmwaresolutions-loginmethod)
* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
