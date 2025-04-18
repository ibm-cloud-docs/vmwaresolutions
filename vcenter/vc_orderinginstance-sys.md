---

copyright:

  years:  2016, 2025

lastupdated: "2025-04-17"

keywords: vcf classic order instance, order vcf automated, order vmware cloud foundation instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# General information
{: #vc_orderinginstance-sys-settings}

Specify or accept the following settings when you order a {{site.data.keyword.vcf-auto}} instance.

## VMware vSphere version
{: #vc_orderinginstance-vsphere-license}

* VMware vSphere® Enterprise Plus 8 is selected by default and is supported only for primary instances. 
* vSphere 7 is also available to order.

### Requirements for upgrading to vSphere 8
{: #vc_orderinginstance-vsphere-v7-8-upgrade}

For instances with vSphere 7, you must add a new cluster or host to your existing instance when you upgrade to vSphere 8. For more information, see [Upgrading to vSphere 8.0](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcs_80_upgrade).

### Requirements for upgrading to vSphere 7
{: #vc_orderinginstance-vsphere-v6-7-upgrade}

Upgrading to vSphere 7 is supported for certain instance configurations with vSphere 6.7. To use vSphere 7, deploy a new vSphere 7 instance and migrate your current workloads to the new instance. For assistance with the upgrade process, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

It is recommended to migrate your workloads for the following use cases:
* Performing a hardware refresh.
* Migrating from VMware NSX–V to VMware NSX–T™.
* Migrating your existing NSX–T topology with separate management and workload clusters to a consolidated topology.

## VMware vCenter Server version
{: #vc_orderinginstance-vcenter-license}

{{site.data.content.para-vcsversion80-vcsline1}}

{{site.data.content.para-vcsversion80-vcsline2}}

## Instance name
{: #vc_orderinginstance-inst-name}

The instance name is set to **vcs-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

{{site.data.content.orderinginstance-inst-name-list}}

## Resource group
{: #vc_orderinginstance-resource-group}

{{site.data.content.para-orderinginstance-resource-group}}

{{site.data.content.note-orderinginstance-resource-group}}

## Instance configuration name
{: #vc_orderinginstance-inst-config}

{{site.data.content.paraone-orderinginstance-inst-config}}

{{site.data.content.paratwo-orderinginstance-inst-config}}

## Instance type
{: #vc_orderinginstance-primary-secondary}

{{site.data.content.para-orderinginstance-primary-secondary}}

## Related links
{: #vc_orderinginstance-sys-related}

* [Licensing](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-licensing-settings)
* [Procedure to order Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
