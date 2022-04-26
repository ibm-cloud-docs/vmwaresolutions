---

copyright:

  years:  2016, 2022

lastupdated: "2022-04-01"

keywords: vSphere order cluster, order vSphere, order vSphere cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Network interface settings
{: #vs_orderinginstances-network-interface-settings}

You must specify the following network interface settings when you order a new VMware vSphere® cluster.

## Host name prefix
{: #vs_orderinginstances-host-name-prefix}

The host name is used for all {{site.data.keyword.cloud}} bare metal server orders. It is recommended to use the host name for all management virtual machines, such as VMware vCenter Server® and VMware NSX®.

The host name prefix must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The host name prefix must start with a lowercase alphabetic character.
* The host name prefix must end with a lowercase alphabetic or numeric character.
* The maximum length of the host name prefix is 10 characters.

## Subdomain label
{: #vs_orderinginstances-subdomain-label}

The subdomain label must meet the following requirements:
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* The subdomain label must start with a lowercase alphabetic character.
* The subdomain label must end with a lowercase alphabetic or numeric character.
* The maximum length of the subdomain label is 10 characters.

The subdomain label is not used for vSphere 7.0 instances.
{: note}

## Domain name
{: #vs_orderinginstances-domain-name}

The domain name is used for all {{site.data.keyword.cloud_notm}} bare metal servers and must meet the following requirements:
* For vSphere 7.0 instances, the domain name must consist of three or more strings that are separated by a period (.)
* For vSphere 6.7 instances, the domain name must consist of two or more strings that are separated by a period (.)
* Only lowercase alphabetic, numeric, and dash (-) characters are allowed.
* Each string must start with a lowercase alphabetic character and end with a lowercase alphabetic or numeric character.
* The last string can contain only lowercase alphabetic characters.
* The length of the last string must be in the range 2 - 24 characters.
* The length of the other strings must be in the range 1 - 63 characters.
* The maximum length of the domain name is 189 characters.

## Networking type
{: #vs_orderinginstances-public-private-network}

Network interface card (NIC) enablement settings are based on your selection of either **Public and private network** or **Private network only**.

## Uplink speed
{: #vs_orderinginstances-uplink}

{{site.data.content.uplink-speed-options-list}}

{{site.data.content.simpletable-uplink-speed-locations}}

## VLANs
{: #vs_orderinginstances-vlans}

Network settings are based on your selection of either **Order new VLANs** or **Select existing VLANs**.

### Order new VLANs
{: #vs_orderinginstances-new-vlans}

If you are ordering for a public and private network, one public VLAN and two private VLANs are required for your cluster order. The two private VLANs are trunked into each bare metal server.

If you are ordering for a private network, two private VLANs are only required for your cluster order.

### Select existing VLANs
{: #vs_orderinginstances-existing-vlans}

Depending on the {{site.data.keyword.cloud_notm}} data center that you selected, existing public and private VLANs might be available.

When you select to reuse existing public and private VLANs, specify the VLANs and subnets:
* **Public VLAN** is for public network access. If you select the **Allocate a new one** option for **Public VLAN**, a new primary public subnet is allocated automatically and cannot be modified.
* **Public primary subnet** is assigned to physical hosts for public network access.
* **Private VLAN** is for connectivity among the data centers and services within the {{site.data.keyword.cloud_notm}}. If you select the **Allocate a new one** option for **Private VLAN**, a new private primary subnet is allocated automatically and cannot be modified.
* **Private primary subnet** is assigned to physical hosts for management traffic.
* **Secondary private VLAN** is for VMware features such as vSAN. You can select an existing secondary private VLAN or select to allocate a new one.

### Important
{: #vs_orderinginstances-important}

* Ensure that the firewall configuration on the selected VLANs does not block the management data traffic.
* Ensure that all VLANs that you select are in the same pod. ESXi servers cannot be provisioned on mixed-pod VLANs.

### FortiGate Physical Appliance 300 Series HA Pair
{: #vs_orderinginstances-fortigate-physical-appliance}

You can also select whether to include the FortiGate® Physical Appliance 300 Series HA Pair to secure your cloud environment. For more information, see [FortiGate Virtual Appliance overview](/docs/vmwaresolutions?topic=vmwaresolutions-fortinetvm_considerations).

This option is only available for an order with both a public and private network.
{: note}

## Related links
{: #vs_orderinginstances-network-related}

* [Summary](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-order-summary)
* [Procedure to order vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-procedure#vs_orderinginstances-procedure-related)
