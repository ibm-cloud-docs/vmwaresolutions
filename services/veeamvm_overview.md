---

copyright:

  years:  2020, 2022

lastupdated: "2022-10-26"

keywords: Veeam, Veeam 11, Veeam install, tech specs Veeam, Veeam overview

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Veeam on IBM Cloud overview
{: #veeamvm_overview}

Veeam® on IBM Cloud seamlessly integrates directly with your VMware® hypervisors to help your enterprise achieve high availability. This service provides recovery points and time objectives for your applications and data. The recovery points and time objectives can be provided in less than 15 minutes after configuration is completed. By using this service, you control both the backup and restore of all virtual machines (VMs) for your infrastructure directly from the Veeam console. Veeam on IBM Cloud is a non-IBM product that is offered under terms and conditions from Veeam, not IBM.
{: shortdesc}

{{site.data.content.para-promotion-services}}

The current Veeam service that is installed is the new Veeam Availability Suite™ 11 known as Veeam 11.
{: note}

## Veeam on a bare metal server
{: #veeamvm_overview-baremetal-server}

You can install Veeam 11 on a bare metal server. This installation is supported only for VMware vSphere® 7.0 with VMware NSX-T™.

* For VMware Regulated Workloads, the Veeam bare metal server is the only option. For Security and Compliance Readiness Bundle, the Veeam bare metal server is the default option with a choice of switching to Veeam VM.
* Veeam is always deployed to the management cluster.
* No migration path is available for existing Veeam users.

For more information about Veeam on bare metal server, see the following topics.

* [Veeam on bare metal server introduction](/docs/vmwaresolutions?topic=vmwaresolutions-veeam-bms-archi-intro)
* [Veeam on bare metal server overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeam-bms-archi-overview)

## Technical specifications for Veeam
{: #veeamvm_overview-specs}

You can choose one of the following deployment types with Veeam 11:
* Windows® Server VM on the management cluster or consolidated cluster
* Single Public Windows VSI
* Bare metal server

For more information about resource requirements and capacity checking for some services, see [Resource requirements for services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-resource-requirements).

The following components are ordered and included in the Veeam 11 service.

### VMs for Veeam
{: #veeamvm_overview-specs-vms}

The following components are included if you deploy Veeam 11 as a Windows Server VM on the management cluster:

* VM with Veeam Backup and Replication 11 OS Add-on and Veeam Availability Suite 11
* Windows Server 2019 Standard Edition (64-bit)
* 8 CPUs, 32 GB RAM
* 100 GB disk (SAN)

### VSIs for Veeam
{: #veeamvm_overview-specs-vsi}

The following components are included if you deploy Veeam 11 as a single public Windows VSI:

* Single VSI with Veeam Backup and Replication 11 OS Add-on and Veeam Availability Suite 11
* Windows Server 2019 Standard Edition (64-bit)
* 4 x 2.0 GHz Cores
* 8 CPUs, 32 GB RAM
* 1 Gbps private network uplink
* 100 GB disk (SAN)

### Bare metal servers for Veeam
{: #veeamvm_overview-specs-baremetal}

The following components are included if you deploy Veeam 11 on a bare metal server:

* Bare metal server with Veeam Backup and Replication 11 OS Add-on and Veeam Availability Suite 11
* Windows Server 2019 Standard Edition (64-bit)
* 2 x 2.2 GHz CPU
* 64 GB RAM
* 10 Gbps private redundant network uplink
* 2 x 1 TB, RAID 1, OS drive
* 2 x 1 TB, RAID 1, database config drive
* User selectable size backup data drive

### Storage for backups for Veeam
{: #veeamvm_overview-specs-storage}

#### Endurance iSCSI storage (VM or VSI option)
{: #veeamvm_overview-specs-storage-vm-or-vsi}

The following options for storage size are available:
   * 2,000 GB
   * 4,000 GB
   * 8,000 GB
   * 12,000 GB

The following options for storage performance (IOPS/GB) are available:
   * 0.25
   * 2
   * 4

#### Local HDD storage (Bare metal server option)
{: #veeamvm_overview-specs-storage-bm-server}

The following options for storage size are available:
* 8 x 2 TB, RAID 6, 12 TB total estimated usable storage
* 8 x 6 TB, RAID 6, 36 TB total estimated usable storage
* 8 x 12 TB, RAID 6, 72 TB total estimated usable storage

#### Repositories created
{: #veeamvm_overview-specs-storage-repositories-created}

As part of the Veeam service installation and configuration, the following repositories are created:
* For the Veeam configuration backup files - a repository named `IC4V Default Config Backup Repository`. The path to the folder where the Veeam backups are stored is `<Drive>:\ConfigBackup\`.
* For scale-out, a repository named `IC4V Scale-Out Repository`. For more information, see [Adding a scale-out repository](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering#icos_ordering-scale-repo).
* For the VM backups - a repository named `IC4V Default VM Backup Repository`. The path to the folder where the VM backups are stored is `<Drive>:\VMBackup\`. This repository is added as an extent to `IC4V Scale-Out repository.

### Linux hardened repository for immutable storage
{: #veeamvm_overview-specs-linux-storage}

When you order Veeam, you can optionally order a Linux hardened repository (LHR). You can use the repository for immutable storage.

* If you order an LHR, an additional bare metal server with Red Hat Enterprise Linux (RHEL) 8.x installed is deployed. The same bare metal hardware is deployed as the Veeam Backup & Replication (VBR) server.
* The disk options are similar to the VBR server. The size options are 2 TB, 6 TB, and 12 TB.
* You can order an LHR for any of the Veeam deployment types: VM, VSI, or bare metal server.
* There is no charge for LHR beyond the cost of the bare metal infrastructure.

See the following information:
* [Cyber recovery with Veeam architecture](/docs/vmwaresolutions?topic=vmwaresolutions-veeam-cr-sa-overview), which describes two solution architectures to help you with cyber recovery.
* [Cyber recovery with Veeam guide](/docs/vmwaresolutions?topic=vmwaresolutions-veeam-cr-sag-overview), which describes how to create two cyber-recovery solution architectures.
* [Hardened repository](https://helpcenter.veeam.com/docs/backup/vsphere/hardened_repository.html?ver=110){: external} in the *Veeam Backup & Replication 11 - User Guide for VMware vSphere*.

### Networking for Veeam
{: #veeamvm_overview-specs-networking}

One primary private IP address. Bare metal and VSI options use one primary private IP address. However, the VM option uses one primary portable IP address.

The Veeam® VSI and Veeam bare metal services are not configured with an IBM Cloud Infrastructure portable IP address or with a NAT connection to the public network, even if you have public interfaces in your instance. This implementation helps to avoid the possibility of asymmetric routing when it uses a network gateway appliance.

When you deploy Veeam as a bare metal server or VSI, you can optionally configure your own proxy or NAT connection to the public network to connect to Veeam support for updates.

When you deploy Veeam as a VM, if your instance has public interfaces, VMware Solutions still creates a NAT connection for Veeam to the public network through the NSX-T services edge.

### Licenses and fees for Veeam
{: #veeamvm_overview-specs-licenses}

For Veeam Availability Suite 11, you can order any number of VM licenses.

You must provide a Microsoft® Windows Server 2019 Standard edition license if you choose the option of installing Veeam as a VM.
{: important}

## Considerations when you install Veeam
{: #veeamvm_overview-install}

You can order a new vCenter Server instance with Veeam and order or delete a Veeam stand-alone license. For more information, see [Tasks you can complete with Veeam 11](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam#managingveeam-fivetasks_v10).

For more information about Veeam license installation and deletion in Veeam 11, see [Considerations for installing and deleting Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam#managingveeam-install-delete-consid).

## Considerations when you delete Veeam
{: #veeamvm_overview-remove}

Deleting the Veeam service stops all backups and deletes all the previous backups. The backup of the management VMs or VSIs stops and the deletion of previous backups is irreversible. If the management VMs or VSIs are corrupted, they can’t be restored.
{: important}

Review the following considerations before you delete the service:
* Deleting the Veeam 11 service does not cancel the Veeam license. You must delete the Veeam license from the **Veeam licenses** table on the **Licenses** page in the {{site.data.keyword.vmwaresolutions_short}} console.
* When you delete the Veeam 11 service, the VMware Solutions automation deletes only the single Veeam VM, VSI, or bare metal server that was deployed and the dedicated private subnet that was ordered for it. If you scaled out the Veeam VM or VSI into multiple ones, those additional VMs or VSIs are not deleted.
* If you order iSCSI storage, that storage is deleted when you delete the Veeam 11 service. Therefore, any data within that storage is lost.

## Related links
{: #veeamvm_overview-related}

* [Ordering Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering)
* [Managing Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam)
* [Ordering Veeam standalone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering_licenses)
* [Managing Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_managing_licenses)
* [Ordering and configuring IBM Cloud Object Storage with Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering)
* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Veeam backup and replication](https://www.ibm.com/cloud/architecture/architectures/virtualization_backup_veeam){: external}
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center (Technical Documentation)](https://www.veeam.com/documentation-guides-datasheets.html){: external}
