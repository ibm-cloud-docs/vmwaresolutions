---

copyright:

  years:  2020, 2023

lastupdated: "2023-04-19"

keywords: vmware regulated workloads, vmware regulated workloads order instance, order vmware regulated workloads, vmware regulated workloads instances

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Requirements for VMware Regulated Workloads
{: #vrw-orderinginstance-req}

The VMware® Regulated Workloads offering includes a secure-by-default architecture that follows the {{site.data.keyword.IBM}} unique policy controls framework. It provides continuous compliance monitoring and the highest level of data encryption (FIPS 140-2 Level 4).

Price calculations are automatically generated when you access the VMware Regulated Workloads instance order page. Default selections include the Data Center SP Professional license for NSX-T™, the Dual Intel® Xeon® Platinum 8260 processor / 48 cores, 2.4 GHz CPU model, 768 GB RAM, the vSAN™ Advanced license for both workload and consolidated clusters, and four 3.8 TB SSD vSAN capacity disks for workload clusters.

Ensure that you complete the following tasks:
* If you are ordering an instance for the first time, complete the tasks in the **Before you begin** section on the ordering page. For more information, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).
* Review the information in [Requirements for the IBM Cloud account](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).
* Review the information in [VMware Regulated Workloads overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-overview).
* Review the domain name format. The domain name is used to generate the username and server names of the instance.

| Name        | Value format |
|:------------|:------------ |
| Domain name | `<root_domain>` (Microsoft® Active Directory™ domain name) |  
| vCenter Server login username | `<user_id>@<root_domain>` (Microsoft® Active Directory user) or `administrator@vsphere.local` |
| vCenter Server (with embedded PSC) FQDN | `<instance_name>-vc.<root_domain>`. The maximum length is 50 characters. Any hyphen (-) characters from the instance name are removed. |
| Single Sign-On (SSO) site name | `<root_domain>` |
| Fully qualified ESXi server name | `<host_prefix><n>.<root_domain>`, where `n` is the sequence of the VMware vSphere® ESXi™ server. The maximum length is 50 characters. |
| NetBIOS name | First string of `<root_domain>`. The maximum length is 15 characters. |
{: caption="Table 1. Value format for instance and domain names" caption-side="bottom"}

After the instance is provisioned, do not modify any value that is set during instance order. Otherwise, the instance might become unusable.
{: important}

## Related links
{: #vrw-orderinginstance-reqs-related}

* [Signing up for an {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts#signing_required_accounts-cloud)
* [VMware Regulated Workloads reference architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-archi-overview)
