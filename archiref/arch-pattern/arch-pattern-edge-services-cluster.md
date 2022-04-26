---

copyright:

  years:  2022

lastupdated: "2022-04-07"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Architecture pattern for using edge services cluster with NSX-T
{: #arch-pattern-edge-services-cluster}

When you deploy a vCenter Server instance in your {{site.data.keyword.cloud}} classic infrastructure, you might optionally deploy an edge services cluster. 

Edge services cluster might host, for example, a Juniper vSRX or third-party router or firewall. You can control which VLANs will be routed through the router or firewall that is running on it through the [gateway appliance](/docs/gateway-appliance?topic=gateway-appliance-about#firewall) configurations.

**Edge services cluster** must not be mixed with **NSX-T edge cluster**, which consists of NSX-T edge transport nodes. Edge services cluster provides compute capacity for Juniper vSRX or third-party router or firewalls. The VLAN routing can be controlled by [gateway appliance configuration](/docs/gateway-appliance?topic=gateway-appliance-managing-vlans-and-gateway-appliances) in {{site.data.keyword.cloud_notm}} classic network.
{: important} 

## Deploying edge services cluster with NSX-T
{: #arch-pattern-edge-services-cluster-overview}

The following diagram presents an overview for an architecture pattern for deploying edge services cluster with NSX-T.

![Edge services cluster with NSX-T](../../images/arch-pattern-nsx-t-edge-services-cluster.svg "Edge services cluster with NSX-T."){: caption="Figure 1. Edge services cluster with NSX-T" caption-side="bottom"}

The architecture pattern deployment is summarized as follows: 

1. You can optionally deploy an edge services cluster to host Juniper vSRX or your own routing or firewall device. This cluster is attached to both {{site.data.keyword.cloud_notm}} private and public networks through transit networks. 
2. vSRX or the third-party device can route assigned VLANs through it. You can choose the VLANs to be routed through it from {{site.data.keyword.cloud_notm}} portal. You must configure the required VLAN interfaces and IP addresses to the devices as well as firewall zones, rules, and policies.
3. If you route your management VLAN through the firewall, you can also secure your management workloads, such as vCenter and NSX-T managers. Ensure that you allow the traffic for your management.
4. Your workload T0 is attached to {{site.data.keyword.cloud_notm}} private network. If you route this VLAN through the firewall, add the required rules on both the firewall and T0.
5. Your workload T0 is attached to {{site.data.keyword.cloud_notm}} public network. If you route this VLAN through the firewall, add the required rules on both the firewall and T0.
6. Alter the automation deployed routes if you need to customize the routing behavior, or establish dynamic routing between your T0 and the vSRX (or third-party device).

## Considerations
{: #arch-pattern-edge-services-cluster-considerations}

When you design or deploy this architecture pattern, consider the following steps: 

* Refer to the specific third-party vendor HW and SW specifications for interoperability with VMware® ESXi™ and NSX-T™.
* You must provide licensing (BYOL) for the third-party router or firewall solution. Contact your vendor for details.

## Related links
{: #arch-pattern-edge-services-cluster-links}

* [VMware vSphere overview](/docs/vmwaresolutions?topic=vmwaresolutions-vs_vsphereclusteroverview)
* [Getting started with {{site.data.keyword.cloud_notm}} Gateway Appliance](/docs/gateway-appliance?topic=gateway-appliance-getting-started)
* [Tier-0 Gateways](https://docs.vmware.com/en/VMware-NSX-T-Data-Center/3.1/administration/GUID-E9E62E02-C226-457D-B3A6-FE71E45628F7.html){: external}
