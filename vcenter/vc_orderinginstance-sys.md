---

copyright:

  years:  2016, 2022

lastupdated: "2022-07-08"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# General information
{: #vc_orderinginstance-sys-settings}

You must specify the following system settings when you order a VMware vCenter Server® instance.

## VMware vSphere version
{: #vc_orderinginstance-vsphere-license}

VMware vSphere® Enterprise Plus 7.0u1 is supported.

### Notes on upgrading to vSphere 7
{: #vc_orderinginstance-vsphere-v6-7-upgrade}

For vCenter Server instances with vSphere 6.7, upgrade to vSphere 7 is supported for selected configurations. If you want to use vSphere 7.0, you have the following options:
* Deploy a new vSphere 7.0 instance and migrate your current workloads to the new instance.
* Contact VMware Solutions Support for assistance with your upgrade process.

Migrating your workloads is recommended in the following cases:
* If you want to perform a hardware refresh.
* If you want to migrate from VMware NSX–V to VMware NSX–T™.
* If you want to migrate your existing NSX–T topology with separate management and workload clusters to a converged topology.

## VMware NSX networking solution
{: #vc_orderinginstance-nsx}

The VMware NSX® networking solution is NSX-T.

## Instance configurations
{: #vc_orderinginstance-inst-config}

* You can select **New configuration** to specify settings for an instance and place the order or save the settings as a configuration template without placing an order.
* You can also select a saved configuration template to further edit it, or to update it and then save it as a new configuration template.

## Instance name
{: #vc_orderinginstance-inst-name}

The instance name is set to **vcs-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

{{site.data.content.orderinginstance-inst-name-list}}

## Resource group
{: #vc_orderinginstance-resource-group}

Use resource groups to organize the resources in your account for access control and billing purposes. The default resource group in your account is selected by default. You can also select another resource group according to your needs. The resource group that you select cannot be changed after the instance is created.

If **No resource group available** is displayed in this field, you currently do not have the permission to add the instance to any resource group in this account. Contact the account owner to be assigned an Editor or Administrator role on a resource group in the account. For more information, see [IAM access](/docs/account?topic=account-userroles).
{: note}

## Instance type
{: #vc_orderinginstance-primary-secondary}

Select whether to order a new primary instance or a secondary instance for an existing primary instance.

## Related links
{: #vc_orderinginstance-sys-related}

* [Licensing](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-licensing-settings)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
