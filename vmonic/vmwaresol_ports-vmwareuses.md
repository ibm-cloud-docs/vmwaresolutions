---

copyright:

  years:  2020, 2025

lastupdated: "2025-10-21"

keywords: VLAN ports, vmware solutions ports, ports usage vmware solutions

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Ports used by VMware components
{: #vmwaresol_ports-vmwareuses}



The following table shows the ports that are used by VMware® by Broadcom components. For more information about the ports that are used for VMware Solutions deployment and Day 2 operations, see [Ports that are used for deployment and Day 2 operations](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-deploy-day2ops).

| Source | Subnet | Target | Subnet | Port | Protocol |
|:------ |:------ |:------ |:------ |:---- |:-------- |
| VMware ESXi™ host | Private primary subnet | VMware vCenter Server® | Infrastructure VMs | 902 | TCP and UDP |
| ESXi host | Private primary subnet | vCenter Server | Infrastructure VMs | 443 | TCP |
| ESXi host | Private primary subnet | NSX® Manager | Infrastructure VMs | 5671 | TCP |
| ESXi host | Private primary subnet | NSX Manager | Infrastructure VMs | 1234 and 1235 | TCP and UDP |
| ESXi host | Private primary subnet | NSX controllers | Infrastructure VMs | 1234 and 1235 | TCP |
| ESXi host | Private primary subnet | Windows® Active Directory™ | Private primary subnet \n Infrastructure VMs | 88 | TCP and UDP |
| ESXi host | Private primary subnet | Windows Active Directory | Private primary subnet \n Infrastructure VMs | 445 | TCP |
| vCenter Server | Infrastructure VMs | ESXi host | Private primary subnet | 902 | TCP and UDP |
| vCenter Server | Infrastructure VMs | ESXi host | Private primary subnet | 443 | TCP |
| vCenter Server | Infrastructure VMs | ESXi host | Private primary subnet | 9080 | TCP |
| vCenter Server | Infrastructure VMs | Windows Active Directory | Private primary subnet \n Infrastructure VMs | 53 | UDP |
| vCenter Server | Infrastructure VMs | Windows Active Directory | Private primary subnet \n Infrastructure VMs | 389 | TCP and UDP |
| vCenter Server | Infrastructure VMs | Windows Active Directory | Private primary subnet \n Infrastructure VMs | 445 | TCP |
| vCenter Server | Infrastructure VMs | Windows Active Directory | Private primary subnet \n Infrastructure VMs | 88 | TCP and UDP |
| NSX Manager | Infrastructure VMs | ESXi host | Private primary subnet | 443 | TCP |
| NSX Manager | Infrastructure VMs | Windows Active Directory | Private primary subnet \n Infrastructure VMs | 53 | UDP |
| UM Appliance without proxy | Infrastructure VMs | `eapi.broadcom.com` |  | 443 | HTTPS |
| UM Appliance with proxy. Ensure that you [enable service endpoints in your account](/docs/account?topic=account-vrf-service-endpoint#service-endpoint) | Infrastructure VMs | `proxy.vmware.cloud.ibm.com` |  | 3128 | HTTPS |
{: caption="Ports used by VMware" caption-side="bottom"}

For more information, see [TCP and UDP ports required to access VMware components](https://knowledge.broadcom.com/external/article?legacyId=1012382){: external}.

## Related links
{: #vmwaresol_ports-vmwareuses-related}

* [Ports for services](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-services)
