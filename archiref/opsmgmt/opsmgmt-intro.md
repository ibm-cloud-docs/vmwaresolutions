---

copyright:

  years:  2016, 2020

lastupdated: "2020-03-31"

subcollection: vmwaresolutions


---

{:external: target="_blank" .external}

# Operations management introduction
{: #opsmgmt-intro}

This reference architecture is to guide and constrain the instantiations of {{site.data.keyword.vmwaresolutions_full}} architectures.

It also:
* Provides a common language for the various stakeholders.
* Provides consistency of technology implementation to solve problems.
* Supports the validation of solutions against proven reference architecture.
* Encourages adherence to common standards, specifications, and patterns.

The primary objective of this reference architecture is to document the Operations Management capability to provide monitoring and alerting of the {{site.data.keyword.vmwaresolutions_short}} environment that is deployed for the client. The tooling has been configured with best practice parameters and thresholds for use by the client’s operations team.

The design allows the client to complete the following tasks:
* Scale up or down as needed.
* Install their own enterprise monitoring tooling as mandated by their operational policies.
* Integrate the tooling into their own enterprise IT Service Management (ITSM) platform.

## Operations management
{: #opsmgmt-intro-opsmgmt}

{{site.data.keyword.vmwaresolutions_short}} is based on the following architectural layers:

![Architecture diagram](../../images/opsmgmt-architecture.svg "Architecture diagram"){: caption="Figure 1. Architectural layers" caption-side="bottom"}

* Physical Layer - The lowest layer of the architecture is the physical layer, which consists of the compute, network, and storage components leveraged from {{site.data.keyword.cloud_notm}}:
  * {{site.data.keyword.cloud_notm}} bare metal servers that run the management, edge, and compute workloads.
  * {{site.data.keyword.cloud_notm}} network that consist of VLANs, subnets, Frontend, and Backend Customer Routers (FCR/BCR).
  * vSAN storage, which is a consolidated datastore from the SSDs in the {{site.data.keyword.cloud_notm}} bare metal servers or Endurance storage.

* Virtual Infrastructure Layer - The virtual infrastructure layer runs on top of the physical layer components. The virtual infrastructure layer controls the access to the underlying physical infrastructure, and controls and allocates resources to the management and compute workloads. The management workloads consist of elements in the virtual infrastructure layer itself, together with elements in the cloud management, service management, business continuity, and security layers.

* Business Continuity Layer – This layer contains elements to support business continuity by providing data backup, restoration, and disaster recovery. For more information see the {{site.data.keyword.vmwaresolutions_short}} backup and restoration architecture, Veeam, IBM Spectrum Protect Plus, and Zerto disaster recovery reference architectures.

* Security Layer – This layer contains the elements to reduce risk and increase compliance. For more information see the Fortinet, F5, NSX, HyTrust, and Caveonix reference architectures.

This document is adding the following layer into the {{site.data.keyword.vmwaresolutions_short}} architecture:

* Operations Management Layer - The architecture of the operations management layer includes management components that provide support for the physical and virtual layers and optionally the compute workloads in real time. The operations management layer understands the {{site.data.keyword.vmwaresolutions_short}} topology: physical, virtual, compute, networking, and storage resources. The operations management layer consists primarily of monitoring and logging functions.

  Information is collected in the following forms:
    * Metrics - structured data such as performance and capacity
    * Logs - unstructured data such as system events

The Operations Management Layer consist of the following tools:

* vRealize Operations Manager (vROps) - vROps uses data collected from system resources (objects) to identify issues in the monitored system components and for many issues, suggests corrective actions to take to fix the issue. For more challenging issues, vROps offers rich analytical tools to; reveal hidden issues, investigate complex technical problems, identify trends, or drill down to gauge the health of a single object.
* vRealize Log Insight (vRLI) - vRLI provides intelligent log management for infrastructure and applications in any environment. This highly scalable log management solution provides intuitive, actionable dashboards, sophisticated analytics, and broad third-party extensibility across physical, virtual, and cloud environments.
* vRealize Network Insight (vRNI) - vRNI delivers intelligent operations for software-defined networking and security. It enables visibility across virtual and physical networks, provides operational views to manage and scale NSX deployments, and accelerates micro-segmentation planning and deployment.
* VMware Update Manager (VUM) - VUM enables centralized, automated patch and version management for VMware vSphere and offers; upgrading and patching of vSphere hosts, the installation and updating of third-party software on hosts, and the upgrading of VM hardware, VMware Tools, and virtual appliances.

For a full enterprise architecture, the following layers might be required but are outside of the {{site.data.keyword.vmwaresolutions_short}} architecture:

* Cloud Management Layer - The cloud management layer is the top layer of the cloud architecture. This layer requests resources and orchestrates the lower layers from a user interface or application programming interface (API). vRealize Automation enables cloud automation on the {{site.data.keyword.cloud_notm}}. For more information, see [IBM Cloud for VMware Solutions vRealize Automation 7.2 Solution Architecture](https://www.ibm.com/cloud/garage/files/IBM_Cloud_for_VMware_Solutions_VRA_Architecture_v1.pdf){:external}.

For more information about how this architecture can be extended with Chef integration, see [IBM Cloud	for VMware Solutions vRealize Automation 7.2 Chef Integration](https://www.ibm.com/cloud/garage/files/IBM_Cloud_for_VMware_Solutions_VRA_Chef_Integration_Architecture.pdf){:external}.

* Service Management Layer – This layer focuses on the full lifecycle of the IT environment and is typically implemented at the enterprise level combining inputs from all the silos of IT Operations and technologies. This layer has traditionally been, architected on IT Service Management (ITSM) frameworks such as; the IT Infrastructure Library (ITIL) and ISO/IEC 20000, which are a framework of best practices for delivering IT services through the processes and stages of the IT service lifecycle. At a product level, ITSM is typified by a centralized workflow management system for handling incidents, service requests, problems, changes, and knowledge connected to a configuration management database.

**Next topic**: [Operations management architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-opsmgmt-arch)
