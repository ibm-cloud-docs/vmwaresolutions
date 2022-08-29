---

copyright:

  years:  2022

lastupdated: "2022-08-09"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Supported VMware Cloud Foundation architectures in {{site.data.keyword.vpc_short}}
{: #vpc-vcf-architectures}

VMware Cloud Foundation™ (VCF) supports two base architecture models - consolidated and standard. You can select a model according to the requirements of your deployment and organization. If you plan to deploy a small-scale environment and extend it according to customer adoption, or if you work on an SDDC proof-of-concept, you can select a consolidated architecture. You can implement a standard architecture for workload provisioning and mobility across VCF instances according to production best practices.

## Consolidated architecture model
{: #vpc-vcf-architectures-consolidated}

In this model, the management and customer workloads run together on a shared management domain. The environment is managed from a single VMware vCenter Server® and VMware vSphere® resource pools provide isolation between management and customer workloads. Resource pools must be properly configured as the domain is shared by the management and compute workloads.

![VCF consolidated architecture model on {{site.data.keyword.vpc_short}}](../../images/vcf-on-vpc-consolidated.svg "VCF consolidated architecture model on {{site.data.keyword.vpc_short}}."){: caption="Figure 1. VCF consolidated architecture model on {{site.data.keyword.vpc_short}}" caption-side="bottom"}

Initial cluster in the management domain hosts includes VMware vCenter Server, NSX-T manager cluster, SDDC manager, and NSX-T edge nodes. VMware NSX Edge™ deployment is a separate workflow, and when you deploy it in {{site.data.keyword.vpc_short}}, it must be done though SDDC manager post initial start process.

As you add extra hosts to a VCF system deployed on a consolidated architecture, you can migrate to the standard architecture by creating a virtual infrastructure (VI) workload domain and moving the customer workload virtual machines (VMs) from the compute resource pool to the newly created VI workload domain. After you move these VMs, you might need to update shares and reservations on the compute resource pool in the management domain.

## Standard architecture model
{: #vpc-vcf-architectures-standard}

With the standard architecture model, management workloads run on a dedicated management domain and customer workloads are deployed in separate (VI) workload domains. Each workload domain is managed by a separate vCenter Server instance, which provides for scalability and allows for autonomous licensing and lifecycle management. Workload domains can run only on the same {{site.data.keyword.vpc_short}} availability zone in the same {{site.data.keyword.cloud_notm}} multizone region. 

![VCF standard architecture model on {{site.data.keyword.vpc_short}}](../../images/vcf-on-vpc-standard.svg "VCF standard architecture model on {{site.data.keyword.vpc_short}}."){: caption="Figure 2. VCF standard architecture model on {{site.data.keyword.vpc_short}}" caption-side="bottom"}

For the first VI workload domain, SDDC manager deploys a vCenter Server and an NSX manager cluster in the management domain (in the management cluster). For each subsequent VI workload domain, SDDC manager deploys an extra vCenter Server. These VI workload domains can share the same NSX manager cluster or you can deploy a new NSX manager cluster.

Standard architecture is the recommended model because it aligns with the VMware best practice of separating management workloads from customer workloads. It provides better long-term flexibility and expansion options. This architecture model supports multiple VCF instances. Each instance runs at least two workload domains - management and virtual infrastructure.

Deploying VI workload domains with multiple availability zones is not supported in {{site.data.keyword.cloud_notm}}. To be able span workload domains across multiple availability zones, the network fabric must support stretched Layer 2 networks between the availability zones. Subnets in {{site.data.keyword.vpc_short}} are deployed for each zone and they do not span across zones.

In the VI workload domains, VMware vSphere clusters host the VMware NSX Edge clusters needed to service north-south traffic of your workloads. NSX Edge clusters cannot be deployed on clusters that are spanning Layer 3 networks in VCF deployments. NSX Edge appliances rely on a single VLAN-backed network for management and uplink connectivity, and as {{site.data.keyword.vpc_short}} subnets are deployed for each zone and they do not span across zones, this deployment scenario is not possible.

If you need an expansion to another zone or region, you can also deploy a new VCF instance.

## Related links
{: #vpc-vcf-architectures-links}

* [VMware Cloud Foundation architecture](https://docs.vmware.com/en/VMware-Cloud-Foundation/4.4/vcf-getting-started/GUID-C6AF75AE-569C-49F8-A15E-E9A6EF9549DA.html?hWord=N4IghgNiBcIMYHsB2BnBECWATMAXApliAL5A){: external}

