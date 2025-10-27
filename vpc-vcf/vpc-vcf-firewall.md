---

copyright:

  years:  2024, 2025

lastupdated: "2025-10-24"

keywords: configure vdefend gateway firewall, configure vdefend distributed firewall, vdefend firewall config, vcf for vpc, nsx firewall config

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Configuring VMware vDefend Firewall for {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-firewall}

{{site.data.content.vms-deprecated-note}}

Before you configure VMware vDefend™ Firewall (formerly VMware NSX Firewall), review the information in [VMware vDefend Firewall add-on](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons#vmware-add-ons-nsx-firewall).

1. {{site.data.content.ol-intro-ui-vcfvpc}}
2. In the instances table, click the instance to configure the firewalls for.
3. On the **Access information** tab, under **Management domain**, use the NSX-T admin account for VMware NSX-T Data Center to log in to the VMware NSX-T console.
   * To configure VMware vDefend™ Gateway Firewall, see [Gateway Firewall](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/security/gateway-firewall.html){: external}.
   * To configure the VMware vDefend™ Distributed Firewall, see [Distributed Firewall](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/security/distributed-firewall.html){: external}.

The {{site.data.keyword.cloud}} security groups for VPC (Virtual Private Cloud) also provide network security and act as a virtual firewall for your Virtual Server Instances and bare metal servers in the {{site.data.keyword.cloud_notm}} VPC environment by managing east-west and north-south network traffic.

The security groups for VPC provide a convenient way to define and apply rules that establish filtering to a target of a resource, based on protocols, ports, and IP addresses. `uplink-priv-sg` and `uplink-pub-sg` are provisioned for the Tier 0 gateway with default rules, and you can modify these rules based on your needs. For more information, see [About security groups](/docs/vpc?topic=vpc-using-security-groups).

## Related links
{: #vpc-vcf-firewall-links}

* [VMware vDefend Firewall add-on](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons&interface=ui#vmware-add-ons-nsx-firewall)
