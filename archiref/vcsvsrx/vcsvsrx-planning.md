---

copyright:

  years:  2019, 2022

lastupdated: "2022-04-22"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# vSRX single data center edge
{: #vcsvsrx-planning}

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

There are two options for deploying a vSRX HA cluster:

* Deploy gateway on bare metal servers - deploys vSRX on a KVM-based host.
* Deploy gateway as part of the {{site.data.keyword.vmwaresolutions_full}} offering (edge services cluster) - deploys vSRX on a VMware vSphere® ESXi™ hypervisor.
  
The two vSRX nodes are tied together in a highly available chassis cluster and deliver a reliable gateway solution that provides for continuous network traffic flows through the loss of a host that supports a node or a vSRX node.

These features are common to both deployment types.
- Provides high availability pair within a single data center.
   - Pair of vSRX gateway appliance hosts.
   - NFS storage shared between the hosts.
- Full vSRX firewall and routing capability implemented.

The following features are unique to a deployment with the ESXi as the host OS.
- VXLAN connectivity into a VMware vCenter Server® instance.
- Ability to host extra VMs on the edge services cluster.
- NSX edges, load balancers.

The basic vSRX offering architecture places a vSRX in front of all the VLANs deployed into a customer account. The vSRX is a powerful Vyatta replacement for situations in which a customer-controlled gateway appliance is desirable.

The following figure represents the typical vSRX deployment.

![Figure 1 - vSRX overview](../../images/vcsvsrx-logical-overview.svg){: caption="Figure 1. vSRX overview" caption-side="bottom"}

The deployment of the VMware vCenter Server® instance is required before the vSRX edge gateway appliance order is placed.
{: note}

## Understanding the default vSRX configuration
{: #vcsvsrx-planning-default-vsrx}

Understanding the default configuration helps both an understanding of the vSRX HA Chassis Cluster and {{site.data.keyword.cloud_notm}} underlay networking. The default configuration is the base upon which all further integration is done.

For more information, see [Understanding the vSRX Default Configuration](/docs/vsrx?topic=vsrx-understanding-the-vsrx-default-configuration#understanding-the-vsrx-default-configuration) and [IBM Cloud IaaS vSRX default configuration](/docs/vmwaresolutions?topic=vmwaresolutions-vcsvsrx-iaas-def-config).

## vSRX and vCenter Server-integrated design
{: #vcsvsrx-planning-vsrx-design}

![Figure 2 - vSRX and vCenter Server integration](../../images/vcsvsrx-vsrx-with-vcs-architecture.svg){: caption="Figure 2. vSRX and vCenter Server integration" caption-side="bottom"}

The tight integration of the vSRX HA Chassis Cluster into a vCenter Server instance extends the basic vCenter Server architecture in a few key areas.

### vCenter Server cluster design
{: #vcsvsrx-planning-vcs-design}

When a vCenter Server instance is deployed to a customer account it is typically a single hyper-converged cluster in which compute, management, and edge functions are delivered by a single three ESXi host (NFS shared storage) or four node (vSAN shared storage) cluster configuration.

The addition of the vSRX offering on ESXi impacts the basic vCenter Server design by moving the edge services out of the hyper-converged cluster onto a dedicated two ESXi host cluster. The edge services cluster is managed by the existing vCenter Server that is deployed with the initial vCenter Server instance.

#### Host sizing
{: #vcsvsrx-planning-host-sizing}

The current vSRX offering has limited hardware options for deployment. Since these options are not variable, it is recommended that you review the options available in the [IBM Cloud infrastructure customer portal](https://control.softlayer.com/network/gatewayappliances).

### Network design
{: #vcsvsrx-planning-network-design}

The vCenter Server offering is designed to manage east-west network traffic at the SDN layer by using NSX distributed logical routers (DLR) and virtual tunnel endpoints (VTEP) on each ESXi host and north-south traffic through NSX edge services gateways (ESG). The vSRX is not a replacement for the DLR but can either assist or potentially replace the ESG firewall services in managing the north-south traffic flows.

The required network design changes are modest and include all customer VM traffic no matter the destination, platform management traffic, direct-link traffic, where applicable, and internet bound traffic. Traffic that is explicitly excluded includes VTEP traffic, storage traffic, and vMotion traffic.

NSX can be extended from the compute cluster to the edge services cluster. Or BGP over an IPsec VPN can be used to enable connectivity between the edge and compute clusters. When the traffic that flows between the vCenter Server compute cluster and the edge services cluster is not in conflict with the {{site.data.keyword.cloud_notm}} infrastructure assigned subnets, the use of a local VLAN and subnet is suitable as a transit link.

BGP over IPsec VPN is the preferred method of connecting to a customer on-premises data center whether the connection traverses the internet or passes between the customer and {{site.data.keyword.cloud_notm}} through one of the {{site.data.keyword.cloud_notm}} infrastructure direct-link offerings.

#### Interface mapping for vSRX on VMware
{: #vcsvsrx-planning-interface-map}

The vSRX on the {{site.data.keyword.cloud_notm}} vCenter Server platform has specific connection requirements to enable and maintain the HA chassis cluster.

![Figure 3 - vSRX HA chassis cluster on vCenter Server interconnections](../../images/vcsvsrx-vsrx-vcs-connections.svg){: caption="Figure 3. vSRX HA chassis cluster on vCenter Server interconnections" caption-side="bottom"}

Each network adapter that is defined on the vSRX is mapped to a specific interface, depending on whether the vSRX instance is a stand-alone VM or one of a cluster pair for high availability.

Note the following information for the stand-alone mode.
* The `fxp0` interface is the out-of-band management interface.
* The `ge-0/0/0` interface is the first traffic (revenue) interface.

Note the following information for the cluster mode.
* The `fxp0` interface is the out-of-band management interface.
* The `em0` interface is the cluster control link for both nodes.
* Any of the traffic interfaces can be specified as the fabric links, such as `ge-0/0/0` for `fab0` on `node 0` and `ge-7/0/0` for `fab1` on `node 1`.

The following table shows information for a stand-alone vSRX VM.

Network adapter | Interface name in Junos OS
---|---
1| `fxp0`
2| `ge-0/0/0`
3| `ge-0/0/1`
4| `ge-0/0/2`
5| `ge-0/0/3`
6| `ge-0/0/4`
7| `ge-0/0/5`
8| `ge-0/0/6`
{: caption="Table 1. Interface names and mappings for a standalone vSRX VM" caption-side="top"}

The following table shows information for a pair of vSRX VMs in a cluster (node 0 and node 1).

Network adapter | Interface name in Junos OS
---|---
1| `fxp0` (node 0 and 1)
2| `em0` (node 0 and 1)
3| `ge-0/0/0` (node 0) and `ge-7/0/0` (node 1)
4| `ge-0/0/1` (node 0) and `ge-7/0/1` (node 1)
5| `ge-0/0/2` (node 0) and `ge-7/0/2` (node 1)
6| `ge-0/0/3` (node 0) and `ge-7/0/3` (node 1)
7| `ge-0/0/4` (node 0) and `ge-7/0/4` (node 1)
8| `ge-0/0/5` (node 0) and `ge-7/0/5` (node 1)
{: caption="Table 2. Interface names and mappings for a pair of vSRX VMs in a cluster (node 0 and node 1)" caption-side="top"}

#### Default security zone configuration
{: #vcsvsrx-planning-default-sec-zone}

The following table shows the factory default settings for security policies.

Source zone|Destination zone|Policy action
---|---|---
trust|untrust|permit
trust|trust|permit
untrust|trust|deny
{: caption="Table 3. Factory default settings for security policies" caption-side="top"}

As noted previously, the default configuration merely represents a point from which to build the required configuration to meet your requirements. The creation of extra security zones is often necessary to support the various traffic flow patterns present in the account.

## vSRX to client on-premises connections
{: #vcsvsrx-planning-client-config}

The preferred method of linking the {{site.data.keyword.cloud_notm}} vCenter Server instance to a client's existing on-premises data center is BGP.  

If the client intends to connect over the Internet by using eBGP, they must obtain a public autonomous system number (ASN) or use BGP over an IPsec VPN to allow the use of private ASNs.

If the client is using Direct Link, BGP by using private ASNs is possible.

![Figure 4 - vSRX BGP over IBM Direct Link](../../images/vcsvsrx-bgp-direct-link.svg){: caption="Figure 4. vSRX BGP over IBM Direct Link" caption-side="bottom"}

The diagram illustrates one of many potential implementations of BGP from the on-premises data center to the {{site.data.keyword.cloud_notm}}.

The traffic that originates from the client facility flows through AT&T NetBond or other provider into the GNPP router. The GNPP router is peered through BGP to the vSRX gateway deployed into the client's {{site.data.keyword.cloud_notm}} account and all traffic is encapsulated in a GRE tunnel over BGP. The packets that exit the tunnel into the vSRX are then routed to the NSX overlay network through an edge services gateway.

**Next topic:** [vSRX example configuration](/docs/vmwaresolutions?topic=vmwaresolutions-vcsvsrx-default-config)

## Related links
{: #vcsvsrx-planning-related}

* [vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle overview](/docs/vmwaresolutions?topic=vmwaresolutions-vcs-hybridity-intro)
* [Getting Started with IBM Cloud Juniper vSRX](/docs/vsrx?topic=vsrx-getting-started)
* [Juniper Networks vSRX Deployment Guide for VMware](https://www.juniper.net/documentation/en_US/vsrx/information-products/pathway-pages/security-vsrx-vmware-guide-pwp.html){: external}
* [Juniper Networks Requirements for vSRX on VMware](https://www.juniper.net/documentation/en_US/vsrx/topics/reference/general/security-vsrx-vmware-system-requirement.html){: external}
* [Juniper Networks vSRX installation with vSphere Web Client](https://www.juniper.net/documentation/en_US/vsrx/topics/task/installation/security-vsrx-vsphere-client-installing.html){: external}
* [Juniper Networks configuring a vSRX Chassis Cluster in Junos OS](https://www.juniper.net/documentation/en_US/vsrx/topics/task/multi-task/security-vsrx-chassis-cluster-configuring.html){: external}
* [Configure ECMP on VMware NSX](https://letsv4real.com/2016/09/23/configure-ecmp-on-vmware-nsx/){: external}
