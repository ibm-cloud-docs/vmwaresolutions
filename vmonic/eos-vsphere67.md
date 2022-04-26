---

copyright:

  years:  2022

lastupdated: "2022-03-23"

keywords: end of marketing notice, vSphere 6.7 deployment, end of support vSphere 6.7, vSphere 6.7 deprecated, vSphere 6.7 support

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# End of Marketing for vSphere 6.7 instance deployments
{: #eos-vsphere67}

VMware® support for all new VMware vSphere 6.7 deployments ends on 15 October 2022.

Beginning on 21 June 2022, you can no longer order new VMware vCenter Server® instances with vSphere 6.7. However, you can still add or remove existing clusters and hosts until 15 October 2022. 

After 15 October 2022, vCenter Server instances with vSphere 6.7 become read–only in the VMware Solutions console and through the public REST API.

Beginning on this date, you can no longer add or remove clusters and hosts until you upgrade to vSphere 7.

{{site.data.keyword.cloud_notm}} will continue to support your infrastructure on our cloud and will continue to support the vSphere 6.7 software until the [VMware announced end of support date](https://lifecycle.vmware.com/#/){: external} of 15 October 2022.

vSphere 6.7 is superseded by vSphere 7. If you have active workloads on vSphere 6.7, consider upgrading or migrating to vSphere 7 today. The documentation provides instructions and considerations for upgrading to vSphere 7.

{{site.data.keyword.cloud_notm}} recommends you to move to vSphere 7, which is the focus of feature investment for both VMware and {{site.data.keyword.cloud_notm}}. Furthermore, {{site.data.keyword.cloud_notm}} recommends that you migrate rather than upgrade to vSphere 7. Migration ensures that you are aligned with current and supported hardware, other {{site.data.keyword.cloud_notm}} features, and the recommended vSphere 7 NSX–T topology, including the use of VDS switches.

Before you upgrade, IBM recommends that you assess your environments for infrastructure and workload dependencies to ensure that they are supported for the current version.

vSphere 7 introduces the following features:
* HTML5 client
* Support for Intel Cascade Lake EVC level
* Enhanced vSphere Lifecycle Manager (LCM)
* Enhancements to DRS and vMotion
* Security enhancements such as multifactor authentication (MFA), vSphere Trust Authority (vTA), and in–flight encryption for vSAN

vSphere 7 is also the exclusive basis for VMware Regulated Workloads.

For more information about end of life procedures for {{site.data.keyword.cloud_notm}} infrastructure services and third-party software products, see [Lifecycle policy for IBM Cloud products](https://www.ibm.com/cloud/cloud-prod-life). If you have any questions or need assistance, email clouddigitalsales@us.ibm.com or open a support ticket in the VMware Solutions console.

## Related links
{: #eos-vsphere67-related}

* [End of Marketing for NSX-V instance deployments](/docs/vmwaresolutions?topic=vmwaresolutions-eos-nsx-v)
* [End of Marketing for vSphere 6.5 instance deployments](/docs/vmwaresolutions?topic=vmwaresolutions-eos-vsphere65)
