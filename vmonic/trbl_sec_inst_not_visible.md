---

copyright:

  years:  2016, 2022

lastupdated: "2022-04-22"

keywords: troubleshooting, secondary vCenter, vSphere inventory issue

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Why doesn't the secondary vCenter Server display in the vSphere Web Client inventory?
{: #trbl_sec_inst_not_visible}
{: troubleshoot}
{: support}

In a multisite configuration, after you add a secondary instance, its VMware vCenter Server® system is not visible when logged in to the VMware vSphere® Web Client of a previously ordered instance.
{: tsSymptoms}

This is a known VMware® issue.
{: tsCauses}

To resolve the problem, you must restart the vSphere Web Client:
{: tsResolve}

1. Using the **root** account, connect over **ssh** to the vCenter VM (virtual machine) of the previously ordered instance.
2. Type ``shell`` to enter the bash shell.
3. Enter `service-control --stop vsphere-client` to stop the client.
4. Enter `service-control --start vsphere-client` to restart the client.
5. After the vSphere Web Client of the previously ordered instance is restarted, confirm that the vCenter Server system for the newly added secondary instance is visible in the vSphere Web Client.
