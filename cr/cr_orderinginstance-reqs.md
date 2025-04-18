---

copyright:

  years:  2022, 2025

lastupdated: "2025-02-12"

keywords: cyber recovery, cyber recovery requirements, requirements cyber recovery, cyber recovery order instance, order cyber recovery, cyber recovery instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Requirements for {{site.data.keyword.cr}}
{: #cr_orderinginstance_reqs}

{{site.data.keyword.cr}} helps you with data protection, cyberthreats, cyberattacks, and ransomware. The instance includes the Veeam Backup and Replication 12.3 add-on service and a Linux® hardened repository (LHR). An edge gateway is required and you can provide your own or order one of the following edges:

* Juniper® vSRX
* FortiGate® Virtual Appliance
* FortiGate Security Appliance

You can order add-on services. For more information, see [Services for {{site.data.keyword.cloud_notm}} {{site.data.keyword.cr}}](/docs/vmwaresolutions?topic=vmwaresolutions-cr_planning#cr_planning-addon-services).

Price calculations are automatically generated when you access the {{site.data.keyword.cr}} instance order page. Default selections include the Data Center SP Professional license for NSX-T™, the Dual Intel® Xeon® Platinum 8260 processor / 48 cores, 2.4 GHz CPU model, 768 GB RAM, and NFS storage for both the consolidated and workload clusters.

Complete the following tasks:

* If you are ordering an instance for the first time, complete the tasks in the **Before you begin** section on the ordering page. For more information, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).
* Review the information in [Signing up for required accounts](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts).
* Review the information in [{{site.data.keyword.cr}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-cr_overview).
* Review the domain name format. The domain name is used to generate the username and server names for the instance.

| Name        | Value format |
|:------------|:------------ |
| Domain name | `<root_domain>` (Microsoft® Active Directory™ domain name) |
| vCenter Server login username | `<user_id>@<root_domain>` (Microsoft Active Directory user) or `administrator@vsphere.local` |
| vCenter Server (with embedded PSC) FQDN | `<instance_name>-vc.<root_domain>`. The maximum length is 50 characters. Any hyphens (-) are removed from the instance name. |
| Single Sign-On (SSO) site name | `<root_domain>` |
| Fully qualified ESXi server name | `<host_prefix><n>.<root_domain>`, where `n` is the sequence of the VMware vSphere® ESXi™ server. The maximum length is 50 characters. |
| NetBIOS name | First string of `<root_domain>`. The maximum length is 15 characters. |
{: caption="Value format for instance and domain names" caption-side="bottom"}

After the instance is provisioned, do not modify any values that are set during the instance order. Otherwise, the instance might become unusable.
{: attention}
