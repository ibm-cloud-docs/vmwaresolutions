---

copyright:

  years:  2022

lastupdated: "2022-04-08"

keywords: end of support notice, vSphere 6.5 deployment, end of support vSphere 6.5, vSphere 6.5 deprecated, vSphere 6.5 support

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# End of Support for vSphere 6.5 instance deployments
{: #eos-vsphere65}

{{site.data.keyword.cloud_notm}} support for ordering all update levels of VMware vSphere® 6.5 ended on 10 October 2021.

Beginning on this date, you can no longer order new VMware vCenter Server® instances with vSphere 6.5. Also, your existing vCenter Server instances with vSphere 6.5 become read–only in the VMware Solutions console and through the public REST API.

Until you upgrade to vSphere 6.7 or later, you cannot complete operations such as:

* Adding and deleting clusters
* Adding and removing ESXi servers
* Adding and removing storage
* Adding and deleting services

You can still view and delete your existing instances with vSphere 6.5.

{{site.data.keyword.cloud_notm}} will continue to support your infrastructure on our cloud and will continue to support the vSphere 6.5 software until the [VMware announced end of support date](https://lifecycle.vmware.com/#/){: external} of 15 October 2022.

vSphere 6.5 is superseded by vSphere 6.7 and vSphere 7. If you have active workloads on vSphere 6.5, consider upgrading or migrating to vSphere 6.7 or vSphere 7 today. The documentation provides instructions and considerations for upgrading to vSphere 6.7 and vSphere 7.

{{site.data.keyword.cloud_notm}} encourages you to move to vSphere 7, which is the focus of feature investment for both VMware® and {{site.data.keyword.cloud_notm}}. Furthermore, {{site.data.keyword.cloud_notm}} encourages that you migrate rather than upgrade to vSphere 7. Migration ensures that you are aligned with current and supported hardware, other {{site.data.keyword.cloud_notm}} features, and the vSphere 7 NSX–T topology, including the use of VDS switches.

Before you upgrade, you must assess your environments for infrastructure and workload dependencies to ensure that they are supported for the current version.

vSphere 6.7 introduces the following features:
* Embedded Platform Services Controller (PSC)
* Improved support for the HTML5 client, including vSAN management
* Support for Intel® Skylake EVC level
* Support for virtual TPM
* Improved support for VMware Update Manager (VUM)
* vSAN support for Windows® Failover Clustering

vSphere 7 introduces the following features:
* HTML5 client
* Support for Intel Cascade Lake EVC level
* Enhanced vSphere Lifecycle Manager (LCM)
* Enhancements to DRS and vMotion
* Security enhancements such as multifactor authentication (MFA), vSphere Trust Authority (vTA), and in–flight encryption for vSAN

vSphere 7 is also the exclusive basis for VMware Regulated Workloads.

For more information about end of life procedures for {{site.data.keyword.cloud_notm}} infrastructure services and Third–Party software products, see [Lifecycle policy for IBM Cloud products](https://www.ibm.com/cloud/cloud-prod-life). If you have any questions or need assistance, email clouddigitalsales@us.ibm.com or open a support ticket in the VMware Solutions console.

## Related links
{: #eos-vsphere65-related}

* [End of Marketing for NSX-V instance deployments](/docs/vmwaresolutions?topic=vmwaresolutions-eos-nsx-v)
* [End of Marketing for vSphere 6.7 instance deployments](/docs/vmwaresolutions?topic=vmwaresolutions-eos-vsphere67)
