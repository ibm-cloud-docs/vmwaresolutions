---

copyright:

  years:  2016, 2025

lastupdated: "2025-10-21"

keywords: HCX updates, HCX management console, login HCX console

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}


# Managing VMware HCX
{: #managinghcx}



## Accessing the HCX management consoles
{: #managinghcx-accessing-consoles}

To manage the VMware HCX™ service, you must access the HCX Cloud console or the HCX Manager Admin console:

* Use the {{site.data.keyword.cloud}} infrastructure VPN or a jump server to allow access to the IP address of the HCX Manager virtual appliance (HCX Manager). You can find the IP address on the HCX service details page in the {{site.data.keyword.vmwaresolutions_short}} console.
* To access the HCX Cloud console, click **View HCX Cloud console** on the HCX service details page, and then log in by using the VMware vCenter Server® credentials.
* To access the HCX Manager Admin console, click **View HCX Manager Admin console** on the HCX service details page. Then, log in by using the HCX Manager credentials that are listed on the same service details page.

For more information, see [Viewing services for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_viewingservices).

## Applying updates to HCX
{: #managinghcx-updates}

HCX is deployed with the most recently tested build of VMware Hybrid Cloud Extension technology. VMware® by Broadcom provides updates to the builds regularly, which include important fixes and new features. These builds are pushed to HCX installations automatically.

To apply any maintenance fixes pushed to your environment, you must use the HCX Manager Admin console in your on-premises data center and your {{site.data.keyword.vcf-auto-short}} instance.

Open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) for the following situations:
* You do not see a build update that you are expecting.
* You have problems with HCX.
* You want to have the most recent HCX build pushed to your system immediately.

## Considerations when you delete HCX
{: #hcx_considerations-delete}

Review the following considerations before you delete the HCX service:

* If you delete a workload cluster and that cluster is the service mesh cluster, the HCX service is automatically deleted.
* The deletion of HCX is automated. The following procedures are completed for the successful deletion of this service:
   * The HCX license that is ordered for the cloud-side HCX Manager is deactivated.
   * HCX Manager is deleted.
   * The vMotion IP addresses that were reserved for HCX are released.
   * The HCX management edge appliances are deleted.
* Only the VMs that were deployed during the initial installation of the HCX instances are deleted. Any node that is deployed after the installation is not cleaned up.

Complete the following tasks before you delete the HCX service:

* Remove any personal VMs from the storage that is deployed with HCX. HCX orders personal VMs only for non-vSAN clusters.
* From the HCX user interface in the on-premises VMware vSphere Web Client, delete the service mesh and the extended networks between the on-premises source site and the {{site.data.keyword.cloud_notm}} target sites.
* From the same user interface, remove the site pairings between the on-premises source site and the {{site.data.keyword.cloud_notm}} target sites.

## Related links
{: #managinghcx-related}

* [HCX overview](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_considerations#hcx_considerations)
* [Glossary of HCX terms](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_glossary)
* [VMware HCX documentation](https://techdocs.broadcom.com/us/en/vmware-cis/hcx.html){: external}
