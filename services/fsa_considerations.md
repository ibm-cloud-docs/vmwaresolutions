---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-05"

---

# Components and considerations for Fortinet on IBM Cloud

The Fortinet on IBM® Cloud service deploys a pair of FortiGate Security Appliance (FSA) service 300 series devices in a highly available mode to provide firewall, routing, NAT, and VPN services to protect all the servers and virtual machines on the public VLAN of your instances. You can manage this service by using the FortiOS Web Client or the Command Line Interface via SSH.

This service is available only to V1.8 and later instances.

You can order an instance with the Fortinet on IBM Cloud service included. For more information, see:
* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)

You can also deploy the Fortinet on IBM Cloud service into your existing instances after initial deployment. For more information, see:
* [Ordering and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Ordering and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)

## Fortinet on IBM Cloud components

As part of the Fortinet on IBM Cloud service, an HA-pair of FortiGate 300 series Security Appliances is ordered in the default public VLAN.

**Note:** The HA-pair of Security Appliances is ordered and will be located on the default public VLAN with the original instance or cluster. If you order additional clusters, the public VLANs for these newly added clusters will not have the HA-pair of Security Appliances.

## Considerations when installing Fortinet on IBM Cloud

Review the following considerations before you install the Fortinet on IBM Cloud service:
* Ensure that the IBM Bluemix Infrastructure (SoftLayer) account that you are using has the **Hardware Firewall** permission. This permission is required to edit or view firewall logs and settings for the Fortinet on IBM Cloud service of your instance.
* If you want to add the Fortinet on IBM Cloud service to a deployed instance, ensure that there is no other firewall from Bluemix Infrastructure already in place on the public VLAN of the instance.
* Installing the Fortinet on IBM Cloud service will add a new public VLAN.
* During the service deployment, your instance might not be able to access the internet temporarily.
* After the Fortinet on IBM Cloud service is installed successfully, you can manage and configure firewall rules for the FSA from the FortiGate console. You must ensure that the FSA firewall rules are defined to allow outbound HTTPS (TCP port 443) communications that are started by management components such as the IBM CloudDriver virtual machine or Zerto Virtual Manager to communicate with the external management database on Bluemix over the internet. The outbound HTTPS (TCP port 443) communications originate from the public IP address of the management services VMware NSX Edge Services Gateway (ESG) in your instance.
*  If you are using NSX Distributed Firewalls (DFW), you must configure rules for all communications from IBM CloudDriver and the SDDC Manager virtual machines (for Cloud Foundation instances only) to allow all protocols to communicate on 10.0.0.0/8 and 161.26.0.0/16. In addition, you must create a DFW rule that allows for HTTPS traffic from the IBM CloudDriver VM (virtual machine) to any destination. These rules must come before any other rules that would block traffic to or from these VMs.

## Considerations when removing Fortinet on IBM Cloud

Review the following considerations before you remove the Fortinet on IBM Cloud service:
* Removing the Fortinet on IBM Cloud service will remove the public VLAN that was added.
* During the service removal, your instance might not be able to access the internet temporarily.
* All FortiGate rules to permit, inspect, block, and route NAT traffic are removed together with the Fortinet service. If you have any NAT
rules, you must reconfigure them.

## Related links

* [Managing Fortinet on IBM Cloud](managingfsa.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
* [FAQ](../vmonic/faq.html)
* [Fortinet website](https://www.fortinet.com/){:new_window}
* [Fortinet Document Library](http://docs.fortinet.com/fortigate/admin-guides){:new_window}
