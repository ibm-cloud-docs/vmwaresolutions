---

copyright:

  years:  2020, 2025

lastupdated: "2025-10-24"

keywords: Veeam, Veeam license, manage Veeam license, Veeam Backup and Replication

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Managing Veeam stand-alone licenses
{: #veeam_managing_licenses}

{{site.data.content.vms-deprecated-note}}

You can edit notes, view, or delete the Veeam® licenses that you ordered for stand-alone use.

## Procedure to edit notes for Veeam stand-alone licenses
{: #veeam_managing_licenses-procedure-edit}

1. In the VMware Solutions console, click **Licensing and metering > Add-on services** from the left navigation panel.
2. Scroll down to the **Veeam licenses** table.
3. Click the license that you want to edit the notes for.
4. On the license details page, edit the license notes, and then click **Confirm**.

## Procedure to view Veeam stand-alone licenses
{: #veeam_managing_licenses-procedure-view}

1. {{site.data.content.ol-intro-ui-licenses}}
2. Scroll down to the **Veeam licenses** table.
3. To view the details of a specific license, click the license. The following information is displayed for the Veeam license:

* License name
* License notes
* Number of virtual machines (VMs) licensed
* Creation date
* License platform
* Status - the status can be one of the following items.
   * Modifying - The license is being created.
   * Installed - The license is ready to use.
   * Removing - The license is being deleted.

   A license key is not displayed. When licenses are ordered, the system does not generate a key, but it applies a primary key.
   {: note}

### Known issues about license date display
{: #veeam_managing_licenses-considerations-date}

If you are using Mozilla® Firefox® as your browser, the license start and end dates might be displayed with no values on the Veeam console. To resolve the issue, view the license information in another browser, such as Google Chrome™.

If you are experiencing this problem and the only browser you can use is Firefox, contact [Veeam support](https://www.veeam.com/support.html){: external} for assistance.

## Procedure to delete Veeam stand-alone licenses
{: #veeam_managing_licenses-procedure-delete}

Before you delete a Veeam license, review [Considerations when you delete Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam#veeamvm_overview-remove).
{: important}

Deleting a Veeam license does not delete the Veeam service that is installed on a {{site.data.keyword.vcf-auto-short}} instance. To delete the service, you must do so in the VMware Solutions console. For more information, see [Deleting services from {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices).

To delete a Veeam license:

1. In the VMware Solutions console, click **Licensing and metering > Add-on services** from the left navigation panel.
2. Scroll down to the **Veeam licenses** table and select the license that you want to delete.
3. From the **Actions** menu, click **Delete instance**.
4. In the **Delete license** window, click **Delete**.
   The status of the license is changed to **Removing**. When the license deletion is completed, the license is no longer listed in the **Veeam licenses** table.

## Related links
{: #veeam_managing_licenses-related}

* [Veeam on {{site.data.keyword.cloud_notm}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview)
* [Ordering Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering)
* [Managing Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam)
* [Ordering Veeam stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering_licenses)
* [Ordering and configuring {{site.data.keyword.cloud_notm}} Object Storage with Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-icos_ordering)
