---

copyright:

  years: 2019, 2025

lastupdated: "2025-07-17"

keywords: release notes, what's new in VMware Solutions, what is new, new features, VMware Solutions release notes, VMware Solutions

subcollection: vmwaresolutions

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for VMware Solutions
{: #vmwaresolutions-relnotes}

Use these release notes to learn about updates to {{site.data.keyword.vmwaresolutions_full}}, including new features, component updates, usability enhancements, and bug fixes.
{: shortdesc}

## 2025
{: #year-2025}



### 17 July 2025
{: #vmwaresolutions-jul1725}
{: release-note}

End of Marketing for {{site.data.keyword.rw}}
:   New deployments of VMware {{site.data.keyword.rw}} instances are no longer supported for new customers. If you are an existing customer, you can still add or delete clusters, add or delete VMware ESXi™ servers or NFS storage, and add or remove services for your existing {{site.data.keyword.rw}} instances. As an existing customer, you can also view or delete your {{site.data.keyword.rw}} instances. For more information, see [End of Marketing for {{site.data.keyword.rw}}](/docs/vmwaresolutions?topic=vmwaresolutions-eos-vrw).

End of Support for KMIP for VMware for Key Protect
:   Support for the Key Protect service as part of Key Management Interoperability Protocol (KMIP™) for VMware® will end on 16 July 2026, after which interoperability with the Key Protect service will no longer work. You must migrate to the native [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud}}](/docs/key-protect) offering, or an alternative key management service of your choice by 16 July 2026. For more information, see [End of Support for KMIP for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-eos-kmip).

End of Support for {{site.data.keyword.redhat_openshift_notm}} for VMware
:   New automated installations of {{site.data.keyword.redhat_openshift_full}} for VMware® are no longer available for new or existing deployments of {{site.data.keyword.vcf-auto}} instances. You can still use or delete your existing {{site.data.keyword.redhat_openshift_notm}} for VMware automated installations until 16 July 2026. The service will no longer be available from 17 July 2026. For more information, see [End of Support for {{site.data.keyword.redhat_openshift_notm}} for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-eos-rhos).

### 28 April 2025
{: #vmwaresolutions-apr2825}
{: release-note}

VNI for {{site.data.keyword.vcf-vpc}}
:   VNI (Virtual Network Interface) is enabled by default for bare metal servers on {{site.data.keyword.vcf-vpc-short}}. This change enhances network segmentation and flexibility.

Configuration updates for {{site.data.keyword.vcf-vpc-short}}
:   You can no longer download updates for some components from the Broadcom® public repositories. For existing {{site.data.keyword.vcf-vpc-short}} instances, you must open [an IBM Support ticket](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) to obtain a download token and configure the download URL for each component manually. For more information, see [Configuration updates for {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-plan#vpc-vcf-plan-configchanges).

### 11 April 2025
{: #vmwaresolutions-apr1125}
{: release-note}

Licensing and metering for VMware Cloud Foundation
:   VMware® by Broadcom now requires {{site.data.keyword.IBM}} and {{site.data.keyword.cloud}} customers to use new license keys and to use VMware vCloud Usage Meter for metering and reporting. This requirement applies to {{site.data.keyword.vcf-classic-short}} (Automated and Flexible), {{site.data.keyword.vcf-vpc-short}}, ESXi roll-your-own (RYO) servers on Classic, {{site.data.keyword.IBM_notm}} Bridge to Cloud program users, and some BYOL for VMware users. Usage Meter is used to report consumption of VCF and add-ons, such as VMware vSAN™ and VMware vDefend™ Firewall to both Broadcom and {{site.data.keyword.IBM_notm}}. The new licensing and metering are applicable to environments with VMware vSphere® 7 and later. For more information, see [Requirements for licensing and metering](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_metering-req).

REST APIs for licensing and metering
:   The following new REST APIs are available:

   * The {{site.data.keyword.vcf-aas}} API provides support for [listing VMware licenses](/apidocs/vmware-service#list-licenses) and for [managing Usage Meter registrations](/apidocs/vmware-service#create-usage-meter-registration).
   * The VMware Solutions API provides support for [deploying Usage Meters](/apidocs/vmware-solutions#controllers-public-v1-proxy-add-uma).

BOM updates for {{site.data.keyword.vcf-classic-short}}
:   The following updates are applied to newly deployed {{site.data.keyword.vcf-classic-short}} instances, clusters, and hosts:

   * VMware vSphere ESXi
      * 8.0 Update 3d (build 24585383)
      * 7.0 Update 3s (build 24585291)
   * VMware NSX 4.2.1.2 (build 24476729)

vSAN storage updates
:   For new {{site.data.keyword.vcf-auto-short}} instances and hosts, you can add more vSAN storage than the default capacity of 1 TB per host core. The {{site.data.keyword.IBM_notm}} automation will calculate and order the vSAN overage.

Add-on services upgrades
:   The following service versions are available for deployment:

   * Caveonix RiskForesight v5.2
   * VMware Aria® Operations™ and VMware Aria Operations™ for Logs v8.18.3

### 18 March 2025
{: #vmwaresolutions-mar1825}
{: release-note}

{{site.data.keyword.vcf-vpc-short}} updates

:   VMware ESXi™ 8.0 Update 3d (build 24585383) is applied to newly deployed {{site.data.keyword.vcf-vpc-short}} instances.

   For existing {{site.data.keyword.vcf-vpc-short}} instances, you are required to apply the following updates yourself:

   * Upgrade ESXi to 8.0 Update 3d. For more information, see [Upgrade ESXi with vSphere Lifecycle Manager Images for VMware Cloud Foundation 5.2](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/5-2/vmware-cloud-foundation-lifecycle-management/upgrade-the-management-domain-to-vmware-cloud-foundation-5-2-lifecycle/upgrade-esxi-with-vsphere-lifecycle-manager-images-for-vmware-cloud-foundation-lifecycle.html){: external}.
   * Upgrade VMware NSX-T™ to version 4.2.1.3. For more information, see [Upgrade NSX for VMware Cloud Foundation 5.2.x](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/5-2/upgrade-nsx-for-vcf-5-2.html){: external}.

### 14 February 2025
{: #vmwaresolutions-feb1425}
{: release-note}

Support for Dual Intel Xeon Platinum 6416H Sapphire Rapids
:   Dual Intel® Xeon® Platinum 6416H (36 cores, 2.2 GHz) bare metal servers are available for deployment with {{site.data.keyword.vcf-auto-short}}, {{site.data.keyword.vcf-flex-short}}, {{site.data.keyword.rw}}, and {{site.data.keyword.cr}} instances with VMware vSphere 7 and 8.

vSphere 8 and Sapphire Rapids - selected by default
:   VMware vSphere 8.0 and Sapphire Rapids servers are selected by default for new instances and new clusters on {{site.data.keyword.vcf-classic}} offerings.

{{site.data.keyword.rw}} multizone on Sapphire Rapids
:   Sapphire Rapids servers are available for existing {{site.data.keyword.rw}} multizone instances. You can add new ESXi servers with vSphere 7 to existing clusters.

Microsoft Entra ID enablement for vCenter Server
:   You can manually replace Single Sign-On (SSO) with Microsoft® Entra ID (formerly Azure Active Directory) to enable multifactor authentication (MFA) in your vCenter Server. For this purpose, open an IBM Support ticket. This option applies only to existing instances.

Add-on services upgrades
:   The following service versions are available for deployment:

   * Caveonix RiskForesight v5.1.5
   * Veeam Backup and Replication 12.3 (does not apply to {{site.data.keyword.vm-shared}} deployments)
   * VMware Aria Operations and VMware Aria Operations for Logs v8.18

### 3 February 2025
{: #vmwaresolutions-feb0325}
{: release-note}

{{site.data.keyword.vcf-vpc}} updates
:   The following updates are available:

   * VMware Cloud Foundation 5.2.1 supports Intel® Sapphire Rapids Generation 3 bare metal profiles for all available regions.
   * The consolidated architecture model is the only option for newly deployed instances.

### 10 January 2025
{: #vmwaresolutions-jan1025}
{: release-note}

End of Support for {{site.data.keyword.vm-shared}} deployments - extended
:   As of 28 March 2024, {{site.data.keyword.vm-shared}} is not available for new deployments. Support for existing instances is extended until 28 February 2025 after which access to all customer and management data, including the backups of workloads, will end. Existing instances are scheduled for deletion in March 2025. Migrate all your {{site.data.keyword.vm-shared}} resources to [{{site.data.keyword.vmware-service_full}}](/docs/vmware-service) by 28 February 2025.

## 2024
{: #year-2024}

### 13 December 2024
{: #vmwaresolutions-dec1324}
{: release-note}

vSphere 7 and 8 on Sapphire Rapids servers
:   The bare metal server Dual Intel Xeon Platinum 8474C (96 cores, 2.1/3.1 GHz) is available for deployment with {{site.data.keyword.vcf-auto-short}}, {{site.data.keyword.vcf-flex-short}}, {{site.data.keyword.rw}}, and {{site.data.keyword.cr}} instances with VMware vSphere 7 and 8. You can also use this bare metal server when you add clusters and hosts to your existing instances. For Sapphire Rapids servers, vSAN storage is now based on either vSAN ESA (Express Storage Architecture) (for vSphere 8 only) or vSAN OSA (Original Storage Architecture) (for vSphere 7 and 8). For Cascade Lake servers, vSAN storage remains based on vSAN OSA and available only with vSphere 7. For more information, see [Storage architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-consold-cluster#vc_orderinginstance-vsan-storage-archi).

vSphere 8 manual upgrade on Sapphire Rapids
:   You can manually upgrade vSphere to version 8.0 on your instances with Sapphire Rapids servers. After that, you can migrate your NFS and gateway clusters to vSphere 8.0. For more information, see [Upgrading VMware vSphere software from vSphere 7.0 to 8.0](/docs/vmwaresolutions?topic=vmwaresolutions-vs_vsphere_80-upgrade).

Data centers for Sapphire Rapids
:   You can deploy instances with **Sapphire Rapids** servers in specific {{site.data.keyword.cloud}} data centers. For more information, see [{{site.data.keyword.cloud_notm}} data center availability](/docs/vmwaresolutions?topic=vmwaresolutions-vc_planning#vc_planning-dc-availability).

DAL14 data center available
:   The **Dallas 14** {{site.data.keyword.cloud_notm}} data center is available for deployment with Automated, Flexible, {{site.data.keyword.rw}}, and {{site.data.keyword.cr}} instances.

Primary cluster reassignment
:   You can reassign the primary cluster to another cluster in your Automated instances.

BOM updates for {{site.data.keyword.vcf-classic-short}}
:   The following updates are applied to newly deployed {{site.data.keyword.vcf-classic}} instances, clusters, and hosts:

   * VMware vCenter Server Appliance
      * 8.0 Update 3d (build 24322831)
      * 7.0 Update 3t (build 24322018)
   * VMware vSphere ESXi 8.0 Update 3b (build 24280767)

Zerto add-on service upgrade
:   Zerto add-on service version 10.0u5 is available for deployment. To upgrade from Zerto versions that are earlier than 10.0u5, you must migrate from a Microsoft Windows® Virtual Service Instance (VSI) to a Linux® virtual machine (VM). For more information, see [Migrating Zerto from Windows ZVM to Linux ZVMA](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_migration).

REST API updates
:   The following updates are available for the [VMware Solutions API](/apidocs/vmware-solutions):

   * The REST APIs to get the list of supported RAM types as a JSON object (`ram_types`) and to get the list of supported disk types as a JSON object (`disk_types`) are replaced by the `server_types` API. For more information, see [Get the list of server CPU types that are supported, per location or vSphere version, as a JSON object](/apidocs/vmware-solutions#controllers-public-v2-proxy-list-server-types).
   * Outdated information is removed.

New and updated documentation
:   The following technical documents are now available:

   * [Migrating Zerto from Windows ZVM to Linux ZVMA](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_migration)
   * [Why does the Zerto Migration from Windows Zerto Virtual Manager to Linux ZVM Appliance fail?](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_zerto_zvma_migration)

### 20 November 2024
{: #vmwaresolutions-nov2024}
{: release-note}

VCF 5.2.1 for {{site.data.keyword.vcf-vpc}}
:   VMware Cloud Foundation 5.2.1 is offered for all {{site.data.keyword.vcf-vpc-short}} instances. The configuration with VMware vSphere 8 and VMware vSAN ESA (Express Storage Architecture) on Intel Sapphire Rapids Generation 3 bare metal profiles is available only in the Sao Paulo region.

### 9 October 2024
{: #vmwaresolutions-oct0924}
{: release-note}

BOM updates for {{site.data.keyword.vcf-classic-short}}
:   The following updates are applied to newly deployed {{site.data.keyword.vcf-classic}} instances, clusters, and hosts:

   * VMware vCenter Server Appliance
      * 8.0 Update 3b (build 24262322)
      * 7.0 Update 3s (build 24201990)

### 17 September 2024
{: #vmwaresolutions-sep1724}
{: release-note}

Veeam 12.2 add-on service upgrade
:   Veeam Backup and Replication 12.2 (Veeam 12.2) add-on service is available for deployment.

### 13 September 2024
{: #vmwaresolutions-sep1324}
{: release-note}

VCDA service for migrating workloads
:   The VMware Cloud Director Availability (VCDA) service is a cost-effective solution to migrate your {{site.data.keyword.vm-shared}} workloads to the {{site.data.keyword.vcf-aas}} multitenant or single-tenant consumption model. For more information, see [Migrating workloads to {{site.data.keyword.vcf-aas}} with VCDA](/docs/vmware-service?topic=vmware-service-tenant-vcda).

### 16 August 2024
{: #vmwaresolutions-aug1624}
{: release-note}

vSphere 8 support
:   VMware vSphere 8.0 is available for new NFS clusters (consolidated and workload), for new gateway clusters, and for new hosts that belong to NFS clusters. For instances with VMware vCenter Server 8, you can use either vSphere 8 or vSphere 7 for new clusters and hosts. For instances with vCenter Server® 7, you can use only vSphere 7. For more information about upgrading your vCenter Server software and upgrading your existing vSphere 7 clusters, see [Upgrading to vCenter Server 8.0](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcs_80_upgrade).

BOM updates for {{site.data.keyword.vcf-classic-short}}
:   The following updates are applied to newly deployed instances, clusters, and hosts:

   * VMware vCenter Server Appliance 8.0 Update 2d (build 23929136)
   * VMware vSphere ESXi 8.0 Update 2b (build 23305546)
   * VMware NSX 4.1.2.4 (build 23786733)

Add-on services upgrades
:   The following service versions are now available for deployment:

   * F5 BIG-IP v17.1.1.3
   * Juniper vSRX v3.0 (23.4R1)
   * {{site.data.keyword.redhat_openshift_notm}} v4.15
   * VMware Aria Operations v8.17.1 and VMware Aria Operations for Logs v8.17

Veeam 12.1.2 for {{site.data.keyword.vm-shared}}
:   Veeam Backup and Replication 12.1.2 (Veeam 12.1.2) is now available for deployment with the {{site.data.keyword.vm-shared}} offering.

Known issue about text overflow
:   When you select the instance type in the **Create a resource** section, the text on the card might overflow out of the card margins. This issue happens on some browsers when the font size setting for the browser is set to **Large** or **Very large**. To resolve the issue, view the console with the font size set to **Medium**.

### 24 June 2024
{: #vmwaresolutions-jun2424}
{: release-note}

VMware Cloud Director upgrade for {{site.data.keyword.vm-shared}}
:   The {{site.data.keyword.vm-shared}} infrastructure is upgraded to VMware Cloud Director v10.5.1.1, which resolves various issues and includes bug fixes.

### 14 June 2024
{: #vmwaresolutions-jun1424}
{: release-note}

{{site.data.keyword.vcf-vpc}} enhancements
:   The following features are now available:

   * **Server backup**: You can do regular backups of management components, such as SDDC Manager, VMware vCenter Server, and NSX Manager.
   * **Contact form**: You can use a form to contact an IBM Sales representative for the 1-year and 3-year subscription options.
   * The following **BOM updates** are applied to newly deployed instances:
      * Cloud Builder VM 5.1.1 (build 23480823)
      * SDDC Manager 5.1.1 (build 23480823)
      * VMware vCenter Server Appliance 8.0 Update 2b (build 23319993)
      * VMware ESXi 8.0 Update 2b (build 23305546)
      * VMware Virtual SAN Witness Appliance 8.0 Update 2 (build 22443122)
      * VMware NSX-T 4.1.2.4 (build 23786733)
      * VMware Aria® Suite Lifecycle Manager 8.16 (build 23377566)

### 1 May 2024
{: #vmwaresolutions-may0124}
{: release-note}

Updated offerings for VMware Solutions

:   Existing {{site.data.keyword.vmwaresolutions_short}} offerings are no longer available as separate components and are replaced by VMware Cloud Foundation. The following offering name changes are available across the portfolio, including the documentation and REST API.

   * VMware as a Service is now called **{{site.data.keyword.vmware-service_short}}** or **{{site.data.keyword.vcf-aas}}**.
   * VMware vCenter Server, VMware vSphere, {{site.data.keyword.cr}}, and {{site.data.keyword.rw}} are merged into **{{site.data.keyword.vcf-classic}}** or **{{site.data.keyword.vcf-classic-short}}**.
   * VMware Cloud Foundation is now called **{{site.data.keyword.vcf-vpc}}** or **{{site.data.keyword.vcf-vpc-short}}**.

   Some documentation, including, but not limited to, tutorials, solutions architectures, solution guides, videos, and diagrams might still be using the old offering names. This information will be gradually updated to the new offering names in future releases.
   {: note}

Licensing updates
:   The VMware licensing model is changed. You are now entitled to the VMware software products that are included in the VMware Cloud Foundation™ bundle. To request VMware NSX license upgrades and other licensing changes, open an IBM Support ticket by following the steps in Getting help and support.

VMware add-ons
:   As a result of the new VMware Cloud Foundation bundle and the new VMware licensing model, you must order separately a number of VMware add-ons.

BOM updates for {{site.data.keyword.vcf-classic}}
:   The following updates are applied to newly deployed instances, clusters, and hosts:

   * VMware vCenter Server Appliance 8.0 Update 2b (build 23319993)
   * VMware vSphere ESXi 7.0 Update 3p (build 23307199)
   * VMware NSX 4.1.2.3 (build 23382408)

Add-on services upgrades
:   The following service versions are available for deployment:

   * FortiGate® Virtual Appliance v7.4.3
   * F5 BIG-IP v17.1.1

vCenter Server with Hybridity Bundle no longer available
:   vCenter Server with Hybridity Bundle is no longer available. This offering is now integrated into {{site.data.keyword.vcf-auto}}.

User interface updates and enhancements
:   The following enhancements are available on the UI (user interface):

   * The behavior of the **Add** button for clusters, hosts, storage, and add-on services is changed for a better user experience. If you are not allowed to add an item, the button is no longer disabled. Instead, when you click it, you get a message that explains why you cannot add the item.
   * When you order new Automated and Flexible instances, or add clusters and hosts, the **Licensing** section is available only for Bring Your Own License (BYOL) users.
   * The UI is updated with various messages and tooltips.

REST API updates
:   The following updates are available for the VMware Solutions API:

   * Support for adding new instances and clusters with BYOL is removed. If you want to use BYOL, you must add these instances and clusters through the UI.
   * Support for deleting licenses for {{site.data.keyword.vcf-flex}} is removed.
   * Method descriptions are updated for consistency.
   * Outdated information is removed.

### 4 April 2024
{: #vmwaresolutions-apr0424}
{: release-note}

Veeam 12.1.1 for {{site.data.keyword.vm-shared}}
:   Veeam Backup and Replication 12.1.1 (Veeam 12.1.1) is now available for deployment with the {{site.data.keyword.vm-shared}} offering.

### 1 April 2024
{: #vmwaresolutions-apr0124}
{: release-note}

Updated packaging and pricing for VMware Solutions offerings
:   {{site.data.keyword.cloud}} is changing its {{site.data.keyword.vmwaresolutions_short}} portfolio and pricing, in response to the changes to the packaging and pricing of the VMware portfolio, announced by Broadcom. These changes will be effective on 1 May 2024.

Updated pricing structure for RHEL for {{site.data.keyword.vm-shared}}
:   The Red Hat Enterprise Linux (RHEL) pricing is updated from the existing 2-tier pricing structure (Small and Large) to a 3-tier pricing structure (Small, Medium, and Large).

### 28 March 2024
{: #vmwaresolutions-mar2824}
{: release-note}

End of Support for {{site.data.keyword.vm-shared}} deployments
:   Starting on 28 March 2024, {{site.data.keyword.vm-shared}} will no longer be available for new deployments. Existing instances will continue to be supported until 15 January 2025. Migrate all your {{site.data.keyword.vm-shared}} resources to {{site.data.keyword.cloud_notm}} for VMware as a Service by 15 January 2025.

### 15 March 2024
{: #vmwaresolutions-mar1524}
{: release-note}

{{site.data.keyword.vcf-vpc}} enhancements
:   The following features are now available:

   * **Async Patch tool**: You can apply critical patches for VMware Cloud Foundation components, such as VMware NSX Manager, VMware vCenter Server, and VMware ESXi by using the Async Patch tool.
   * **New regions available**: VMware Cloud Foundation is now available for use in **Tokyo** and **London**.
   * **BOM updates**: ESXi 7.0 Update 3p (build 23307199) is applied to newly deployed instances.

### 14 February 2024
{: #vmwaresolutions-feb1424}
{: release-note}

VMware Cloud Director upgrade for {{site.data.keyword.vm-shared}}
:   The {{site.data.keyword.vm-shared}} infrastructure is upgraded to VMware Cloud Director v10.4.2.2, which resolves various issues, includes security fixes, and introduces new features, such as an improved tenant login experience.

### 7 February 2024
{: #vmwaresolutions-feb0724}
{: release-note}

vCenter Server 8 support
:   VMware vCenter Server 8.0 is available for newly deployed instances. For new instances with vCenter Server 8 and existing instances or clusters with vCenter Server 7, you can add only vCenter Server 7 clusters or hosts.

vCenter Server and VMware vSphere BOM updates
:   The following updates are applied to newly deployed instances, clusters, and hosts:

   * VMware vCenter Server Appliance
      * 8.0 Update 2a (build 22617221)
      * 7.0 Update 3p (build 22837322)
   * VMware vSphere ESXi 7.0 Update 3o (build 22348816)
   * VMware NSX 4.1.2.1 (build 22667789)

Add-on services upgrades
:   The following service versions are now available for deployment:

   * VMware Aria Operations v8.14.1 and VMware Aria Operations for Logs v8.14
   * {{site.data.keyword.redhat_openshift_notm}} v4.14
   * Zerto v9.7u4

User interface updates and enhancements
:   The following enhancements are available on the UI:

   * The ordering flow of {{site.data.keyword.cr}} is simplified to remove the optional add-on services.
   * The UI (user interface) is updated with various messages and tooltips.

New and updated documentation
:   The following technical documents are now available or updated:

   * Architecture pattern for integrating {{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection with vCenter Server
   * Caveonix RiskForesight Security and Compliance Center integration
   * Architecture patterns for integrating {{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection with VMware as a Service
   * VMware Cloud Foundation architecture patterns
   * Veeam backup guide

## 2023
{: #year-2023}

### 13 December 2023
{: #vmwaresolutions-dec1323}
{: release-note}

VMware Cloud Foundation - consolidated
:   (Updated on 12 January 2024) The VMware Cloud Foundation offering is simplified to a single edition. All new deployments of VMware Cloud Foundation include Enterprise Edition software.

vCenter Server and VMware vSphere BOM updates
:   The following updates are applied to newly deployed instances, clusters, and hosts:

   * VMware vCenter Server Appliance 7.0 Update 3o (build 22357613)
   * VMware vSphere ESXi 7.0 Update 3o (build 22348816)
   * VMware NSX 4.1.0.2 (build 21761695)

Active Directory server OS upgrade
:   To upgrade your Microsoft Active Directory™ server, open an IBM Support ticket by following the steps in Getting help and support. Before you proceed with a new server installation, ensure that you back up all domain controllers and vCenter Server instances.

Add-on services upgrades
:   The following service versions are now available for deployment:

   * Caveonix RiskForesight v5.0
   * FortiGate Virtual Appliance v7.4.1

New region for KMIP for VMware
:   The KMIP™ for VMware service is now available for use in the Madrid region.

Ordering Veeam licenses
:   You can order a maximum of 500 VMs under a single license key for Veeam. If you need a single license key for more than 500 VMs, you must order a stand-alone license separately.

REST API updates
:   The following updates are available for the VMware Solutions API:

   * The `check_price` parameter is deprecated. Beginning with this release, the `verify_only` parameter performs a price check regardless of whether `check_price` is indicated.
   * The `disks` parameter used to order vSAN storage can now also be defined as an object (size and quantity), in addition to an array of disk types.
   * Outdated endpoints, such as `v2/supported_config_options` are removed.
   * Performance improvements are made to the API calls.

customerroot user - deprecated
:   The `customerroot` user is no longer created by the VMware Solutions automation for newly deployed instances, clusters, hosts, and new vCenter Server VMs. The `root` user is used instead. Existing instances, clusters, hosts, and vCenter Server VMs might still use the `customerroot` credentials.
{: deprecated}

New documentation
:   A number of tutorials are now available from the user documentation. These solution tutorials provide step-by-step instructions about using VMware as a Service to implement common patterns based on best practices.

### 18 October 2023
{: #vmwaresolutions-oct1823}
{: release-note}

VMware Cloud Foundation
:   (Updated on 3 November 2023) The {{site.data.keyword.cloud}} for VMware Cloud Foundation offering is a full-stack Software Defined Data Center (SDDC) solution that is built on VMware Cloud Edition. It delivers compute, storage, networking, management automation, and security in a single platform on {{site.data.keyword.bm_is_full_notm}} (VPC).

VMware Cloud Foundation BOM updates
:   (Updated on 17 November 2023) The following updates are applied to newly deployed instances:

   * Cloud Builder VM 4.5.2 (build 22223457)
   * SDDC Manager 4.5.2 (build 22223457)
   * VMware ESXi 7.0 Update 3n (build 21930508)
   * VMware NSX-T 3.2.3.1. (build 22104592)
   * VMware Aria Suite Lifecycle Manager 8.12.0.9 (build 22652426)

VMware vSphere Day 2 updates
:   You can now choose a new bare metal server configuration when you add a host to your existing instances.

vCenter Server and VMware vSphere BOM updates
:   The following update is applied to newly deployed instances, clusters, and hosts:

   * VMware vCenter Server Appliance 7.0 Update 3n (build 21958406)

Mirrored M.2 boot drives - NFS storage
:   For vCenter Server with NFS storage, mirrored M.2 boot drives are provisioned with your order when you add new NFS clusters or when you add new ESXi servers to existing NFS clusters and select a new bare metal server configuration.

Add-on services upgrades
:   The following service versions are now available for deployment:

   * Juniper vSRX v3.0 (23.2R1)
   * {{site.data.keyword.redhat_openshift_notm}} v4.13.10
   * VMware Aria Operations v8.12.1

ProtectIO
:   ProtectIO is now available as a data migration and resiliency service from the VMware Solutions console.

User interface updates and enhancements
:   The UI (user interface) is updated with various messages and tooltips, and provides the following enhancements:

   * The **VMware instance configuration manager** is enhanced with extra details and tooltips to differentiate and help you choose from the available saved configurations.
   * The checkbox **Maintenance mode** in the **Add ESXi server** window is changed to a switch, for consistency with other similar UI options.
   * The contents of the **Add ESXi server** and **Add NFS storage** panels is better structured and organized for a more streamlined user experience.
   * For gateway and edge clusters, the uplink speed setting is now included in the **CPU model** table when you choose your servers.

New documentation
:   The Veeam backup guide provides information about expanding backup storage as a day-2 operation, the deployment of proxy and repository servers, and recommendations for sizing and performance.

### 24 August 2023
{: #vmwaresolutions-aug2423}
{: release-note}

VMware vSphere 8 on Cascade Lake - not supported
:   (Updated on 25 September 2023) IBM does not support VMware vSphere 8.x on Intel® Cascade Lake hardware due to RAID Controller incompatibility and because IBM licenses for vSphere 8.x, VMware vCenter Server 8.x, and VMware vSAN 8.x are not available currently.

   Do not upgrade to vSphere 8.x on Cascade Lake servers. If you upgrade to vSphere 8.x, your environment configuration becomes unsupported by IBM and VMware.
   {: important}

Veeam 12 for {{site.data.keyword.vm-shared}}
:   Veeam Backup and Replication 12 (Veeam 12) is now available for deployment with the {{site.data.keyword.vm-shared}} offering.

vCenter Server and VMware vSphere BOM updates
:   The following updates are applied to newly deployed instances, clusters, and hosts:

   * VMware vCenter Server Appliance 7.0 Update 3m (build 21784236)
   * VMware vSphere ESXi 7.0 Update 3n (build 21930508)

Mirrored M.2 boot drives
:   For vCenter Server with vSAN storage and for VMware vSphere instances with vSAN disks, mirrored M.2 boot drives are provisioned with your order when you add new vSAN clusters or when you add new ESXi servers to existing vSAN clusters and select a new bare metal server configuration.

Entrust CloudControl - deprecated
:   New installations of Entrust CloudControl™ are no longer supported for new or existing deployments of vCenter Server instances. You can still use or delete existing Entrust CloudControl installations on your existing instances.
{: deprecated}

FortiGate Virtual Appliance v7.4
:   The FortiGate Virtual Appliance v7.4 add-on service is available for deployment.

Name change for PrimaryIO
:   The PrimaryIO add-on service name is changed to PrimaryIO Migrations and its About page is updated with the most recent feature information.

User interface updates and enhancements
:   The UI is updated with various messages and tooltips, and provides the following enhancements:

   * For VMware vSphere, the term **cluster** is updated to **instance** throughout the UI, user documentation, and REST APIs.
   * For VMware vSphere instances, the **Instance configuration name** field is changed to a side pane. You can manage your configuration templates from a list of saved configurations in the side pane.

New and updated documentation
:   The following updates are available:

   * The {{site.data.keyword.vm-shared}} metrics are updated with metadata details.
   * New documentation is available to assist with expanding ordered endurance storage after ordering the Veeam add-on service.

### 5 July 2023
{: #vmwaresolutions-jul0523}
{: release-note}

VMware vSphere Day 2 support
:   You can view or delete VMware vSphere instances from the VMware Solutions console. You can also add or delete VMware ESXi servers, and add or delete licenses for vSphere instances from the VMware Solutions console.

{{site.data.keyword.rw}} multizone instances - deprecated
:   New deployments of VMware {{site.data.keyword.rw}} multizone instances are no longer supported. For existing multizone instances, you can still add and delete clusters, add and delete ESXi servers or NFS storage, and delete add-on services.
{: deprecated}

Updates to VMware vCenter Server and VMware vSphere instances
:   The following upgrades are applied to newly deployed instances, clusters, and hosts:

   * VMware vCenter Server Appliance 7.0 Update 3l (build 21477706)
   * VMware vSAN Witness 7.0 Update 3l (build 21424296)

Add-on services upgrades
:   The following service versions are now available for deployment:

   * Caveonix RiskForesight v4.1
   * FortiGate Virtual Appliance v7.2.5
   * F5 BIG-IP v17.1
   * Juniper vSRX v3.0 (23.1R1)
   * {{site.data.keyword.redhat_openshift_notm}} v4.12
   * VMware Aria Operations and VMware Aria Operations for Logs v8.12
   * Zerto v9.7u3

Name change for VMware vRealize products
:   VMware changed the vRealize® Suite Lifecycle Manager product name to VMware Aria® Suite Lifecycle. All vRealize products that are managed by vRealize Suite Lifecycle Manager are now referred as VMware Aria. The names are updated throughout the VMware Solutions documentation. The following products are rebranded:

   * vRealize Operations and Log Insight is renamed to VMware Aria Operations and VMware Aria Operations for Logs.
   * vRealize Automation is renamed to VMware Aria® Automation™.
   * vRealize Operations (vROps) is renamed to VMware Aria Operations.
   * vRealize Log Insight™ (vRLI) is renamed to VMware Aria Operations for Logs.
   * vRealize Network Insight (vRNI) is renamed to VMware Aria Operations™ for Networks.

REST API updates
:   The following updates are available:

   * The VMware Solutions API provides support for viewing and deleting VMware vSphere instances. You can also add or delete ESXi servers, and add or delete licenses for vSphere instances.
   * Also for the VMware Solutions API, you can specify either `quantity` or `host_names` for the number of new hosts to be added in the `hosts_order_data` object.

User interface updates and enhancements
:   The UI is updated with various messages and tooltips, and provides the following enhancements:

   * For VMware vSphere, vCenter Server, {{site.data.keyword.cr}}, and {{site.data.keyword.rw}} instances, the **Instance configuration name** field is changed to a side pane. You can manage your configuration templates from a list of saved configurations in the side pane.
   * The checkbox **Select a different cluster location** is changed to a switch, for consistency with other similar UI options.
   * The **SAP-certified** Cascade Lake selections (**NetWeaver** and **HANA**) are merged into a single option for a more streamlined user experience when you choose the **CPU model** for your servers.
   * The process to set up your environment for your first order is simplified on the UI.

### 3 May 2023
{: #vmwaresolutions-may0323}
{: release-note}

Madrid data centers available
:   (Updated on 22 June 2023) The {{site.data.keyword.cloud_notm}} data centers **Madrid 02**, **Madrid 04**, and **Madrid 05** are now available for deployment.

Bring Your Own License (BYOL) no longer available
:   BYOL is now disabled in the **Licensing** section for VMware vCenter Server instances, VMware vSphere clusters, adding hosts and clusters, and vRealize Operations and Log Insight service.

VMware NSX-T 4.0.1.1 manual upgrade
:   VMware NSX-T version 4.0.1.1 is now available if you want to upgrade your existing NSX-T instances manually. All newly deployed VMware NSX-T instances are still provisioned with NSX-T version 3.2.0.1.

Updates to VMware vCenter Server instances and VMware vSphere clusters
:   The following upgrades are applied to newly deployed instances, clusters, and hosts.
   * VMware vCenter Server Appliance 7.0 Update 3k (build 21290409)
   * VMware vSAN Witness 7.0 Update 3c (build 19193900)

Veeam 12 availability
:   Veeam Backup and Replication 12 (Veeam 12) is now available for deployment with VMware vCenter Server, {{site.data.keyword.cr}}, and {{site.data.keyword.rw}} offerings. Veeam 12 allows you to write directly to {{site.data.keyword.cloud}} Object Storage and it provides other features, such as data protection, improved Recovery Point Objective using Continuous Data Protection for disaster recovery purposes, and general operational efficiency.

New and updated documentation
:   The table of contents is updated for topic rearrangement and removal of outdated content.

User interface updates and enhancements
:   The UI is updated with various messages and tooltips, and provides the following enhancements.

   * The term **edge gateway cluster** is updated to **gateway cluster** throughout the UI, user documentation, and REST APIs.
   * You can check the prices for VMware Solutions offerings without having to sign in to {{site.data.keyword.cloud_notm}}. However, you might have limited access to some sections of the ordering pages. To place an order, or for a complete access to the ordering pages, you must log in to {{site.data.keyword.cloud_notm}}.
   * The page titles and labels for adding clusters, storage, and services are updated for consistency throughout the UI.
   * The status of instances and clusters when they are ready to use is updated to **Available**.
   * The UI controls for the separate workload cluster, gateway cluster, and file shares are changed to switches instead of checkboxes.
   * Guidance is provided on the UI for the workload and gateway cluster configuration.
   * A side pane is displayed when you add hosts to vCenter Server, {{site.data.keyword.cr}}, and {{site.data.keyword.rw}} instances.

### 8 March 2023
{: #vmwaresolutions-mar0823}
{: release-note}

VMware Cloud Director upgrade for {{site.data.keyword.vm-shared}}
:   The {{site.data.keyword.vm-shared}} infrastructure is upgraded to VMware Cloud Director v10.4.1. This release resolves various issues, includes several deprecations, and introduces new features, such as API tokens and edge static routes.

End of Marketing for {{site.data.keyword.cloud_notm}} Secure Virtualization
:   The {{site.data.keyword.cloud_notm}} Secure Virtualization offering is no longer available for new deployments. Support for existing customers who are using the offering is still provided.
{: deprecated}

Updates to VMware vCenter Server instances and VMware vSphere clusters
:   The following upgrades are applied to newly deployed instances, clusters, and hosts.
   * VMware vCenter Server Appliance 7.0 Update 3j (build 20990077)
   * VMware vSphere ESXi 7.0 Update 3k (build 21313628)

Add-on services upgrades
:   The following service versions are now available for deployment:
   * Entrust CloudControl v6.6
   * F5 BIG-IP v17.0
   * vRealize Operations and vRealize Log Insight v8.10
   * Zerto v9.7u1

F5 BIG-IP migration from NSX-V to NSX-T
:   To migrate the F5 BIG-IP service from VMware NSX-V to VMware NSX-T, open an IBM Support ticket by following the steps in Getting help and support.

New and updated documentation
:   Documentation is available to assist with your custom cyber-recovery requirements.

REST API updates
:   The VMware Solutions API provides support for getting and canceling billing item IDs for VMware vSphere clusters, deleting hosts from vSphere clusters, and deleting vSphere clusters.

User interface updates and enhancements
:   The UI is updated with various messages and tooltips, and provides the following enhancements.

   * BYOL notification in the **Licensing** section for VMware vCenter Server instances, VMware vSphere clusters, add hosts and clusters, vRealize Operations and Log Insight, and VMware HCX services. Bring Your Own License (BYOL) is no longer supported, except for migrations or upgrades of existing BYOL clusters.
   * The term **edge services cluster** is updated to **edge gateway cluster** throughout the UI, user documentation, and REST APIs.
   * A side pane is now displayed when you add NFS storage to VMware vCenter Server, {{site.data.keyword.cr}}, and {{site.data.keyword.rw}} instances.


### 10 January 2023
{: #vmwaresolutions-jan1023}
{: release-note}

VMware Cloud Director upgrade for {{site.data.keyword.vm-shared}}
:   The {{site.data.keyword.vm-shared}} infrastructure is upgraded to VMware Cloud Director v10.4, which supports up to virtual hardware version 19. If you use the VMware Cloud Director API, consider the following updated product support notices:
   * VMware Cloud Director API versions 31.0 and 32.0 are not supported.
   * VMware Cloud Director API versions 33.0, 34.0, 35.0, and 35.2 are deprecated and are not supported starting with the next major release of VMware Cloud Director.

Name change for vRealize Operations Tenant App for VMware Cloud Director
:   VMware changed the vRealize Operations Tenant App for VMware Cloud Director product name to VMware Chargeback. The name is updated throughout the {{site.data.keyword.vm-shared}} documentation.

Bring Your Own License (BYOL) no longer supported
:   {{site.data.keyword.cloud_notm}} previously allowed you to bring your own license (BYOL) when you move your existing on-premises VMware workloads to {{site.data.keyword.cloud_notm}}. BYOL is no longer allowed by VMware. You can no longer bring your own licenses for any new hosts. This restriction applies to all VMware products that are available from {{site.data.keyword.cloud_notm}}. For existing BYOL servers, you can still upgrade and migrate to refresh software and hardware.

SAP-certified servers updates
:   SAP HANA certified bare metal servers now offer only fixed configurations with defined RAM sizes. Also, new SAP HANA and SAP NetWeaver models are available for deployment with VMware vSphere 7.0u3. These models are available for VMware vCenter Server and {{site.data.keyword.cr}} instances and clusters, and for VMware vSphere clusters.

NetBIOS domain name
:   The first qualifier of the root domain name is now the NetBIOS name by default. It is part of the network diagram when your order vCenter Server and {{site.data.keyword.cr}} instances.

Add-on services upgrades
:   The following service versions are now available to install on deployed instances.
   * FortiGate Virtual Appliance 7.2.2
   * Juniper vSRX v21.4 (R2)

Veeam migration from NSX-V to NSX-T
:   To migrate the Veeam service from VMware NSX-V to VMware NSX-T, open an IBM Support ticket.

REST API updates
:   For {{site.data.keyword.vm-shared}}, the V1 API support ended on 31 December 2022. Use the V2 API.

User interface updates and enhancements
:   The left navigation menu in the instance detail page is now changed to tabs. Also, a new tab **Access information** is added, where you can find information such as AD/DNS IP and remote desktop credentials for your instance.

## 2022
{: #year-2022}

### 31 October 2022
{: #vmwaresolutions-oct3122}
{: release-note}

{{site.data.keyword.cr}}
:   The V5.0 release offers a new {{site.data.keyword.cr}} instance. The instance can help you protect your systems and data from cyberthreats and attacks. It can assist you with handling ransomware and help you with other problems and threats.

   The {{site.data.keyword.cr}} instance includes Veeam Backup and Replication 12, a Linux hardened repository (LHR), and an edge gateway.

Private network endpoint enhancements
:   You can now edit the private network endpoints allowlisted IP addresses and subnets for your VMware Solutions Shared instance.

Veeam self-service portal for {{site.data.keyword.vm-shared}}
:   The Veeam self-service portal is now automatically enabled for existing and new VMware Cloud Director organizations.

MEX01 data center no longer available
:   (Updated on 14 November 2022) The **Mexico 01** {{site.data.keyword.cloud_notm}} data center is closing on 31 January 2023. This data center is no longer available for deployments.

VMware vSphere 7.0u2 - deprecated
:   (Updated on 14 November 2022) The vSphere 7.0u2 option is no longer available for adding hosts to vCenter Server instances and scaling existing vSphere clusters. For existing instances with vSphere 7.0u2, you can add only ESXi servers with vSphere 7.0u3.
{: deprecated}

Dark mode temporarily unavailable
:   Starting on 14 November 2022, the UI **Dark** mode is temporarily unavailable. Until it becomes enabled again, use **Light** mode.

Hostname prefix updates
:   You can now customize the hostnames prefix individually when you order VMware vCenter Server instances, order new VMware vSphere clusters, and add hosts and clusters to existing instances.

Updates to VMware vCenter Server instances and VMware vSphere clusters
:   The following upgrades are applied to newly deployed instances, clusters, and hosts.
   * VMware vSphere ESXi 7.0 Update 3f (build 20036589)
   * VMware vSphere ESXi 6.7 P08 (build 19997733)

Considerations for selecting a new NSX Data Center SP edition
:   Beginning with the V5.0 release, if you have a BYOL for VMware NSX-T that is not a Data Center SP license, you can now order NSX Data Center SP licenses to replace your licenses. You are responsible to select the appropriate NSX Data Center SP license edition based on your needs.

   Also, beginning with this release, if you have a BYOL Data Center SP edition license, you can start renting NSX Data Center SP edition licenses from IBM. If you already rent an NSX Data Center SP edition license from IBM, you can upgrade and downgrade. If you have VMware HCX and an NSX Data Center Enterprise Plus license, you cannot downgrade your license. If you uninstall HCX, you can then downgrade your license.

Add-on services upgrades
:   The following service versions are now available to install on deployed instances.
   * Caveonix RiskForesight v4.0
   * FortiGate Virtual Appliance v7.2.1
   * Red Hat OpenShift v4.11
   * vRealize Log Insight v8.8
   * Zerto v9.5u3

KMIP support for Key Protect key rings
:   KMIP for VMware supports Key Protect key rings.

Ordering Veeam stand-alone licenses
:   Starting with this release, if you order Veeam stand-alone licenses, the ordering process automatically starts. You get an email confirming what you ordered. A license key is generated for you. When the key is ready, it is emailed to you.

   There is no limit to the number of licenses that you can order.

REST API updates
:   The following updates are available:

   * For {{site.data.keyword.vm-shared}}, the support date for the V1 API is being extended until 31 December 2022. To ensure smooth transition in the future, start using the V2 API.
   * For VMware Solutions API, support is provided for Caveonix RiskForesight, Veeam, Zerto, and VMware HCX stand-alone licenses. Also, support for the 2U chassis types is added by using the new `large_chassis_only` parameter.

User interface enhancements
:   The left navigation panel on the VMware Solutions console now groups items as **Resources** and **Licenses** so that they are more aligned with the resource types and names.

### 29 August 2022
{: #vmwaresolutions-aug2922}
{: release-note}

**HKG02** and **SEO01** data centers no longer available
:   (Updated on 20 September 2022) The **Hong Kong 02** and **Seoul 01** {{site.data.keyword.cloud_notm}} data centers are no longer available for deployment.

Price calculation updates for {{site.data.keyword.vmwaresolutions_short}} Shared
:   Price calculations are now automatically generated when you access the order pages for {{site.data.keyword.vmwaresolutions_short}} Shared offerings.

vRealize Operations Tenant App for VMware Cloud Director availability
:   You can now access the vRealize Operations Tenant App for a VMware Cloud Director for new and existing organizations through the VMware Cloud Director tenant portal.

Standard - Catalog storage policy availability
:   The Standard - Catalog storage policy is now available for storing vApp templates and media files in your VMware Cloud Director catalog.

Private network endpoints for multizone virtual data centers
:   Two private network endpoints are ordered to correspond with each VMware NSX Edge™ Service Gateway when you create a private network endpoint for VMware Solutions Shared multizone virtual data centers.

vCPU and RAM limits for on-demand and reserved virtual data centers
:   The vCPU and RAM limits for VMware Solutions Shared virtual data center orders are now increased. Beginning with the 4.9 release, the maximum vCPU limit is 1 - 2000 and the maximum RAM limit is 1 - 40 TBs for both on-demand and reserved virtual data center orders.

Updates to VMware vCenter Server instances and VMware vSphere clusters
:   The following upgrades are applied to newly deployed instances, clusters, and hosts.
   * VMware vSphere ESXi 7.0 Update 3e (build 19898904)
   * VMware vSphere ESXi 6.7 P07 (build 19898906)

Considerations for selecting a new NSX Data Center SP edition
:   Beginning with the V4.9 release, if your NSX-V instance is using BYOL licenses, you can now order legacy NSX licenses from IBM to replace your own license.

   Also, beginning with this release, if your NSX-T instance is using legacy NSX licenses, you can now order NSX Data Center SP licenses to replace your legacy NSX licenses. You are responsible to select the appropriate NSX Data Center SP license edition based on your needs.

Zerto 9.5u1 support
:   Zerto 9.5u1 is available to install on deployed instances.

   Zerto v9.5u1 is not supported for vSphere 6.5 and 6.7. However, you can order stand-alone licenses for existing vSphere 6.x instances.
   {: note}

HCX Appliance activation with BYOL NSX Data Center Enterprise Plus license
:   If you have a BYOL NSX Data Center Enterprise Plus license and you install VMware HCX, your NSX Data Center Enterprise Plus license key is now used to activate the HCX appliance.

Linux hardened repository for Veeam
:   When you order Veeam, you can order a Linux hardened repository for immutable storage.

REST API updates
:   The VMware Solutions API provides support for scaling existing VMware vSphere clusters.

User interface updates and enhancements
:   The UI is updated with various error messages and tooltip enhancements and provides the following enhancements.

   * A vertical progress indicator bar is now available on the ordering page for VMware Solutions Shared offerings. The progress indicator maps to each section and helps to quickly browse to different areas of the page.
   * If you are running VMware NSX-V or a vSphere 6 version on the instances in your environment, you now receive notifications to update your environment to the most recent supported version of NSX or vSphere. You can go to the instance summary page to check the NSX solution type and the vSphere version that is most suitable for your environment.
