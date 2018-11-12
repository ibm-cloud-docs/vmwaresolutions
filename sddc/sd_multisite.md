---

copyright:

  years:  2016, 2018

lastupdated: "2018-10-29"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Multi-site configuration for Cloud Foundation instances

{{site.data.keyword.vmwaresolutions_full}} allows instances to be deployed across different locations and have them up and running in a short time.

**Notes:**
* You cannot link between VMware Cloud Foundation and VMware vCenter Server instances in a multi-site configuration.
* You cannot link instances that are deployed in V2.0 with instances from earlier releases (even if they were upgraded to V2.0).


## Multi-site deployment components

A multi-site deployment consists of the following components.

* **Primary instance**: The primary VMware Cloud Foundation instance has the following configuration:
  *  Microsoft Active Directory (AD) and DNS (Domain Name System) root domain
  *  Cloud Foundation subdomain
  *  SSO (Single Sign-On) domain
  *  SSO site name
* **Secondary instance or instances**: One or more secondary Cloud Foundation instances, linked to the primary instance, with the following configuration:
   *  SSO site name
   *  DNS subdomain that is linked to the root domain on the primary instance
   *  DNS and AD replication is set up between the AD virtual machines on the primary and secondary instances
   *  PSC (Platform Services Controller) deployed and configured to replicate with the PSC on the primary instance
   *  VMware vCenter on the secondary instances is set up with Enhanced Linked Mode to the vCenter on the primary instance

## Cloud Foundation multi-site deployment

The multi-site configuration feature uses a hub and spoke topology with a primary site and a maximum of seven secondary sites. A single layer of sites is supported, that is, you cannot configure subsequent sites that are linked to other secondary sites. You can have a total of 128 ESXi servers in a multi-site configuration across all instances.

If your configuration requires a multi-site deployment with more than 128 ESXi servers, contact IBM Support for assistance. For more information, see [Contacting IBM Support](../vmonic/trbl_support.html).
{:note}

The following graphic depicts the overall view of the Cloud Foundation multi-site deployment.

Figure 1. Cloud Foundation multi-site deployment

![Cloud Foundation multi-site deployment](multisite-hub-spoke.svg "Cloud Foundation multi-site deployment")

The model contains the following layers:

* **Primary instance**: In a multi-site configuration, to deploy the first instance, you define that instance as primary during the instance order process.
* **Secondary instances**: In a multi-site configuration, you define the instances that are attached to the primary instance as secondary instances during the order process.

You can assign only one secondary instance to a primary instance at a time. You cannot assign multiple secondary instances to a primary instance at the same time. To do that, you must go through the order process again and select the previously defined primary instance as a primary instance for the secondary instance. You must repeat the process for all secondary instances that you want to create.

You can have a maximum of 8 (1 primary and 7 secondary) instances that are deployed in a multi-site configuration.

Deleting Cloud Foundation instances that are part of a multi-site configuration requires special planning. For more information, see [Deleting Cloud Foundation instances in a multi-site configuration](sd_deletinginstance_multi.html).
{:note}

### Related links

* [Assign Primary Role to NSX Manager](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-44E8AE16-BA3F-4DD9-B582-FC1E137E6CFC.html){:new_window}
* [Configuring Secondary NSX Managers](https://pubs.vmware.com/NSX-62/topic/com.vmware.nsx-cross-vcenter-install.doc/GUID-9E48BC57-15E3-49C7-8BC5-F94ED8918BBE.html){:new_window}
* [Active Directory Trusts supported with VMware vCenter Single Sign-On](https://kb.vmware.com/kb/2064250){:new_window}
* [Securely connect your private VMware workloads in the {{site.data.keyword.cloud_notm}}](https://www.ibm.com/developerworks/library/se-securely-connect-private-vmware-workloads-ibm-cloud/index.html){:new_window}
