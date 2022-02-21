---

copyright:

  years:  2016, 2022

lastupdated: "2022-01-24"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# System settings
{: #vc_orderinginstance-sys-settings}

You must specify the following system settings when you order a VMware vCenter Server® instance.

## Instance configurations
{: #vc_orderinginstance-inst-config}

* You can select **New configuration** to specify settings for an instance and place the order or save the settings as a configuration template without placing an order.
* You can also select a saved configuration template to further edit it, or to update it and then save it as a new configuration template.

## Instance name
{: #vc_orderinginstance-inst-name}

The instance name is set to **vcs-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

You can also specify an instance name that meets the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The instance name must start with a lowercase alphabetic character.
* The instance name must end with a lowercase alphabetic or numeric character.
* The maximum length of the instance name is 10 characters.
* The instance name must be unique within your account.

## Resource group
{: #vc_orderinginstance-resource-group}

Use resource groups to organize the resources in your account for access control and billing purposes. The default resource group in your account is selected by default. You can also select another resource group according to your needs. The resource group that you select cannot be changed after the instance is created.

If **No resource group available** is displayed in this field, you currently do not have the permission to add the instance to any resource group in this account. Contact the account owner to be assigned an Editor or Administrator role on a resource group in the account. For more information, see [IAM access](/docs/account?topic=account-userroles).
{: note}

## Initial cluster name (NSX-V only)
{: #vc_orderinginstance-cluster-name}

The initial cluster name is set to **_instance name_-cluster** by default.

You can also specify a new initial cluster name that meets the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The cluster name must start with a lowercase alphabetic character.
* The cluster name must end with a lowercase alphabetic or numeric character.
* The maximum length of the cluster name is 30 characters.
* The cluster name must be unique within the vCenter Server instance.

## VMware vSphere version
{: #vc_orderinginstance-vsphere-license}

* For vCenter Server with VMware NSX-T® instances, only VMware vSphere® Enterprise Plus 7.0u1 is supported.
* For vCenter Server with NSX-V instances, only vSphere Enterprise Plus 6.7u3 is supported.

### Notes on upgrading to vSphere 7
{: #vc_orderinginstance-vsphere-v6-7-upgrade}

For vCenter Server instances with vSphere 6.7, upgrade to vSphere 7 is supported for selected configurations. If you want to use vSphere 7.0, you have the following options:
* Deploy a new vSphere 7.0 instance and migrate your current workloads to the new instance.
* Contact VMware Solutions Support for assistance with your upgrade process.

Migrating your workloads is recommended in the following cases:
* If you want to perform a hardware refresh.
* If you want to migrate from NSX–V to NSX–T.
* If you want to migrate your existing NSX–T topology with separate management and workload clusters to a converged topology.

## VMware NSX networking solution
{: #vc_orderinginstance-nsx}

* If you select vSphere 7.0u1, the VMware NSX networking solution is set to **NSX-T**.
* If you select vSphere 6.7u3, the VMware NSX networking solution is set to **NSX-V**.

## Instance type
{: #vc_orderinginstance-primary-secondary}

Select whether to order a new primary instance or a secondary instance for an existing primary instance.

## Related links
{: #vc_orderinginstance-sys-related}

* [Licensing settings](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-licensing-settings)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
