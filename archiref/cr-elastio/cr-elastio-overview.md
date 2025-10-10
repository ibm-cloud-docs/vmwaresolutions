---

copyright:

  years:  2025

lastupdated: "2025-10-09"

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Cyber resilience with Elastio
{: #cr-elastio-overview}

{{site.data.keyword.vcf-auto}} instances can host the Elastio™ Stack and integrate with the Elastio Ransomware Recovery Assurance Platform. By combining the {{site.data.keyword.cloud}} robust infrastructure with the Veeam® data protection solutions and the Elastio advanced resilience capabilities, organizations can build a secure, scalable, and compliant hybrid cloud environment for their requirements.

## {{site.data.keyword.vcf}} on IBM Cloud
{: #cr-elastio-overview-vcf}

{{site.data.keyword.vcf}} ({{site.data.keyword.vcf-short}}) offers a fully integrated, enterprise-grade platform that delivers the complete VMware software-defined data center (SDDC) stack. This platform includes VMware vSphere®, VMware vSAN™, VMware NSX®, and VMware Aria® Suite components, providing a consistent and secure environment for running traditional and containerized workloads.

The following items are the key features of the offering:
* Provision a fully operational {{site.data.keyword.vcf-short}} environment in under 12 hours by using IBM® automated deployment tools.
* Provision optional add-on services such as Veeam Backup and Replication.
* Choose between Classic and Virtual Private Cloud (VPC) deployments.
* Deploy {{site.data.keyword.vcf-short}} environments across {{site.data.keyword.cloud_notm}} global data centers, which can ensure proximity to users and compliance with regional regulations.
* Use {{site.data.keyword.cloud_notm}} security features, including Hyper Protect Crypto Services and FIPS 140-2 Level 4 key management to protect sensitive data.
* Integrate with {{site.data.keyword.cloud_notm}} Services such as Security and Compliance Center Workload Protection and {{site.data.keyword.cloud_notm}} Logs.

## Data protection with Veeam Backup and Replication
{: #cr-elastio-overview-veeam}

Veeam Backup and Replication provides comprehensive data protection and disaster recovery solutions for VMware environments. Fully compatible with {{site.data.keyword.cloud_notm}} for VMware Solutions, Veeam ensures that your workloads are safeguarded against data loss and downtime.

Integration highlights include the following features:
* Veeam integrates directly with vSphere environments on {{site.data.keyword.cloud_notm}}, offering the same functions as on-premises deployments.
* Use features like Instant VM Recovery, SureBackup, and constant data protection to meet stringent RTO and RPO requirements.
* Scale your backup infrastructure in tandem with your {{site.data.keyword.vcf-short}} environment to ensure consistent performance and protection.
* Extend data protection across hybrid and multicloud environments, which facilitates seamless workload mobility and disaster recovery.

## Enhancing resilience with Elastio
{: #cr-elastio-overview-elastio}

Elastio Ransomware Recovery Assurance Platform offers advanced protection for {{site.data.keyword.vcf-short}} environments on {{site.data.keyword.cloud_notm}} when integrated with Veeam Backup and Replication. This integration provides proactive ransomware detection, which ensures data integrity and facilitates rapid recovery.

The following items are the key features of the integration:
* Elastio seamlessly integrates with Veeam without requiring agents, which preserves system performance and simplifies deployment.
* The platform inspects Veeam backup data at scale to identify ransomware encryptions as soon as the data is backed up, enabling swift response to threats.
* Elastio scans for malware binary files, helping prevent ransomware attacks before they impact business operations.
* By tracking changes across backups, Elastio detects sophisticated attacks that evolve over time, providing a robust defense against evolving ransomware threats.
* Older or previously unscanned backups can be examined to ensure that they are ransomware-free before recovery, adding an extra layer of security.
* Developed from reverse-engineering over 2,300 ransomware families, Elastio achieves 99.99% accuracy in detecting unknown ransomware encryptions.
* Organizations can confidently restore critical business processes with clean, ransomware-free data, reducing downtime and operational impact.
* Continuous scanning of every backup allows for immediate threat identification, which ensures that data remains uncompromised.
* Elastio provides meaningful alerts to focus on genuine threats, reducing false positives and enhancing response efficiency.
* The platform fits effortlessly into existing backup processes without operational disruption, maintaining business continuity.

By combining Elastio's advanced ransomware detection capabilities with Veeam's robust backup solutions, organizations can enhance their data protection strategies, which ensures resilience against sophisticated cyberthreats.

## Getting started
{: #cr-elastio-overview-get-started}

1.	**Provision a {{site.data.keyword.vcf-short}} instance on {{site.data.keyword.cloud_notm}}** - Use the {{site.data.keyword.cloud_notm}} portal to deploy your {{site.data.keyword.vcf-short}} environment, selecting the appropriate configuration for your workloads.
2.	**Integrate Veeam Backup and Replication** - Configure Veeam within your {{site.data.keyword.vcf-short}} instance to establish backup and recovery processes.
3.	**Deploy Elastio** - Set up Elastio to integrate with Veeam Backup and Replication to provide continuous data protection and enhance your resilience against data threats.
4.	**Monitor and manage** - Use {{site.data.keyword.cloud_notm}}'s monitoring tools alongside Veeam and Elastio dashboards to oversee your environment's health and compliance.

## Cyber resilience with Elastio overview
{: #cr-elastio-overview-overview}

The following diagram shows the high-level architecture overview:

![Overview of Elastio on VMware Solutions](../../images/cr-elastio-overview.svg "Overview diagram"){: caption="Overview of Elastio on VMware Solutions" caption-side="bottom"}

When you purchase the the Elastio Ransomware Recovery Assurance Platform service, a resilient Elastio Cloud Connector is instantiated in the Elastio managed AWS Account. The details of this Cloud Connector are sent to you so you can configure your Elastio Stack.

* The Elastio Stack is delivered as a lightweight Open Virtual Appliance (OVA), designed for scale-out scanning within VMware infrastructures. This architecture is simple to deploy, requiring minimal management, and operates efficiently with low resource usage. Using the OVA an initial Worker VM is deployed hosting the Controller and a Scan Worker. More Worker nodes with Scan Workers can be added for scaling purposes.
* The Controller interfaces with the API of the Veeam Backup and Replication server to get the servers backup inventory and to issue mount requests. After the requested backup is mounted, it can be scanned by a Scan Worker.
* All ransomware and data integrity scans are performed entirely within the {{site.data.keyword.vcf-short}} instance, which ensures that sensitive data never leaves your environment, maintaining full security and compliance.
* Elastio supports automatic updates to its ransomware detection models and scanning engines, which ensures continuous protection against the latest threats without manual intervention.
* The Elastio stack operates without requiring agents on workload virtual machines (VMs), which preserves system performance, reduces complexity, and delivers comprehensive backup scanning and validation.
* Job status and scan results are sent to your Elastio Ransomware Recovery Assurance Platform console, offering detailed insights into data integrity, ransomware resilience, and recovery readiness. This centralized reporting enables organizations to proactively monitor and enhance their security posture.

## Cyber resilience with Elastio architecture
{: #cr-elastio-overview-architecture}

The following diagram shows more details of the {{site.data.keyword.vcf-short}} instance architecture with Veeam and Elastio:

![Architecture of Elastio on VMware Solutions](../../images/cr-elastio-architecture.svg "Architecture diagram"){: caption="Architecture of Elastio on VMware Solutions" caption-side="bottom"}

* The {{site.data.keyword.vcf-short}} instance hosts your workload VMs hosted on the NSX overlay segments. For more information about {{site.data.keyword.vcf-short}}, see [Overview of VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-solution_overview).
* The {{site.data.keyword.vcf-short}} instance can use VMware vSAN or NFS data stores. For more information, see [Physical storage design](/docs/vmwaresolutions?topic=vmwaresolutions-design_physicalinfrastructure#design_physicalinfrastructure-storage-design).
* Veeam Backup and Recovery can be automatically installed on a VM, VSI, or bare metal server. For more information, see [Veeam on IBM Cloud overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview).
* Optionally, but recommended, The {{site.data.keyword.vcf-short}} instance can include a gateway cluster to host one of the following appliances to protect the {{site.data.keyword.vcf-short}} instance networks:
    * Juniper® vSRX appliances. For more information, see [Ordering a Juniper vSRX](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-ordering).
    * FortiGate® Security Appliance. For more information, see [Create FortiGate Security Appliance 10 Gbps](/netsec/firewalls/multi-vlan/provision#about).
    * FortiGate Virtual Appliance. For more information, see [Ordering a FortiGate Virtual Appliance](/docs/vmwaresolutions?topic=vmwaresolutions-fortinetvm_ordering).
    * Bring your own gateway appliance.
* The {{site.data.keyword.vcf-short}} instance can include any of the optional add-on services, such as Caveonix RiskForesight™ or VMware Aria® Operations™. For more information, see [Add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-getting-started#getting-started-add-on-services).
* Optionally, you can use encryption with Hyper Protect Crypto Services and KMIP™ for VMware. For more information, see [KMIP for VMware overview](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_standalone_considerations).

To create the pattern described in the diagram, follow the procedure to order a [{{site.data.keyword.vcf-short}} for Classic - Automated instance](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure). 

After your {{site.data.keyword.vcf-short}} instance is provisioned:

1. Configure your firewalls by using the vendor’s documentation as a guide and the following information:

   * [IBM Cloud IP ranges](/docs/infrastructure-hub?topic=infrastructure-hub-ibm-cloud-ip-ranges)
   * [Ports that are used for deployment and Day 2 operations](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-deploy-day2ops)
   * [Ports used by VMware components](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-vmwareuses)
   * [Ports for services](/docs/vmwaresolutions?topic=vmwaresolutions-vmwaresol_ports-services)

2.  Order a Cloud Object Storage instance and configure a bucket.
3.	Configure Veeam to use the object storage bucket as a backup repository.
4.	Configure Veeam backup jobs to back up your VMs.
5.	Register for the Elastio Ransomware Recovery Assurance Platform service and install the Elastio Stack following their documentation.
6.	Configure Elastio to interface with Veeam.

While this pattern describes Veeam Backup and Recovery with a {{site.data.keyword.vcf-short}} for Classic - Automated instance, the instance can be {{site.data.keyword.vcf-short}} for Classic - Flexible or {{site.data.keyword.vcf-short}} on VPC. The backup appliances that are supported by Elastio include:
* Cohesity
* NetBackup
* Commvault
* Rubrik

Veeam and Elastio can also be installed on an existing {{site.data.keyword.vcf-short}} instance.

## Summary
{: #cr-elastio-overview-summary}

Use {{site.data.keyword.cloud_notm}}'s global infrastructure to extend your on-premises VMware environment into the cloud, enabling workload mobility, disaster recovery, and capacity expansion without significant rearchitecture. Use {{site.data.keyword.cloud_notm}}'s security certifications and Elastio's policy-driven management to meet industry-specific compliance requirements and maintain data governance standards.

## Related links
{: #cr-elastio-overview-related}

* [Elastio](https://elastio.com){: external}
* [Architecture pattern for using Transit Gateway with a vCenter Server with NSX-T instance](/docs/vmwaresolutions?topic=vmwaresolutions-arch-pattern-nsx-t-transit-gw)
* [Architecture pattern for using IPsec over Direct Link with a vCenter Server with NSX-T instance](/docs/vmwaresolutions?topic=vmwaresolutions-arch-pattern-nsx-t-direct-link-ipsec)
* [Architecture pattern for using Direct Link with NSX-T edge cluster in colocation](/docs/vmwaresolutions?topic=vmwaresolutions-arch-pattern-direct-link-edge)
* [Architecture pattern for using Direct Link with NSX-T and EVPN](/docs/vmwaresolutions?topic=vmwaresolutions-arch-pattern-direct-link-evpn)
* [Virtual Private Network (VPN)](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/administration-guide/virtual-private-network-vpn.html){: external}
