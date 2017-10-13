---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-12"

---



# Networking on Cloud Foundation

Intro para


## Networking

* Three VLANs (Virtual LANs): one public VLAN and two private VLANs
* A secure management services VMware NSX Edge Services Gateway (ESG) for outbound HTTPS
management traffic, which is deployed by IBM as part of the management networking typology.
This ESG is used by the IBM management virtual machines to communicate with specific
external IBM management components that are related to automation. For more information, see [Does the management services NSX Edge pose a security risk?](../vmonic/faq.html#does-the-management-services-nsx-edge-pose-a-security-risk-)

  **Important**: This ESG is not accessible to you and you cannot use it. If you modify this ESG, you might not be able to manage the Cloud Foundation instance from the
  {{site.data.keyword.vmwaresolutions_short}} console. In addition, note that using a
  firewall or disabling the ESG communications to the external IBM management components
  will cause {{site.data.keyword.vmwaresolutions_short}} to become unusable.

## Using NSX with your Virtual Machines

  The VCF automation installs, licenses, and configures VMWare’s NSX platform. It also sets up
  the NSX Manager, NSX Controllers, NSX Transport Zone, and prepares each host with
  the NSX components. The end-user must configure NSX for use by their workload VMs if the
  VMs need to communicate with each other and have access to the internet. For more information, see [Setting up NSX for workload VMs on VMware Cloud Foundation on IBM Cloud (VCF)](){:new_window}

## Related links

* [Overview of NSX](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx-cross-vcenter-install.doc/GUID-10944155-28FF-46AA-AF56-7357E2F20AF4.html){:new_window}
* [NSX Edge Services Gateway](https://www.ibm.com/cloud/garage/content/architecture/virtVCenterServerPlatform/nsx-esg){:new_window}
* [VMware NSX 6 Documentation Center](https://pubs.vmware.com/NSX-6/index.jsp){:new_window}
* [Managing NAT Rules](https://docs.vmware.com/en/VMware-NSX-for-vSphere/6.2/com.vmware.nsx.admin.doc/GUID-5896D8CF-20E0-4691-A9EB-83AFD9D36AFD.html){:new_window}
* [Managing Fortinet on IBM Cloud](../services/managingfsa.html#managing-fortinet-on-ibm-cloud)
* [Managing F5 on IBM Cloud](../services/managing_f5.html#managing-f5-on-ibm-cloud)
