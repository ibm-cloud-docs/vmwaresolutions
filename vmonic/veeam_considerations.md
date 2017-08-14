---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-11"

---

# Components and considerations for Veeam on IBM Cloud

The Veeam on IBM® Cloud service seamlessly integrates directly with your VMware hypervisors to help your enterprise achieve high availability. This service can provide recovery points and time objectives of less than 15 minutes upon configuration for your applications and data. By using this service, you can directly control both the backup and restore of all virtual machines for your infrastructure from the Veeam console. This service is only available to V1.8 and higher instances.

You can order an instance with the Veeam on IBM Cloud service included. For more information, see:
* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)

You can also deploy the Veeam on IBM Cloud service into your existing instances after initial deployment. For more information, see:
* [Ordering, viewing, and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Ordering, viewing, and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)

## Veeam on IBM Cloud components

The following components are ordered and included in the Veeam on IBM Cloud service:
* One Windows Server 2016 VSI with a primary private IP address and 1 GbE interface
* IBM Cloud Endurance block storage of the size and performance that you select when you order the service

## Considerations when installing Veeam on IBM Cloud

* The management components that are backed up by the Veeam on IBM Cloud service include the VMware vCenter Server, the Platform Services Controller (PSC), the IBM CloudDriver, and VMware SDDC Manager (applies to Cloud Foundation instances only).
* The configurations of the ESXi servers are not backed up by the Veeam on IBM Cloud service.
* By default, the configurations of the NSX Controller and the NSX Edge are backed up daily by using the NSX Manager with up to 14 points of restoration. For a full restore of the NSX configurations, you must create a service ticket to IBM Support, because the backups of the NSX configurations are saved on the storage that is internal to {{site.data.keyword.vmwaresolutions_full}}. For more information on managing the NSX configuration backups by using NSX Manager, see the [VMware technical instructions](https://pubs.vmware.com/NSX-6/index.jsp#com.vmware.nsx.admin.doc/GUID-72EFCAB1-0B10-4007-A44C-09D38CD960D3.html).

## Considerations when removing Veeam on IBM Cloud

Review these considerations before you remove the Veeam on IBM Cloud service: removing this service will stop all backups (including the backup of the management VMs) and will delete all the previous backups (the deletion is irreversible). If the management VMs are corrupted subsequently, they cannot be restored.

## Related links

* [Managing Veeam on IBM Cloud](managingveeam.html)
* [Contacting IBM Support](trbl_support.html)
* [FAQ](faq.html)
* [Veeam.come website](https://www.veeam.com/)
* [Veeam technical documentation](https://www.veeam.com/documentation-guides-datasheets.html)
