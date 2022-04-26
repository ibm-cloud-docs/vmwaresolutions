---

copyright:

  years:  2016, 2022

lastupdated: "2022-04-22"

keywords: troubleshooting, Zerto VRA, Zerto uninstall

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Why are Zerto VRAs visible on the ESXi host in the vCenter console after Zerto is uninstalled?
{: #trbl_zerto_vra}
{: troubleshoot}
{: support}

Zerto Virtual Replication Appliances (VRAs) are not removed after you use the {{site.data.keyword.slportal_full}} to successfully uninstall the Zerto service.
{: tsSymptoms}

Manually remove the VRAs from the vCenter® console.
{: tsResolve}

1. Log in to the vCenter console.
2. Click **Hosts and Clusters** and locate the virtual machines with names that start with **Z-VRA-**. For example, **`Z-VRA-host0-vcs40dal.vcs.icvs.org`**.
3. Right-click the **Z-VRA-** virtual machine and click **Delete from Disk**.
