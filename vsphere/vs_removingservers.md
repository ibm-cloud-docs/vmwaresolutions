---

copyright:

  years:  2023, 2024

lastupdated: "2024-05-16"

keywords: flexible remove hosts, flexible remove ESXi servers, delete server

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Deleting ESXi servers from Flexible instances
{: #vs_removingservers}

You can contract the capacity of your {{site.data.keyword.vcf-flex}} instance according to your business needs by deleting VMware ESXi™ servers.

## Before you delete ESXi servers from Flexible instances
{: #vs_removingservers-prereq}

Before you delete ESXi servers, ensure that you remove your workloads from these servers:
1. First, place the ESXi servers to delete in maintenance mode and migrate the VMs running on them manually using the VMware vSphere® Web Client.
2. After that, delete the ESXi servers by using the VMware Solutions console.

## Procedure to delete ESXi servers from Flexible instances
{: #vs_removingservers-procedure}

1. {{site.data.content.ol-intro-ui-vcfclassic}}
2. In the **{{site.data.keyword.vcf-classic}}** table, click the instance for which you want to contract capacity.
3. Click the **Infrastructure** tab.
4. In the **ESXi servers** section, select the servers that you want to delete and click **Delete**.
5. Click **Delete** in the **Delete ESXi server** window.

## Results after you delete ESXi servers from Flexible instances
{: #vs_removingservers-results}

1. You might experience a slight delay on the console, while the instance status changes from **Available** to **Modifying**. Allow the operation to complete before you make more changes to the instance.
2. You are notified by email that your request to delete ESXi servers is being processed. On the console, the status of the instance is changed to **Modifying**.
3. The ESXi servers are fully reclaimed by {{site.data.keyword.cloud_notm}} infrastructure at the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle, which is typically 30 days.

   You are billed until the end of the {{site.data.keyword.cloud_notm}} infrastructure billing cycle for the deleted ESXi servers.
   {: note}

## Related links
{: #vs_removingservers-related}

* [Planning for Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_planning)
* [Procedure to order Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-procedure)
* [Place a host in maintenance mode](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/8-0/esxi-upgrade-8-0/upgrading-esxi-hosts-upgrade/how-to-upgrade-hosts-by-using-esxcli-commands-upgrade/place-a-host-in-maintenance-mode-upgrade.html){: external}
* [Enhanced vMotion Compatibility (EVC) processor support](https://knowledge.broadcom.com/external/article?legacyId=1003212){: external}
