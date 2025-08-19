---

copyright:

  years:  2016, 2025

lastupdated: "2025-08-18"

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# VMware Update Manager introduction
{: #vum-intro}

As the system administrator of a {{site.data.keyword.vcf-auto}} instance, review the instructions on how to configure VMware® Update Manager (VUM) to maintain the currency of your {{site.data.keyword.vcf-auto-short}} instance.

If you have a {{site.data.keyword.vcf-auto-short}} instance that is deployed with vSphere 7.x version or later, then VMware® added new functions and rebranded it as vSphere Lifecycle Manager (vLCM). For more information, see [What’s New with vSphere in VMware Cloud Foundation 9.0](https://blogs.vmware.com/cloud-foundation/2025/06/23/vsphere-in-vcf-9-0-whats-new/){: external}

VUM enables centralized, automated patch and version management for VMware vSphere®. With VUM, you can complete the following tasks in your {{site.data.keyword.vcf-auto-short}} environment:
* Upgrade and patch the vSphere ESXi hosts.
* Install and update third-party software on the hosts.
* Upgrade virtual machine hardware, VMware Tools, and virtual appliances.

This document also describes the processes to maintain the following components of your {{site.data.keyword.vcf-auto-short}} instance:
* VMware vCenter® Server Appliance (VCSA)
* NSX®
* vSAN™

This document describes the use of a proxy server implementation, based on CentOS and Squid, to enable VUM to access the VMware repositories. When VUM requests a resource from the update server at VMware, the request is sent to the proxy server first and the proxy server then sends the request to the update server through the External Services Gateway (ESG). After the resource is obtained by the proxy server, it sends the resource to VUM.

![Overview diagram](../../images/vum-vcsproxy.svg "Overview diagram"){: caption="Overview diagram" caption-side="bottom"}

This information is organized into the following sections:
* [VMware Update Manager overview](/docs/vmwaresolutions?topic=vmwaresolutions-vum-overview) - Describes the VUM process and introduces key terms that are needed to understand the operations and UI of the tool.
* **Installation, Configuration, and Usage** - Describes the steps that are required to get VUM working in a {{site.data.keyword.vcf-auto-short}} instance:
   * [Initial configuration](/docs/vmwaresolutions?topic=vmwaresolutions-vum-init-config) - A one-time task to complete the following processes:
      * Configure NSX networking to allow the proxy server access to the internet.
      * Install and configure a proxy server to provide internet access for VUM.
      * The initial setup of VUM to use the proxy server.
   * [Collecting the metadata](/docs/vmwaresolutions?topic=vmwaresolutions-vum-metadata) - VUM downloads metadata about the upgrades, patches, or extensions through a predefined automatic process that you can modify. At regular configurable intervals, VUM contacts VMware, or third-party sources, to gather the most recent metadata about available upgrades, patches, or extensions.
   * [Creating baselines](/docs/vmwaresolutions?topic=vmwaresolutions-vum-baselines) - Use the predefined baselines and baseline groups or create custom ones. Baselines and baseline groups are then attached to inventory objects.
   * [Scanning and review](/docs/vmwaresolutions?topic=vmwaresolutions-vum-scanning) - Inventory objects are scanned, and the results are reviewed to determine how they comply with the baselines and baseline groups. Scan results can be filtered by text search, group selection, baseline selection, and compliance status selection.
   * [Staging and remediation](/docs/vmwaresolutions?topic=vmwaresolutions-vum-staging) - Patches and extensions can be optionally staged before remediation to ensure that they are downloaded to the host. During remediation, VUM applies the patches, extensions, and upgrades to the inventory objects.

This document assumes that you have one primary {{site.data.keyword.vcf-auto-short}} instance that is deployed, or a number of separate primary {{site.data.keyword.vcf-auto-short}} instances. If you have primary and secondary {{site.data.keyword.vcf-auto-short}} instances that are deployed and that use Single Sign On (SSO), see [SSO-linked vCenters](/docs/vmwaresolutions?topic=vmwaresolutions-vum-updating-vcsa).

If you deployed a {{site.data.keyword.vcf-auto-short}} instance with vSAN, see [Updating vSAN clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vum-updating-vsan) first.

If you want to update the {{site.data.keyword.cloud_notm}} infrastructure management automation, use the {{site.data.keyword.vmwaresolutions_short}} console.

On the [{{site.data.keyword.vmwaresolutions_short}} console](/vmware){: external}, you can complete the following actions:
* Upgrade licenses for example, upgrade NSX Base to another version.
* Initiate updates to the {{site.data.keyword.vcf-auto-short}} instance.
* View the status of updates.
* View the installed updates.

This facility enables the automated updating for the management components of the {{site.data.keyword.vcf-auto-short}} instances only. VMware product updates must be applied by using the procedures that are detailed in this document.

## Related links
{: #vum-intro-related}

* [VMware HCX solution architecture](/docs/vmwaresolutions?topic=vmwaresolutions-hcx-archi-intro#hcx-archi-intro)
* [{{site.data.keyword.vmwaresolutions_short}}](https://www.ibm.com/products/vmware){: external}
