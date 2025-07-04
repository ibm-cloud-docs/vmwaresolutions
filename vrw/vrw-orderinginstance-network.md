---

copyright:

  years:  2020, 2025

lastupdated: "2025-06-25"

keywords: vmware regulated workloads, vmware regulated workloads order instance, order vmware regulated workloads, vmware regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Network interface
{: #vrw-orderinginstance-network-interface}

You must specify the following network interface settings when you order a {{site.data.keyword.vcf-auto}} instance.

## Hostname prefix
{: #vrw-orderinginstance-hostname-prefix}

The hostname prefix must meet the following requirements:
* Only lowercase alphabetic, numeric, and hyphen (-) characters are allowed.
* No consecutive hyphens are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the hostname prefix is 10 characters.

The hostname prefix applies to all hosts in the instance.
{: note}

## Domain name
{: #vrw-orderinginstance-domain-name}

The domain name must meet the following requirements:
* The domain name must consist of three or more strings that are separated by a period (.) with a maximum of 50 characters.
* The first string (NetBIOS name) must start with a lowercase alphabetic character and end with a lowercase alphabetic or numeric character. It must not exceed 15 characters.
* All strings, except for the last one, can contain only lowercase alphabetic, numeric, and hyphen (-) characters.
* No consecutive hyphens are allowed.
* The last string can contain only lowercase alphabetic characters.
* The length of the last string must be in the range 2 - 24 characters.

The maximum length of the Fully Qualified Domain Name (FQDN) for hosts and VMs is 63 characters. Domain names must accommodate for this maximum length.
{: restriction}

## DNS configuration
{: #vrw-orderinginstance-dns-config}

The only deployment type that is supported is **Two highly available dedicated Windows server VMs on the management cluster**, which helps enhance security and robustness.

You must provide two Microsoft® Windows® Server 2019 Standard edition licenses to use the two Microsoft Windows VMs.
{: important}

Each license can be assigned only to one single physical server and covers up to two physical processors. One Standard edition license can run two virtualized Microsoft Windows VMs per two-processor server. Therefore, two licenses are required since two Microsoft Windows VMs are deployed in two different hosts.

You have 30 days to activate the VMs.

For more information about ordering Windows Server 2019 licenses, see [Get started with Windows Server 2019](https://learn.microsoft.com/en-us/windows-server/get-started/get-started-with-windows-server){: external}.

## Configure hostnames individually
{: #vrw-orderinginstance-network-diagram}

You can customize the prefix for each hostname by toggling the switch on.

The hostname prefix must meet the following requirements:
* Only lowercase alphabetic, numeric, and hyphen (-) characters are allowed.
* No consecutive hyphens are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the hostname prefix is 13 characters.

## Related links
{: #vrw-orderinginstance-network-related}

* [Resource details](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-resource-details)
* [Procedure to order {{site.data.keyword.rw}}](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-orderinginstance-procedure)
* [{{site.data.keyword.rw}} reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
