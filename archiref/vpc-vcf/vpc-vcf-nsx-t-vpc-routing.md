---

copyright:

  years:  2022

lastupdated: "2022-08-09"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# VMware NSX-T logical routing on VPC
{: #vpc-vcf-nsx-t-vpc-routing}

When you design logical network topologies on {{site.data.keyword.vpc_full}} hosted in VMware NSX-T™, you must decide how to route the traffic of NSX-T segment attached workloads between NSX-T, {{site.data.keyword.vpc_short}}, and public internet.

The following diagram presents an overview of the routing between NSX-T Logical Routers and VPC.

![VPC routing with NSX-T Logical Routers](../../images/vcf-on-vpc-overlay-routing.svg "VPC routing with NSX-T Logical Routers"){: caption="Figure 1. VPC routing with NSX-T Logical Routers" caption-side="bottom"}

If your design does not need direct inbound public access, you can customize the architecture. Various customization aspects of the connectivity architecture are discussed in the following topics.

## Routing between Tier-0 and Tier-1 logical routers
{: #vpc-vcf-nsx-t-vpc-routing-edge-tier-0-routing-t1}

In this design, the workloads are connected to NSX-T overlay segments behind T1, and when T1 is connected to its parent T0, it has a default route that points to the T0. By default, T0 does not detect the segments that are attached to T1, where route advertisement is needed.

If you want to route natively with {{site.data.keyword.vpc_short}} subnets and other connected service without using NAT in T1, enable route advertisement of "All Connected Segments & Service Ports" in the specific T1. You must not configure a routing protocol or static routes between T1 and T0 logical routers. After you enable the route advertisement, NSX-T creates routes automatically. With this approach, you have all connected segments on your T1 routed to T0, and then you can decide how to proceed with the public and private traffic in T0.

## Public traffic between Tier-0 and VPC
{: #vpc-vcf-nsx-t-vpc-routing-edge-tier-0-routing-public}

If your workloads need direct public traffic and have inbound public traffic without using any network translation, you must provision the public uplink subnet and public T0 uplink VLAN interfaces. Also, you must configure your T0 with public uplinks as described in the topic [Tier-0 logical router](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-nsx-t-logical-routers#vpc-vcf-nsx-t-logical-routers-edge-tier-0) previously. As the NSX-T T0 uses Active-Standby, the HA VIP provides high availability for the routing of public traffic between VPC, T0, and your NSX-T workloads. When you need public IP addresses, you can order floating IP address to the HA VIP VLAN interface. Each floating IP address is a single `/32` IP address, and you can order as many as you need within [VPC Quotas](/docs/vpc?topic=vpc-quotas).

Interface name | Interface type | VLAN ID | Subnet | Allow float | Allow IP spoofing | Enable infra NAT| NSX-T interface | Segment name
----------------------------|----------------|---------|------------------------------|--------------|-------------------|-------------------|----------------------------|------------------------------
vlan-nic-t0-pub-uplink-vip  | vlan           | 2711    | vpc-t0-public-uplink-subnet  | true         | false             | false             | T0 Public Uplink VIP       | vpc-zone-t0-public-*vlanid*
{: caption="Table 1. Public uplink HA VIP to be used for public floating IPs" caption-side="bottom"}

VLAN interfaces with `Allow IP spoofing` and `Enable Infrastructure NAT` set to `false` allow public floating IP address to traverse non-NATted to the public uplinks of the T0 logical router. For high availability with NSX-T T0 logical router, HA VIPs can be used. When you order floating IP address for public uplinks, always use the VIP VLAN interface instead of the uplinks that are reserved for the actual Edge Nodes.
{: note}

You can currently use the public IP addreses, for example, for the following purposes.

* To perform destination NAT done in either Tier-0 or Tier-1 Logical Routers for inbound public traffic to NSX-T overlay.
* To perform source NAT done in either Tier-0 or Tier-1 Logical Routers for outbound public traffic from NSX-T overlay.
* To establish VPNs in either Tier-0 or Tier-1.

For more information, see [Network Services that are provided by Tier-0 and Tier-1 Logical Routers](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-nsx-t-vpc-routing#vpc-vcf-nsx-t-vpc-routing-edge-services).

For public IP addresses, you can currently use one or more `/32` IP address, but you cannot have subnets, such as `/29` or `/26`.
{: note}

In this case, your default route `0.0.0.0/0` in NSX-T T0 Logical Router must be pointed to the default gateway of the `vpc-t0-public-uplink-subnet`.

Route description           | Device             | CIDR             | Next-hop
----------------------------|--------------------|------------------|----------------------------------------------
Default route               | T0 Logical Router  | 0.0.0.0/0        | Default GW of `vpc-t0-public-uplink-subnet`
{: caption="Table 2. Default route in T0 Logical Router with public uplinks" caption-side="bottom"}

If you do not need inbound traffic from internet, you do not need public uplinks on T0 nor the public VLAN interfaces. Alternatively, you can use Public Gateway in {{site.data.keyword.vpc_short}}, which provides you the outbound internet access from NSX-T overlay segments, and use the T0s private uplinks for this traffic. In this case, your default route `0.0.0.0/0` in NSX-T T0 Logical Router must be pointed to the default gateway of the `vpc-t0-private-uplink-subnet`.

Route description           | Device             | CIDR             | Next-hop
----------------------------|--------------------|------------------|----------------------------------------------
Default route               | T0 Logical Router  | 0.0.0.0/0        | Default GW of `vpc-t0-private-uplink-subnet`
{: caption="Table 3. Default route in T0 Logical Router with private uplinks only" caption-side="bottom"}

## Private traffic between Tier-0 and VPC
{: #vpc-vcf-nsx-t-vpc-routing-edge-tier-0-routing-private}

If you have both Public and Private Uplinks, first you must create a route in NSX-T T0 pointing to the Private networks. You must connect it to the VMware workloads attached to NSX-T overlay segments. These networks must then be reachable through the VPC, or DL/TGW, which the VPC is attached to. The following table shows an example, when private prefix `172.16.0.0/16` is used elsewhere and this prefix is known by VPC, either directly or through attached {{site.data.keyword.dl_short}} (DL) or {{site.data.keyword.tg_short}} (TGW).

Route description           | Device             | CIDR             | Next-hop
----------------------------|--------------------|------------------|----------------------------------------------
Private networks            | T0 Logical Router  | 172.16.0.0/16    | Default GW of `vpc-t0-private-uplink-subnet`
{: caption="Table 4. Private routes in T0 Logical Router with public uplinks" caption-side="bottom"}

If you use only private route, then your default route `0.0.0.0/0` in NSX-T T0 Logical Router routes all traffic to the VPC.
{: note}

You must define inbound traffic from VPC. Then, you must create a VPC route in the Zone to the IP subnet or prefix that you are using in the NSX-T overlay. As the NSX-T T0 uses Active-Standby, the HA VIP provides high availability for the routing of private traffic between VPC and your NSX-T overlay. Therefore, the next-hop for the VPC route must be the HA VIP, as specified on the following table.

Interface name | Interface type | VLAN ID | Subnet | Allow float | Allow IP spoofing | Enable Infra NAT | NSX-T interface | Segment name
----------------------------|----------------|---------|------------------------------|--------------|-------------------|-------------------|----------------------------|------------------------------
vlan-nic-t0-priv-uplink-vip | vlan           | 2712    | vpc-t0-private-uplink-subnet | true         | true              | true              | T0 Private Uplink VIP      | vpc-zone-t0-private-*vlanid*
{: caption="Table 5. VLAN interfaces for T0 uplinks" caption-side="bottom"}

VLAN interfaces with `Allow IP spoofing` and `Enable Infrastructure NAT` set to `true` allow VMware workloads on NSX-T overlay with private IP addresses to be routed to {{site.data.keyword.vpc_short}}. To enable this action, a VPC route is created with IP address of private uplink HA VIP/vlan-nic-t0-priv-uplink-vip as the next-hop configured in the {{site.data.keyword.vpc_short}} Zone.
{: note}

When you plan the routing, summarize the NSX-T overlay subnets, or prefixes to keep the number required routes minimal. When you create a route that points to the NSX-T overlay, the following table provides an example for the required parameters for an NSX-T overlay subnets `192.168.4.0/24`, `192.168.5.0/24`, `192.168.6.0/24`, and `192.168.7.0/24` attached to T1. Further summarized to a prefix `192.168.4.0/22` and by using NSX-T HA VIP `192.168.0.10` in Zone `us-south-2` as the next-hop. For more information about VPC routes, see [VPC routing tables and routes](/docs/vpc?topic=vpc-about-custom-routes).

Route description           | Zone           | Traffic type   | CIDR             | Action    | Type   | Next-hop
----------------------------|----------------|----------------|------------------|-----------|--------|-------------------
NSX-T overlay networks      | us-south-2     | Egress         | 192.168.4.0/22   | Deliver   | IP     | 192.168.0.10
{: caption="Table 6. VPC routes" caption-side="bottom"}

VPC routes are Zone specific.
{: note}

When you create a VPC route, it enables traffic within the Zone or VPC depending on how it is created. If you use any of the interconnectivity options, such as {{site.data.keyword.dl_short}} or {{site.data.keyword.tg_short}}, and you need connectivity from another VPC attached to a TGW, in addition to the VPC route, you can create a VPC prefix by matching the NSX-T overlay subnet or prefix. This action allows both DL and TGW to advertise your NSX-T overlay subnet or prefix to the attached TGW connections or DL. By using the previous example, you can create a VPC prefix by matching the route `192.168.4.0/22`, which enables TGW to advertise this prefix to the other attached VPCs, or Classic. For more information about VPC prefixes and about creating prefixes, see [Bring your own subnet](/docs/vpc?topic=vpc-configuring-address-prefixes).

## Related links
{: #vpc-vcf-nsx-t-vpc-routing-links}

* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} bare metal servers](/docs/vpc?topic=vpc-planning-for-bare-metal-servers)
* [{{site.data.keyword.vpc_short}} RYO VMware reference architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-ryo-arch-overview)
* [{{site.data.keyword.dl_full_notm}} overview](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl)
* [{{site.data.keyword.tg_full_notm}} overview](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [{{site.data.keyword.vpc_short}} VPN overview](/docs/vpc?topic=vpc-vpn-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on bare metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)
