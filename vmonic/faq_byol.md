---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-14"

---

{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}

# FAQ about licensing and BYOL
{: #faq_byol}

Find answers to frequently asked questions about licensing, including the Bring Your Own License (BYOL) feature of {{site.data.keyword.vmwaresolutions_full}}.

## What is BYOL?
{: #faq_byol-def}

Bring Your Own License, or BYOL, is a feature available to VMware Cloud Foundation instances in V1.8 and later, and to VMware vCenter Server and VMware vSphere clusters in V2.0 and later. With BYOL, you can use your own VMware licenses for one or more of the following VMware software components:
* VMware vCenter Server
* VMware vSphere
* VMware NSX
* VMware vSAN

If you choose to use your own license for a VMware component and provide a valid license key for it, no license is ordered from IBM for this component and no monthly license charges are incurred to your {{site.data.keyword.cloud_notm}} infrastructure account for this component.

The BYOL feature is not available to Business Partner users.
{:note}

## Where do I manage the licenses and components that are ordered through VMware vSphere on IBM Cloud?
{: #faq_byol-license-mgmt}

After an order to create a new cluster for VMware vSphere on {{site.data.keyword.cloud_notm}} is placed, the VMware licenses, ESXi servers, and other networking components, are delivered and can be managed from the {{site.data.keyword.slportal}}.

After deployment, go to the {{site.data.keyword.vmwaresolutions_short}} console to scale the new cluster by using the saved configuration. For more information, see [Scaling existing vSphere clusters](/docs/services/vmwaresolutions/vsphere?topic=vmware-solutions-vs_scalingexistingclusters).

## What license editions and CPUs are required for BYOL?
{: #faq_byol-license-cpu-reqs}

The following requirements apply to the license editions for BYOL.

### BYOL requirements for vCenter Server instances
{: #faq_byol-vcs-reqs}

Table 1. License editions and CPU minimum requirements for vCenter Server instances

  | VMware component | License edition required | Minimum CPU required
  |:-------------  |:-------------  |:-------|
  | vCenter Server | Standard                | N/A |
  | vSphere        | Enterprise Plus | 8 CPUs |
  | vSAN           | Advanced or Enterprise | 8 CPUs |
  | NSX            | Standard, Advanced, or Enterprise | 8 CPUs |

### BYOL requirements for Cloud Foundation instances
{: #faq_byol-cf-reqs}

Table 2. License editions and CPU minimum requirements for Cloud Foundation instances

  | VMware component | License edition required | Minimum CPU required
  |:-------------  |:-------------  |:-------|
  | vCenter Server | Standard | N/A |
  | vSphere        | Enterprise Plus | 8 CPUs |
  | vSAN           | Advanced or Enterprise | 8 CPUs |
  | NSX            | Enterprise | 8 CPUs |

## What happens if the license key I provided is not correct?
{: #faq_byol-incorrect-license}

All the license keys that you provide are validated to ensure that they are correct for the corresponding VMware components and that they meet the minimum edition and CPU requirements of the VMware components. If the validation of any license key fails, you get a notification and you cannot proceed with the instance order.

## Can I provide a license key with more than 8 CPUs?
{: #faq_byol-license-key}

Yes. For each VMware component, one license per CPU is required. Currently, all vCenter Server and Cloud Foundation servers have two CPUs. Therefore, two licenses are required for each server. It is recommended that you provide a license key that can support the base instance and any expansion nodes that you want to add to the instance in the future.

## Can I provide the SDDC Manager license if I use the BYOL feature?
{: #faq_byol-sddc}

No. Our agreement with VMware requires that we must accept a client’s actual license key. Although the Cloud Foundation deployment includes SDDC Manager licenses, we cannot accept SDDC Manager license key files and validate them for BYOL. Therefore, SDDC Manager licenses are charged by IBM for all instances. SDDC Manager licenses represent a small portion of the overall license charges for a Cloud Foundation instance.

## Can I use the BYOL feature for some VMware components and purchase monthly licenses for others?
{: #faq_byol-mthly-license}

Yes. You can use the BYOL feature or purchase licenses for any combination of the four VMware components. The {{site.data.keyword.vmwaresolutions_short}} console makes it straightforward for you to select the licensing option when you order your instance. Your licensing option at the time of initial instance order applies for the lifetime of that instance.

## For a specific VMware component, can I use BYOL for some licenses and buy the rest of licenses from IBM?
{: #faq_byol-purchase}

Yes. If you selected BYOL for a specific VMware component when you create a cluster, you have the following options:
* Enter a new BYOL key
* Continue to use an existing BYOL key
* Purchase IBM-provided licensing for that cluster.

Currently, only VMware vSphere Enterprise and VMware vSAN can be licensed per cluster.

## Can I use BYOL when I create a cluster?
{: #faq_byol-cluster}

Yes. You can BYOL from existing BYOL licenses or enter a new BYOL when you create a cluster. Also, you can purchase an IBM-provided subscription license when you create a cluster.

Currently, only VMware vSphere Enterprise and VMware vSAN can be licensed per cluster.

## How do I manage my BYOL licenses?
{: #faq_byol-mgmt}

You can manage your BYOL licenses by using the VMware vSphere Web Client after the instance deployment is completed.

## When I add more ESXi servers to my instance later, does the instance validate if my BYOL licenses have enough capacity?
{: #faq_byol-add-esxi}

Yes. When you're adding more ESXi servers to a deployed instance, the capacity of your BYOL licenses is automatically checked for the specified number of ESXi servers. If the capacity is not sufficient, the ESXi servers are not added and you get a console notification.

## How can I tell how much license capacity I have available on a cluster with BYOL?
{: #faq_byol-capacity}

To find the number of CPUs available in your license key, complete the following steps:
1. Go to the **Deployed Instances** page.
2. Locate and click the instance.
3. On the **Infrastructure** tab, click the cluster that you want to check the license capacity for.
   The number of available CPUs is listed in the **User-Provided License** table.

## Does IBM provide support if I select the BYOL licensing option?
{: #faq_byol-support}

IBM Support continues to be your point of contact for any instance configuration concern. However, if the reported concern is determined to be for a BYOL VMware component, you are directed to VMware Support.

## Why do vSphere license charges show up on the price estimation list if I am using BYOL? Am I being charged for it?
{: #faq_byol-vsphere}

{{site.data.keyword.baremetal_short}} are provisioned with VMware vSphere already installed and with vSphere licenses already included. If you selected BYOL for vSphere, a process is automatically initiated upon instance deployment to remove the included vSphere licenses. Then, the license charges are credited to your {{site.data.keyword.cloud_notm}} account. You do not have to do anything in this process.

## Can I still use the existing manual process for BYOL?
{: #faq_byol-manual-process}

With the introduction of the BYOL feature, continued use of the manual process is not recommended. If you want to use BYOL, provide your own licenses when you are ordering the instance.

## Is BYOL supported for other VMware products such as VMware vRealize Automation, VMware vRealize Operations, or VMware vRealize Log Insight?
{: #faq_byol-other-support}

No, because these VMware products are not part of the instance deployment. These VMware products might be installed in addition to the initial deployment, which requires the clients or their agents to install and license these products.

## Can I order NFS storage with vCenter Server with Hybridity Bundle?
{: #faq_byol-nfs}

For newly deployed instances, only vSAN all-flash storage is supported. The vCenter Server with Hybridity Bundle offering includes vSAN Advanced or Enterprise licensing.

If you have a vCenter Server instance with NFS storage, you can upgrade your existing instance to vCenter Server with Hybridity Bundle. While vSAN Advanced licensing is ordered during the upgrade, you are not required to provision an all-flash vSAN cluster.

## Can I use BYOL with vCenter Server with Hybridity Bundle?
{: #faq_byol-hybridity}

You cannot bring your own VMware licensing (BYOL) to {{site.data.keyword.cloud_notm}}. vCenter Server with Hybridity Bundle requires that all VMware licenses are provided by IBM.

## What is the difference between vCenter Server with Hybridity Bundle licensing and vCenter Server licensing?
{: #faq_byol-hybridity-vcs}

The individual VMware licenses that are available in vCenter Server are priced per CPU. As with all per-CPU VMware licenses provided by IBM, there is a 1.3x uplift in price across all servers that have more than 16 cores per CPU, for example, for Dual Intel Xeon Gold 6140.

vCenter Server with Hybridity Bundle is a prescribed set of VMware licenses and editions that are licensed per core, and not per CPU. Therefore, the licensing price for these instances does not change.

## Which IBM-provided VMware license components and editions are available for vCenter Server with Hybridity Bundle?
{: #faq_byol-hybridity-avail}

New instances of vCenter Server with Hybridity Bundle include VMware vSphere Enterprise Plus, VMware vCenter Standard, VMware NSX Advanced or Enterprise, VMware vSAN Advanced or Enterprise, and VMware Hybrid Cloud Extension (HCX).

If you have a vCenter Server instance with NSX Base edition, you are upgraded to NSX Advanced automatically when you order vCenter Server with Hybridity Bundle.

## Can I upgrade the NSX Advanced edition that is included in vCenter Server with Hybridity Bundle to NSX Enterprise edition?
{: #faq_byol-nsx-upgrade}

While the vCenter Server with Hybridity Bundle includes NSX Advanced, you can upgrade to the NSX Enterprise edition after you order the vCenter Server with Hybridity Bundle. To do so, use the **Update and Patch** tab on the instance details page tab of the {{site.data.keyword.vmwaresolutions_short}} console.

## Related links
{: #faq_byol-related}

* [Ordering Cloud Foundation instances](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_orderinginstance)
* [Cloud Foundation instances](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_cloudfoundationoverview)
* [Accessing the console](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-loginmethod)
* [Contacting IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
