---

copyright:

  years:  2021, 2025

lastupdated: "2025-04-04"

keywords: VMware Solutions Shared modify private network endpoint

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Modifying a private network endpoint for a virtual data center
{: #shared_modifying-endpoints}

{{site.data.content.shared-deprecated-note}}

You can add or remove allowlisted IP addresses or subnets for a private network endpoint.

## Procedure to add an IP address or subnet for a private network endpoint
{: #shared_modifying-endpoints-add}

1. {{site.data.content.ol-intro-ui-shared}}
2. In the **{{site.data.keyword.vm-shared}}** table, expand the site and click a virtual data center name.
3. Click the **Services** tab.
4. From the **Private network endpoint** details pane, click the **Edit** icon ![Edit icon](../../icons/edit-tagging.svg "Edit") next to **Allowlisted IPs and subnets**.
5. Enter the IP address in the **New IP** field and click **Add**.
6. When all modifications are complete, click **Update**.

## Procedure to delete an IP address or subnet from a private network endpoint
{: #shared_modifying-endpoints-delete}

1. In the VMware Solutions console, click **Resources > {{site.data.keyword.vm-shared}}** from the left navigation panel.
2. In the **{{site.data.keyword.vm-shared}}** table, expand the site and click a virtual data center name.
3. Click the **Services** tab.
4. From the **Private network endpoint** details pane, click the **Edit** icon ![Edit icon](../../icons/edit-tagging.svg "Edit") next to **Allowlisted IPs and subnets**.
5. Locate the IP address that you want to delete and click the **Delete** icon ![Delete icon](../../icons/delete.svg "Delete").
6. When all modifications are complete, click **Update**.

## Related links
{: #shared_modifying-endpoints-related}

* [Operating {{site.data.keyword.vm-shared}}](/docs/vmwaresolutions?topic=vmwaresolutions-shared_vcd-ops-guide)
* [{{site.data.keyword.vm-shared}} pricing](/docs/vmwaresolutions?topic=vmwaresolutions-shared_pricing)
* [Creating a private network endpoint](/docs/vmwaresolutions?topic=vmwaresolutions-shared_creating-endpoints)
* [Viewing a private network endpoint for a virtual data center](/docs/vmwaresolutions?topic=vmwaresolutions-shared_viewing-endpoints)
* [Deleting a private network endpoint from a virtual data center](/docs/vmwaresolutions?topic=vmwaresolutions-shared_deleting-endpoints)
