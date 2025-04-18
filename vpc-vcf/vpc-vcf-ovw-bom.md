---

copyright:

  years:  2016, 2025

lastupdated: "2025-03-18"

keywords: vmware cloud foundation BOM, bill of materials vmware cloud foundation, BOM

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.vcf-vpc-short}} BOM
{: #vpc-vcf-ovw-bom}

Review the Bill of Materials (BOM) information for {{site.data.keyword.vcf-vpc}} instances.

## VPC Infrastructure BOM for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-ovw-bom-vpc}

Review the BOM information for Bare Metal Servers on {{site.data.keyword.vpc_full}} ({{site.data.keyword.vpc_short}}).

| Type | Details |
| ---- | ------- |
| Bare Metal Servers | Provides compute capacity for a minimum of 4 hosts for the consolidated architecture. |
| VLANs | Assigned to physical VMware ESXi™ servers for traffic of VMware vSphere® management, VMware vSAN™, vSphere vMotion, and VMware NSX® TEP. |
| Subnets | Created for vSphere management traffic, vSAN, vSphere vMotion, NSX TEP, and NSX-T™ Tier-0 Gateway. |
| Security Groups | To create logical groups and apply rules to traffic of vSphere management, vSAN, vSphere vMotion, and NSX TEP. |
| Virtual Server Instances | Optional. Windows Server 2019 Standard Edition (AMD64), 2 vCPU, 8 GB RAM, and a bandwidth cap of 4 Gbps. |
{: caption="BOM for {{site.data.keyword.vpc_short}} infrastructure in {{site.data.keyword.vcf-vpc-short}} instances" caption-side="bottom"}

## Software BOM for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-ovw-bom-software}

Review the BOM information for {{site.data.keyword.vcf-vpc-short}} software components.

| Component | Version | Build number |
| --------- | ------- | ------------ |
| Cloud Builder VM | 5.2.1 | 24307856 |
| SDDC Manager | 5.2.1 | 24307856 |
| VMware vCenter Server Appliance | 8.0 Update 3c | 24305161 |
| VMware ESXi | 8.0 Update 3d | 24585383 |
| VMware Virtual SAN Witness Appliance | 8.0 Update 3b | 24280767 |
| VMware NSX-T | 4.2.1 | 24304122 |
| VMware Aria® Suite Lifecycle Manager | 8.18 | 24029603 |
{: caption="BOM for software components in {{site.data.keyword.vcf-vpc-short}} instances" caption-side="bottom"}

If you are provisioning VMware Aria® Suite components with Lifecycle Manager, see [VMware Product Interoperability Matrix](https://interopmatrix.broadcom.com/Interoperability){: external} for detailed product and version support information for the specific Aria Suite components that you need. For more information, see [Deploying VMware validated solutions](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-deploy-vvs).
{: note}

## Network MTU configuration settings
{: #vpc-vcf-ovw-bom-mtu-config}

The vSphere cluster has a single vSphere Distributed Switches (vDS) for public and for private network connectivity.

The private network connections are configured to use Jumbo Frames MTU (Maximum Transmission Unit) with a size of 9000 (when applicable), which improves performance for large data transfers such as storage and vMotion. This value is the maximum MTU allowed within VMware and by {{site.data.keyword.cloud_notm}}.

The public network connections use a standard Ethernet MTU of 1500, which must be maintained. Any changes might cause packet fragmentation over the internet.

Review the following table for an overview of the Network MTU configuration settings that are applied to the Virtual Distributed Switch, VMkernel adapters, and NSX Tier 0 uplinks.

| Configuration setting | Value |
| --------------------- | ----- |
| Virtual Distributed Switch | 9000 (Jumbo Frames) |
| VMkernel adapters for management | 1500 (Default) |
| VMkernel adapters for VSAN | 9000 (Jumbo Frames) |
| VMkernel adapters for vMotion | 9000 (Jumbo Frames) |
| VMkernel adapters for TEP traffic | 9000 (Jumbo Frames) |
| Tier 0 private uplinks | 9000 (Jumbo Frames) |
| Tier 0 public uplinks | 1500 (Default) |
{: caption="MTU configuration settings for {{site.data.keyword.vcf-vpc-short}}" caption-side="bottom"}

NSX Global Gateway Configuration is set to MTU of 1500 for the router links and interfaces at the overlay.

## Related links
{: #vpc-vcf-ovw-bom-links}

* [{{site.data.keyword.vcf-vpc-short}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-ovw)
* [Planning for {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-plan)
