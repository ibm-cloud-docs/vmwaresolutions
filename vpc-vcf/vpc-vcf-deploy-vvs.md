---

copyright:

  years:  2023, 2025

lastupdated: "2025-10-21"

keywords: vmware cloud foundation, IBM Cloud, vpc

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Deploying VMware validated solutions
{: #vpc-vcf-deploy-vvs}



A VMware validated solution is a technically validated implementation that is built and tested by VMware and VMware partners to help you resolve common business use cases. VMware validated solutions are operational, cost-effective, performant, reliable, and secure.

Each solution contains a detailed design, implementation, and operational guidance. The following information provides a summary of the validated solutions on your {{site.data.keyword.vcf-vpc}} instance with some {{site.data.keyword.cloud}} specific design and installation considerations and notes.

If you are provisioning VMware Aria® Suite components with Lifecycle Manager, review the following changes for VMware Aria® Suite v8.18 and later.
{: important}

1. You must download all product support packs and their product and patch binary files from the [Broadcom Support Portal](https://support.broadcom.com/web/ecx){: external}. To do that, contact {{site.data.keyword.cloud_notm}} Support and provide the list of binary files that you need with their version details. For more information about product and version support, see [VMware Product Interoperability Matrix](https://interopmatrix.broadcom.com/Interoperability){: external}.

2. Before you deploy the Aria Suite Lifecycle components to Lifecycle Manager, upload the binary files provided by {{site.data.keyword.cloud_notm}} Support.

3. In VMware Aria Suite Lifecycle, map the binary files to each VMware Aria Suite product. For more information, see [Configure product binaries](https://techdocs.broadcom.com/us/en/vmware-cis/aria/aria-suite-lifecycle/8-18/vmware-aria-suite-lifecycle-installation-upgrade-and-management-8-18/configuring-vmware-aria-suite-lifecycle/configure-settings/working-with-product-support/configure-product-binaries.html){: external}.

## Identity and Access Management for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-deploy-vvs-iam}

The [Identity and Access Management for VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/identity-and-access-management-for-vmware-cloud-foundation.html){: external} validated solution provides detailed design, implementation, configuration, and operation guidance on the use of Active Directory as an identity provider and authentication source, and on the use of role-based access control (RBAC) in {{site.data.keyword.vcf-vpc-short}} SDDC Manager™, VMware vCenter Server®, VMware ESXi™, and VMware NSX®.

This solution is intended for cloud architects and administrators who are familiar with VMware software and a role-based access control solution by using a central identity provider for {{site.data.keyword.vcf-vpc-short}}.

Solution-added products for this VMware validated solution include VMware Workspace ONE Access.

To deploy the Identity and Access Management for {{site.data.keyword.vcf-vpc-short}} validated solution in {{site.data.keyword.cloud_notm}}, follow the process in [Identity and Access Management for VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/identity-and-access-management-for-vmware-cloud-foundation.html){: external}.

Use VMware Aria® Suite Lifecycle Manager (formerly VMware vRealize® Suite Lifecycle Manager) to deploy this VMware validated solution. Aria Suite Lifecycle Manager is deployed as part of the automation.
{: important}

## Developer Ready Infrastructure for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-deploy-vvs-tanzu}

The [Developer Ready Infrastructure for VMware Cloud Foundation validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/developer-ready-infrastructure-for-vmware-cloud-foundation.html){: external} provides design, implementation, and operational guidance for a workload domain that runs vSphere with Tanzu workloads (TKG Runtime) in the Software-Defined Data Center (SDDC).

This solution is intended for cloud architects and administrators who are familiar with using VMware software to deploy and manage a workload domain that runs vSphere with Tanzu workloads in the SDDC.

The solution does not include any new solution-added products, but the Broadcom® documentation provides a fast and efficient path to automating the Developer Ready Infrastructure for {{site.data.keyword.vcf-vpc-short}} implementation.

To deploy the Developer Ready Infrastructure for {{site.data.keyword.vcf-vpc-short}} validated solution in {{site.data.keyword.cloud_notm}}, follow the process in [Developer Ready Infrastructure for VMware Cloud Foundation validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/developer-ready-infrastructure-for-vmware-cloud-foundation.html){: external}.

### Important notes
{: #vpc-vcf-deploy-vvs-tanzu-notes}

* Use Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager) to deploy this VMware validated solution. Aria Suite Lifecycle Manager is deployed as part of the automation.
* When you are deploying TKG Runtime in a {{site.data.keyword.vcf-vpc-short}} instance with {{site.data.keyword.cloud_notm}}, ensure that your edge cluster nodes appliance size is either **Large** or **Extra Large**. Currently, only the Active Standby edge cluster is supported in {{site.data.keyword.cloud_notm}}.
* To get the NSX edge cluster visible in compatible list under the SDDC Kubernetes deployment, before you deploy the TKG runtime, follow the steps in [Unable to get the NSX edge cluster visible in compatible list under the SDDC Kubernetes deployment](https://knowledge.broadcom.com/external/article?legacyId=83991){: external}.

## Intelligent Logging and Analytics for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-deploy-vvs-aria-operations-for-logs}

[The Intelligent Logging and Analytics for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/intelligent-logging-and-analytics-for-vmware-cloud-foundation.html){: external} provides information on the use of a log analysis tool that delivers highly scalable log management with intuitive and actionable dashboards, sophisticated analytics, and broad third-party extensibility. The solution provides deep operational visibility and fast troubleshooting for your {{site.data.keyword.vcf-vpc-short}} instance and workloads that are running on it.

Solution-added products for this VMware validated solutions include Aria Operations™ for Logs (formerly vRealize Log Insight). Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager) is deployed as part of the initial provisioning for your {{site.data.keyword.vcf-vpc-short}} instance, and you use this deployment method to deploy Intelligent Logging and Analytics for {{site.data.keyword.vcf-vpc-short}}.

To deploy the Intelligent Logging and Analytics for {{site.data.keyword.vcf-vpc-short}} validated solution in {{site.data.keyword.cloud_notm}}, follow the process in [Intelligent Logging and Analytics for {{site.data.keyword.vcf-vpc-short}}](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/intelligent-logging-and-analytics-for-vmware-cloud-foundation.html){: external}.

Use Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager) to deploy this VMware validated solution. Aria Suite Lifecycle Manager is deployed as part of the automation.
{: important}

## Intelligent Operations Management for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-deploy-vvs-aria-operations}

[The Intelligent Operations Management for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/intelligent-operations-management-for-vmware-cloud-foundation.html){: external} provides instructions for implementing a centralized monitoring and alerting platform to deliver proactive management of system failures through a single interface to review and act on events and alerts for your {{site.data.keyword.vcf-vpc-short}} instance and workloads that are running on it.

This solution is intended for cloud architects and administrators who are familiar with and want to use VMware software and to provide a centralized monitoring and alerting platform to deliver proactive management of system failures.

Solution-added products for this VMware validated solutions include Aria Operations Manager (formerly vRealize Operations Manager). Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager) is deployed as part of the initial provisioning of your {{site.data.keyword.vcf-vpc-short}} instance. You can use this method to deploy Intelligent Operations Management for {{site.data.keyword.vcf-vpc-short}}.

To deploy the Intelligent Operations Management for {{site.data.keyword.vcf-vpc-short}} validated solution in {{site.data.keyword.cloud_notm}}, follow the process in [Intelligent Logging and Analytics for {{site.data.keyword.vcf-vpc-short}}](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/intelligent-operations-management-for-vmware-cloud-foundation.html){: external}.

Use Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager) to deploy this VMware validated solution. Aria Suite Lifecycle Manager is deployed as part of the automation.
{: important}

## Private Cloud Automation for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-deploy-vvs-aria-automation}

[The Private Cloud Automation for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/private-cloud-automation-for-vmware-cloud-foundation.html){: external} provides information about the use of Aria Automation (formerly vRealize Automation) for cloud automation services with the {{site.data.keyword.vcf-vpc-short}} platform.

This solution is intended for cloud architects and administrators who are familiar with implementation of cloud automation services that can use {{site.data.keyword.vcf-vpc-short}}.

Solution-added products for this VMware validated solution include Aria Automation (formerly vRealize Automation).

To deploy the Private Cloud Automation for {{site.data.keyword.vcf-vpc-short}} validated solution in {{site.data.keyword.cloud_notm}}, see [Private Cloud Automation for {{site.data.keyword.vcf-vpc-short}}](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/private-cloud-automation-for-vmware-cloud-foundation.html){: external}.

### Important notes
{: #vpc-vcf-deploy-vvs-aria-automation-notes}

* Use Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager) to deploy this VMware validated solution. Aria Suite Lifecycle Manager is deployed as part of the automation.
* Before deployment, upgrade vRealize Operations Manager (now Aria Operations Manager) 8.10.0 to the most recent version and follow the procedure in [Private Cloud Automation for VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/private-cloud-automation-for-vmware-cloud-foundation.html){: external}.

## Advanced Load Balancing for {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-deploy-vvs-nsx-advanced-load-balancing}

Deploying VMware Avi Load Balancer (formerly NSX Advanced Load Balancer) Controllers require new {{site.data.keyword.vpc_full}} ({{site.data.keyword.vpc_short}}) bare metal server VLAN interfaces and changes to {{site.data.keyword.vpc_short}} default routing tables. This configuration task is manual and it requires understanding of the {{site.data.keyword.vpc_short}} and its routing concepts.
{: important}

[The Advanced Load Balancing for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/advanced-load-balancing-for-vmware-cloud-foundation.html){: external} provides information on the use of Avi Load Balancer as a load-balancing solution for {{site.data.keyword.vcf-vpc-short}}.

This solution is intended for cloud architects and administrators who want to use Avi Load Balancer for load balancing in {{site.data.keyword.vcf-vpc-short}}.

Solution-added products for VMware validated solutions include Avi Load Balancer.

To deploy the Advanced Load Balancing for {{site.data.keyword.vcf-vpc-short}} validated solution in {{site.data.keyword.cloud_notm}}, see [Advanced Load Balancing for {{site.data.keyword.vcf-vpc-short}}](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/advanced-load-balancing-for-vmware-cloud-foundation.html){: external}.

### Notes
{: #vpc-vcf-deploy-vvs-nsx-advanced-load-balancing-notes}

* Broadcom recommends that you use [VMware Avi Load Balancer](https://www.vmware.com/products/cloud-infrastructure/avi-load-balancer){: external} for load balancing.
* Avi Load Balancer is available as an add-on to the VMware Cloud Foundation license. For more information, see [VMware Avi Load Balancer add-on](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons#vmware-add-ons-nsx-avi).
* Avi Load Balancer Controllers implement the control plane for the Avi Load Balancer. For high availability, it is typically deployed as a 3-node cluster. In a {{site.data.keyword.vcf-vpc-short}}, Avi Load Balancer Controllers run as VMs in the management domain.
* Deploying the Controller cluster nodes on the {{site.data.keyword.vcf-vpc-short}} management network requires 4 new {{site.data.keyword.cloud_notm}} bare metal server VLAN interfaces on the management network as shown in the following table. To create VLAN interfaces, see [Managing network interfaces for bare metal servers on {{site.data.keyword.vpc_short}}](/docs/vpc?topic=vpc-managing-nic-for-bare-metal-servers).
* Avi Load Balancer Service Engine implements the data plane for the Avi Load Balancer. The Avi Load Balancer SEs perform load balancing for the configured applications. The Avi Load Balancer Controller cluster provides load-balancing services and it also manages the service engines that are deployed in the VI workload domain that is managed by the NSX-T Data Center.
* A new overlay management network is required to deploy the Service Engines in the VI workload domain's overlay with connectivity to the management domain's management network. This solution might require an {{site.data.keyword.vpc_short}} egress and ingress routes with a workload domain's Tier 0 Gateway HA VIP as the next hop.

The following table shows the VLAN interfaces for Avi Load Balancer Controllers.

| Interface name | Interface type | VLAN ID | Subnet | Allow float | NSX interface | Distributed port group name |
| ---------------|----------------|---------|--------|-------------|---------------|---------------------------- |
| `vlan-nic-avi-0` | `vlan` | 1611 | `vpc-mgmt-subnet` | `true` | Avi Load Balancer Controller 1 | `pg-mgmt` |
| `vlan-nic-avi-1` | `vlan` | 1611 | `vpc-mgmt-subnet` | `true` | Avi Load Balancer Controller 2 | `pg-mgmt` |
| `vlan-nic-avi-2` | `vlan` | 1611 | `vpc-mgmt-subnet` | `true` | Avi Load Balancer Controller 3 | `pg-mgmt` |
| `vlan-nic-avi-vip` | `vlan` | 1611 | `vpc-mgmt-subnet` | `true` | Avi Load Balancer Controller VIP | `pg-mgmt` |
{: caption="VLAN interfaces for Avi Load Balancer Controllers" caption-side="bottom"}

## Related links
{: #vpc-vcf-deploy-vvs-links}

* [The Developer Ready Infrastructure for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/developer-ready-infrastructure-for-vmware-cloud-foundation.html){: external}
* [The Intelligent Logging and Analytics for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/intelligent-logging-and-analytics-for-vmware-cloud-foundation.html){: external}
* [The Intelligent Operations Management for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/intelligent-operations-management-for-vmware-cloud-foundation.html){: external}
* [The Private Cloud Automation for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/private-cloud-automation-for-vmware-cloud-foundation.html){: external}
* [The Advanced Load Balancing for {{site.data.keyword.vcf-vpc-short}} validated solution](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vvs/1-0/advanced-load-balancing-for-vmware-cloud-foundation.html){: external}
