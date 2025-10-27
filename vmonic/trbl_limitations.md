---

copyright:

  years:  2016, 2025

lastupdated: "2025-10-24"

keywords: troubleshooting, Windows automatic installation, Windows updates

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Why Windows updates are not getting installed automatically on the Active Directory Domain Services server?
{: #trbl_limitations}
{: troubleshoot}

{{site.data.content.vms-deprecated-note}}

The updates from Windows® do not get installed automatically on the Microsoft® Active Directory™ (AD) Domain Services server.
{: tsSymptoms}

It is a known limitation.
{: tsCauses}

The Active Directory Domain Services server is automatically set up to download the updates only. It does not install these updates or restart automatically. You must install the updates manually and restart at a scheduled time that avoids any interruptions of the ongoing AD server configuration and other backup jobs. To apply Windows® updates, install the updates manually.
{: tsResolve}

If you want to upgrade your Active Directory server OS version, open an {{site.data.keyword.IBM}} Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support#trbl_support-procedure). Before you proceed with a new OS installation, you must back up all domain controllers and {{site.data.keyword.vcf-auto}} instances.
{: note}
