---

copyright:

  years:  2025

lastupdated: "2025-09-10"

keywords: licenses, add license keys, assign licenses, validate licenses, manage licenses

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Managing VMware product licenses
{: #licensing_manage}

After you registered VMware vCloud Usage Meter with IBM, you can add and assign license keys to various VMware products.

## Adding license keys to VCF, vCenter Server, vSAN, and ESXi
{: #licensing_manage-add-vcf}

To add license keys to VMware Cloud Foundation (VCF) and VMware vSAN, complete the following steps in the VMware vSphere® Web Client:

1. Log in to VMware vCenter Server with administrator privileges.
2. Click **Administration > Licenses**.
3. Under **Licenses**, click **Add**.
4. Under **Enter license keys**, paste the vCenter Server, vSAN, and vSphere ESXi licenses, one per line, and click **Next**.
5. Under **Edit license names**, enter the names of the licenses and review the license keys, product, and capacity, then click **Next**.
6. Under **Ready to complete**, review the license information and click **Finish**.

## Assigning licenses
{: #licensing_manage-assign}

To assign licenses to vCenter Server, complete the following steps:

1. In the **Licenses** page, on the **Assets** tab, select **vCenter Server systems**.
2. Check the vCenter Server box note that you want to assign the license and click **Assign license**.
3. In the **Assign license** window, select the new license key that was added previously.
4. In the **Assignment validation** box, click **OK** to acknowledge the message that the license assignment is valid. If it is not valid, check that the license key is correct and that it contains the required capacity.
5. On the **Assets** tab, select **Hosts**.
6. Select all checkboxes for the hosts to which you want to assign the license and click **Assign license**. To assign the license to multiple objects, click **Yes**.
7. In the **Assign license** window, select the new license key that was added previously.
8. In the **Assignment validation** box, click **OK** to acknowledge the message that the license assignment is valid. If it is not valid, check that the license key is correct and that it contains the required capacity.
9. On the **Assets** tab, select **vSAN clusters**.
10. Select the vSAN cluster checkbox that you want to assign the license and click **Assign license**.
11. In the **Assign license** window, select the new vSAN license that was added previously.
12. In the **Assignment validation** box, click **OK** to acknowledge the message that the license assignment is valid. If it is not valid, check that the license key is correct and that it contains the required capacity.

### Results after you assign licenses
{: #licensing_manage-assign-results}

* In the **Licenses** page, on the **Licenses** tab, all old licenses now show 0 in the **Usage** column.
* If the licenses don't show 0 usage, verify that the new licenses are applied to all objects in the environment. You can remove the licenses with 0 usage from the environment by selecting them and clicking **Remove**.

## Adding license keys to NSX-T
{: #licensing_manage-add-nsx}

To add license keys to VMware NSX-T™ (NSX component or VMware vDefend Firewall), complete the following steps:

1. Log in to NSX-T UI with administrator privileges.
2. On the **System** tab, click **Licenses**.
3. Click **Add License**.
4. Enter the license key and click **Add**. The browser refreshes after the license is applied.
5. Verify that all new licenses are **Valid** under the **Validity** column and that the **Quantity** value is correct.

The VMware NSX Networking license requires VMware NSX® 3.2 or later.
{: important}

You can delete old licenses by selecting them and clicking **Delete**.
{: tip}

## Adding license keys to Aria Operations
{: #licensing_manage-add-aria}

To add license keys to VMware Aria® Operations™, complete the following steps:

1. Log in to Aria Operations with administrator privileges.
2. On **Administration**, click **Licensing**.
3. On the **License keys** tab, click **Add**.
4. On the **Add license** window, select **vRealize Operations**.
5. Enter the Aria Operations license key and click **Validate**, then click **Save**.
6. When the success message is displayed, click **OK**. The new license appears in the **License keys** table.

You can delete old licenses by selecting them and clicking the three dots icon and then **Delete**.
{: tip}

## Adding license keys to HCX Manager
{: #licensing_manage-add-hcx}

To add license keys to HCX™ Manager, complete the following steps:

1. Log in to HCX Manager with administrator privileges.
2. On **Configuration**, select **Licensing and activation**.
3. On the existing license, click the three dots icon next to the license key.
4. On the new window, enter the new license key and click **OK**. The new license shows the **Active** status and **Perpetual license** validity.

## Validating licenses
{: #licensing_manage-validate}

To validate the licenses for VMware products, complete the following steps:

### Validating licenses for NSX
{: #licensing_manage-validate-nsx}

1. Log in to the NSX-T UI with administrator privileges.
2. On the **System** tab, select **Licenses**.
2. Verify that the new license appears in the list.

### Validating licenses for Aria Operations
{: #licensing_manage-validate-aria}

1. Log in to Aria Operations with administrator privileges.
2. On **Administration**, click **Licensing**.
3. Verify that the new license appears in the list.

### Validating licenses for HCX Manager
{: #licensing_manage-validate-hcx}

1. Log in to HCX with administrator privileges.
2. On **Configuration**, select **Licensing and activation**.
3. Verify that the new license appears in the list.

## Related links
{: #licenses-add-assign-related}

* [Retrieving VCF license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses)
