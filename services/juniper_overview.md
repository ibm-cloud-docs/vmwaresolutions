---

copyright:

  years:  2020, 2021

lastupdated: "2021-07-26"

keywords: Juniper vSRX, manage Juniper vSRX, Juniper vSRX virtual security appliance, Juniper virtual security appliance, Juniper vSRX console

subcollection: vmwaresolutions

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:download: .download}
{:preview: .preview}

# Juniper vSRX overview
{: #juniper-overview}

Juniper® vSRX is a virtual security appliance that provides security and networking services at the perimeter or edge in virtualized private or public cloud environments. Within a VMware® infrastructure, vSRX runs as a pair of virtual machines (VMs) within the VMware vSphere® environment.
{: shortdesc}

{{site.data.keyword.vmwaresolutions_full}} offers promotions for some add-on services. Promotional pricing offers a number of months free of charge for a service’s licenses, if the service has license charges. For more information, see [Promotions for VMware Solutions add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-service-promotions).

The current Juniper vSRX version that is installed is 3.0 (20.4R2).
{:note}

For more information about vSRX and the vSRX 3.0 architecture, see [vSRX Deployment Guide for Private and Public Cloud Platforms](https://www.juniper.net/documentation/us/en/software/vsrx/vsrx-consolidated-deployment-guide/index.html){:external}.

You can install Juniper vSRX as one of the following components:
* As a virtual appliance on the management cluster. In this case, Juniper vSRX protects the traffic in the management cluster. That is, the service protects only the traffic that you forward from your devices, for example, setting the default gateway to point to Juniper vSRX.
* As a security or gateway appliance on the edge services cluster. In this case, Juniper vSRX works like a gateway appliance, which you can set without having to configure any devices. Juniper vSRX protects all clusters in the same pod and data center. With this deployment, you route all traffic in the same pod and data center to protect a broader portion of the system.

   You cannot install Juniper vSRX and Fortigate Virtual Appliance on the same edge services cluster.

Juniper vSRX is built on the Junos® operating system (Junos OS™) and delivers networking and security features similar to ones on the software releases for SRX Series Services Gateways.

Juniper vSRX provides a complete Next-Generation Firewall (NGFW) solution, including core firewall, VPN, NAT, advanced Layer 4 through Layer 7 security services such as Application Security, intrusion detection and prevention (IPS), and UTM features, which include Enhanced Web Filtering and Anti-Virus.

You can install multiple instances of Juniper vSRX on the management cluster. On a single edge services cluster, you can install only one instance of Juniper vSRX.

You can manage this service by using the J-Web interface link that is provided on the service details page on the {{site.data.keyword.vmwaresolutions_short}} console.

## Technical specifications for Juniper vSRX
{: #juniper-overview-specs}

For more information about resource requirements and capacity checking for some services, see [Resource requirements for services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-resource-requirements).

The following components are ordered and included in the Juniper vSRX service:

### Virtual machines
{: #juniper-overview-specs-vms}

* vSRX is deployed as a pair of VMs configured for High Availability.
* Each VM is configured with 6 CPUs, 16 GB of memory, and 16 GB of storage. When installed on a cluster with 25 Gb uplink speed, each VM is configured with 10 CPUs, 16 GB of memory, and 16 GB of storage.

### High availability
{: #juniper-overview-specs-ha}

On management cluster installs, the two vSRX nodes are deployed with DRS rules to ensure that the VMs reside on two physically separate hosts and do not migrate, that is, they’re pinned. If a host must be replaced or redeployed, you must adjust the preconfigured DRS rules before you can proceed.

### Networking
{: #juniper-overview-specs-network}

The vSRX appliance can be accessed for administration purposes by either the J-Web console interface or direct ssh access. You can find the IP address information and credentials on the service details page.

### License and fees
{: #juniper-overview-specs-license}

Two license types are offered:
* Standard
* Content Security Bundle

Each license type includes a different set of features and options. The Content Security Bundle license includes all the features and options in the Standard license and additional features, such as:
* AppSecure
* UTM
* SSL Proxy

On 25 Gb uplink speed clusters, only the Content Security Bundle license is available.

For more information about the features and options in each license, see [Choosing a vSRX License](/docs/vsrx?topic=vsrx-getting-started#choosing-license).

Two licenses of the selected type are ordered, one for each of the appliance nodes.

You cannot change the licensing level after service installation. To change the licensing level, you must delete the existing service and reinstall the service by using a different licensing option.
{:important}

If you need to extend your license after expiration, you can update your vSRX license key. For more information, see [Managing Junos OS Licenses](https://www.juniper.net/documentation/en_US/release-independent/licensing/topics/topic-map/managing-junos-os-licenses-for-srx-series.html){:external}.

## Considerations when you install Juniper vSRX
{: #juniper-overview-install-consider}

Review the following considerations before you install the Juniper vSRX service:
* The Juniper vSRX VMs are deployed only into the default cluster or the edge services cluster.
* Juniper vSRX can protect only items in the same data center and pod.
* You are responsible for Juniper vSRX configuration.
* For guidance information about extra configuration options that you might want to include and as an example, see [The IBM Cloud IaaS vSRX default configuration](/docs/vmwaresolutions?topic=vmwaresolutions-vcsvsrx-iaas-def-config). This information does not illustrate your configuration. Your own configuration is different.

## Considerations when you delete Juniper vSRX
{: #juniper-overview-remove-consider}

Any network operations that rely on routes that are established through vSRX might be affected and require reconfiguration.

## Related links
{: #juniper-overview-related-links}

* [Managing Juniper vSRX](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-managing)
* [Ordering services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices)
* [Viewing services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_viewingservices)
* [Deleting services from vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices)
* [General FAQ about VMware Solutions Dedicated](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [Juniper vSRX Virtual Firewall](https://www.juniper.net/us/en/products-services/security/srx-series/vsrx/){:external}
* [Overview of the available virtual SRX models, vSRX, and vSRX 3.0](https://kb.juniper.net/InfoCenter/index?page=content&id=KB33572){:external}
* [Juniper vSRX Documentation](https://www.juniper.net/documentation/product/en_US/vsrx){:external}
