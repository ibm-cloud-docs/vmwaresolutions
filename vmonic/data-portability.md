---

copyright:

  years: 2025

lastupdated: "2025-10-24"

subcollection: vmwaresolutions

keywords: data portability, vmware solutions, IBM Cloud for VMware Solutions

---

{{site.data.keyword.attribute-definition-list}}


# Understanding data portability for VMware Solutions
{: #data-portability}

{{site.data.content.vms-deprecated-note}}

Data portability involves a set of tools and procedures that enable you to export the digital artifacts that are needed to implement similar workload and data processing on different service providers or on-premises software. It includes procedures for copying and storing the service customer content, including the related configuration that is used by the service to store and process the data, in your location.
{: shortdesc}

## Responsibilities
{: #data-portability-responsibilities}

{{site.data.keyword.cloud_notm}} services provide interfaces and instructions to guide you through the process of copying and storing service customer content, including the related configuration, in your selected location.

You're responsible for the use of the exported data and configuration for data portability to other infrastructures, which includes:

- The planning and execution for setting up alternative infrastructure on different cloud providers or on-premises software that provide similar capabilities to the {{site.data.keyword.IBM_notm}} services.
- The planning and execution for the porting of the required application code on the alternative infrastructure, including the adaptation of your application code, deployment automation, and so on.
- The conversion of the exported data and configuration to the format required by the alternative infrastructure and adapted applications.

For more information about your responsibilities for {{site.data.keyword.vmwaresolutions_short}}, see [Understanding your responsibilities when you use VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-understand-responsib).

## Data export procedures
{: #data-portability-procedures}

Data portability in VMware Solutions is accomplished by using one of the following products:
* VMware HCX
* VMware vSphere Replication
* Cross vCenter vMotion

## Exported data formats
{: #data-portability-data-formats}

The exported data format is set and controlled by one of the following products:
* VMware HCX
* VMware vSphere Replication
* Cross vCenter vMotion

For more information about data export procedures and exported data formats, see:

- [VMware HCX - User Guide](https://techdocs.broadcom.com/us/en/vmware-cis/hcx/vmware-hcx/4-10/vmware-hcx-user-guide-4-10.html){: external}
- [VMware vSphere Replication](https://techdocs.broadcom.com/us/en/vmware-cis/live-recovery/vsphere-replication/9-0.html){: external}
- [Migrating virtual machines between vCenter Server systems](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/8-0/vcenter-and-host-management-8-0/migrating-virtual-machines-host-management/vmotion-across-vcenter-server-systems-host-management.html){: external}

## Data ownership
{: #data-portability-ownership}

All exported data is classified as customer content. Apply the full customer ownership and licensing rights, as stated in the [{{site.data.keyword.cloud_notm}} Services Agreement](https://www.ibm.com/support/customer/csol/terms/?id=Z126-6304_WS){: external}.
