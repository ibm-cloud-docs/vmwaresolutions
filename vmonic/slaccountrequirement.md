---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-27"

---

# Requirements for the IBM Cloud infrastructure account

To use {{site.data.keyword.vmwaresolutions_full}} to order instances, you must have an {{site.data.keyword.cloud_notm}} infrastructure (SoftLayer) account. The cost of the components that are ordered in your instances is billed to that {{site.data.keyword.cloud_notm}} account.

**Note:** The {{site.data.keyword.cloud_notm}} infrastructure (SoftLayer) account was previously known as the IBM SoftLayer account.

## Permissions for the IBM Cloud infrastructure account

The {{site.data.keyword.cloud_notm}} infrastructure account that you are using must have certain permissions to be able to order the components in your instances and perform operations on your behalf. The permission requirements are applicable to all types of instances and services you are ordering from the {{site.data.keyword.vmwaresolutions_short}} console.

Authorized users can verify and update the permissions for an {{site.data.keyword.cloud_notm}} infrastructure account in the {{site.data.keyword.slportal}}. For more information, see _Editing a user's customer portal permissions_ in [Managing a user profile](../../../customer-portal/cpmanuserprof.html){:new_window}.

Table 1. Required permissions for the {{site.data.keyword.cloud_notm}} infrastructure account

| Permission         | Details                                 |
|:------------------ |:--------------------------------------- |
| Add Server | This permission is required for the following operations: to order {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} on which VMware ESXi runs and to provision hourly virtual servers that are used for instance configuration, maintenance, and support operations. |
| Cancel Server | This permission is required to release and reclaim {{site.data.keyword.baremetal_short}} on which VMware ESXi runs. If you delete your instance, the ordered components are automatically released in the correct dependency sequence. |
| View Virtual Server Details | This permission is required to retrieve the server provisioning details, which are required for order validation and automated configuration. |
| Add Storage | This permission is required to order backup storage and shared storage for the instance. |
| Manage Storage | This permission is required to manage backup storage and shared storage for the instance. |
| Hardware Firewall | This permission is required to edit or view firewall log files and settings for the Fortinet on {{site.data.keyword.cloud_notm}} service, if it is installed on your instance. |
| Add Compute with Public Network Port | This permission is required to order hardware and VSIs (Virtual Server Instances) with public network ports. |
| Add IP Addresses | This permission is required to order portable private subnet ranges on your behalf, which is needed to manage the virtual machines that run in a vSphere cluster. When more services are added to your instance, the portable private IP addresses are assigned to VMware ESXi servers to isolate and allocate bandwidth. |
| Add Tickets | This permission is required to open service tickets on your behalf. Tickets might be created for the following operations: to initiate restore operations and to initiate problem resolution processes automatically when issues are found. |
| Edit Tickets | This permission is required to edit the service tickets that are created on your behalf. |
| View Tickets | This permission is required to monitor the service tickets that are related to the components in your instance for {{site.data.keyword.cloud_notm}} infrastructure provisioning delays and problems. |
| View Hardware Details | This permission is required to retrieve the hardware details, which are needed for order validation and automated configuration. |
| View Licenses | This permission is required to retrieve and validate the licenses that are used by your instance. |
| View Passwords | This permission is required to be able to administer the ordered VSIs. |
| Manage Server Monitoring | This permission is not required to place an order but it is required to retrieve and validate the monitoring status of the {{site.data.keyword.cloud_notm}} {{site.data.keyword.baremetal_short}} on which the VMware ESXi servers are running in your instance. |

## VLAN spanning for classic (non-VRF) accounts

If you are using a classic (non-VRF) {{site.data.keyword.cloud_notm}} infrastructure account, VLAN spanning must be enabled. If VLAN spanning is not enabled for classic accounts, the various components of the VMware virtualization environment might not be able to communicate with each other. To enable VLAN spanning in your {{site.data.keyword.cloud_notm}} infrastructure account, see [Enable or Disable VLAN Spanning](../../../infrastructure/vlans/vlan-spanning.html){:new_window}.

### Related links

* [Requirements for Cloud Foundation instances](../sddc/sd_planning.html)
* [Requirements for vCenter Server instances](../vcenter/vc_planning.html)
* [User account and settings](useraccount.html)
