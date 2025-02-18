---

copyright:

  years:  2016, 2025

lastupdated: "2025-02-17"

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Updating VMware NSX
{: #vum-updating-nsx}

The following information is a summary of the update process for NSX-T Data Center®. Refer to the VMware® guide for the update process for the NSX-T Data Center version that you are upgrading to, for example to update to version 3.2 see [Upgrading NSX-T Data Center](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/3-2/upgrade-guide/nsx-t-upgrade-guide.html){: external}.

VMware provides the [NSX-T Data Center Upgrade Checklist](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/3-2/upgrade-guide/upgrading-nsx-t-checklist.html){: external} with the steps that are required to update NSX-T Data Center. In summary, the steps are:

1. Upgrade vCenter, if needed to support the required host OS.
2. Upgrade the host OS, if needed to support the required NSX-T Data Center version.
3. Download the most recent NSX-T Data Center upgrade bundle - The upgrade bundle contains all the files to upgrade the NSX-T Data Center infrastructure.
4. Upgrade NSX-T - The upgrade coordinator runs in the NSX Manager and is a self-contained web application that orchestrates the upgrade of the following components.
   * NSX edge cluster - Familiarize yourself with the upgrade impact during and after the NSX Edge cluster upgrade.
   * NSX on the hosts - For ESXi hosts that are part of a fully enabled DRS cluster, if the host is not in maintenance mode, the upgrade coordinator requests the host to be put in maintenance mode. vSphere DRS migrates the VMs to another host in the same cluster during the upgrade and places the host in maintenance mode.
   * NSX management plane.

Review the following best practice information:

* NSX-T Data Center is updated by using a download from _my.vmware.com_. Therefore, you need an account to download the update. If you are using {{site.data.keyword.cloud}} subscription licensing with your {{site.data.keyword.vcf-auto}} instance, you cannot download the updates with your **my.vmware.com** account. [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).
* Before you begin the upgrade, check the NSX-T Data Center notes for upgrade issues and workarounds. Using the release notes, verify that vCenter and the host OS meets the new system requirements for NSX-T Data Center.
* If you installed any additional software from VMware Business Partners, contact your IBM Business Partner representative or IBM Sales representative for compatibility and upgrade details.
* Back up the NSX Manager before you start the upgrade process. See [Configure Backups](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/backing-up-and-restoring-the-nsx-manager/configure-backup-location.html){: external}.
* Disable automatic backups before you start the upgrade process.
* Ensure that your host OS is supported for NSX Manager. If your ESXi host is unsupported, manually upgrade your ESXi host to the supported version. Review [Software BOM for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_bom#vc_bom-software) for currently supported software levels on {{site.data.keyword.vcf-auto}} instances.
* Stop any active SSH sessions or local shell scripts that might be running on the NSX Manager or the NSX Edge nodes.
* Updating the vSphere hypervisor can be done from the ESXi CLI, vSphere Update Manager, or starting with NSX-T Data Center 3.1.1 and vSphere 7.0 U1, for vSphere Lifecycle Manager-enabled clusters, you can upgrade your ESXi host along with NSX-T Data Center, by using vSphere Lifecycle Manager, see [Upgrade a vSphere Lifecycle Manager-enabled Cluster](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/upgrade-guide/upgrading-nsxt/configuring-and-upgrading-hosts-nsx-t/upgrade-vsphere-lifecycle-manager-enabled-cluster.html){: external}.
* Verify that the vSAN environment is in good health. See [Monitoring vSAN Health](https://techdocs.broadcom.com/us/en/vmware-cis/vsan/vsan/7-0/vsan-monitoring/monitoring-vsan-skyline-health.html){: external}.

## Related links
{: #vum-updating-nsx-related}

* [VMware HCX solution architecture](/docs/vmwaresolutions?topic=vmwaresolutions-hcx-archi-intro#hcx-archi-intro)
* [{{site.data.keyword.vmwaresolutions_short}}](https://www.ibm.com/products/vmware)
