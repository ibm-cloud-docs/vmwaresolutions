---

copyright:

  years:  2016, 2025

lastupdated: "2025-10-24"

keywords: flexible order instance, order vSphere, order flexible instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# General information
{: #vs_orderinginstances-sys-settings}

{{site.data.content.vms-deprecated-note}}

The information that you specify for a new {{site.data.keyword.vcf-flex}} instance is based on an instance configuration template.

## VMware vSphere version
{: #vs_orderinginstance-vsphere-license}

VMware vSphere® Enterprise Plus 8 is selected by default. When you use vSphere 8, consider the following information:
* For new instances, you can use only VMware vCenter Server® 8.
* vSAN storage is not supported with vSphere 8.
* BYOL users can also select a vSphere version for the instance.

## Bring Your Own License
{: #vs_orderinginstance-byol}

{{site.data.content.attnnote-byol}}

If you are a Bring Your Own License (BYOL) user, toggle the **BYOL** switch to **Enabled**.

## VMware vSphere Enterprise Plus license key
{: #vs_orderinginstance-vsphere-license-key}

You must provide a single vSphere® Enterprise Plus edition license key with sufficient capacity for your instance configuration.

## Instance name
{: #vs_orderinginstances-instance-name}

The instance name is set to **vss-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

You can also specify an instance name that meets the following requirements:
* Only lowercase alphabetic, numeric, and hyphen (-) characters are allowed.
* The instance name must start with a lowercase alphabetic character.
* The instance name must end with a lowercase alphabetic or numeric character.
* The maximum length of the instance name is 10 characters.
* The instance name must be unique within your account.

## Resource group
{: #vs_orderinginstance-resource-group}

{{site.data.content.para-orderinginstance-resource-group}}

{{site.data.content.note-orderinginstance-resource-group}}

## Instance configuration name
{: #vs_orderinginstance-instance-config}

{{site.data.content.paraone-orderinginstance-inst-config}}

{{site.data.content.paratwo-orderinginstance-inst-config}}

## Related links
{: #vs_orderinginstances-sys-related}

* [Procedure to order Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-procedure)
