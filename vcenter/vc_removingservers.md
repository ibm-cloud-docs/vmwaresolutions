---

copyright:

  years:  2021, 2022

lastupdated: "2022-10-20"

keywords: vCenter Server remove hosts, vCenter Server remove ESXi servers

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Removing ESXi servers from vCenter Server instances
{: #vc_removingservers}

You can contract the capacity of your VMware vCenter Server® instance according to your business needs by removing VMware ESXi™ servers.

## Before you remove ESXi servers from vCenter Server instances
{: #vc_removingservers-prereq}

* Removing ESXi servers from vCenter Server instances with VMware vSphere® 6.5 is not supported.
* For the edge services cluster, you cannot add or remove ESXi servers.
* {{site.data.content.para-vcenterremoveESXiservers}}
* When you remove ESXi servers, the servers are placed in maintenance mode, and then, all the virtual machines (VMs) running on the servers are migrated before they are removed from vCenter Server. For maximum of control over the relocation of VMs, place the ESXi servers to remove in maintenance mode and migrate the VMs running on them manually using the VMware vSphere Web Client. After that, remove the ESXi servers by using the VMware Solutions console.
* If you are using vSAN storage, at least four ESXi servers are required.
* If you are using NFS storage, NSX-T™ instances require at least three ESXi servers for a consolidated cluster or at least two servers for any other cluster. NSX-V instances require at least two ESXi servers.
* (NSX-V only) If F5® BIG-IP® or FortiGate® Virtual Appliance is installed on your ESXi server, you must migrate the F5 BIG-IP and FortiGate VMs to a different ESXi server than the one that is hosting the VMs.
* (NSX-V only) If IBM Spectrum® Protect Plus is installed on your ESXi server, ensure that there are no active (failed or in progress) backup or restore operations. These active operations might prevent the ESXi server from being removed.

## Procedure to remove ESXi servers from vCenter Server instances
{: #vc_removingservers-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources > vCenter Server** from the left navigation pane.
2. In the **vCenter Server instances** table, click the instance for which you want to contract capacity.
3. Click **Infrastructure** on the left navigation pane.
4. In the applicable cluster table, click the cluster from which you want to remove ESXi servers.
5. In the **ESXi servers** section, select the servers that you want to remove and click **Remove**.
6. Click **Delete** in the **Remove ESXi server** window.

## Results after you remove ESXi servers from vCenter Server instances
{: #vc_removingservers-results}

1. You might experience a slight delay on the console, while the instance status changes from **Ready to use** to **Modifying**. Allow the operation to complete before you make more changes to the instance.
2. You are notified by email that your request to remove ESXi servers is being processed. On the console, the status of the cluster that is associated with the ESXi servers is changed to **Modifying**.
3. The ESXi servers are fully reclaimed by {{site.data.keyword.cloud_notm}} infrastructure at the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle, which is typically 30 days.

   You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the removed ESXi servers.
   {: note}

## Related links
{: #vc_removingservers-related}

* [vCenter Server BOM](/docs/vmwaresolutions?topic=vmwaresolutions-vc_bom)
* [Planning for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_planning)
* [Ordering vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-req)
* [Deleting clusters from vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingclusters)
* [Place a host in maintenance mode](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.resmgmt.doc/GUID-8F705E83-6788-42D4-93DF-63A2B892367F.html){: external}
* [Enhanced vMotion Compatibility (EVC) processor support](https://kb.vmware.com/s/article/1003212){: external}
