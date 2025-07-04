---

copyright:

  years:  2016, 2025

lastupdated: "2025-06-06"

keywords: Entrust KeyControl, tech specs Entrust KeyControl

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Entrust KeyControl on {{site.data.keyword.cloud_notm}} overview
{: #entrust-kc_considerations}

New installations of Entrust KeyControl™ (formerly HyTrust KeyControl) are not supported for new or existing deployments of {{site.data.keyword.vcf-auto}} instances. You can still use or delete existing Entrust KeyControl installations on your existing instances.
{: deprecated}

Entrust KeyControl on {{site.data.keyword.cloud}} simplifies the management of encrypted workloads. This service automates and simplifies the lifecycle of encryption keys, including key storage, key distribution, key rotation, and key revocation. Using FIPS 140-2 compliant encryption, enterprises can easily manage encryption keys at scale. Entrust KeyControl on {{site.data.keyword.cloud_notm}} is a non-IBM product that is offered under terms and conditions from Entrust, not IBM.
{: shortdesc}

## Technical specifications for Entrust KeyControl
{: #entrust-kc_considerations-specs}

The following components are included in your existing Entrust KeyControl service:

### Entrust KeyControl appliance
{: #entrust-kc_considerations-appliance}

* CPU - 2 CPU
* RAM - 8 GB
* Disk - 20 GB VMDK resident on vSAN in the consolidated cluster
* Network - Placed on a VLAN-backed private portable network specified for management

### High availability
{: #entrust-kc_considerations-ha}

Two KeyControl appliances in an active-active clustered configuration.

Optionally, you can specify to deploy two KeyControl appliances in a stand-alone unclustered configuration.

### Licenses and fees
{: #entrust-kc_considerations-licenses}

An Entrust KeyControl license for each instance installation.
