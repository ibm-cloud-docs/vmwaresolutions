---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-14"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Securing VMware Federal instances
{: #securing-vmware-federal-instances}

Complete the following procedure to secure your deployed VMware Federal instance, that is, to remove the open management connection for ongoing access to the instance.

## Before you begin
{: #vc_fed_securinginstance-prereq}

Review the following information to understand the results of securing your deployed VMware Federal instance:

* Record and save any credentials that you might need for your environment before you complete this procedure. All credentials for your environment are erased from the {{site.data.keyword.vmwaresolutions_full}} database and cannot be retrieved after the secure action is started.
* Except for a full instance delete, all other management functions are disabled after the secure action is started.

## Procedure to secure VMware Federal instances
{: #vc_fed_securinginstance-procedure}

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Deployed Instances** from the left navigation pane.
2. In the **vCenter Server Instances** table, click the instance to secure.
3. Click the overflow menu icon next to **vCenter console**.
4. Click **Secure Instance**.
5. Click **OK** to confirm that you want to disconnect the instance from automation.

  Before you complete this step, ensure that you review the information in the **Before you begin** section.
  {:note}

6. Remove the public facing management services VMware NSX Edge Services Gateway (ESG) from your environment and optionally remove your client-managed ESG that is deployed during automation.
7. Reset passwords or keys for all accounts that are used by IBM automation. For more information, see [How can I secure my environment to remove access by IBM automation and support?](https://developer.ibm.com/answers/questions/452354/how-can-i-secure-my-environment-to-remove-access-b/)

## Results
{: #vc_fed_securinginstance-results}

The status of the instance is changed to **Modifying**.

When the instance is secured successfully, the status of the instance is changed to **Secured** and only the instance properties and deployment history are available.

## Related links
{: #vc_fed_securinginstance-related}

* [VMware Federal on {{site.data.keyword.cloud_notm}} overview](/docs/services/vmwaresolutions/vcenter/vc_fed_overview.html)
* [Ordering VMware Federal instances](/docs/services/vmwaresolutions/vcenter/vc_fed_orderinginstance.html)
* [Viewing VMware Federal instances](/docs/services/vmwaresolutions/vcenter/vc_fed_viewinginstance.html)
* [Deleting VMware Federal instances](/docs/services/vmwaresolutions/vcenter/vc_fed_deletinginstance.html)
* [Contacting IBM Support](/docs/services/vmwaresolutions/vmonic/trbl_support.html)
