---

copyright:

  years:  2022

lastupdated: "2022-11-18"

keywords: Cyber Recovery, Cyber Recovery offering, Cyber Recovery instance, data protection, cyber threat, ransomware, Cyber resilience

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Cyber Recovery overview
{: #cr_overview}

The most critical aspects of your organization are your overall computer systems and networks, and your data. You must protect everything from different types of situations and threats.

Cyber resilience is the ability to avert, handle, and recover from various incidents that can damage or compromise your data or systems. You must be able to continue to provide your operations to your users.

For more information, see [What is cyber resilience](https://www.ibm.com/topics/cyber-resilience){: external}.

Cyber Recovery can help protect you from cyberthreats, cyberattacks, and ransomware. A Cyber Recovery instance includes Veeam® 11, a Linux® hardened repository (LHR), and an edge gateway.

For the gateway, you can bring your own gateway appliance or choose from the following options:

* Edge services cluster with Juniper® vSRX
* Edge services cluster with FortiGate® Virtual Appliance
* FortiGate Security Appliance

VMware vSphere® v7.0u3 and VMware NSX-T™ v3.2 are automatically installed.

The offering is for a single-zone VMware instance only.

When you install Cyber Recovery, the add-on service Veeam 11 and the add-on service that you choose as your firewall appliance are automatically included services. When you edit Veeam to configure it, the Linux hardened repository is already chosen and is a required selection. You cannot deselect it.

## Related links
{: #cr_overview-related-links}

* [Planning for Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_planning)
* [Requirements for Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance_reqs)
