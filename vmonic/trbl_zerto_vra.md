---

copyright:

  years:  2016, 2021

lastupdated: "2021-03-17"

keywords: troubleshooting, Zerto VRA, Zerto uninstall

subcollection: vmwaresolutions

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:support: data-reuse='support'}

# Why are Zerto VRAs visible on the ESXi host in the vCenter console after Zerto is uninstalled?
{: #trbl_zerto_vra}
{: troubleshoot}
{: support}

Zerto Virtual Replication Appliances (VRAs) are not removed after you use the {{site.data.keyword.slportal_full}} to successfully uninstall the Zerto service.
{: tsSymptoms}

Manually remove the VRAs from the vCenter console.
{: tsResolve}

1. Log in to the vCenter console.
2. Click **Hosts and Clusters** and locate the virtual machines with names that start with **Z-VRA-**. For example, **Z-VRA-host0-vcs40dal.vcs.icvs.org**.
3. Right-click the **Z-VRA-** virtual machine and click **Delete from Disk**.
