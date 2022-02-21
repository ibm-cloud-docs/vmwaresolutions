---

copyright:

  years:  2016, 2022

lastupdated: "2022-01-24"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Licensing settings
{: #vc_orderinginstance-licensing-settings}

## License options
{: #vc_orderinginstance-licensing-opt}

Specify the licensing options for the VMware® components in the instance.

For VMware vCenter Server® with NSX-T® instances:
* VMware vSphere® Enterprise Plus 7.0
* NSX-T 3.1.1 (Data Center SP Base, Data Center SP Professional, Data Center SP Advanced, or Data Center SP Enterprise Plus)

The VMware HCX™ service is not available for Data Center SP Enterprise Plus.

Small differences exist between NSX-T Data Center and Data Center SP editions. For more information, see [Product offerings for VMware NSX-T Data Center 3.1.x (80866)](https://kb.vmware.com/s/article/80866){: external}.
{: note}

For vCenter Server with NSX-V instances:
* vSphere 6.7
* NSX Service Providers 6.4 (Base, Advanced, or Enterprise edition). The VMware HCX service requires either the NSX Advanced or NSX Enterprise edition license.

For Business Partner users, the vCenter Server license (Standard edition), the vSphere license (Enterprise Plus edition), and the NSX license are included and purchased on your behalf. However, you must specify the edition for the NSX license.

For users who are not Business Partners, you can use the IBM-provided VMware licenses for these components by selecting **Include with purchase**, or you can Bring Your Own License (BYOL) by selecting **I will provide** and entering your own license keys.

## Licensing notes
{: #vc_orderinginstance-licensing-notes}

* The minimum number of licenses for BYOL that are required depends on the number of CPUs per server and the number of servers in the order. The license choice for each VMware component applies to the base instance and to any ESXi servers that you add to the instance later. Ensure that your license supports future capacity expansion in your infrastructure.
* The minimum license editions are indicated on the user interface. If different component editions are supported, you can select the edition that you want. You are responsible to ensure that the license key provided is correct for each VMware component selected.
* For vSphere, a license charge is incurred at the time of order, but the license charge is then credited to your account.
* You can change any licenses that you provided by using the VMware vSphere Web Client after the instance deployment is completed.
* Support for the VMware components that you provide licenses is provided by VMware, not by IBM Support.

## Related links
{: #vc_orderinginstance-licensing-related}

* [Cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-mngt-workload-cluster-settings)
* [Procedure to order vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure)
