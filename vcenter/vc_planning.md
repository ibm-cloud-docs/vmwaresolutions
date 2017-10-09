---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-06"

---

# Requirements and planning for vCenter Server instances

Review the following requirements before you order your VMware vCenter Server instances. Plan your instance based on the IBM Cloud data center location, your workload capacity requirements, and additional service requirements.

## IBM Bluemix Infrastructure (SoftLayer) account requirements

The Bluemix Infrastructure (SoftLayer) account that you are using must meet certain requirements. For more information, see [Bluemix Infrastructure (SoftLayer) account requirements](../vmonic/slaccountrequirement.html).

## Data centers availability

The vCenter Server deployment has strict requirements on the physical infrastructure. Therefore, you can deploy instances only in IBM® Cloud data centers that meet the requirements. The following data centers are available for vCenter Server deployment:

Table 1. Available data centers for vCenter Server instances

| Data center | Location |
|:-----|:----------------|
| AMS03 | Amsterdam |
| CHE01 | Chennai |
| DAL09 | Dallas |
| DAL10 | Dallas |
| DAL12 | Dallas |
| DAL13 | Dallas |
| FRA02 | Frankfurt |
| HKG02 | Hong Kong |
| LON02 | London |
| LON04 | London |
| LON06 | London |
| MEL01 | Melbourne |
| MEX01 | Queretaro |
| MIL01 | Milan |
| MON01 | Montreal |
| OSL01 | Oslo |
| PAR01 | Paris |
| SAO01 | Sao Paulo |
| SEO01 | Seoul |
| SJC03 | San Jose |
| SJC04 | San Jose |
| SNG01 | Singapore |
| SYD01 | Sydney |
| SYD04 | Sydney |
| TOK02 | Tokyo |
| TOR01 | Toronto |
| WDC04 | Washington, DC |
| WDC06 | Washington, DC |
| WDC07 | Washington, DC |

A large subset of IBM Cloud data centers offer pre-built, standardized **Small**, **Medium**, and **Large** bare metal server options. Depending on availability and inventory supply, IBM Cloud data centers might display a status indicator in the {{site.data.keyword.vmwaresolutions_full}} console to help you plan your deployments.

Table 2. Status indicators for data centers when ordering vCenter Server instances

| Status | Status Details |
|:------------------------------|:--------------------------------------------------|
| Coming Soon                   | The data center is not available currently. |
| Temporarily Out of Inventory  | The data center has no availability at this time. |
| Limited Inventory             | The data center has limited availability and the order might not be completed. |

## Services for vCenter Server instances

When you order a vCenter Server instance, you can also order additional services.

### Veeam on IBM Cloud

This service integrates seamlessly with your VMware environment to help you manage the backup and restore of all the virtual machines (VMs) in your environment, including the backup and restore of the management components. It can help provide a recovery point objective (RPO) of less than 15 minutes upon configuration for your data.

This service is selected by default and is configured to back up the management VMs immediately after the deployment of your instance. If you do not order this service, there is no backup of the management VMs. For more information, see [Managing Veeam on IBM Cloud](../services/managingveeam.html).

### F5 on IBM Cloud

This service optimizes performance and ensures availability and security for applications with the F5 BIG-IP Virtual Edition (VE). For more information, see [Managing F5 on IBM Cloud](../services/managing_f5.html).

### Fortinet on IBM Cloud

This service deploys an HA-pair of FortiGate Security Appliance (FSA) 300 series devices that can provide firewall, routing, NAT, and VPN services to protect the public network connection to your environment. For more information, see [Managing Fortinet on IBM Cloud](../services/managingfsa.html).

### Zerto on IBM Cloud

This service provides replication and disaster recovery capabilities to help protect your workloads. For more information, see [Managing Zerto on IBM Cloud](../services/managingzertodr.html).

## Capacity considerations

For capacity information and considerations, see the _Bill of
Materials_ document in the [Architecture Center](https://www.ibm.com/devops/method/content/architecture/virtVCenterServerPlatform){:new_window}.

## Related links

* [vCenter Server overview](vc_vcenterserveroverview.html)
* [Ordering vCenter Server instances](vc_orderinginstance.html)
* [Expanding and contracting capacity for vCenter Server instances](vc_addingremovingservers.html)
* [Ordering and removing services for vCenter Server instances](vc_addingremovingservices.html)
