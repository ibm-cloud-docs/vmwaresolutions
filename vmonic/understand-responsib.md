---

copyright:

  years: 2019, 2025

lastupdated: "2025-10-09"

subcollection: vmwaresolutions

keywords: vmware solutions responsibilities, customer responsibilities, management responsibilities

---

{{site.data.keyword.attribute-definition-list}}

# Understanding your responsibilities when you use VMware Solutions
{: #understand-responsib}

Learn about the management responsibilities and terms and conditions that you have when you use {{site.data.keyword.vmwaresolutions_full}}. For a high-level view of the service types in {{site.data.keyword.cloud_notm}} and the breakdown of responsibilities between the customer and {{site.data.keyword.IBM}} for each type, see [Shared responsibilities for {{site.data.keyword.cloud_notm}} offerings](/docs/overview?topic=overview-shared-responsibilities).
{: shortdesc}

Review the following information for the specific responsibilities for you and for {{site.data.keyword.IBM_notm}} when you use VMware Solutions. For the overall terms of use, see [{{site.data.keyword.cloud_notm}} terms and notices](/docs/overview?topic=overview-terms).

## Incident and operations management
{: #understand-responsib-incident-and-ops}

Incident and operations management includes tasks such as monitoring, event management, high availability, problem determination, recovery, and full state backup and recovery. The following table describes the responsibilities that are related to incident and operations management:

| Task | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Availability | Offer VMware® infrastructure in multiple locations, including [multizone regions (MZR)](#x9774820){: term}. | Plan and provision VMware infrastructure according to your availability requirements. |
| Infrastructure monitoring and notification | Forward to the client all network intrusion notifications detected. Maintain shared cloud infrastructure, including network and storage. | Implement monitoring system and integrate with virtualization management. Determine the impact of each notification reported. Engage {{site.data.keyword.IBM_notm}} Support as required. |
| Workload monitoring |  | Monitor and respond to OS or software failures. |
| Infrastructure management | | Implement monitoring and management system that is integrated with virtualization management. |
| Incident management | Unplanned incidents with customer impact are communicated through the CIE process. | Impacted customers can obtain a report about the incident upon request. |
{: row-headers}
{: caption="Responsibilities for incident and operations for VMware Solutions" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that a customer or {{site.data.keyword.IBM_notm}} might be responsible for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}
{: #understand-responsib-incident-and-ops-dedicated-table}

## Change management
{: #understand-responsib-change-management}

Change management includes tasks such as deployment, configuration, upgrades, patching, configuration changes, and deletion. The following table describes the responsibilities that are related to change management:

| Task | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Scaling | Scale your VMware infrastructure as requested. | Choose the capacity for your VMware Solutions instances. |
| Upgrading and patching | {{site.data.keyword.IBM_notm}} does not have access to components to perform upgrades and patching. | It's your responsibility to apply updates to VMware components (VMware vSphere ESXi™, VMware vCenter Server®, VMware NSX-T™, VMware vSAN™, and Microsoft Active Directory™) and any additional add-on components (VMware Aria, Caveonix RiskForesight, and Veeam Backup and Replication). You can use [VMware Update Manager](/docs/vmwaresolutions?topic=vmwaresolutions-opsmgmt-vum) to assist with the updates. |
{: row-headers}
{: caption="Responsibilities for change management for VMware Solutions" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that a customer or {{site.data.keyword.IBM_notm}} might be responsible for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}
{: #understand-responsib-change-management-dedicated-table}

## Identity and access management
{: #understand-responsib-iam-responsibilities}

Identity and access management includes tasks such as authentication, authorization, access control policies, and approving, granting, and revoking access. The following table describes the responsibilities that are related to identity and access management:

| Task | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Identity and access | Provide the function to restrict access to resources through the {{site.data.keyword.cloud_notm}} console and REST APIs. Provide default access to the provisioned VMware environment. | Manage access to resources through IAM. Manage access to the VMware environment. |
{: row-headers}
{: caption="Responsibilities for identity and access management for VMware Solutions" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that a customer or {{site.data.keyword.IBM_notm}} might be responsible for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}
{: #understand-responsib-iam-responsibilities-table}

## Security and regulation compliance
{: #understand-responsib-security-compliance}

Security and regulation compliance includes tasks such as security controls implementation and compliance certification. The following table describes the responsibilities that are related to security and regulation compliance:

| Task | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Encryption | Provide integration with Key Protect and Hyper Protect Crypto Services through KMIP service as an option for implementing data at-rest encryption. | Configure and manage encryption for both data at rest and in transit, as needed. |
{: row-headers}
{: caption="Responsibilities for security and regulation compliance for VMware Solutions" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that a customer or {{site.data.keyword.IBM_notm}} might be responsible for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}
{: #understand-responsib-security-compliance-dedicated-table}

## Disaster recovery
{: #understand-responsib-disaster-recovery}

Disaster recovery includes tasks, such as:
* Providing dependencies on disaster recovery sites
* Provision disaster recovery environments
* Data and configuration backup
* Replicating data and configuration to the disaster recovery environment
* Fail over on disaster events

The following table describes the responsibilities that are related to disaster recovery:

| Task | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|:---- |:----------------------------------------------- |:--------------------- |
| Business continuity and Disaster Recovery (DR) | Provide automated provision and integration for third-party services, such as Veeam and Zerto. | Provision third-party solutions such as Veeam and Zerto, or other solutions of your choice, along with the VMware Solutions instance. Configure these solutions to meet your business continuity and DR requirements for your workload. |
{: row-headers}
{: caption="Responsibilities for disaster recovery for VMware Solutions" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that a customer or {{site.data.keyword.IBM_notm}} might be responsible for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}
{: #understand-responsib-disaster-recovery-dedicated-table}

## Preserving critical configuration
{: #understand-responsib-preserve-config}

Configuration changes can impact the ability to use the VMware Solutions console to view and manage instances. Preserving certain configurations and settings is critical for the VMware Solutions automation to continue to function properly.

You must manage the VMware Solutions components that are created in your {{site.data.keyword.cloud_notm}} account only in the VMware Solutions console. For more information, see:
* [{{site.data.keyword.vcf-auto}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview)
* [Expanding and contracting capacity for Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservers)

If you change your credentials, for example passwords, {{site.data.keyword.IBM_notm}} Support might no longer be able to help you recover lost or forgotten credentials, or to troubleshoot any problems in your environment. For more information, see [Client responsibilities](/docs/vmwaresolutions?topic=vmwaresolutions-vc_compl_info#vc_compl_info-client-responsibilities).

Changes to VMware ESXi server names or configurations might have a negative impact on managing your instance. For more information, see:
* [Can I change the ESXi server names and IP addresses?](/docs/vmwaresolutions?topic=vmwaresolutions-faq_esxi#faq_esxi-change-name-ip)
* [Considerations about changing vCenter Server artifacts](/docs/vmwaresolutions?topic=vmwaresolutions-vcenter_chg_impact)

In {{site.data.keyword.vmwaresolutions_short}}, every primary instance deploys an Active Directory domain controller. To understand the limitations on changes that you can make and recommendations on integration in your environment, see:
* [VMware Solutions infrastructure domain](/docs/vmwaresolutions?topic=vmwaresolutions-adds-infra-domain)
* [VMware Solutions workload domain](/docs/vmwaresolutions?topic=vmwaresolutions-adds-wkld-domain)

## Related links
{: #understand-responsib-related}

* [Compliance information for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_compl_info)
* [Post-deployment considerations for your VMware instance](/docs/vmwaresolutions?topic=vmwaresolutions-solution_considerations)
* [Day 2 operational procedures guide](/docs/vmwaresolutions?topic=vmwaresolutions-opsprocs-intro-overview)
* [Operations management guide](/docs/vmwaresolutions?topic=vmwaresolutions-opsmgmt-intro)
* [VMware Update Manager guide](/docs/vmwaresolutions?topic=vmwaresolutions-vum-intro)
