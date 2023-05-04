---

copyright:

  years:  2022, 2023

lastupdated: "2023-04-12"

keywords: Cyber Recovery remove hosts, Cyber Recovery remove ESXi servers

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Removing ESXi servers from Cyber Recovery instances
{: #cr_removingservers}

You can contract the capacity of your Cyber Recovery instance according to your business needs by removing VMware ESXi™ servers.

## Before you remove ESXi servers from Cyber Recovery instances
{: #cr_removingservers-prereq}

* For the gateway cluster, you cannot add or remove ESXi servers.
* Whenever possible, remove ESXi servers by using the VMware Solutions console because changes that you make on the VMware vSphere® Web Client are not synchronized with the VMware Solutions console. Therefore, remove ESXi servers from Cyber Recovery only for on-premises ESXi servers or ESXi servers that you don't manage in the VMware Solutions console.
* When you remove ESXi servers, the servers are placed in maintenance mode, and then, all the virtual machines (VMs) running on the servers are migrated before they are removed from Cyber Recovery. For maximum of control over the relocation of VMs, place the ESXi servers to remove in maintenance mode and migrate the VMs running on them manually using the VMware vSphere Web Client. After that, remove the ESXi servers by using the VMware Solutions console.
* If you are using NFS storage, NSX-T™ instances require at least three ESXi servers for a consolidated cluster or at least two servers for any other cluster.
* If you are using vSAN™ storage, at least four ESXi servers are required.

## Procedure to remove ESXi servers from Cyber Recovery instances
{: #cr_removingservers-procedure}

1. From the {{site.data.keyword.vmwaresolutions_full}} console, click **Resources > Cyber Recovery** from the left navigation pane.
2. In the **Cyber Recovery** table, click the instance for which you want to contract capacity.
3. Click the **Infrastructure** tab.
4. In the applicable cluster table, click the cluster from which you want to remove ESXi servers.
5. In the **ESXi servers** section, select the servers that you want to remove and click **Remove**.
6. Click **Delete** in the **Remove ESXi server** window.

## Results after you remove ESXi servers from Cyber Recovery instances
{: #cr_removingservers-results}

1. You might experience a slight delay on the console, while the instance status changes from **Available** to **Modifying**. Allow the operation to complete before you make more changes to the instance.
2. You are notified by email that your request to remove ESXi servers is being processed. On the console, the status of the cluster that is associated with the ESXi servers is changed to **Modifying**.
3. The ESXi servers are fully reclaimed by {{site.data.keyword.cloud_notm}} infrastructure at the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle, which is typically 30 days.

   You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the removed ESXi servers.
   {: note}

## Related links
{: #cr_removingservers-related}

* [Planning for Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_planning)
* [Procedure to order Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-order-procedure)
* [Deleting clusters from Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_deletingclusters)
* [Place a host in maintenance mode](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.resmgmt.doc/GUID-8F705E83-6788-42D4-93DF-63A2B892367F.html){: external}
* [Enhanced vMotion Compatibility (EVC) processor support](https://kb.vmware.com/s/article/1003212){: external}
