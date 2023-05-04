---

copyright:

  years:  2020, 2023

lastupdated: "2023-04-20"

keywords: ordering prerequisites, before you order, pre-order checklist, before first order

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Setting up your environment for your first order
{: #completing_checklist}

The setup information applies only to the following offerings: VMware vSphere, VMware vCenter Server, VMware Regulated Workloads, and Cyber Recovery.
{: note}

When you order your instance for the first time, ensure that your environment is ready for your order. Follow the instructions in the **Before you begin** section on the ordering page. The instructions might vary depending on the instance type that you select.

## Procedure to set up your environment for your first order
{: #completing_checklist-procedure}
{: help}
{: support}

1. [Upgrade your account to a Pay-As-You-Go account](/docs/account?topic=account-upgrading-account#upgrade-paygo). Subscription accounts are not supported for VMware®.
2. [Create a classic infrastructure API key](/docs/account?topic=account-classic_keys#create-classic-infrastructure-key).
3. In the {{site.data.keyword.vmwaresolutions_full}} console, retrieve your API key and username. Click **Settings** from the left navigation pane and click **Retrieve credentials**.
4. Review the username and API key that are automatically entered and click **Save credentials**. If you receive a message that administrator access is required, you can locate an account administrator by using the steps in [Locating an IAM account administrator](/docs/vmwaresolutions?topic=vmwaresolutions-iam_verify_permissions).
5. Verify or update the [permissions](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts#signing_required_accounts-infra-permissions) for your {{site.data.keyword.cloud}} infrastructure account.
6. Convert your {{site.data.keyword.cloud_notm}} infrastructure account to a [virtual routing and forwarding (VRF) account](/docs/direct-link?topic=direct-link-what-happens-during-the-account-conversion-process).
7. Enable [service endpoints](/docs/account?topic=account-vrf-service-endpoint#service-endpoint) to connect to certain services over the {{site.data.keyword.cloud_notm}} private network rather than the public network.

## Results
{: #completing_checklist-results}

* The {{site.data.keyword.cloud_notm}} infrastructure credentials are stored in the VMware Solutions console after the first order. Future orders use the stored credentials by default.
* After you complete the checklist instructions, the checklist is no longer displayed next time that you are on the ordering page. You can update the credentials on the **Settings** page later on.
* If the API key for your {{site.data.keyword.cloud_notm}} infrastructure account changes, you must update the key on the **Settings** page in the VMware Solutions console.

## Related links
{: #completing_checklist-related}

* [Managing user accounts and settings](/docs/vmwaresolutions?topic=vmwaresolutions-useraccount)
* [FAQ](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Ordering vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-req)
