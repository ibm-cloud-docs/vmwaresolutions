---

copyright:

  years:  2016, 2017

lastupdated: "2017-05-30"

---

# SoftLayer account requirements

To order instances, you must have a SoftLayer® account. The cost of the components that are ordered in your instances is billed to that SoftLayer account.

## SoftLayer permissions

The SoftLayer account that you are using must have certain permissions to be able to order the components in your instances and perform operations on your behalf. The permission requirements are applicable to both VMware Cloud Foundation instances and VMware vCenter Server instances.

Authorized users can verify and update the SoftLayer user permissions on the SoftLayer Customer Portal. For more information, see [Edit a User's Customer Portal Permissions](https://knowledgelayer.softlayer.com/procedure/edit-users-customer-portal-permissions){:new_window}.

Table 1. Required permissions for the SoftLayer account

| Permission         | Details                                 |
|:-------------------|:----------------------------------------|
| Add IP Addresses | This permission is required to order portable private subnet ranges from SoftLayer on your behalf, which is  needed to manage the virtual machines that run in a vSphere cluster. When more services are added to your instance, the portable private IP addresses are assigned to VMware ESXi servers to isolate and allocate bandwidth. |
| Add Server | This permission is required for the following operations: to order the IBM Cloud bare metal server on which VMware ESXi runs and to provision hourly virtual servers that are used for instance configuration, maintenance, and support operations. |
| Cancel Server | This permission is required to release and reclaim the IBM Cloud bare metal server on which VMware ESXi runs. If you later delete your instance, the ordered components are automatically released in the correct dependency sequence. |
| View Virtual Server Details | This permission is required to retrieve the server provisioning details, which are required for order validation and automated configuration. |
| Add Storage | This permission is required to order backup storage and shared storage for the instance. |
| Manage Storage | This permission is required to manage backup storage and shared storage for the instance. |
| Order Compute with  Public Network Port | This permission is required to order hardware and VSIs (Virtual Server Instances) with public network ports. |
| Add Tickets | This permission is required to open service tickets on your behalf. Tickets might be created for the following operations: to initiate restore operations and to initiate problem resolution processes automatically when issues are found. |
| Edit Tickets | This permission is required to edit the service tickets that are created on your behalf. |
| View Tickets | This permission is required to monitor the service tickets that are related to the components provisioned in your instance for SoftLayer provisioning delays and problems. |
| View Hardware Details | This permission is required to retrieve the hardware details, which are required for order validation and    automated configuration. |
| View Licenses | This permission is required to retrieve and validate the licenses that are used by your instance. |

## VLAN spanning for classic (non-VRF) accounts

If you are using a classic (non-VRF) SoftLayer account, VLAN spanning must be enabled. If VLAN spanning is not enabled for classic accounts, the various components of the VMware virtualization environment might not be able to communicate with each other. To enable VLAN spanning in your SoftLayer account, see [Enable or Disable VLAN Spanning](https://knowledgelayer.softlayer.com/procedure/enable-or-disable-vlan-spanning){:new_window}.

## Related links

* [Requirements for Cloud Foundation instances](../sddc/sd_planning.html)
* [Requirements for vCenter Server instances](../vcenter/vc_planning.html)
* [User account and settings](useraccount.html)
