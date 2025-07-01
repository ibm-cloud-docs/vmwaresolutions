---

copyright:

  years: 2025

lastupdated: "2025-07-01"

keywords: HA firmware solutions, DR for vmware solutions, vmware solutions recovery time objective, vmware solutions recovery point objective

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Understanding high availability and disaster recovery for VMware Solutions
{: #ha-dr-draft}

[High availability](#x2284708){: term} (HA) is the ability for a service to remain operational and accessible in the presence of unexpected failures. [Disaster recovery](#x2113280){: term} is the process of recovering the service instance to a working state.
{: shortdesc}

VMware Solutions is a highly available global service designed for availability during a regional outage. However, the VMware Solutions service is only used to provision VMware resources into your cloud account. It is your responsibility to design and manage your VMware resources to meet your high availability and disaster recovery goals.

## High availability architecture
{: #ha-architecture}

### High availability features
{: #ha-features}

When appropriately configured, you can build highly available solutions by using VMware software. Some of these features are available out of the box with the {{site.data.keyword.vcf-auto}} offering, while you must configure other features.

* vSphere HA can be used to recover virtual machines (VMs) from host to host if the host fails.
* vMotion and Distributed Resource Scheduler (DRS) can be used to proactively move VMs from host to host.
* vSAN stretched cluster when combined with appropriate network configuration can be used together with vSphere HA to recover VMs from zone to zone if the zone fails.
* Clusters or instances that are deployed in multiple zones can host applications and databases that implemented their own synchronous or asynchronous replication.
* Clusters or instances that are deployed in multiple regions can host applications and databases that implemented their own asynchronous replication.
* Load balancing solutions or software can be used to route traffic to appropriate regions and zones.

## Disaster recovery architecture
{: #disaster-recovery-intro}

### Disaster recovery features
{: #dr-features}

When appropriately configured, you can build disaster recovery solutions by using VMware software. You must configure these features.

* Replication software such as VMware Cloud Director Availability (VCDA), VMware Live Recovery by using vSphere replication, Veeam CDP, and Zerto Replication can be used to replicate your workloads from region to region.
* Incremental backup software such as Veeam Backup and Replication and Zerto Journaling can be used, optionally in combination with IBM Cloud Object Storage (COS) to create local or remote backups of your workloads.

### Planning for disaster recovery
{: #features-for-disaster-recovery}

Establish a detailed DR plan and practice it regularly. You might have different plans for different scenarios. Consider the following cases to include:

* Loss of one network access point.
* Failure of a single host.
* Failure of an entire zone.
* Failure of an entire region.
* Data corruption within your virtual workloads or management plane.
* Malware and ransomware within your virtual workloads or management plane.

## Your responsibilities for HA and DR
{: #feature-responsibilities}

It is your responsibility to continuously test your plan for HA and DR.

Interruptions in network connectivity and hardware failures might occur. It is your responsibility to make sure that you have appropriately implemented and tested the high availability and disaster recovery solutions that you intend to use.
{: note}

For more information about responsibility ownership between you and {{site.data.keyword.vmwaresolutions_full}}, see [Understanding your responsibilities when you use VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-understand-responsib).

## Recovery time objective (RTO) and recovery point objective (RPO)
{: #rto-rpo-features}

The RTO and RPO of your high availability and disaster recovery solution depends on your chosen solution.

The only way to achieve zero RPO is to use application and database-level synchronous replication, or to use a storage subsystem implementing synchronous replication (for example, NFS storage within the same zone, vSAN storage within a single zone, or stretched vSAN storage between two zones). All other solutions that integrate with the VMware hypervisor APIs (for example, Veeam CDP and Zerto replication) will have small but nonzero RPO.

The lowest RTO is obtained with active-active application deployments on multiple hosts or zones, with a load balancer or global load balancer (GLB) configured in front of them. Solutions that rely on restart of a VM (for example, vSphere HA) or on declaration of a disaster followed by restart of an entire workload (for example, Veeam CDP or Zerto replication) will have longer RTO.

## Change management
{: #change-management}

Most of the changes to your VMware environment and workloads will take place within the VMware software rather than within the {{site.data.keyword.cloud_notm}} console. You must configure appropriate access control and audit logging for your VMware management plane. Grant your users the minimum privileges required for their work. Consider implementing a change management process or solution for your VMware management plane. Also, consider creating manual backups of VMware vCenter Server® and VMware NSX® before you upgrade them to new versions.

## How {{site.data.keyword.IBM_notm}} maintains services
{: #ibm-service-maintenance}

{{site.data.keyword.IBM}} maintains the VMware Solutions service in a highly available fashion, replicating our data and control plane across multiple {{site.data.keyword.cloud_notm}} regions for resilience. All upgrades to the VMware Solution service follow {{site.data.keyword.IBM_notm}} service best practices, including recovery plans and rollback processes. Regular maintenance might cause short interruptions, mitigated by [client availability retry logic](/docs/resiliency?topic=resiliency-high-availability-design#client-retry-logic-for-ha). {{site.data.keyword.IBM_notm}} reverts updates at the first sign of a defect.

Changes that impact customer workloads are detailed in {{site.data.keyword.cloud_notm}} notifications. For more information about planned maintenance, announcements, and release notes that impact this service, see [Monitoring notifications and status](/docs/account?topic=account-viewing-cloud-status).
