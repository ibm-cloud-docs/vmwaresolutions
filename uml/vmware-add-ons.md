---

copyright:

  years:  2024, 2025

lastupdated: "2025-10-24"

keywords: vmware add-ons, firewall add-ons, vsan add-on, vmware avi add-on

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# VMware add-ons for VMware Cloud Foundation
{: #vmware-add-ons}

{{site.data.content.vms-deprecated-note}}

You must order separately a number of VMware® add-ons for your VMware Cloud Foundation™ bundle.

## VMware Avi Load Balancer add-on
{: #vmware-add-ons-nsx-avi}

The Avi Load Balancer (formerly VMware NSX Advanced Load Balancer) is available as a VMware add-on.

If you need load balancing for your environment, you can purchase the Avi Load Balancer license from the {{site.data.keyword.cloud}} console. You are then responsible for installing the Avi Load Balancer yourself.

## VMware vDefend Firewall add-on
{: #vmware-add-ons-nsx-firewall}

VMware vDefend™ Distributed Firewall (formerly VMware NSX Distributed Firewall) and VMware vDefend™ Gateway Firewall (formerly VMware NSX Gateway Firewall) are extracted from NSX and are available as an add-on to the VMware Cloud Foundation bundle. Add-on licenses are available for purchase in the {{site.data.keyword.cloud_notm}} console. You must purchase licenses for the number of cores that are required for your environment separately.

Unless you are part of the IBM Bridge to Cloud program, do not order vDefend keys that are labeled **solution key**. Most customers must order separate gateway keys for use with NSX Edge Gateway firewall, and distributed keys for use with the Distributed Firewall. Only the IBM Bridge to Cloud program customers that use vSphere 8 solution keys must order vDefend solution keys. For more information about vDefend solution and component keys, see [VMware vDefend Firewall Solution License Key](https://knowledge.broadcom.com/external/article/381444/vmware-vdefend-firewall-solution-license.html){: external}.

To review requirements for licensing and metering for the IBM Bridge to Cloud program, see [On-premises VMware licenses as part of the IBM Bridge to Cloud program](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_metering-req#licensing_metering-on-premises).

You must order the appropriate number of firewall cores for your environment.

* If you are ordering a new {{site.data.keyword.vcf-auto}} instance, the minimum gateway firewall cores are calculated for your order. IBM recognizes that you might resize or reconfigure these gateways, so the ongoing management of these keys, including their deletion, is your responsibility. These keys are not removed automatically when you delete your instance.
* If you are an existing customer or if you are changing your environment to configure an extra Gateway Firewall or to configure a Distributed Firewall, you must purchase vDefend Firewall licenses separately for the number of cores that are required for your environment.
* To calculate the number of firewall cores that you need for your environment and to confirm the cost (depending on whether you use distributed, gateway, or no firewall), based on your procurement vehicle, contact your IBM Business Partner representative or IBM Sales representative. If you are running NSX 4.1 or later, see [Counting Cores for VMware vDefend Firewall and vDefend Firewall with Advanced Threat Prevention](https://knowledge.broadcom.com/external/article?articleNumber=395111){: external} to calculate the number of cores that you need.

For on-demand, the cost for the firewall add-on is $12.50 per core, per month. Discounts are available depending on your contract commitment.

* **Distributed Firewall**: For this option, all host cores that are running NSX must be licensed for the vDefend Distributed Firewall add-on. This is done because virtual network segments span the entire environment and a virtual machine (VM) can run on any host. The applicable license key that you must order is named **VMware vDefend Firewall - Distributed** and is available in multiple sizes.
* **Gateway Firewall**: For this option, the vCPUs that are running on the edge VMs provide the gateway firewall service, therefore they are counted. To get the edge VMs properly configured, the VMs are sized and 4 cores per vCPU in the edge VMs are calculated. The applicable license key that you must order is named **VMware vDefend Firewall - Gateway** and is available in multiple sizes.

For example, by using the sizing guidance at [NSX Edge Installation Requirements](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-2/installation-guide/installing-nsx-edge/nsx-edge-installation-requirements.html){: external} if you choose a large edge, then each edge requires 8 vCPU, therefore 32 cores to be licensed: `8 vCPUs in the VM * 4 cores per vCPU = 32 cores`

As many environments use multiple edges for redundancy, 2 large edges (8 vCPUs each) require 64 cores worth of licensing: `2 edge VMs * 8 vCPUs per edge * 4 cores per vCPU = 64 cores`

For more information about how to enter these license keys into NSX Manager, see [Add a License Key and Generate a License Usage Report](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-2/administration-guide/operations-and-management/about-nsx-licenses/add-a-license-key-and-generate-a-license-usage-report.html){: external}.

## vSAN add-on
{: #vmware-add-ons-vsan}

VMware vSAN is included at a rate of 1 TiB per VMware Cloud Foundation core.

To calculate the amount of vSAN storage for your entire environment, see [Counting Cores for VMware Cloud Foundation and vSphere Foundation and TiBs for vSAN](https://knowledge.broadcom.com/external/article?legacyId=95927){: external}. If you need more than 1 TiB of vSAN, order the new vSAN add-on from the {{site.data.keyword.cloud_notm}} console.

The vSAN add-on is priced at $21 per TiB of vSAN per month. Discounts are available depending on your contract commitment.

The vSAN add-on does not generate any license keys and it is used only to report your vSAN usage.

For the {{site.data.keyword.vcf-auto-short}} offering, the IBM automation will automatically order the vSAN add-on for any new hosts that are provisioned as needed.
{: important}

## Ordering the VMware add-ons
{: #vmware-add-ons-order}

You can order licenses for the VMware add-ons from the {{site.data.keyword.cloud_notm}} console.

1. Click **Infrastructure > Classic Infrastructure** from the left navigation menu.
2. Click **Devices > Manage > VMware licenses**.
3. Order the VMware add-on.

You can also cancel the VMware add-ons from the {{site.data.keyword.cloud}} console.

## What to do next
{: #vmware-add-ons-next}

If applicable to you, complete the following tasks:

* If you purchased the Avi Load Balancer add-on license, activate the license by adding it to the Avi Load Balancer Controller. For more information, see [Using Avi Load Balancer license file](https://techdocs.broadcom.com/us/en/vmware-security-load-balancing/avi-load-balancer/avi-load-balancer/31-1/vmware-avi-load-balancer-administration-guide/licensing/nsx-advanced-load-balancer-editions/nsx-alb-license-management/using-avi-vantage-license-file.html){: external}. Then, install the Avi Load Balancer manually.
* If you are planning to order VMware Cloud Foundation for VPC instances, also [configure the NSX firewalls for {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-firewall) after you deployed your {{site.data.keyword.vcf-vpc-short}} instance.

## Related links
{: #vmware-add-ons-links}

* [VMware Avi Load Balancer](https://techdocs.broadcom.com/us/en/vmware-security-load-balancing/avi-load-balancer.html){: external}
* [Gateway Firewall](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/security/gateway-firewall.html){: external}
* [Distributed Firewall](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/security/distributed-firewall.html){: external}
* [NSX Edge Installation Requirements](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-2/installation-guide/installing-nsx-edge/nsx-edge-installation-requirements.html){: external}
* [Counting Cores for VMware Cloud Foundation and vSphere Foundation and TiBs for vSAN](https://knowledge.broadcom.com/external/article?legacyId=95927){: external}
* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
