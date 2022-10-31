---

copyright:

  years:  2016, 2022

lastupdated: "2022-10-07"

keywords: Entrust DataControl, tech specs Entrust DataControl

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Entrust DataControl overview
{: #entrust-dc_considerations}

New installations of Entrust DataControl® (formerly known as HyTrust DataControl) are no longer supported for new or existing deployments of vCenter Server® instances. You can still use or delete existing Entrust DataControl installations on your existing instances.
{: deprecated}

## Technical specifications for Entrust DataControl
{: #entrust-dc_considerations-specs}

The following components are included in your existing Entrust DataControl service.

### Entrust DataControl appliance
{: #entrust-dc_considerations-appliance}

* CPU - 2 CPUs
* RAM - 8 GB
* Disk - 20 GB VMDK resident on vSAN in the consolidated cluster
* Network - Placed on a VLAN-backed private portable network specified for management

### High availability
{: #entrust-dc_considerations-ha}

Two Entrust DataControl appliances in an active-active configuration.

### Licenses and fees
{: #entrust-dc_considerations-licenses}

Per host license - A Entrust DataControl license is ordered for each host in the environment.

## Considerations when you delete Entrust DataControl
{: #entrust-dc_considerations-remove}

Review the following considerations before you delete the service:

* Before you delete the Entrust DataControl service, decouple all clients from using DataControl. After you delete the service, the keys might be deleted, and you might be locked out of your virtual machines.
* If you installed the Entrust DataControl service before VMware® Solutions v4.0, and you then delete that service, you must manually remove the DNS entries. For more information, see [Manually removing the DNS entries](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices#vc_deletingservices-DNS-entries).

## Related links
{: #entrust-dc_considerations-related}

* [Managing Entrust DataControl](/docs/vmwaresolutions?topic=vmwaresolutions-managing-entrust-dc)
* [Contacting {{site.data.keyword.IBM}} Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Entrust website](https://www.entrust.com/){: external}
