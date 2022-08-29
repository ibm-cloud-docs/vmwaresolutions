---

copyright:

  years:  2019, 2022

lastupdated: "2022-06-28"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# vCenter Server encryption options
{: #htdc-hpcs-encryption-options}

New installations of Entrust DataControl® (formerly known as HyTrust DataControl) are no longer supported for new or existing deployments of vCenter Server® instances. You can still use or delete existing Entrust DataControl installations on your existing instances.
{: deprecated}

Enterprises that require encrypted data at rest on their vCenter Server instance have the following options:

* {{site.data.keyword.cloud}} Endurance native encryption - This option uses IBM-managed keys, so is not suitable for clients that require either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK). The encryption scope is the complete NFS volume.
* vSAN encryption - This option requires the use of a key management server such as the following, the encryption scope are the vSAN™ disks:
   * IBM KeyProtect™ (IBM KP) service for customers who require BYOK, along with the KMIP™ for VMware® service.
   * IBM Hyper Protect Crypto Services (IBM HPCS), for customers who require KYOK, with the KMIP for VMware service.
   * Entrust KeyControl™ on {{site.data.keyword.cloud_notm}}.
   * A manually installed solution such as IBM Security Key Lifecycle Manager (SKLM). This solution can also use {{site.data.keyword.cloud_notm}} HSMs.
* vSphere encryption - This option requires the use of a key management server. However, the encryption scope is the virtual machine (VM) disks.
* Entrust DataControl® encryption - This option uses the Entrust KeyControl key management server and Policy Agent, both components of Entrust DataControl. This option can now also use IBM HPCS to deliver KYOK. The encryption scope includes Microsoft® Windows® or Linux® VM disks, files, or file systems.

The use of IBM KP or IBM HPCS allows:
* Bring Your Own Key (BYOK) - Bring your keys to the cloud and manage them using the IBM KP multitenant key management service.
* Keep Your Own Key (KYOK) - Keep your keys protected with the IBM HPCS single-tenant key management service. It has built-in customer-controlled FIPS 140-2 Level 4 Hardware Security Modules (HSM), which provide control and authority over encryption keys.

For a comparison of features between Entrust DataControl, vSphere Encryption, and vSAN Encryption, see [vSphere and vSAN encryption with Entrust KeyControl](https://www.entrust.com/-/media/documentation/buyersguide/dps-vsphere-vsan-encryption-keycontrol-bg.pdf){: external}.

## Related links
{: #htdc-hpcs-encryption-options-related}

* [Multicloud encryption - Entrust](https://www.entrust.com/digital-security/multi-cloud-encryption){: external}
* [{{site.data.keyword.cloud_notm}} Hyper Protect Crypto Services](https://www.ibm.com/cloud/hyper-protect-crypto){: external}
