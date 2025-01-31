---

copyright:

  years:  2022, 2025

lastupdated: "2025-01-31"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Supported VMware Cloud Foundation architecture models
{: #vpc-vcf-architectures}

VMware Cloud Foundation™ supports two base architecture models - consolidated and standard. You can select a model according to the requirements of your deployment and organization. If you plan to deploy a small-scale environment and extend it according to your needs, or if you work on an SDDC proof-of-concept you can select a consolidated architecture. For a production environment, you can implement a standard architecture according to VMware's production best practices.

## Consolidated architecture model
{: #vpc-vcf-architectures-consolidated}

In this model, the management and customer workloads run on a shared management domain. The environment is managed from a single VMware vCenter Server®. VMware vSphere® resource pools provide isolation between management and customer workloads. Resource pools must be properly configured as the compute capacity is shared between the management and compute workloads.

![VMware Cloud Foundation consolidated architecture model on {{site.data.keyword.vpc_short}}](../../images/vcf-vpc-v2-arch-cons.svg "VMware Cloud Foundation consolidated architecture model on {{site.data.keyword.vpc_short}}."){: caption="VMware Cloud Foundation consolidated architecture model on {{site.data.keyword.vpc_short}}" caption-side="bottom"}

Initial cluster in the management domain hosts includes VMware vCenter Server, NSX manager cluster, SDDC manager, and NSX edge nodes. VMware NSX edge™ deployment is a separate workflow, but in {{site.data.keyword.vpc_short}}, it is done through the Terraform and Ansible automation as part of the initial provisioning.

## Standard architecture model
{: #vpc-vcf-architectures-standard}

With the standard architecture model, the management workloads run on a dedicated management domain and the customer workloads are deployed in separate virtual infrastructure (VI) workload domains. Each VI workload domain is managed by a separate vCenter Server instance, which provides for scalability and allows for autonomous licensing and lifecycle management.

Currently, the offering does not support the standard architecture model.


## Related links
{: #vpc-vcf-architectures-links}

* [VMware Cloud Foundation architecture](https://docs.vmware.com/en/VMware-Cloud-Foundation/5.1/vcf-getting-started/GUID-C6AF75AE-569C-49F8-A15E-E9A6EF9549DA.html){: external}
