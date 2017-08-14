---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-11"

---

# Components and considerations for Fortinet on IBM Cloud

The Fortinet on IBM® Cloud service deploys a pair of FortiGate Security Appliance (FSA) service 300 series devices in a highly available mode to provide firewall, routing, NAT, and VPN services to protect all the servers and virtual machines on the public VLAN of your instances. This service is only available to V1.8 and higher instances. You can manage this service by using the FortiOS Web Client or the Command Line Interface via SSH.

You can order an instance with the Fortinet on IBM Cloud service included. For more information, see:
* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)

You can also deploy the Fortinet on IBM Cloud service into your existing instances after initial deployment. For more information, see:
* [Ordering, viewing, and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Ordering, viewing, and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)

## Components of the Fortinet on IBM Cloud service

An HA-pair of FortiGate 300 series Security Appliance is ordered and included in the Fortinet on IBM Cloud service.

## Considerations when installing the Fortinet on IBM Cloud service

Review the following considerations before you install the Fortinet on IBM Cloud service:
* Ensure that the SoftLayer account that you are using has the **Hardware Firewall** permission. This permission is required to edit or view firewall logs and settings for the Fortinet on IBM Cloud service of your instance.
* If you want to add the Fortinet on IBM Cloud service to a deployed instance, ensure that there is no other firewall from SoftLayer already in place on the public VLAN of the instance.
* Installing the Fortinet on IBM Cloud service will add a new public VLAN.
* During the service deployment, your instance might not be able to access the Internet temporarily.
* After the Fortinet on IBM Cloud service is installed successfully, you can manage and configure firewall rules for the FSA from the FortiGate console. You must ensure that the FSA firewall rules are defined to allow outbound HTTPS (TCP port 443) communications that are initiated by management components such as the IBM CloudDriver virtual machine or Zerto Virtual Manager to communicate with the external management database on IBM Bluemix over the Internet. The outbound HTTPS (TCP port 443) communications originate from the public IP address of the management services VMware NSX Edge Services Gateway (ESG) in your instance.

## Considerations when removing the Fortinet on IBM Cloud service

Review the following considerations before you remove the Fortinet on IBM Cloud service:
* Removing the Fortinet on IBM Cloud service will remove the public VLAN that it added.
* During the service removal, your instance might not be able to access the Internet temporarily.
* All FortiGate rules to permit, inspect, block, route, and NAT traffic are removed together with the FortiGate. If you have any NAT
rules, you must reconfigure connections because of the removal of the NAT.

## Related links

* [Managing Fortinet on IBM Cloud](managingfsa.html)
* [Contacting IBM Support](trbl_support.html)
* [FAQ](faq.html)
* [fortinet.com website](https://www.fortinet.com/)
* [Fortinet technical documentation](http://docs.fortinet.com/fortigate/admin-guides)
