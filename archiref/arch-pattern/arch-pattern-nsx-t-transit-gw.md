---

copyright:

  years:  2022

lastupdated: "2022-04-22"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Architecture pattern for using Transit Gateway with a vCenter Server with NSX-T instance
{: #arch-pattern-nsx-t-transit-gw}

This architecture pattern presents hybrid cloud connectivity by using [{{site.data.keyword.tg_full}}](/docs/transit-gateway?topic=transit-gateway-about). This solution is applicable for NSX-T based vCenter Server instance, which is provisioned in {{site.data.keyword.cloud_notm}} classic infrastructure. This pattern requires a [gateway appliance](/docs/gateway-appliance?topic=gateway-appliance-about#firewall) or [edge services cluster](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-edge-services-cluster) with Juniper vSRX or other third-party device, which supports GRE. In this solution, GRE tunnel is established between this device and Transit GW Router in a specific Zone. NSX-T T0 advertises routes through vSRX (or other device) to Transit Gateway.

## Deploying Transit Gateway with vCenter Server and NSX-T
{: #arch-pattern-nsx-t-transit-gw-overview}

The following diagram presents an overview for an architecture pattern for deploying Transit Gateway with vCenter Server and NSX-T.

![Transit Gateway with vCenter Server and NSX-T](../../images/arch-pattern-vcs-nsx-t-transit-gw.svg "Transit Gateway with vCenter Server and NSX-T."){: caption="Figure 1. Transit Gateway with vCenter Server and NSX-T" caption-side="bottom"}

This architecture pattern deployment is summarized as follows: 

1. vCenter Server instance is deployed at {{site.data.keyword.cloud_notm}} Classic Infrastructure. Two {{site.data.keyword.cloud_notm}} private VLANs and one {{site.data.keyword.cloud_notm}} Public VLAN (optional) is deployed. Each of them hosts multiple subnets. You can see the details through {{site.data.keyword.vmwaresolutions_short}} portal.
2. NSX-T T0 is deployed with two interfaces - private and public (optional). If you opt for a public, this interface is attached to your Public VLAN and has direct internet access. Your T0 private interface is attached to the Private VLAN and it is using {{site.data.keyword.cloud_notm}} Portable Private IP.
3. vSRX (or other device) running on the edge services cluster or gateway appliance is deployed to your Classic Infrastructure. Configure your vCenter Server instance Private Primary VLAN to be routed through the vSRX or Gateway Appliance. Also, establish routing between your NSX-T T0 and vSRX, such as BGP.
4. Order an {{site.data.keyword.tg_full_notm}} at your {{site.data.keyword.cloud_notm}} data center or zone location and [add your classic network as a connection](/docs/transit-gateway?topic=transit-gateway-adding-connections).
5. [Create a GRE connection on your transit gateway](/docs/transit-gateway?topic=transit-gateway-GRE-connection) by using your classic network as the transport for your GRE tunnel. For the remote gateway IP, select your vSRX or gateway appliance private IP. For the Local gateway IP, you can select an IP address to be advertised through your Classic Network to the vSRX or Gateway Appliance. Ensure that your vSRX or Gateway Appliance has a route to this IP. For Local or Remote tunnel IP, you can select the IPs for the GRE tunnel IPs.
6. Your vSRX or Edge Gateway Appliance and Transit Gateway must exchange routes through BGP. TGW can choose a BGP ASN for your NSX-T networks, or you can enter your own ASN when creating the GRE connection in TGW. You must configure your ESG to advertise your preferred NSX-T overlay networks to the Transit Gateway. Ensure that you do not advertise routes that collide with your Classic Private Subnets. Also, ensure that you advertise the networks learned from your NSX-T T0 to the Transit Gateway.
7. [You can add other connections](/docs/transit-gateway?topic=transit-gateway-adding-connections) (VPC or other Classic) to the Transit Gateway. Your VPC IP address allocation design must not overlap with the attached Classic network nor with the NSX-T overlay networks.
8. You can [add {{site.data.keyword.dl_short}} connections to the transit gateway](/docs/transit-gateway?topic=transit-gateway-adding-connections) for on-premises Connectivity. Transit Gateway advertises the attached routes of VPC, Classic Network and GRE tunnel to the attached {{site.data.keyword.dl_short}}.

## Considerations
{: #arch-pattern-nsx-t-transit-gw-considerations}

When you design or deploy this architecture pattern, you must consider the following steps:

* {{site.data.keyword.dl_short}} can be attached as a connection to the Transit Gateway.
* Transit gateway GRE tunnels support traffic flows:
   * From GRE to VPC and from VPC to GRE, and
   * From GRE to {{site.data.keyword.dl_short}} and from {{site.data.keyword.dl_short}} to GRE.
* Plan your AS numbering before you order the GRE tunnels to Transit Gateway.

## Related links
{: #arch-pattern-nsx-t-transit-gw-links}

* [VMware vSphere overview](/docs/vmwaresolutions?topic=vmwaresolutions-vs_vsphereclusteroverview)
* [Getting started with {{site.data.keyword.cloud_notm}} Gateway Appliance](/docs/gateway-appliance?topic=gateway-appliance-getting-started)
* [Getting started with {{site.data.keyword.tg_full_notm}}](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [GRE Configuration Example](https://kb.juniper.net/InfoCenter/index?page=content&id=KB19371&cat=SRX_SERIES&actp=LIST){: external}
