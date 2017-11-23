---

copyright:

  years:  2016, 2017

lastupdated: "2017-11-21"

---

# Requirements and planning for Cloud Foundation instances

Review the following requirements before you order your VMware Cloud Foundation instances. Plan your instance based on the {{site.data.keyword.CloudDataCent}} location, your workload capacity requirements, and additional service requirements.

## IBM Cloud account requirements

The {{site.data.keyword.cloud_notm}} account that you are using must meet certain requirements. For more information, see [{{site.data.keyword.cloud_notm}} account requirements](../vmonic/slaccountrequirement.html).

## Data centers availability

The Cloud Foundation deployment has strict requirements on the physical infrastructure. Therefore, you can deploy instances only in {{site.data.keyword.CloudDataCents_notm}} that meet the requirements. The following data centers are available for Cloud Foundation deployment:

Table 1. Available data centers and {{site.data.keyword.baremetal_long}} configurations for Cloud Foundation instances

| Data center | Location | Server configurations |
|:-----|:----------------| :---------------------------|
| AMS03 | Amsterdam | User customized |
| CHE01 | Chennai | User customized |
| DAL09 | Dallas | User customized |
| DAL10 | Dallas | Small, Large, User customized |
| DAL12 | Dallas | User customized |
| DAL13 | Dallas | User customized |
| FRA02 | Frankfurt | Small, Large, User customized |
| HKG02 | Hong Kong | User customized |
| LON02 | London | User customized |
| LON04 | London | User customized |
| LON06 | London | Small, Large, User customized |
| MEL01 | Melbourne | User customized |
| MEX01 | Queretaro | User customized |
| MIL01 | Milan | User customized |
| MON01 | Montreal | User customized |
| OSL01 | Oslo | User customized |
| PAR01 | Paris | User customized |
| SAO01 | Sao Paulo | User customized |
| SEO01 | Seoul | User customized |
| SJC03 | San Jose | Small, Large, User customized |
| SJC04 | San Jose | User customized |
| SNG01 | Singapore | User customized |
| SYD01 | Sydney | User customized |
| SYD04 | Sydney | User customized |
| TOK02 | Tokyo | User customized |
| TOR01 | Toronto | Small, Large, User customized |
| WDC04 | Washington, DC | Small, Large, User customized |
| WDC06 | Washington, DC | User customized |
| WDC07 | Washington, DC | User customized |

Depending on availability and inventory supply, {{site.data.keyword.CloudDataCents_notm}} might display a status indicator in the {{site.data.keyword.vmwaresolutions_full}} console to help you plan your deployments.

Table 2. Status indicators for data centers when ordering Cloud Foundation instances

| Status | Status Details |
|:------------------------------|:--------------------------------------------------|
| Coming Soon                   | The data center is not available currently. |
| Temporarily Out of Inventory  | The data center has no availability at this time. |
| Limited Inventory             | The data center has limited availability and the order might not be completed. |

## Services for Cloud Foundation instances

When you order a Cloud Foundation instance, you can also order additional services.

### Veeam on IBM Cloud

This service integrates seamlessly with your VMware environment to help you manage the backup and restore of all the virtual machines (VMs) in your environment, including the backup and restore of the management components. It can help provide a recovery point objective (RPO) of less than 15 minutes upon configuration for your data.

This service is selected by default and is configured to back up the management VMs immediately after the deployment of your instance. If you do not order this service, there is no backup of the management VMs. For more information, see [Managing Veeam on {{site.data.keyword.cloud_notm}}](../services/managingveeam.html).

### F5 on IBM Cloud

This service optimizes performance and ensures availability and security for applications with the F5 BIG-IP Virtual Edition (VE). For more information, see [Managing F5 on {{site.data.keyword.cloud_notm}}](../services/managing_f5.html).

### FortiGate Security Appliance on IBM Cloud

This service deploys an HA-pair of FortiGate Security Appliance (FSA) 300 series devices that can provide firewall, routing, NAT, and VPN services to protect the public network connection to your environment. For more information, see [Managing FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](../services/managingfsa.html).

### FortiGate Virtual Appliance on IBM Cloud

This service deploys an HA-pair of FortiGate Virtual Appliances that can allow you to reduce risk by implementing critical security controls within your virtual infrastructure. For more information, see [Managing FortiGate Virtual Appliance on {{site.data.keyword.cloud_notm}}](../services/managingfortinetvm.html).

### Managed Services from IMI

These services enable IBM Integrated Managed Infrastructure (IMI) to deliver dynamic remote management services for a broad range of cloud infrastructures. For more information, see [Requesting managed services from IMI](../services/managing_imi.html).

### Zerto on IBM Cloud

This service provides replication and disaster recovery capabilities to help protect your workloads. For more information, see [Managing Zerto on {{site.data.keyword.cloud_notm}}](../services/managingzertodr.html).

## Capacity considerations

For capacity information and considerations, see the _Bill of Materials_ document in the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtCloudFoundationPlatform){:new_window}.

## Related links

* [Cloud Foundation overview](sd_cloudfoundationoverview.html)
* [Ordering Cloud Foundation instances](sd_orderinginstance.html)
* [Expanding and contracting capacity for Cloud Foundation instances](sd_addingremovingservers.html)
* [Ordering and removing services for Cloud Foundation instances](sd_addingremovingservices.html)
