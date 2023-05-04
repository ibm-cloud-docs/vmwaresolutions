---

copyright:

  years:  2016, 2023

lastupdated: "2023-03-10"

keywords: Entrust CloudControl, tech specs Entrust CloudControl

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Entrust CloudControl on IBM Cloud overview
{: #entrust-cc_considerations}

Entrust CloudControl™ on IBM Cloud (formerly known as HyTrust CloudControl) enforces and controls compliance against security standards, which includes role-based access control (RBAC), approval, and auditing. Entrust CloudControl on IBM Cloud is a non-IBM product that is offered under terms and conditions from Entrust, not IBM.
{: shortdesc}

New installations of Entrust CloudControl are supported only for VMware vCenter Server® with NSX-T™ instances. The Entrust CloudControl version available for deployment is 6.6. Previous installations of Entrust CloudControl 5.6 are still supported for existing VMware® vCenter Server with NSX-V instances V4.7 and earlier. 
{: note}

{{site.data.content.para-promotion-services}}

## Technical specifications for Entrust CloudControl
{: #entrust-cc_considerations-specs}

For more information about resource requirements and capacity checking for some services, see [Resource requirements for services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-resource-requirements).

Entrust CloudControl is preconfigured with connections to the following components:
* Microsoft® Active Directory™
* vCenter Server
* VMware NSX-T

As part of Entrust CloudControl service configuration, global PIP is enabled.

Sample users and groups are preconfigured in Active Directory (AD) and are displayed on the service details page. If you delete Entrust CloudControl, the sample users are deleted from AD too. A sample trust manifest is set up that gives single sign-on (SSO) permissions to the sample users that are created. You can change this setting or customize it for your own requirements.

The following components are ordered and included in the Entrust CloudControl service:

### Entrust CloudControl appliance
{: #entrust-cc_considerations-appliance}

* CPU - 4 CPUs
* RAM - 16 GB
* Disk - 186 GB VMDK
* Network - Placed on VLAN-backed private portable network specified for management

### High availability
{: #entrust-cc_considerations-ha}

Two Entrust CloudControl appliances are deployed in an active-passive configuration.

### Licenses and fees
{: #entrust-cc_considerations-licenses}

Per host license - A Entrust CloudControl license is ordered for each host in the environment.

## Considerations when you delete Entrust CloudControl
{: #entrust-cc_considerations-remove}

Review the following considerations before you delete the service:

* Before you delete Entrust CloudControl, ensure that you disable **Root Password Vaulting**, if configured, and that you delete all protected hosts from Entrust CloudControl.

* If you installed the Entrust CloudControl service before VMware Solutions v4.0, and you then delete that service, you must manually remove the DNS entries. For more information, see [Manually removing the DNS entries](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices#vc_deletingservices-DNS-entries).

## Related links
{: #entrust-cc_considerations-related}

* [Ordering Entrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-entrust-cc_ordering)
* [Managing Entrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-managing-entrust-cc)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Entrust website](https://www.entrust.com/){: external}
