---

copyright:

  years:  2022

lastupdated: "2022-10-07"

keywords: manage shared resources, set IAM integration the VMware Cloud Director Management console, shared iam roles, iam roles

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Enabling and managing Identity and Access Management
{: #shared_set-iam}

You can optionally enable {{site.data.keyword.cloud}} Identity and Access Management (IAM) for your VMware Cloud Director Organization. For new organizations, IAM is enabled by default. For existing organizations, you can set or reset the IAM enablement from the virtual data center site details page.

## Before you begin
{: #shared_set-iam-prereq}

Review roles and assign resource access for {{site.data.keyword.vmwaresolutions_short}} Shared service instances. For more information, see [Managing IAM access for VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-iam) and [Roles and permissions for VMware Cloud Director](/docs/vmwaresolutions?topic=vmwaresolutions-iam_vcd&interface=ui).

## Procedure to enable IAM
{: #shared_set-iam-procedure}

Enable IAM for existing organizations or reset the IAM integration if necessary.

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Resources > VMware Shared** from the left navigation pane.
2. In the **VMware Solutions Shared** table, click the site name to open the site properties page.
3. Click **Summary** from the left navigation pane.
4. From the **Properties** pane, click **Set IAM integration**.

## Results after you enable IAM
{: #shared_set-iam-results}

The IAM integration status can have the following results.

| Status        | Description       |
|:------------- |:------------- |
| Integration pending | The IAM integration is in progress. |
| Integration incomplete | The integration is not successful. Contact IBM Support. |
| Integration enabled | The IAM integration was previously enabled for the organization. You can reset the integration, if needed. |
{: caption="Table 1. Status descriptions for IAM implementation" caption-side="bottom"}

### Resetting an IAM integration
{: #shared_set-iam-results-reset}

You must delete all OpenID Connect (OIDC) users and imported groups with the OIDC type, then the OIDC provider before you can reset the IAM integration. For more information, see [Deleting the OpenID Connect configuration in your VMware Cloud Director Organization](/docs/vmwaresolutions?topic=vmwaresolutions-shared_vcd-ops-guide#shared_vcd-ops-guide-delete-oidc).

### Single sign-on availability
{: #shared_set-iam-results-sso}

After the IAM integration is enabled, you can use single sign-on to log in to the VMware Cloud Director console.
1. In the {{site.data.keyword.vmwaresolutions_short}} console, click **VMware Cloud Director console**.
2. From the log in panel, click **SIGN IN WITH SINGLE SIGN-ON** to log in to the console.

## Related links
{: #shared_set-iam-related}

* [VMware Solutions Shared overview](/docs/vmwaresolutions?topic=vmwaresolutions-shared_overview)
* [Viewing site and virtual data center details](/docs/vmwaresolutions?topic=vmwaresolutions-shared_viewing-vdc-details)
* [Locating an IAM account administrator](/docs/vmwaresolutions?topic=vmwaresolutions-iam_verify_permissions)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [VMware Cloud Director](https://www.vmware.com/ca/products/vcloud-director.html){: external}
