---

copyright:

  years:  2021, 2022

lastupdated: "2022-01-31"

keywords: order Security and Compliance Readiness Bundle, order scb instances, order vcs scb
subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Resource details
{: #scb-orderinginstance-res-details}

## Instance configurations
{: #scb_orderinginstance-inst-config}

* You can select **New configuration** to specify settings for an instance and place the order or save the settings as a configuration template without placing an order.
* You can also select a saved configuration template to further edit it, or to update it and then save it as a new configuration template.

## Instance name
{: #scb-orderinginstance-inst-name}

The instance name is set to **vcs-_xx_** by default, where _xx_ represents two randomly generated alphabetic characters.

You can also specify an instance name that meets the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The instance name must start with a lowercase alphabetic character.
* The instance name must end with a lowercase alphabetic or numeric character.
* The maximum length of the instance name is 10 characters.
* The instance name must be unique within your account.

## Resource group
{: #scb-orderinginstance-resource-group}

Use resource groups to organize the resources in your account for access control and billing purposes. The default resource group in your account is selected by default. You can also select another resource group according to your needs. The resource group that you select cannot be changed after the instance is created.

If **No resource group available** is displayed in this field, you currently do not have the permission to add the instance to any resource group in this account. Contact the account owner to be assigned an Editor or Administrator role on a resource group in the account. For more information, see [IAM access](/docs/account?topic=account-userroles).
{: note}

## VMware properties
{: #scb-orderinginstance-vm-prpt}

* VMware vSphere® version (vSphere 7.0u1)
* Network virtualization platform (VMware vCenter Server® with NSX-T™)
* Instance type (Primary)

## Related links
{: #scb-orderinginstance-res-details-related}

* [Licensing](/docs/vmwaresolutions?topic=vmwaresolutions-scb-orderinginstance-licensing)
* [Procedure to order VMware Security and Compliance Readiness Bundle](/docs/vmwaresolutions?topic=vmwaresolutions-scb-orderinginstance-procedure)
