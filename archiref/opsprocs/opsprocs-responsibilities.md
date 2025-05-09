---

copyright:

  years:  2016, 2025

lastupdated: "2025-02-10"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Responsibilities for Day 2 operations
{: #opsprocs-responsibilities}

Review the two key principles for Day 2 operations.

* Your {{site.data.keyword.vcf-auto}} instance is not actively monitored by {{site.data.keyword.IBM}}. After deployment, use existing tools, use a managed service. Examples of a managed service include IBM Integrated Managed Infrastructure, a third-party managed service, or implement a self-managed monitoring solution as described in [Operations management introduction](/docs/vmwaresolutions?topic=vmwaresolutions-opsmgmt-intro).
* IBM Support does not enter the VMware® management layer under normal operations without a client–written support ticket. You must raise a support ticket to engage support from IBM. For more information, see [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support). You must actively manage the ticket to ensure that you provide the requested information that is required by IBM in a timely manner. For more information, see [Managing your support cases](/docs/account?topic=account-managing-support-cases&interface=ui) and [Escalating support cases](/docs/account?topic=account-managing-support-cases&interface=ui#escalation).

For more information about IBM and customer responsibilities that concern compliance, see [Customer versus IBM responsibility for {{site.data.keyword.vcf-auto-short}}](/docs/vmwaresolutions?topic=vmwaresolutions-vc_compl_info#vc_compl_info-responsibility).

Day 2 responsibilities include the following items:

* Service Support - IBM provides support for {{site.data.keyword.vmwaresolutions_full}} issues that you report. You must raise support tickets as directed in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).
* Service Provisioning - Provision and resize your {{site.data.keyword.vcf-auto-short}} instances on demand, by using the [VMware Solutions console](https://cloud.ibm.com/vmware).
* IBM Management component updates - For instances deployed in (or upgraded to) V2.5 or later, updates and patches for the IBM management components are applied automatically, as needed.
* Incident and Problem Management - You are responsible for incident and problem management of your {{site.data.keyword.vcf-auto-short}} instances after deployment. You must have tools and processes to detect incidents, record the issues, classify their severity, escalate, and return the failing component to service.
* Capacity Management - You are responsible for capacity management of your {{site.data.keyword.vcf-auto-short}} instances, adding or removing additional capacity to match business demands. For more information, see [Adding ESXi servers to {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservers) and [Adding clusters for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingclusters).
* Data Recovery - You are responsible for all backup and restoration of the components in the {{site.data.keyword.vcf-auto-short}} instance, including VMware vCenter® Server Appliance, NSX Manager, virtual appliances, virtual machines, and content libraries. Use optional services, such as [Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview) or implement your own enterprise systems.
* Bare metal server firmware - You are responsible for updating out-of-date firmware. For more information, see [FAQ: Bare metal servers](/docs/virtual-servers?topic=virtual-servers-bm-faq).
* VMware software updates - Updates to the VMware software, such as fixes and service packs, are necessary to maintain the health and availability of your {{site.data.keyword.vcf-auto-short}} instance. Review these updates and apply them periodically. For more information, see [VMware update manager introduction](/docs/vmwaresolutions?topic=vmwaresolutions-vum-intro).
* VMware software upgrades - You must upgrade existing {{site.data.keyword.vcf-auto-short}} instances to continue to benefit from the automation. For more information, see [Upgrading {{site.data.keyword.vcf-auto-short}} vSphere software from vSphere 6.5 or 6.7 to 7.0](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vsphere_70_upgrade).
* IBM provides notification of scheduled maintenance at [Planned maintenance](/status/maintenance){: external}.
* Security - You are responsible for ensuring adequate protection of your deployed content including, but not limited to the following items: VM operating system patching, application security fixes, data encryption, access controls, roles, and permissions that are granted to users, security of the virtual network components, which includes distributive or gateway firewall rules. You are responsible for the detection, classification, and remediation of all security events within your deployed {{site.data.keyword.vcf-auto-short}} instances and the associated VMs, operating systems, applications, data, or content. In addition, you are responsible for any compliance or certification program in which you are required to participate. For more information about the automated deployment of services to assist with security responsibilities, see [Add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-getting-started#getting-started-add-on-services).
* Encryption - You are responsible for determining encryption requirements and implementing these requirements. Use encryption options such as [Entrust DataControl](/docs/vmwaresolutions?topic=vmwaresolutions-entrust-dc_considerations), and vSphere or vSAN encryption with [KMIP for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_standalone_considerations).
* High availability - You are responsible to design and deploy your workload in a way that achieves your high availability requirements, which also includes anti-affinity rules and load balancing.
* The [Cloud status page](/status){: external} is the central place to find unplanned incidents, planned maintenance, announcements, and security bulletin notifications about key events that affect the {{site.data.keyword.cloud_notm}} platform, infrastructure, and major services.

## Related links
{: #opsprocs-responsibilities-links}

* [Managing system notifications](/docs/vmwaresolutions?topic=vmwaresolutions-notifications)
* [Compliance information for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_compl_info)
* [Using the Support Center](/docs/account?topic=account-using-avatar)
* [FAQ for getting support](/docs/account?topic=account-get-supportfaq)
* [Cloud Event Management documentation](https://www.ibm.com/docs/en/cem)
