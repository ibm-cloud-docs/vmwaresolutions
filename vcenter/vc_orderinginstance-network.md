---

copyright:

  years:  2016, 2025

lastupdated: "2025-05-29"

keywords: network interface, domain name, hostname prefix, configure hostnames, dns configuration

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Network interface
{: #vc_orderinginstance-network-interface-settings}

You must specify the following network interface settings when you order a {{site.data.keyword.vcf-auto}} instance.

## Hostname prefix
{: #vc_orderinginstance-host-name-prefix}

The hostname prefix applies to all clusters in the instance. It must meet the following requirements:
* Only lowercase alphabetic, numeric, and hyphen (-) characters are allowed.
* No consecutive hyphens are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the hostname prefix is 10 characters.

## Domain name
{: #vc_orderinginstance-domain-name}

The root domain name must meet the following requirements:
* The domain name must consist of three or more strings that are separated by a period (.) with a maximum of 50 characters.
* The first string (NetBIOS name) must start with a lowercase alphabetic character and end with a lowercase alphabetic or numeric character. It must not exceed 15 characters.
* All strings, except for the last one, can contain only lowercase alphabetic, numeric, and hyphen (-) characters.
* No consecutive hyphens are allowed.
* The last string can contain only lowercase alphabetic characters.
* The length of the last string must be in the range 2 - 24 characters.

The maximum length of the Fully Qualified Domain Name (FQDN) for hosts and VMs is 63 characters. Domain names must accommodate for this maximum length.
{: restriction}

## Configure hostnames individually
{: #vc_orderinginstance-network-diagram}

You can customize the prefix for each hostname by toggling the **Configure hostnames individually** switch on.

The hostname prefix must meet the following requirements:
* Only lowercase alphabetic, numeric, and hyphen (-) characters are allowed.
* No consecutive hyphens are allowed.
* The hostname prefix must start with a lowercase alphabetic character.
* The hostname prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the hostname prefix is 10 characters.

## DNS configuration
{: #vc_orderinginstance-dns-config}

Select the Domain Name System (DNS) configuration for your instance:

* **Single public Windows VSI for Active Directory/DNS** - A single Microsoft® Windows® Server VSI for Microsoft® Active Directory™ (AD) is deployed and can be looked up. The VSI functions as the DNS for the instance where the hosts and VMs are registered.
* **Two highly available dedicated Windows Server VMs on the consolidated cluster** - Two Microsoft Windows® VMs are deployed, which enhances security and robustness.

You must provide two Microsoft Windows Server 2019 Standard edition licenses if you configure your instance to use two Windows Server VMs.
{: important}

Each license can be assigned only to one single physical server and covers up to two physical processors. One Standard edition license can run two virtualized Windows VMs per 2-processor server. Therefore, two licenses are required since two Windows VMs are deployed on two different hosts.

You have 30 days to activate the VMs.

For more information about ordering Windows Server 2019 licenses, see [Get started with Windows Server 2019](https://learn.microsoft.com/en-us/windows-server/get-started/get-started-with-windows-server){: external}.

## Related links
{: #vc_orderinginstance-network-related}

* [Add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-addon-services)
* [Procedure to order Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
