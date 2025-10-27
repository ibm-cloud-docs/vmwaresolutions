---

copyright:

  years:  2016, 2025

lastupdated: "2025-10-24"

keywords: network config, network configuration, manage NSX ESG

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Configuring your network to use the customer-managed NSX edge cluster with your VMs
{: #vc_esg_config}

{{site.data.content.vms-deprecated-note}}

Configure the network for your virtual machines (VMs) so you can take advantage of the VMware NSX Edge™ cluster that is deployed in your {{site.data.keyword.vcf-auto}} instances. For more information about the security measures that are in place to help minimize security risk, see [Does the management services NSX Edge pose a security risk?](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions#faq-mgmt-nsx)

VMware NSX® is a network virtualization platform that allows the virtualization of isolated networks and provides several networking services such as switches, routing, and firewalls. For more information about NSX, see [VMware NSX Documentation](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-2/migration-guide/nsx-t-data-center-migration-guide.html){: external}.

As part of the ordering process for your Automated instance, the following actions are completed on your behalf:
* A private customer subnet is ordered to be used by your VMs to access the {{site.data.keyword.cloud}} infrastructure private network.
* A public customer subnet is ordered to allow your VMs to access the internet.
* NSX is deployed and configured in your Automated instance.
* A sample NSX Logical Switch is deployed to be used by the customer workload VMs.
* A sample router is deployed for potential east-west communication between local workloads that are connected to layer 2 (L2) networks. This router is a NSX-T™ Tier 1 Router.
* An NSX Edge appliance is deployed and configured to perform network address translation (NAT). NAT is done from the range of IP addresses of the workload logical switch to a public IP address on the NAT rules.

## Configuring the networking settings for your VMs
{: #vc_esg_config-procedure-config-networking}

To take advantage of NSX for your workload VMs, you must configure a number of settings by completing the following steps when you create your VMs:

1. Set the network adapter of the VM to the workload logical switch:
   1. On the **New Virtual Machine** dialog box, click the **Customize Hardware** tab.
   2. On the **new device** menu, select **Network** and click **Add**.
   3. On the newly added network adapter, select the workload logical switch from the menu. The name of the workload logical switch is `overlay-ls`

   Ensure that you do not select the **Workload Transit** switch.
   {: important}

2. Identify an available IP address for the VM:
   *  The IP address must be in the range of `192.168.10.0/24`. The IP address `192.168.10.1` is reserved (see **Step 3**).
   *  When you configure the networking of the operating system that runs on the VM, use the selected IP address and the netmask `255.255.255.0`.

   You are responsible for managing the range of IP addresses to which you assigned your VMs.
   {: note}

3. Assign the default gateway of the VM as `192.168.10.1`. This address is the IP address of the downlink router port on the customer Tier 1 logical router. The address is connected to the same overlay logical switch as the workload VMs.

## Enabling the SNAT rule
{: #vc_nsx-t_esg_config-procedure-enable-snat-rule}

The SNAT rule is enabled by default. For more information about modifying the existing rules, see [Configure source and destination NAT on a Tier-0 logical router](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/manager-mode/advanced-nat/nat/tier-0-nat/configure-source-and-destination-nat-on-a-tier-0-router.html){: external}.

## Enabling the firewall rule
{: #vc_esg_config-procedure-enable-firewall-rule}

All traffic through the workload NSX edge rule is disabled by default. To allow VMs to use the SNAT rule described in the previous section, you must create a firewall policy and rule to define and allow the traffic. For more information about modifying the existing rules, see [Add a Gateway Firewall Policy and Rule](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/security/gateway-firewall/add-a-gateway-firewall-policy-and-rule.html){: external}.

## Identifying customer subnets details
{: #vc_nsx-t_esg_config-procedure-identify-customer-subnets-details}

The logical routers `<instance_name>-<podname>-<cluster_name>-T1-workload` and `<instance_name>-<podname>-<cluster_name>-T0-workload`, and the edges `cust-edge0` and `cust-edge1` are intended for your own usage. You can modify them to define more NAT rules for inbound or outbound traffic. These rules must use only the IP addresses on the public or private customer subnets that are ordered on your behalf.

To identify the details for the customer subnets so you can use the IP addresses ordered, complete the following steps:

1. {{site.data.content.ol-intro-ui-vcfclassic}}
2. In the **{{site.data.keyword.vcf-classic}}** table, locate and select the instance.
3. Click the **Infrastructure** tab and select the management cluster.
4. Go to the **Network interface** section on the cluster page.
5. Collapse the **Public VLAN** and **Private VLAN** options. The public and private customer subnets are the ones that have the **customer workload edge** phrase in the **Description** field.

Additionally, you can find more details about the customer subnets by completing the following steps in the {{site.data.keyword.slportal}}:

1. Click **Networking > IP Management > Subnets**.
2. Click the filter menu and in the **Subnet** field enter the identifier as seen in the description of **cust-edge0** in the NSX-T Web Client.
3. Review the notes that are shown for the IP addresses. These notes identify which of the subnets and IP addresses are ordered and used during the initial setup.

   Do not use the IP addresses that are ordered and used during the initial setup. However, you can use other IP addresses on these subnets according to your requirements. To set up more network address translation rules, see [Configure an NSX NAT/DNAT/No SNAT/No DNAT/Reflexive NAT](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-2/administration-guide/network-address-translation/configure-an-nsx-nat.html){: external}.
   {: important}

## Ordering more subnets
{: #vc_esg_config-procedure-additional-subnets}

You can order more subnets if the provided subnets do not fulfill your requirements for IP addresses. You can order more public or private static subnets and configure them with the Tier-0 VIP for the subnet's endpoint.

## Related links
{: #vc_esg_config-related}

* [Considerations about changing vCenter Server artifacts](/docs/vmwaresolutions?topic=vmwaresolutions-vcenter_chg_impact#vcenter_chg_impact)
* [FAQ for VCF for Classic](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [VMware NSX-T design](/docs/vmwaresolutions?topic=vmwaresolutions-nsx-t-design)
