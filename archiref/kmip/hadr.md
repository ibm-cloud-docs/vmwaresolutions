---

copyright:

  years:  2023, 2025

lastupdated: "2025-10-24"

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# High availability and disaster recovery for KMIP for VMware
{: #kmip-hadr}

{{site.data.content.vms-deprecated-note}}

{{site.data.content.kmip-deprecated-note}}

{{site.data.content.kmip-imp-note}}

## High availability within a region
{: #kmip-hadr-regional}

Within a single region:

* KMIP for VMware and Key Protect are highly available when correctly configured. If any one of the three zones in that region fail entirely, key management continues to be available to your VMware® workloads.
* KMIP for VMware and Hyper Protect Crypto Services (HPCS) are highly available if you deploy two or more crypto units for your HPCS instance. If you do so and any one of the three zones in that region fail entirely, key management continues to be available to your VMware workloads.

## Disaster recovery across regions
{: #kmip-hadr-cross-region}

When you are using VMware vSAN® encryption, each site is protected by its own key provider. If you are using vSAN encryption to protect workloads that you replicate between multiple sites, you must create separate KMIP for VMware instances in each site that is connected to separate Key Protect or HPCS instances in those sites. You must connect your VMware vCenter Server® in each site to the local KMIP for VMware instance as its key provider.

When you are using VMware vSphere® encryption, most VMware replication and migration techniques today (for example, cross-vCenter vMotion and vSphere replication) rely on having a common key manager between the two sites. This topology is not supported by KMIP for VMware. Instead, you must create a separate KMIP for VMware instance in each site that is connected to separate Key Protect or HPCS instances in those sites. You must connect your vCenter Server in each site to the local KMIP for VMware instance as its key provider, and then use a replication technology that supports the attachment and replication of decrypted disks.

Veeam Backup and Replication supports this replication technique. To implement this technique, see the [steps that you must take](https://helpcenter.veeam.com/docs/backup/vsphere/encrypted_vms_backup.html?ver=120){: external} as indicated in the Veeam® documentation.

This technique does not support the replication of virtual machines with a vTPM device.
{: note}

## Related links
{: #kmip-hadr-related}

* [Solution overview](/docs/vmwaresolutions?topic=vmwaresolutions-kmip-overview)
* [Solution design](/docs/vmwaresolutions?topic=vmwaresolutions-kmip-design)
* [Implementation and management](/docs/vmwaresolutions?topic=vmwaresolutions-kmip-implementation)
* [Veeam and encrypted VMs](https://helpcenter.veeam.com/docs/backup/vsphere/encrypted_vms_backup.html?ver=120){: external}
