---

copyright:

  years:  2016, 2022

lastupdated: "2022-08-26"

keywords: Veeam, Veeam configuration, order Veeam

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Ordering Veeam
{: #veeam_ordering}

You can include the Veeam® service with a new VMware vCenter Server® instance or add the service to your existing vCenter Server instance.

## Ordering Veeam for a new instance
{: #veeam_ordering-new}

When you [order the instance](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure), scroll down to the Add-on services section. Veeam is in the Recommended services category and is already selected.

Select **Edit** to review and specify the information. If you enter or change information, click **Save**.

If you do not want to order Veeam, toggle its switch off.

## Ordering Veeam for an existing instance
{: #veeam_ordering-existing}

1. On the instance details page, click **Services** on the left navigation pane.
2. Click **Add** to add the service.
3. On the **Services** page, locate the **Veeam** service and toggle its switch on.
4. Follow the steps to configure and add the service to your instance.

## Veeam service configuration
{: #veeam_ordering-config}

When you order the service, provide the following settings.

### Name
{: #veeam_ordering-name}

Specify a unique name for this service instance. The name must be unique across all Veeam service instances and all instances in the {{site.data.keyword.cloud}} account.

### Deployment type
{: #veeam_ordering-depl-type}

Select one of the following options:
* **Windows Server VM with iSCSI storage**. This option is not supported by VMware® Regulated Workloads instances.
* **Single Windows VSI with iSCSI storage**. This option is not supported by Security and Compliance Readiness Bundle instances or VMware Regulated Workloads instances.
* **Bare metal server with local storage**. This option requires VMware vSphere 7.

### Storage size
{: #veeam_ordering-config-storage-size}

The capacity that meets your storage needs. This option is not applicable to the **Bare metal server with local storage** deployment type.

For an example that shows what the capacity might be like, see [Capacity planning for backup repositories](https://helpcenter.veeam.com/docs/one/reporter/capacity_planning_for_repositories.html?ver=100){: external}.

### Storage performance
{: #veeam_ordering-config-storage-performance}

The IOPS (input/output operations per second) per GB based on your workload requirements. This option is not applicable to the **Bare metal server with local storage** deployment type.

### Backup disk
{: #veeam_ordering-config-backup-disk}

The backup disks are used as storage repositories for backups. This option is applicable only to the **Bare metal server with local storage** deployment type.

### Linux hardened repository
{: #veeam_Linux_hardened_repository}

You can order a Linux® hardened repository (LHR) to use for immutable storage. If you select a Linux hardened repository, a list of backup disk size options is displayed. Select the disk size that you want to order.

The Linux hardened repository is only supported for vSphere 7 NSX-T instances.

For more information, see [Hardened Repository](https://helpcenter.veeam.com/docs/backup/vsphere/hardened_repository.html?ver=110){: external} in the *Veeam Backup & Replication 11 - User Guide for VMware vSphere*.

### Number of VMs to license
{: #veeam_ordering-config-vms}

Specify the number of virtual machines (VMs) to license, in increments of 10. At least 10 VMs are required for license management.

## Related links
{: #veeam_ordering-related}

* [Veeam 11 overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview)
* [Managing Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam)
* [Ordering Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering_licenses)
* [Managing Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_managing_licenses)
* [Ordering and configuring IBM Cloud Object Storage with Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering)
* [Veeam backup and replication](https://www.ibm.com/cloud/architecture/architectures/virtualization_backup_veeam)
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center](https://www.veeam.com/documentation-guides-datasheets.html){: external}
