---

copyright:

  years:  2022

lastupdated: "2022-10-27"

keywords: cyber recovery, IBM Cloud cyber recovery, cyber recovery network interface, network interface cyber recovery, cyber recovery order instance, order cyber recovery, cyber recovery instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Network interface
{: #cr_orderinginstance-net-interface}

You must specify the following network interface settings when you order a Cyber Recovery instance.

## Hostname prefix
{: #cr_orderinginstance-net-interface-hostname-prefix}

The hostname prefix must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* No consecutive dash characters are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the hostname prefix is 10 characters.

The hostname prefix applies to all hosts in the instance.
{: note}

## Domain name
{: #cr_orderinginstance-net-interface-domain-name}

The domain name must meet the following requirements:
* The domain name must consist of three or more strings that are separated by a period (.) with a maximum of 50 characters.
* The first string must start with a lowercase alphabetic character.
* The first string must end with a lowercase alphabetic or numeric character.
* All strings, except for the last one, can contain only lowercase alphabetic, numeric, and dash (-) characters.
* No consecutive dash characters are allowed.
* The last string can contain only lowercase alphabetic characters.
* The length of the last string must be in the range 2 - 24 characters.

The maximum length of the Fully Qualified Domain Name (FQDN) for hosts and VMs is 50 characters. Domain names must accommodate for this maximum length.
{: note}

## DNS configuration
{: #cr_orderinginstance-net-interface-dns-config}

Select the DNS configuration for your instance:

* **Single public Windows VSI for Active Directory/DNS** - A single Microsoft® Windows® Server VSI for Microsoft Active Directory™ (AD) is deployed and can be looked up. The VSI functions as the DNS for the instance where the hosts and VMs are registered.
* **Two highly available dedicated Windows server VMs on the management cluster** - Two Microsoft Windows® VMs are deployed, helping enhance security and robustness.

You must provide two Microsoft Windows Server 2019 Standard edition licenses if you configure your instance to use the two Microsoft Windows VMs.
{: important}

Each license can be assigned only to one single physical server and covers up to two physical processors. One Standard edition license can run two virtualized Microsoft Windows VMs per 2-processor server. Therefore, two licenses are required since two Microsoft Windows VMs are deployed in two different hosts.

You have 30 days to activate the VMs.

For more information about ordering Windows Server 2019 licenses, see [Get started with Windows Server 2019](https://docs.microsoft.com/en-us/windows-server/get-started-19/get-started-19){: external}.

## Network diagram
{: #cr_orderinginstance-net-interface-network-diagram}

You can customize the hostnames prefix individually by selecting **Configure hostnames individually**. It must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* No consecutive dash characters are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.

## Related links
{: #cr_orderinginstance-net-interface-related-links}

* [Resource details](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-resource-details)
* [Procedure to order a Cyber Resource instance](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-order-procedure)
