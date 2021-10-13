---

copyright:

  years:  2016, 2021

lastupdated: "2021-08-26"

keywords: IBM Cloud Object Storage, ICOS configuration, order Cloud Object Storage

subcollection: vmwaresolutions

---

{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Ordering and configuring IBM Cloud Object Storage with Veeam
{: #icos_ordering}

For Veeam Availability Suite™ 9.5 Update 4 and later, Veeam® is compatible with {{site.data.keyword.cloud}} Object Storage. The ordering of {{site.data.keyword.cloud_notm}} Object Storage is not automated when you order Veeam, but it can be added after deployment.

To order {{site.data.keyword.cloud_notm}} Object Storage, complete the following tasks in the specified order.

## Creating an Object Storage instance
{: #icos_ordering-obj}

For more information about creating an Object Storage instance, see [Creating a new service instance](/docs/cloud-object-storage/basics?topic=cloud-object-storage-provision#provision-instance). Follow the steps and return here to continue with the following tasks.

## Creating a bucket
{: #icos_ordering-bucket}

For more information about creating a bucket, see [Create some buckets to store your data](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage#gs-create-buckets). Follow the steps and return here to continue with the following tasks.

## Creating service credentials
{: #icos_ordering-service-cred}

For more information about creating service credentials, see [Service credentials](/docs/cloud-object-storage/hmac?topic=cloud-object-storage-service-credentials). Follow the steps and return here to continue with the following tasks.

## Adding a scale-out repository
{: #icos_ordering-scale-repo}

* As part of the Veeam service installation and configuration, a scale-out backup repository with the name `IC4V Scale-Out Repository` is created. The `IC4V Default VM Backup Repository` repository is added to the scale-out repository as an extent.
* When you create the backup job, you must select `IC4V Scale-Out Repository` as the backup repository, and not `IC4V Default Config Backup Repository`. The latter repository is intended for the Veeam configuration backups.
* You can add more repositories to this default repository, such as a backup repository of type Object Storage. For more information, see [Adding scale-Out repositories](https://helpcenter.veeam.com/docs/backup/vsphere/sobr_add.html?ver=95u4){: external}. Follow the steps and return here to continue with the following tasks.

## Veeam on an instance deployed with private network only
{: #icos_ordering-private-network}

If you want to access {{site.data.keyword.cloud_notm}} Object Storage by using Veeam on a private-only vCenter Server instance, you must configure Veeam to access the internet through a proxy server. This way, Veeam can verify the TLS certificate that is used by {{site.data.keyword.cloud_notm}} Object Storage.

For more information, see [How to set an HTTP proxy for Veeam components](https://www.veeam.com/kb3090){: external}.

## Maintaining and managing your cloud tier
{: #icos_ordering-manage-cloud}

For more information about maintaining and managing your cloud tier, see [Managing capacity tier data](https://helpcenter.veeam.com/docs/backup/vsphere/capacity_tier_managing_data.html?ver=95u4){: external}.

## Related links
{: #icos_ordering-related}

* [Veeam v9.5 overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_considerations)
* [Veeam v11 overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview)
* [Ordering Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering)
* [Managing Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-managingveeam)
* [Ordering Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_ordering_licenses)
* [Managing Veeam licenses](/docs/vmwaresolutions?topic=vmwaresolutions-veeam_managing_licenses)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [Veeam on {{site.data.keyword.cloud_notm}} - Demos](https://www.ibm.com/demos/collection/Veeam-on-IBM-Cloud/){: external}
