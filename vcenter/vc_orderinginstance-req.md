---

copyright:

  years:  2016, 2023

lastupdated: "2023-04-25"

keywords: vCenter Server order instance, order vCenter Server, order vCenter Server instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Requirements for vCenter Server instances
{: #vc_orderinginstance-req}

To deploy a flexible and customizable VMware® virtualized platform that best fits your workload needs, order a VMware vCenter Server® instance.

New deployments of vCenter Server multizone instances are not supported.
{: deprecated}

You can also add services, such as [Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr) for disaster recovery. For more information about the available services, see [Available services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices#vc_addingservices-available-services).

Price calculations are automatically generated when you access the VMware vCenter Server® instance order page. Default selections include the Data Center SP Professional license for NSX-T, the Dual Intel® Xeon® Platinum 8260 processor / 48 cores, 2.4 GHz CPU model, and 768 GB RAM.

Ensure that you complete the following tasks:
* If you are ordering an instance for the first time, complete the tasks in the **Before you begin** section on the ordering page. For more information, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).
* Review the information in [Planning for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_planning).
* Review the domain name format. The domain name is used to generate the username and server names of the instance.

The subdomain label is not used for VMware vSphere® 7.0 instances.
{: note}

| Name        | Value format |
|:------------|:------------ |
| Domain name | `<root_domain>` |  
| vCenter Server login username | `<user_id>@<root_domain>` (Microsoft® Active Directory™ user) or `administrator@vsphere.local` |
| vCenter Server (with embedded PSC) FQDN | `<instance_name>-vc.<root_domain>`. The maximum length is 50 characters. Any hyphen (-) characters from the instance name are removed. |
| Single Sign-On (SSO) site name | `<root_domain>` |
| Fully qualified VMware ESXi™ server name | `<host_prefix><n>.<root_domain>`, where `n` is the sequence of the ESXi server. The maximum length is 50 characters. |
| NetBIOS name | First string of `<root_domain>`. The maximum length is 15 characters. |
{: caption="Table 1. Value format for instance and domain names" caption-side="bottom"}

After the instance is provisioned, do not modify any values that are set during instance order. Otherwise, the instance might become unusable. For example, if public networking shuts down, if servers and Virtual Server Instances (VSIs) move behind a Vyatta mid-provision, or if the IBM CloudBuilder VSI stops or is deleted.
{: attention}
