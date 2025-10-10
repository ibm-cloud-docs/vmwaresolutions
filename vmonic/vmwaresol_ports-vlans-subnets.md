---

copyright:

  years:  2020, 2025

lastupdated: "2025-10-09"

keywords: VLAN subnets, vmware solutions VLANs, subnets VLAN vmware solutions

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# VLANs and subnets in VMware Solutions
{: #vmwaresol_ports-vlans-subnets}

The following table provides information about the subnets that are used in each VLAN. You can either order new VLANs or subnets for {{site.data.keyword.vcf-auto}} instances or you can select existing VLANs. You can define your firewall rules based on the subnets and ports that the network traffic goes through.

It is not recommended to put a firewall on a secondary private VLAN that has storage and VMware vSphere vMotion® traffic.
{: note}

| Public VLAN | Private VLAN | Secondary private VLAN |
|:------------|:-------------|:-----------------------|
| Primary subnet | Primary subnet | |
| Portable subnets \n - Management edge gateway public \n - Customer edge gateway public | Portable subnets \n - Infrastructure VMs (VMware vCenter Server®, \n VMware NSX® Managers, NSX edges, \n Microsoft® Active Directory VMs, \n IBM® CloudDriver automation VSI) \n - NSX host Tunnel Endpoint (TEP) traffic[^hosttep-v7] \n - Customer edge gateway private | Portable subnets \n - VMware vSAN™ traffic \n - Shared storage traffic \n - vMotion traffic \n - NSX edge TEP traffic \n - Customer edge TEP traffic |
{: caption="Subnets for public, private, and secondary private VLANs" caption-side="bottom"}

[^hosttep-v7]: For Automated instances with vSphere 7

## Related links
{: #vmwaresol_ports--vlans-subnets-related}

* [Ports that are used for deployment and Day 2 operations](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-deploy-day2ops)
