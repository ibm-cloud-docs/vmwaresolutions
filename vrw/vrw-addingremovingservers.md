---

copyright:

  years:  2021, 2025

lastupdated: "2025-07-15"

keywords: vmware regulated workloads, add hosts vmware regulated workloads, add servers vmware regulated workloads, remove hosts vmware regulated workloads

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Expanding and contracting capacity for {{site.data.keyword.rw}}
{: #vrw-addingremovingservers}

{{site.data.content.vrw-deprecated-note}}

Expand or contract the capacity of your {{site.data.keyword.rw}} instances according to your business needs, by adding or deleting VMware vSphere® ESXi™ servers or Network File System (NFS) storage.

## Before you add or delete ESXi servers
{: #vrw-addingremovingservers-before}

You must migrate the VMware vCenter Server® virtual machines (VMs) before you delete a server. This requirement applies to the vCenter Server VM and to the additional vCenter high availability VMs on the management and witness clusters.

## Adding or deleting ESXi servers
{: #vrw-addingremovingservers-add-delete-esxi}

The processes to add and delete servers for {{site.data.keyword.rw}} instances are similar to the ones for {{site.data.keyword.vcf-auto}} instances. For more information, see:
* [Adding ESXi servers to Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservers)
* [Deleting ESXi servers from Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_removingservers)

## Adding or removing NFS storage
{: #vrw-addingremovingservers-add-delete-nfs}

The processes to add and remove NFS storage for {{site.data.keyword.rw}} instances are similar to the ones for {{site.data.keyword.vcf-auto-short}} instances. For more information, see:
* [Adding NFS storage to Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingnfs)
* [Removing NFS storage from Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_removingnfs)
