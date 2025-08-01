---

copyright:

  years:  2016, 2025

lastupdated: "2025-07-31"

keywords: Veeam, Veeam configuration, order Veeam

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Ordering Veeam
{: #veeam_ordering}

You can include the Veeam® service with a new {{site.data.keyword.vcf-auto}} instance or add the service to your existing instance.

Veeam Backup and Replication 12.3 is available for deployment on new instances.

If you have Veeam 9.5u4b, you can continue to use it. However, you cannot install Veeam 9.5u4b on a new or existing instance.
{: restriction}

## Considerations when you install Veeam
{: #veeamvm_overview-install}

Before you install Veeam on an instance, review the [tasks that you can complete with Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam#managingveeam-fivetasks_v10).

## Considerations for a Linux hardened repository
{: #managingveeam-linux-repository}

When you install Veeam, you can optionally install a Linux® hardened repository. For more information, see [Linux hardened repository for immutable storage](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview#veeamvm_overview-specs-linux-storage).

Due to security considerations and best practices, as part of the automation, a setting is created to prevent the `root` user from being accessed by using SSH. You can access the Linux hardened repository through the IPMI (Intelligent Platform Management Interface) on the {{site.data.keyword.cloud_notm}} console.

## Ordering Veeam for a new instance
{: #veeam_ordering-new}

1. When you [order the instance](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure), scroll down to the **Add-on services** section. Veeam is in the **Recommended services** category and is already selected.
2. Click **Edit** to review and specify [the configuration information](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering#veeam_ordering-config), then click **Save**.

## Ordering Veeam for an existing instance
{: #veeam_ordering-existing}

1. On the instance details page, click the **Services** tab.
2. Click **Add** to add the service.
3. On the **Add services** page, locate the **Veeam** service in the **Business continuity and migration** section and toggle its switch to on.
4. Click **Edit** to review and specify [the configuration information](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering#veeam_ordering-config), then click **Save**.

## Veeam configuration
{: #veeam_ordering-config}

When you order the service, provide the following settings.

### Name
{: #veeam_ordering-name}

Specify a name for this service instance. The name must be unique across all Veeam service instances and all instances in the {{site.data.keyword.cloud}} account.

### Deployment type
{: #veeam_ordering-depl-type}

Select one of the following options:
* **Windows Server VM with iSCSI storage**. This option is not supported for {{site.data.keyword.rw}} instances.
* **Single Windows VSI with iSCSI storage**. This option is not supported for Security and Compliance Readiness Bundle instances and {{site.data.keyword.rw}} instances.
* **Bare metal server with local storage**. This option requires VMware vSphere® 7.

### Storage size
{: #veeam_ordering-config-storage-size}

The capacity that meets your storage needs. This option is not applicable to the **Bare metal server with local storage** deployment type.

For an example that shows what the capacity might be like, see [Capacity planning for backup repositories](https://helpcenter.veeam.com/docs/one/reporter/capacity_planning_for_repositories.html?ver=120){: external}.

### Storage performance
{: #veeam_ordering-config-storage-performance}

The IOPS (input/output operations per second) per GB based on your workload requirements. This option is not applicable to the **Bare metal server with local storage** deployment type.

### Backup disk
{: #veeam_ordering-config-backup-disk}

The backup disks are used as storage repositories for backups. This option is applicable only to the **Bare metal server with local storage** deployment type.

### Linux hardened repository
{: #veeam_Linux_hardened_repository}

You can order a Linux® hardened repository (LHR) to use for immutable storage. If you select a Linux hardened repository, a list of backup disk size options is displayed. Select the disk size that you want to order.

The Linux hardened repository is supported only for {{site.data.keyword.vcf-auto-short}} with VMware NSX-T™ instances and vSphere 7.
{: important}

For more information, see [Hardened repository](https://helpcenter.veeam.com/docs/backup/vsphere/hardened_repository.html?ver=120){: external}.

### Number of VMs to license
{: #veeam_ordering-config-vms}

Enter the number of VMs (virtual machines) to license (minimum 1).

You can order a maximum of 500 VMs under a single license key. If you need multiple licenses that are consolidated under a single license key, you must first purchase them. Then, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) to request that the license keys are consolidated into a single key.

If you need a single license key for more than 500 VMs, you must order a stand-alone license separately. For more information, see [Ordering Veeam stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering_licenses).

## Related links
{: #veeam_ordering-related}

* [Veeam on {{site.data.keyword.cloud_notm}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview)
* [Managing Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam)
* [Managing Veeam stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_managing_licenses)
* [Ordering and configuring {{site.data.keyword.cloud_notm}} Object Storage with Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering)
* [Veeam on {{site.data.keyword.cloud_notm}}](https://www.ibm.com/products/veeam){: external}
* [Veeam Technical Documentation](https://helpcenter.veeam.com/){: external}
