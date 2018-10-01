---

copyright:

  years:  2016, 2018

lastupdated: "2018-09-26"

---

# FortiGate Security Appliance on IBM Cloud overview

The FortiGate Security Appliance on {{site.data.keyword.cloud}} service deploys a pair of FortiGate Security Appliance (FSA) 300 series devices in a highly available mode to provide firewall, routing, NAT, and VPN services to protect all the servers and virtual machines on the public VLAN of your instances.

You can manage this service by using the FortiOS Web Client or the command line interface via SSH.

**Availability:** This service is available only to instances that are deployed in V1.8 or later releases.

## Technical specifications for FortiGate Security Appliance on IBM Cloud

The following components are ordered and included in the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service:

### Hardware

The FortiGate 300 series Security Appliance.

### High availability

Two appliances are deployed in active-passive configuration.

### Networking

* Dual 1 GbE bonded on both upstream and downstream networks
* One new upstream {{site.data.keyword.cloud_notm}} public VLAN
* One existing downstream {{site.data.keyword.cloud_notm}} public VLAN

## Considerations when you install FortiGate Security Appliance on IBM Cloud

Review the following considerations before you install the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service:
* Ensure that the {{site.data.keyword.cloud_notm}} account that you're using has the **Hardware Firewall** permission. This permission is required to edit or view firewall logs and settings for the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service of your instance.
* If you want to add the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service to a deployed instance, ensure that no other firewall from {{site.data.keyword.cloud_notm}} infrastructure is already in place on the public VLAN of the instance.
* Installing the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service adds a new public VLAN.
* During the service deployment, your instance might not be able to access the internet temporarily.
* After the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service is installed successfully, you can manage and configure firewall rules for the FSA from the FortiGate console. You must ensure that the FSA firewall rules are defined to allow outbound HTTPS (TCP port 443) communications that are started by management components such as the Zerto Virtual Manager to communicate with the external management database on {{site.data.keyword.cloud_notm}} over the internet. The outbound HTTPS (TCP port 443) communications originate from the public IP address of the management services VMware NSX Edge Services Gateway (ESG) in your instance.
* You must manage the FortiGate Security Appliance configuration carefully to allow only necessary communications and deny all other communications.
* If you order additional clusters, the public VLANs for these newly added clusters do not have the HA-pair of Security Appliances.

## Considerations when you remove FortiGate Security Appliance on IBM Cloud

Review the following considerations before you remove the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service:
* Removing the FortiGate Security Appliance on {{site.data.keyword.cloud_notm}} service removes the public VLAN that was added.
* During the service removal, your instance might not be able to access the internet temporarily.
* All FortiGate rules to permit, inspect, block, and route NAT traffic are removed together with the Fortinet service. If you have any NAT rules, you must reconfigure them.

### Related links

* [Ordering FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](fsa_ordering.html)
* [Managing FortiGate Security Appliance on {{site.data.keyword.cloud_notm}}](managingfsa.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
* [FAQ](../vmonic/faq.html)
* [Fortinet website](https://www.fortinet.com/){:new_window}
* [Fortinet Document Library](http://docs.fortinet.com/fortigate/admin-guides){:new_window}
