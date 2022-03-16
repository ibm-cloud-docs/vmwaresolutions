---

copyright:

  years:  2022

lastupdated: "2022-03-11"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# FAQ about VMware NSX-V to NSX-T migration
{: #faq-v2t-migration}


## Can I attach my existing IBM Cloud File Storage to the new vCenter Server instance?
{: #faq-v2t-migration-storage}

If you are using NFS storage, you can manually attach the NFS storage to the new instance and perform a cross–vCenter vMotion without also requiring a storage vMotion. You must authorize the NFS subnet from their new instance to the NFS storage.

The following recommendations apply:

* Configure static `/etc/hosts` entries on the new hosts for the storage hostnames for bootstrap purposes.
* Configure static routes on the new hosts to ensure that traffic to the NFS is driven over the NFS subnet and storage VLAN.
* After migration, open a support ticket to ensure that IBM Support decouples the NFS storage from the original instance. This way, the storage is not cancelled when the original instance is deleted.

## Can I reuse my existing Active Directory in the new vCenter Server instance?
{: #faq-v2t-migration-ad}

Most customers do not use the AD/DNS servers that are deployed with VMware vCenter Server®, but instead added their own domain controllers as an additional identity source to vCenter Server and NSX Manager.

You can preserve the existing Active Directory (AD) controllers for ongoing use if you are aware of the following information:

* The new instance deploys new domain controllers that it must use for DNS and authenticating the IBM automation users.
* If you are using VMs, the domain controllers from the old instance can be migrated to the new instance. If you are using VSIs, the domain controllers from the old instance can be used by the new instance. If the new instance is deployed with a different root domain than the original instance, the domain controllers can be added as an identity source to vCenter Server and NSX manager. So, if the old instance domain is `example.cloud.local`, the new instance can be named `example.cloud2.local`. The original AD can be configured to delegate DNS for this domain to the new AD, and users can log in using their existing `user@example.cloud.local` identities to access resource hostnames like `instance1-vc.example.cloud2.local`.
* If the original AD is deployed as a VSI, open a support ticket to ensure that IBM Support decouples the VSI from the original instance to ensure that the VSI is not cancelled when the original instance is deleted.
* In all cases, it is advised to back up the original controllers before you remove the original vCenter Server instance.

## Can I use vMotion with vSphere Encryption between the two vCenter Server instances?
{: #faq-v2t-migration-encryption}

With vSphere encryption, it is possible to perform an advanced cross vCenter vMotion on vSphere–encryption–protected virtual machines. You need to upgrade the source vCenter to v7.0 and connect both vCenters to the same Key Management System (KMS) and assign it the same name. Also, ensure that you have equivalent storage encryption policies in each vCenter Server.

## What happens to assets that were deployed manually?
{: #faq-v2t-migration-manual-custom}

If you added deployed assets to the instance manually, after initial deployment, the automation does not know about them. Therefore, you must migrate the assets to the new instance manually.

## I have VMware workloads on IBM Cloud Bare Metal Servers with vSphere 6.5 and 6.7 and the support is ending. I am not using NSX for my workloads. What do I need to do keep the environment supported, and what options do I have?
{: #faq-v2t-migration-6x-classic}

The End of General Support for VMware vSphere® 6.5 and 6.7 is 15 October 2022. For more information, see [End of general support for vSphere 6.5 and vSAN 6.5/6.6](https://kb.vmware.com/s/article/83223){: external} and [VMware product lifecycle matrix](https://lifecycle.vmware.com/#/){: external}.

Instances with IBM Cloud Bare Metal Servers vSphere 6.7 servers are not orderable after 21 June 2022. IBM Cloud support for ordering all update levels of vSphere 6.5 ended on 10 October 2021, and vSphere 6.5 will not be orderable after 21 June 2022. 

IBM Cloud recommends an upgrade to vSphere 7.x. If you ordered your servers from the Bare metal catalog for IBM Cloud Classic Infrastructure, you have the following options.

* Check whether your server and its hardware options are compatible with vSphere 7.0. For more information, see [VMware compatibility guide](https://www.vmware.com/resources/compatibility/search.php){: external}. Alternatively, if you are running vCenter, you can upgrade your vCenter, set up vSphere Update Manager (VUM) or vSphere Lifecycle Manager, and run Hardware Compatibility Checks for the upgrade.
* Order new IBM Cloud Bare Metal Servers with vSphere 7.x from the Bare metal catalog for IBM Cloud Classic Infrastructure or from the VMware Solutions console, the VMware Solutions Dedicated - VMware vSphere offering. Configure your vSphere host and vCenter Server and migrate the workloads. After the workloads are migrated, you can remove the ESXi hosts from vCenter Server and decommission the old servers through the IBM Cloud portal. 

## I have VMware Solutions Dedicated - VMware vSphere, IBM Cloud Bare Metal Servers with vSphere 6.5 or 6.7, and the support is ending. I am not using NSX for my workloads. What do I need to do to keep the environment supported, and what options do I have?
{: #faq-v2t-migration-6x-vss}

The End of General Support for vSphere 6.5 and 6.7 is 15 October 2022. For more information, see [End of general support for vSphere 6.5 and vSAN 6.5/6.6](https://kb.vmware.com/s/article/83223){: external} and [VMware product lifecycle matrix](https://lifecycle.vmware.com/#/){: external}.

Instances with IBM Cloud Bare Metal Servers vSphere 6.7 servers are not orderable after 21 June 2022. IBM Cloud support for ordering all update levels of VMware vSphere 6.5 ended on 10 October 2021, and VMware vSphere 6.5 will not be orderable after 21 June 2022. 

IBM Cloud recommends an upgrade to vSphere 7.x. If you ordered your servers from the VMware Solutions console, the VMware Solutions Dedicated - VMware vSphere offering, you have the following options.

* Check whether your server and its hardware options are compatible with vSphere 7.0. For more information, see [VMware compatibility guide](https://www.vmware.com/resources/compatibility/search.php){: external}. Alternatively, you can upgrade your vCenter Server, set up vSphere Update Manager (VUM) or vSphere Lifecycle Manager, and run hardware compatibility checks for the upgrade.
* Order new IBM Cloud Bare Metal Servers with vSphere 7.x from the VMware Solutions console, the VMware Solutions Dedicated - VMware vSphere offering, configure your vSphere host and vCenter Server, and migrate the workloads. After the workloads are migrated, you can remove the ESXi hosts from vCenter and decommission the old servers from the IBM Cloud portal. 

## I have VMware Solutions Dedicated - vCenter Server with NSX-V, IBM Cloud Bare Metal Servers with vSphere 6.5 or 6.7, and the support is ending. What do I need to do to keep the environment supported, and what options do I have?
{: #faq-v2t-migration-6x-vcs}

The End of General Support for vSphere 6.5 and 6.7 is 15 October 2022. For more information, see [End of general support for vSphere 6.5 and vSAN 6.5/6.6](https://kb.vmware.com/s/article/83223){: external} and [VMware product lifecycle matrix](https://lifecycle.vmware.com/#/){: external}.

In addition, the vCenter Server instances with vSphere 6.5 or 6.7 typically run NSX-V 6.4. NSX-V 6.4 is End of General Support on 16 January 2022 and end of technical guidance on 16 January 2023. See more on VMware Official Product Lifecycle Matrix. An exclusive support agreement between VMware and IBM to support NSX-V until 4 November 2022.

IBM Cloud recommends an upgrade to vSphere 7.x and NSX-T 3.x.

To migrate from NSX-V to NSX-T (also called a V2T migration), IBM Cloud uses a migration approach that is called _lift-and-shift_. In the lift-and-shift approach, the IBM Cloud automation is used to deploy a new vCenter Server instance. You need to migrate network configurations from NSX-V to NSX-T and migrate workloads between instances. IBM Cloud provides extensive documentation for a validated approach and guidance for existing IBM Cloud for VMware Solutions customers with vCenter Server instances. 

## How do I know whether my IBM Cloud Bare Metal Server hardware is suitable for in-place vSphere 7.x upgrade?
{: #faq-v2t-migration-7x-hw-support}

You can check whether your server and its hardware options are compatible with vSphere 7.x. For more information, see [VMware compatibility guide](https://www.vmware.com/resources/compatibility/search.php){: external}.

Alternatively, you can upgrade your vCenter, set up vSphere Update Manager (VUM) or vSphere Lifecycle Manager, and run Hardware Compatibility Checks for the upgrade.

## What are the different ways that I can use IBM Cloud Bare Metal Servers for VMware workloads in IBM Cloud?
{: #faq-v2t-migration-vmware-platforms}

You can use a VMware® platform on IBM Cloud in the following ways.

* Bare Metal - Use the Bare metal catalog for IBM Cloud Classic Infrastructure and order a bare metal server with vSphere as the Operating System. For more information, see [VMware for Classic](/docs/vmware).
* VMware Solutions Dedicated - VMware vSphere - Use the VMware Solutions console to provision IBM-hosted VMware hosts. For more information, see [VMware vSphere overview](/docs/vmwaresolutions?topic=vmwaresolutions-vs_vsphereclusteroverview).
* VMware Solutions Dedicated - vCenter Server - Use the VMware Solutions console to provision an IBM-hosted private cloud based on vSphere, NSX, and optionally vSAN. For more information, see [vCenter Server overview](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview).

Upgrade and migration processes vary depending on the consumption model.
{: note}

## What is the impact if I don't upgrade vSphere 6.x on my IBM Cloud bare metal hosts?
{: #faq-v2t-migration-6x-impact}

Upgrading your vSphere software is a customer responsibility and the decision to upgrade to a supported version is yours. However, your business might be at risk because VMware is under no obligation to provide product patches and updates, such as security updates and bug fixes. If IBM Cloud provides your vSphere licenses, then IBM Support cannot assist you with vSphere issues until you upgrade. IBM Cloud continues to support your bare metal servers infrastructure on our cloud and the vSphere 6.5 software until the VMware announced end of support date of 15 October 2022.

See also [different ways to run VMware workloads in IBM Cloud](/docs/vmwaresolutions?topic=vmwaresolutions-faq-v2t-migration#faq-v2t-migration-vmware-platforms).

## What is the impact if I don't upgrade vSphere 6.x on my VMware Solutions Dedicated - VMware vSphere (vSS) hosts?
{: #faq-v2t-migration-6x-impact-vss}

Upgrading your vSphere software is a customer responsibility and the decision to upgrade to a supported version is yours. However, your business might be at risk because VMware is under no obligation to provide product patches and updates, such as security updates and bug fixes. If IBM Cloud provides your vSphere licenses, then IBM Support cannot assist you with vSphere issues until you upgrade. IBM Cloud continues to support your bare metal servers infrastructure on our cloud and the vSphere 6.5 software until the VMware announced end of support date of 15 October 2022.

See also [different ways to run VMware workloads in IBM Cloud](/docs/vmwaresolutions?topic=vmwaresolutions-faq-v2t-migration#faq-v2t-migration-vmware-platforms).

## What is the impact if I don't upgrade vSphere 6.x on my VMware Solutions Dedicated - vCenter Server (vCS) hosts?
{: #faq-v2t-migration-6x-impact-vcs}

Upgrading your vSphere software is a customer responsibility and the decision to upgrade to a supported version is yours. However, your business might be at risk because VMware is under no obligation to provide product patches and updates, such as security updates and bug fixes. IBM Cloud support for ordering all update levels of VMware vSphere 6.5 ended on 10 October 2021 and you can no longer order new vCS instances with vSphere 6.5. Existing vCS vSphere 6.5 instances became read–only in the VMware Solutions console and through the public REST API, which means that you cannot add or remove clusters, hosts, storage, or services. Your workloads that are hosted on the platform continue to run. 

To regain the ability to add or remove clusters, hosts, storage, or services you must upgrade to vSphere 6.7 or later. IBM Cloud recommends upgrading to 7.x until the VMware announced end of support date of 15 October 2022. If your vCenter Server instance is running NSX-V, consider moving to vCenter Server with NSX-T. This lift and shift upgrade approach can be more beneficial due to the end of support of NSX-V. You might benefit from a target platform with updated hardware, upgraded VMware software, NSX-T, and a lower impact lift and shift migration rather than an in-place upgrade.

See also [different ways to run VMware workloads in IBM Cloud](/docs/vmwaresolutions?topic=vmwaresolutions-faq-v2t-migration#faq-v2t-migration-vmware-platforms).

## If I am using Bring Your Own License (BYOL) on my IBM Cloud bare metal hosts how does this impact the upgrade?
{: #faq-v2t-migration-6x-upgrade-impact-byol}

Upgrading vSphere software is your responsibility. However, with BYOL you can access VMware Support directly by using your license agreement. IBM Cloud provides support for your bare metal servers infrastructure on IBM cloud. 

For more information about upgrading, see [VMware ESXi upgrade VMware vSphere 6.7](https://docs.vmware.com/en/VMware-vSphere/6.7/vsphere-esxi-671-upgrade-guide.pdf){: external} and [vSphere upgrade VMware vSphere 6.5](https://docs.vmware.com/en/VMware-vSphere/6.5/vsphere-esxi-vcenter-server-651-upgrade-guide.pdf){: external}. As part of the upgrade planning, consider moving to the IBM Cloud vCenter Server with NSX-T offering, this lift and shift upgrade approach might be more beneficial.

See also [different ways to run VMware workloads in IBM Cloud](/docs/vmwaresolutions?topic=vmwaresolutions-faq-v2t-migration#faq-v2t-migration-vmware-platforms).

## If I am using Bring Your Own License (BYOL) on my VMware Solutions Dedicated - vCenter Server (vCS) hosts how does this impact the upgrade?
{: #faq-v2t-migration-6x-upgrade-impact-byol-vcs}

Upgrading vSphere software is your responsibility. However, with BYOL you access VMware Support directly by using your license agreement. IBM Cloud provides support for your bare metal servers infrastructure on our cloud. For more information, see [Upgrading vCenter Server vSphere software from vSphere 6.5 or 6.7 to 7.0](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vsphere_70_upgrade). If your vCenter Server instance is running NSX-V, consider moving to vCenter Server with NSX-T. This lift and shift upgrade approach might be more beneficial due to the end of support of NSX-V.

See also [different ways to run VMware workloads in IBM Cloud](/docs/vmwaresolutions?topic=vmwaresolutions-faq-v2t-migration#faq-v2t-migration-vmware-platforms).

## What product is it running in the VMware Solutions Dedicated - vCenter Server instance? 
{: #faq-v2t-migration-what-products}

For a vCenter Server instance, the following information is displayed on the VMware Solutions user interface.

* VMware NSX networking solution - NSX-T
* NSX for vSphere - 3.1.1.0
* NSX license edition - VMware NSX Advanced

What product is it running in the vCenter Server instance?

This vCenter Server instance is running NSX-T version 3.1.1. Due to the licensing agreement between IBM Cloud and VMware, NSX-V licenses were being used for NSX-T instances. Newer vCenter Server instances use NSX-T licenses, so the instance is correctly licensed.

## Related links
{: #faq-v2t-migration-links}

* [General FAQ about VMware Solutions Shared](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions-shared)
* [General FAQ about VMware Solutions Dedicated](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Considerations about changing vCenter Server artifacts](/docs/vmwaresolutions?topic=vmwaresolutions-vcenter_chg_impact)

