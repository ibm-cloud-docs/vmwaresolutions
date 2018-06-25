---

copyright:

  years:  2016, 2018

lastupdated: "2018-06-19"

---
# Solution overview

The {{site.data.keyword.vmwaresolutions_full}} offerings enable you to extend your existing VMware virtualized datacenter into the {{site.data.keyword.cloud}} or to house cloud native applications.

The solution supports use cases such as capacity expansion into the cloud (and contraction when not needed), migration to the cloud, disaster recovery to the cloud, and backup into the cloud. With the solution, you can create a dedicated cloud environment for development, testing, training, lab, or production.

This document details the design of the {{site.data.keyword.vmwaresolutions_short}} offerings, including VMware Cloud Foundation and VMware vCenter Server, whose target workloads require high levels of availability and scalability.

This design serves as a baseline architecture that provides the foundation for other internal or vendor specific components to be added for specific use cases.

Figure 1. Overview of VMware on {{site.data.keyword.cloud}}
![Overview of VMware on {{site.data.keyword.cloud_notm}}](solution_overview.svg "The solution virtualizes compute, network, and optionally storage resources to be consumed by VMs where you can run your applications.")

## Key benefits

VMware Cloud Foundation and vCenter Server on {{site.data.keyword.cloud_notm}} provide the fundamental building blocks, which includes VMware vSphere, vCenter Server, NSX, and shared storage options including vSAN, that are needed to flexibly architect a VMware software-defined data center solution that best fits your workloads. By applying advanced automation and single-tenant bare metal infrastructure, you can quickly deploy the entire VMware environment to the {{site.data.keyword.cloud_notm}} and access your virtual environment with your favorite tools in a matter of hours. At this point, you can access and manage the IBM­-hosted environment via the native VMware clients, Command Line Interface (CLI), existing scripts, or other familiar vSphere API-compatible tools.

Post-deployment, you can add ESXi host nodes and manage the preconfigured backup and patching for some management components. {{site.data.keyword.cloud_notm}} Professional Services and Managed Services are also available to help accelerate your journey to the cloud with offerings such as migration, implementation, and on-boarding services.

The VMware on {{site.data.keyword.cloud_notm}} offerings bring the following benefits:

* **Accelerating delivery** of IT projects for developers and lines of business by reducing the time it takes for procurement, architecture, implementation, and deployment of resources from weeks or even months, to hours.
* **Enhancing security** with dedicated bare metal servers in a hosted private cloud, including the encryption of data at rest.
* **Enabling consistent management and governance** of the deployed hybrid cloud by providing full administrative access to virtualization management, thus preserving your existing VMware tooling, scripts, and investments in training.
* **Leverage VMware expertise at global scale** with IBM Professional and Managed Services spanning 30+ IBM Cloud data centers worldwide.
