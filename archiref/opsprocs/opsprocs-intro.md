---

copyright:

  years:  2016, 2020

lastupdated: "2020-06-02"

subcollection: vmwaresolutions


---

{:external: target="_blank" .external}

# Operational procedures overview
{: #opsprocs-intro-overview}

This document provides a view of day 2 operations that need to carried out by the customer after your vCenter Server instance has been provisioned. {{site.data.keyword.vmwaresolutions_full}} is a deployment service that automatically deploys VMware’s Software-Defined Data Center software on to the {{site.data.keyword.cloud_notm}}. Many of the following day 0 and day 1 tasks are completed by the deployment automation:

* Day 0:
  * Requirements
  * Architecture
  * Design
* Day 1:
  * Installation
  * Setup
  * Configuration. For more information, see [Configuration tasks](/docs/vmwaresolutions?topic=vmwaresolutions-opsprocs-configure).

Day 2 operations typically consist of the following high level tasks:

* Compliance. For more information, see [Compliance](/docs/vmwaresolutions?topic=vmwaresolutions-opsprocs-compliance).
* Proactive and reactive maintenance. For more information, see [Proactive tasks](/docs/vmwaresolutions?topic=vmwaresolutions-opsprocs-proactive) and [Troubleshooting](/docs/vmwaresolutions?topic=vmwaresolutions-opsprocs-trouble).

For more information on day 2 responsibilities, see [Responsibilities for Day 2 operations](/docs/vmwaresolutions?topic=vmwaresolutions-opsprocs-responsibilities).

## Operational procedures introduction
{: #opsprocs-intro-proc}

Many IT organizations document their operational procedures in a runbook. A runbook is a set of standardized documents, references and procedures that explain common recurring IT tasks. IT staff refer to the runbook for an optimal way to get their work done. Runbooks improve organizational efficiency through standardization and they assist with onboarding employees more effectively. There are typically two types of runbook:

1. General documentation used to capture procedures, guides, and tasks. They tend to be general in nature, and refer to existing documentation provided by vendors.
2. Specialized documentation written for the enterprise. This documentation is specific to a system, an application, or suite of applications and is not covered by vendors documentation. When you document your specialized documentation, the following structure is recommended:

 * Overview - An overview of the service with sections that describes:
    * What is the service and why is the service needed by the enterprise?
    * Who are the primary contacts for the service?
    * How to report issues with the service.
 * Build - This section is focused on the development teams and the main software components of the service and how the service is constructed. Information on software products, locations of OVAs, distribution media, or the location of the source code. The required steps for packaging or distributing the release. It includes any required instructions for how a new developer gets started.
 * Deployment - This section is focused on the operations team and how to deploy the software. It includes details of the hardware and virtualized infrastructure and how to build the virtual machines (VMs) including: vCPU, RAM and disk requirements, OS version and configuration, what middleware or packages to install.
 * Procedures - Step-by-step instructions for common tasks like: add, change and delete, common issues and their solutions, troubleshooting advice.
 * Troubleshooting - A list of common alerts from the monitoring system including step-by-step tasks for these alerts, as well as generic guidance on troubleshooting the service.
 * Disaster recovery plans and procedures - Details on how to recover the service at another location due to a disaster at the primary location.
 * Service level agreement - The agreed service parameters such as operational level agreements, key point indicators, availability goals, recovery point objectives, recovery time objective.

Most IT organizations have multiple runbooks that act as their reference manuals. This series of documentation is designed for use as a general runbook for your organization consuming vCenter Server instances. While every runbook's content is specific to the organization's needs, the methodology of runbook creation is fairly standard using two stages:

1. The first stage is to decide which procedures need to be documented, and when listed, document each one with sufficient detail.
2. The second stage is ongoing and consists of maintaining, updating, and correcting these procedures, adding new procedures and retiring procedures that are no longer needed.

{{site.data.keyword.vmwaresolutions_short}} enables you to use you team's existing skills, toolsets, and runbooks you have on-premises to manage your instances in {{site.data.keyword.cloud_notm}}.

The following list contains the most common procedures, guides, and tasks:
* Configuration tasks - These tasks are common activities that systems administrators need to perform to tailor the environment to suit the enterprise's needs and respond to service requests such as: add new VMs and increase capacity. These tasks are grouped into the following structure:
 * Generic guidance
 * VM procedures
 * vCenter procedures
 * vSphere ESXi host procedures
 * Storage procedures
 * Network procedures
* Alarms - vSphere includes an events and alarms subsystem, which tracks events occurring in the vSphere environment and makes this information available in vCenter. This section describes this subsystem and how to enable and use the alarms in your enterprise.
* Proactive daily checks - These checks enable system administrators to keep the environment healthy. When carried out daily, it should prevent many common issues that are related to capacity and performance from impacting your workloads.
* Troubleshooting - Even when carrying out proactive daily checks, issues occur that impact your workloads. Therefore, you need to fix the underlying issue as quickly as possible. These troubleshooting guides and some common troubleshooting scenarios assist system administrators with identifying and fixing these issues quickly.
* Compliance - The compliance guide provides some insights on maintaining compliance of the environment against a regulatory compliance regime or industry best practice. The focus of this guide is on the VMware hardening guide, which is a number of documented lists of best practice for a VMware environment.

Many of the previous tasks are automated in Operations Management on {{site.data.keyword.cloud_notm}}, and for those tasks that are not, these tools make the manual processes easier for your systems administrators. It is imperative that you have the core components of the VMware environment monitored, in Operations Management on {{site.data.keyword.cloud_notm}}, this is achieved as follows:

## Operations management on IBM Cloud
{: #opsprocs-intro-ops-mgmt}

You can have enterprise tools in place that you can use to monitor and manage your vCenter Server instance. Table 1 describes the core components of the vCenter Server environment, why they need to be monitored and how they are monitored by using Operations Management on {{site.data.keyword.cloud_notm}}. For more information, see the reference architecture documentation.

| Component     | Why | Monitored by |
| ------------- | --- | ------------ |
| vCenter | vCenter is the infrastructure management component that manages the vSphere hosts and manages virtualized constructs such as clusters. vSAN is monitored through vCenter. vSphere networking such as distributed switches and port groups are monitored through vCenter. | vRealize Operations Manager (vROps) and the VMware SDDC Health Management Pack. vRealize Log Insights (vRLI) collects the log data from vCenter and the Content Pack for vSphere adds specific understanding to the logs and in turn sends alerts to vROPs. |
| vSphere Hosts | vSphere hosts provide the virtualized CPU, RAM, and network to the compute VMs. | vROps via vCenter. vRLI collects the log data. |
| vSAN | vSAN provides a datastore by consolidating storage in the hosts for use by the VMs. Issues that affect capacity and performance have an effect on the applications running on these VMs. | vROps and the Management Pack for vSAN provides additional dashboards to aid with the monitoring of vSAN. vCenter vSAN Health Checks are collected via vROps. vRLI collects the log data from vCenter. |
| NSX | NSX provides the virtualized network components that are used by the compute VMs, any failures of the network can impact the applications running on these VMs. | vROps and the vROps Management Pack for VMware NSX provides visibility into the network topology. vRLI collects the log data from the NSX components such as Controllers, ESG, and logical switches. vRealize Network Insight (vRNI) provides in-depth troubleshooting of network issues. |
{: caption="Table 1. vCenter Server environment core components" caption-side="top"}

In addition to monitoring, Operations Management on {{site.data.keyword.cloud_notm}}, helps with configuration, compliance, and many of the proactive tasks detailed in this documentation.

**Next topic**: [Responsibilities for Day 2 operations](/docs/vmwaresolutions?topic=vmwaresolutions-opsprocs-responsibilities)

## Related links
{: #opsprocs-intro-links}

* [About vSphere Monitoring and Performance](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.monitoring.doc/GUID-A8B06BE0-E5FC-435C-B12F-A31618B21E2C.html){:external}
* [VMware security hardening guides](https://www.vmware.com/uk/security/hardening-guides.html){:external}
* [Operations management introduction](/docs/vmwaresolutions?topic=vmwaresolutions-opsmgmt-intro)
* [Considerations about changing vCenter Server artifacts](/docs/vmwaresolutions?topic=vmwaresolutions-vcenter_chg_impact#vcenter_chg_impact)
