---

copyright:

  years:  2016, 2022

lastupdated: "2022-07-15"

keywords: Entrust DataControl, tech specs Entrust DataControl

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Entrust DataControl overview
{: #entrust-dc_considerations}

New installations of Entrust DataControl® (formerly known as HyTrust DataControl) are no longer supported for new or existing deployments of vCenter Server® instances. You can still use or delete existing Entrust DataControl installations on your existing instances.
{: deprecated}

The Entrust DataControl service offers strong encryption with integrated key management to secure workloads throughout their lifecycle. The service provides encryption at both the operating system level and at the data level. This encryption enables any directory, folder, or file within a workload to be encrypted and decrypted.
{: shortdesc}

{{site.data.keyword.vmwaresolutions_full}} offers promotions for some services. Promotional pricing offers a number of months free of charge for a service's licenses, if the service has license charges. For more information, see [Promotions for VMware Solutions services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-service-promotions).

The current Entrust DataControl version that is installed is 5.5. This version is supported for VMware vSphere® 6.7.
{: note}

## Technical specifications for Entrust DataControl
{: #entrust-dc_considerations-specs}

For more information about resource requirements and capacity checking for some services, see [Resource requirements for services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-resource-requirements).

The following components are ordered and included in the Entrust DataControl service:

### Entrust DataControl appliance
{: #entrust-dc_considerations-appliance}

* CPU - 2 CPUs
* RAM - 8 GB
* Disk - 20 GB VMDK resident on vSAN in the consolidated cluster
* Network - Placed on a VLAN-backed private portable network specified for management

### High availability
{: #entrust-dc_considerations-ha}

Two Entrust DataControl appliances are deployed in an active-active configuration.

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

* [Ordering Entrust DataControl](/docs/vmwaresolutions?topic=vmwaresolutions-entrust-dc_ordering)
* [Managing Entrust DataControl](/docs/vmwaresolutions?topic=vmwaresolutions-managing-entrust-dc)
* [Contacting {{site.data.keyword.IBM}} Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Entrust website](https://www.entrust.com/){: external}
