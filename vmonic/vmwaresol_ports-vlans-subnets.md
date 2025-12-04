---

copyright:

  years:  2020, 2025

lastupdated: "2025-12-03"

keywords: VLAN subnets, vmware solutions VLANs, subnets VLAN vmware solutions

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# VLANs and subnets in VMware Solutions
{: #vmwaresol_ports-vlans-subnets}

{{site.data.content.vms-deprecated-note}}

The following table provides information about the subnets that are used in each VLAN. You can either order new VLANs or subnets for {{site.data.keyword.vcf-auto}} instances or you can select existing VLANs. You can define your firewall rules based on the subnets and ports that the network traffic goes through.

It is not recommended to put a firewall on a secondary private VLAN that has storage and VMware vSphere vMotion® traffic.
{: note}

| Public VLAN | Private VLAN | Secondary private VLAN |
|:------------|:-------------|:-----------------------|
| Primary subnet | Primary subnet | |
| Portable subnets \n - Management edge gateway public \n - Customer edge gateway public | Portable subnets \n - Infrastructure VMs (VMware vCenter Server®, \n VMware NSX® Managers, NSX edges, \n Microsoft® Active Directory VMs, \n IBM® CloudDriver automation VSI) \n - Customer edge gateway private | Portable subnets \n - VMware vSAN™ traffic \n - Shared storage traffic \n - vMotion traffic \n - NSX TEP traffic for hosts and edges |
{: caption="Subnets for public, private, and secondary private VLANs" caption-side="bottom"}

## Related links
{: #vmwaresol_ports--vlans-subnets-related}

* [Ports that are used for deployment and Day 2 operations](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-deploy-day2ops)
