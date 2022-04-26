---

copyright:

  years:  2020, 2022

lastupdated: "2022-04-20"

keywords: Veeam, Veeam 11, Veeam install, tech specs Veeam, Veeam overview

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Veeam v11 overview
{: #veeamvm_overview}

The Veeam® service seamlessly integrates directly with your VMware® hypervisors to help your enterprise achieve high availability. This service provides recovery points and time objectives for your applications and data. The recovery points and time objectives can be provided in less than 15 minutes after configuration is completed. By using this service, you control both the backup and restore of all virtual machines (VMs) for your infrastructure directly from the Veeam console.
{: shortdesc}

{{site.data.content.para-promotion-services}}

The current Veeam service that is installed is the new Veeam Availability Suite™ v11 known as Veeam v11.
{: note}

## Veeam on a bare metal server
{: #veeamvm_overview-baremetal-server}

You can install Veeam v11 on a bare metal server. This installation is only supported on VMware vSphere® 7.0 with NSX-T™.

* For VMware Regulated Workloads, the Veeam bare metal server is the only option. For Security and Compliance Readiness Bundle, the Veeam bare metal server is the default option with a choice of switching to Veeam VM.
* Veeam is always deployed to the management cluster.
* There is no migration path for existing Veeam users.

For more information about the technical specifications, see [Technical specifications for Veeam v11](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview#veeamvm_overview-specs).

For more information about Veeam on bare metal server, see the following topics.

* [Veeam on bare metal server introduction](/docs/vmwaresolutions?topic=vmwaresolutions-veeam-bms-archi-intro)
* [Veeam on bare metal server overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeam-bms-archi-overview)

## Technical specifications for Veeam v11
{: #veeamvm_overview-specs}

For more information about resource requirements and capacity checking for some services, see [Resource requirements for services](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-resource-requirements).

You can choose one of the following deployment types with Veeam v11:
* Windows® Server virtual machine (VM) on the management cluster or consolidated cluster
* Single Public Windows VSI
* Bare metal server

The following components are ordered and included in the Veeam v11 service:

### VMs for Veeam v11
{: #veeamvm_overview-specs-vms}

The following are included if you deploy Veeam v11 as a Windows Server VM on the management cluster:

* Virtual machine (VM) with Veeam Backup and Replication 11 OS Add-on and Veeam Availability Suite 11
* Windows Server 2019 Standard Edition (64-bit)
* 8 CPUs, 32 GB RAM
* 100 GB disk (SAN)

### VSIs for Veeam v11
{: #veeamvm_overview-specs-vsi}

The following components are included if you deploy Veeam v11 as a single public Windows VSI:

* Single VSI with Veeam Backup and Replication 11 OS Add-on and Veeam Availability Suite 11
* Windows Server 2019 Standard Edition (64-bit)
* 4 x 2.0 GHz Cores
* 8 CPUs, 32 GB RAM
* 1 Gbps private network uplink
* 100 GB disk (SAN)

### Bare metal servers for Veeam v11
{: #veeamvm_overview-specs-baremetal}

The following components are included if you deploy Veeam v11 on a bare metal server:

* Bare metal server with Veeam Backup and Replication 11 OS Add-on and Veeam Availability Suite 11
* Windows Server 2019 Standard Edition (64-bit)
* 2 x 2.2 GHz CPU
* 64 GB RAM
* 10 Gbps private redundant network uplink
* 2 x 1 TB, RAID 1, OS drive
* 2 x 1 TB, RAID 1, database config drive
* User selectable size backup data drive

### Storage for backups for Veeam v11
{: #veeamvm_overview-specs-storage}

#### Endurance iSCSI storage (VM or VSI options)
{: #veeamvm_overview-specs-storage-vm-or-vsi}

* Storage size
   * 2,000 GB
   * 4,000 GB
   * 8,000 GB
   * 12,000 GB

* Storage performance (IOPS/GB)
   * 0.25
   * 2
   * 4

#### Local HDD storage (Bare metal server option)
{: #veeamvm_overview-specs-storage-bm-server}

Storage size

* 8x2 TB, RAID 6, 12 TB total estimated usable storage
* 8x6 TB, RAID 6, 36 TB total estimated usable storage
* 8x12 TB, RAID 6, 72 TB total estimated usable storage

#### Repositories created
{: #veeamvm_overview-specs-storage-repositories-created}

As part of the Veeam service installation and configuration, the following repositories are created:
* For the Veeam configuration backup files - a repository named `IC4V Default Config Backup Repository`. The path to the folder where the Veeam backups are stored is `<Drive>:\ConfigBackup\`.
* For scale-out, a repository named `IC4V Scale-Out Repository`. For more information, see [Adding a scale-out repository](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering#icos_ordering-scale-repo).
* For the virtual machine (VM) backups - a repository named `IC4V Default VM Backup Repository`. The path to the folder where the VM backups are stored is `<Drive>:\VMBackup\`. This repository is added as an extent to `IC4V Scale-Out repository.

### Networking for Veeam v11
{: #veeamvm_overview-specs-networking}

One primary private IP address.

Bare metal and VSI options use one primary private IP address. However, the VM option uses one primary portable IP address.

The Veeam® VSI and Veeam bare metal services are not configured with an IBM Cloud Infrastructure portable IP address or with a NAT connection to the public network, even if you have public interfaces in your instance. This implementation helps to avoid the possibility of asymmetric routing when using a network gateway appliance.

When you deploy Veeam as a bare metal server or VSI, you can optionally configure your own proxy or NAT connection to the public network if you want to be able to connect to Veeam support for updates.

When you deploy Veeam as a VM, if your instance has public interfaces, IBM Cloud for VMware Solutions still creates a NAT connection for Veeam to the public network through the NSX-T services edge.

### Licenses and fees for Veeam v11
{: #veeamvm_overview-specs-licenses}

For Veeam Availability Suite 11, you can order 10 - 500 VM licenses in increments of 10.

You must provide a Microsoft® Windows Server 2019 Standard edition license if you choose the option of installing Veeam as a VM.
{: important}

## Considerations when you install Veeam v11
{: #veeamvm_overview-install}

You can complete various tasks with Veeam v11, such as ordering a new vCenter Server instance with Veeam and ordering or deleting a Veeam stand-alone license. For more information, see [Tasks you can complete with Veeam v11](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam#managingveeam-fivetasks_v10).

Veeam license installation and deletion are different starting with Veeam v11. For more information, see [Considerations for installing and deleting Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam#managingveeam-install-delete-consid).

### Considerations when you delete Veeam v11
{: #veeamvm_overview-remove}

Deleting the Veeam service stops all backups and deletes all the previous backups. The backup of the management VMs or VSIs stops and the deletion of previous backups is irreversible. If the management VMs or VSIs are corrupted, they can’t be restored.
{: important}

Review the following considerations before you delete the service:
* Deleting the Veeam v11 service does not cancel the Veeam license. You must delete the Veeam license from the **Veeam licenses** table on the **Resources** page in the {{site.data.keyword.vmwaresolutions_short}} console.
* When you delete the Veeam v11 service, the {{site.data.keyword.vmwaresolutions_short}} automation deletes only the single Veeam VM, VSI, or bare metal server that was deployed and the dedicated private subnet that was ordered for it. Therefore, if you scaled out the Veeam VM or VSI into multiple ones, those additional VMs or VSIs are not deleted.
* If you order iSCSI storage, that storage is deleted when you delete the Veeam v11 service. Therefore, any data within that storage is lost.

## Related links
{: #veeamvm_overview-related}

* [Ordering Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering)
* [Managing Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam)
* [Ordering Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering_licenses)
* [Managing Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_managing_licenses)
* [Ordering and configuring IBM Cloud Object Storage with Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering)
* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Veeam backup and replication](https://www.ibm.com/cloud/architecture/architectures/virtualization_backup_veeam){: external}
* [Veeam website](https://www.veeam.com/){: external}
* [Veeam Help Center (Technical Documentation)](https://www.veeam.com/documentation-guides-datasheets.html){: external}
