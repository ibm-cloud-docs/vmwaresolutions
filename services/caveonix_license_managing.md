---

copyright:

  years:  2016, 2022

lastupdated: "2022-10-10"

keywords: Caveonix view license, Caveonix manage license, delete Caveonix license

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Managing Caveonix RiskForesight licenses
{: #caveonix_license_managing}

This information applies to VMware vCenter Server® instances only. It does not apply to VMware® Regulated Workloads or Security and Compliance Readiness Bundle instances.
{: note}

You can view, edit notes, or delete the Caveonix RiskForesight™ licenses that you ordered for stand-alone use.

## Procedure to view Caveonix RiskForesight licenses
{: #caveonix_license_managing_procedure-view}

1. From the {{site.data.keyword.vmwaresolutions_full}} console, click **Licenses** from the left navigation pane and go to the **Caveonix RiskForesight licenses** table.
2. To view the details of a specific license, click the license.

Review the following Caveonix RiskForesight license details.

| Item | Description |
|:-----|:------------|
| Name | The name of the license. |
| Creation time | The date and time when the license was created. |
| Status | The status of the license: \n Modifying - The license is being created. \n Installed - The license is ready to use. \n Removing - The license is being deleted. |
{: caption="Table 1. Description of Caveonix RiskForesight license items" caption-side="bottom"}

## Procedure to edit notes for Caveonix RiskForesight licenses
{: #caveonix_license_managing_procedure-edit}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Licenses** from the left navigation pane.
2. In the **Caveonix RiskForesight licenses** table, click the license that you want to edit the notes for.
3. On the license details page, edit the license notes, and then click **Confirm**.

## Known issues about license date display
{: #caveonix_license_considerations-date}

If you are using Mozilla® Firefox® as your browser, the license start and end dates might be displayed with no values on the Caveonix RiskForesight console. To resolve the issue, view the license information in another browser, such as Google Chrome™.

If you are experiencing this problem and the only browser you can use is Firefox, contact [Caveonix Support](https://www.caveonix.com/support/){: external} for assistance.
{: note}

## Procedure to delete Caveonix RiskForesight licenses
{: #caveonix_license_managing_procedure-delete}

Deleting Caveonix RiskForesight automatically deletes the initial Caveonix RiskForesight license that is originally associated with the service. However, you need to manually delete any other unwanted licenses from the Caveonix RiskForesight licenses table on the Resources page in the VMware Solutions console.

To delete the Caveonix RiskForesight service, you must do so in the {{site.data.keyword.vmwaresolutions_full}} console. For more information, see [Deleting services from vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_deletingservices).
{: note}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Licenses** from the left navigation pane.
2. In the **Caveonix RiskForesight licenses** table, find the license to delete.
3. In the **Actions** column, click the **Delete** icon ![Delete icon](../../icons/delete.svg "Delete").
4. In the **Delete License** window, click **OK**.
   The status of the license is changed to **Removing**. When the license deletion is completed, the license is no longer available in the **Caveonix RiskForesight licenses** table.

## Related links
{: #caveonix_license_managing-related}

* [Caveonix RiskForesight overview](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_considerations)
* [Ordering Caveonix RiskForesight licenses](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_license_ordering)
