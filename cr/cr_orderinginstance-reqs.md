---

copyright:

  years:  2022

lastupdated: "2022-12-14"

keywords: cyber recovery, cyber recovery requirements, requirements cyber recovery, cyber recovery order instance, order cyber recovery, cyber recovery instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Requirements for Cyber Recovery
{: #cr_orderinginstance_reqs}

The Cyber Recovery offering helps you with data protection, cyberthreats and attacks, ransomware, and more. The instance automatically includes the Veeam 11 add-on service and a Linux® hardened repository (LHR). An edge gateway is required and you can provide your own or order one of the following edges:

* Juniper® vSRX
* FortiGate® Virtual Appliance
* FortiGate Security Appliance

You can order add-on services. For more information, see [Services for {{site.data.keyword.cloud_notm}} Cyber Recovery](/docs/vmwaresolutions?topic=vmwaresolutions-cr_planning#cr_planning-addon-services).

Price calculations are automatically generated when you access the {{site.data.keyword.cloud_notm}} Cyber Recovery instance order page. Default selections include the Data Center SP Professional license for NSX-T™, the Dual Intel® Xeon® Platinum 8260 processor / 48 cores, 2.4 GHz CPU model, 768 GB RAM, and NFS storage for both the consolidated and workload clusters.

Ensure that you complete the following tasks:

* If you are ordering an instance for the first time, complete the tasks in the **Before you begin** section on the ordering page. For more information, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).

* Review the information in [Requirements for the {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).

* Review the information in [Cyber Recovery overview](/docs/vmwaresolutions?topic=vmwaresolutions-cr_overview).

* Review the domain name format. The domain name is used to generate the username and server names of the instance.

| Name        | Value format |
|:------------|:------------ |
| Domain name | `<root_domain>` (Microsoft® Active Directory™ domain name) |
| Cyber Recovery login username | `<user_id>@<root_domain>` (Microsoft Active Directory user) or `administrator@vsphere.local` |
| Cyber Recovery (with embedded PSC) FQDN | `<instance_name>-vc.<root_domain>`. The maximum length is 50 characters. |
| Single Sign-On (SSO) site name | `<root_domain>` |
| Fully qualified ESXi server name | `<host_prefix><n>.<root_domain>`, where `n` is the sequence of the VMware vSphere® ESXi™ server. The maximum length is 50 characters. |
| NetBIOS name | First string of `<root_domain>`. The maximum length is 15 characters. |
{: caption="Table 1. Value format for instance and domain names" caption-side="bottom"}

After the instance is provisioned, do not modify any value that is set during instance order. Otherwise, the instance might become unusable.
{: important}

## Related links
{: #cr_orderinginstance_reqs_related}

* [Signing up for an {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts#signing_required_accounts-cloud)
* [Service prerequisites](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance_serv_prereq)
