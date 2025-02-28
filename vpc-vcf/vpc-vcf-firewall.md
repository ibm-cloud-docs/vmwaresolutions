---

copyright:

  years:  2024

lastupdated: "2025-02-28"

keywords: vmware cloud foundation, configure firewall, firewall config, vcf for vpc

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Configuring the NSX firewalls for {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-firewall}

Before you configure the VMware NSX® firewalls, review the information in [NSX firewall add-ons](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons#vmware-add-ons-nsx-firewall).

1. From the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-vpc-short}}** from the left navigation pane.
2. In the instances table, click the instance to configure the firewalls for.
3. On the **Access information** tab, under **Management domain**, use the NSX-T admin account for VMware NSX-T Data Center to log in to the VMware NSX-T console.
   * To configure the gateway firewall, see [Gateway Firewall](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/3-2/administration-guide/security/gateway-firewall.html){: external}.
   * To configure the distributed firewall, see [Distributed Firewall](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/3-2/administration-guide/security/distributed-firewall.html){: external}.

The {{site.data.keyword.cloud}} security groups for VPC (Virtual Private Cloud) also provide network security and act as a virtual firewall for your Virtual Server Instances and bare metal servers in the {{site.data.keyword.cloud_notm}} VPC environment by managing east-west and north-south network traffic.

The security groups for VPC provide a convenient way to define and apply rules that establish filtering to a target of a resource, based on protocols, ports, and IP addresses. `uplink-priv-sg` and `uplink-pub-sg` are provisioned for the Tier 0 gateway with default rules, and you can modify these rules based on your needs. For more information, see [About security groups](/docs/vpc?topic=vpc-using-security-groups).

## Related links
{: #vpc-vcf-firewall-links}

* [NSX firewall add-ons](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons&interface=ui#vmware-add-ons-nsx-firewall)
