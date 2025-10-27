---

copyright:

  years:  2020, 2025

lastupdated: "2025-10-24"

keywords: troubleshooting, bypassing signing and acceptance, bypassing verification issue

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Why do I see a bypassing verification message when I add a host?
{: #trbl_add_host_bypass}
{: troubleshoot}

{{site.data.content.vms-deprecated-note}}

When you add a host, you see the following event in VMware vCenter Server®:
{: tsSymptoms}

`Attempting to install an image profile bypassing signing and acceptance level verification.`

This event occurs because VMware® is installing the high availability agent by intended bypassing acceptance level verification.
{: tsCauses}

This message does not indicate a problem and can be ignored.
{: tsResolve}
