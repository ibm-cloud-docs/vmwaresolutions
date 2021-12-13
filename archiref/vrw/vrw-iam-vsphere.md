---

copyright:

  years:  2020, 2021

lastupdated: "2021-10-21"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# vCenter identity and access management
{: #vrw-iam-vsphere}

Inside {{site.data.keyword.cloud_notm}} for VMware® Regulated Workloads, multiple levels of access are available. The automation uses a set of user IDs to perform operations such as adding hosts, clusters, or storage to your VMware® instance.

## vCenter and Platform Services Controller user IDs
{: #vrw-iam-vsphere-vcenter}

The following user IDs are used to add an identity source, which is embedded by default, into vCenter.

| User     | User ID      | Method | Description |
|:---------|:-------------|:-------|:------------|
| Privileged user | `root` | SSH | Used for VMware configuration such as setting up VMware High Availability and creating distributed switches. Used post deployment to pair primary and secondary vCenter Server instances. |
| Privileged user | `customerroot` | SSH | Created for customer use only. |
| IBM automation | `automation`@``root_domain``  \n (Active Directory user) | HTTPS | Used post deployment to add and remove hosts and clusters and to deploy and configure virtual machines (VMs) for add-on services. |
| Privileged user | `cloudadmin`@`root_domain`  \n (Active Directory user) | HTTPS | Created for customer use only. |
{: caption="Table 1. vCenter and Platform Services Controller user IDs" caption-side="top"}

HTTPS is used for vCenter setup and configuration, and for VMware operations such as adding hosts, clusters, or storage for vCenter management of resources.

### vCenter access
{: #vrw-iam-vsphere-vcenter-access}

Privileged users are granted `cloudadmin` access to vCenter Server through the HyTrust CloudControl role. No direct access to vCenter Server is provided.

## NSX Manager user IDs
{: #vrw-iam-vsphere-nsx}

| User     | User ID      | Description |
|:---------|:-------------|:------------|
| IBM automation | `ibm_automation`  \n (NSX-T™ principal identity user) | Used post deployment to manage NSX VTEP IP addresses and to manage host and cluster configuration when hosts and clusters are added or removed. Also used to manage ESG configuration for add-on services that require public network access for licensing, activation, or usage reporting. |
| Privileged user | `admin` | Created for customer use only. |
{: caption="Table 2. NSX Manager user IDs" caption-side="top"}

## ESXi host user IDs
{: #vrw-iam-vsphere-esx}

| User     | User ID      | Description |
|:---------|:-------------|:------------|
| Privileged user | `ic4vroot` | Used post deployment to add more NFS storage, configure routes for that storage, and to run all server validation code. |
| Privileged user | `root` | Created for customer use only. |
{: caption="Table 3. ESXi host user IDs" caption-side="top"}

## Active Directory user IDs
{: #vrw-iam-vsphere-aduser}

| User     | User ID       | Description |
|:---------|:------------- |:------------|
| IBM automation | `automation` | Used to add a host or a VM for service, and to set up Microsoft® Active Directory and DNS entries. |
| Privileged user | `Administrator` | Default Windows® user |
| Privileged user | `cloudadmin` | Default user for customer to access vCenter Server |
| Privileged user | `cloudreadonly` | Read-only account for customer |
{: caption="Table 4. Active Directory user IDs" caption-side="top"}

## Microsoft Active Directory groups
{: #vrw-iam-vsphere-adgroup}

| User     | User ID       | Description |
|:---------|:------------- |:------------|
| Privileged user | `IC4v-vCenter` | vCenter Administration Group |
{: caption="Table 5. Microsoft Active Directory groups" caption-side="top"}

## Service user IDs
{: #vrw-iam-vsphere-serviceid}

| User ID                                    | Description |
|:-------------------------------------------|:----------- |
| `prod-BigIP-dynamicID-@domainName` | Used for installation and configuration of the F5 service. |
| `prod-Caveonix-dynamicID-@domainName` | Used for installation and configuration of the Caveonix RiskForesight service. |
| `prod-Fortigate-dynamicID-@domainName` | Used for installation and configuration of the FortiGate Security Appliance service. |
| `prod-FortigateVM-dynamicID-@domainName` | Used for installation and configuration of the FortiGate Virtual Appliance service. |
| `prod-HyTrustCC- shortID-@domainName` | Used for installation and configuration of the HyTrust CloudControl on {{site.data.keyword.cloud_notm}} service. |
| `prod-KMIPAdapter-dynamicID-@domainName` | Used for installation and configuration of the KMIP for VMware service. |
| `prod-SPPlus-dynamicID-@domainName` | Used for installation and configuration of the IBM Spectrum Protect Plus service. |
| `prod-Veeam-dynamicID-@domainName` | Used for installation and configuration of the Veeam service. |
| `prod-HCX-dynamicID-@domainName` | Used for installation and configuration of the VMware HCX service. |
{: caption="Table 6. Service user IDs" caption-side="top"}

where:
* `dynamicID` is the 8 - 10 characters that are generated dynamically during the service installation.
* `shortID` is the 5 characters that are generated dynamically during the service installation.
* `domainName` is the domain name of your instance.

**Next topic**: [NSX-T administration interface identity and access management](/docs/vmwaresolutions?topic=vmwaresolutions-vrw-iam-nsxt)

## Related links
{: #vrw-iam-vsphere-related}

* [IBM Cloud compliance programs](https://www.ibm.com/cloud/compliance)
* [HyTrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-htcc_considerations)
* [HyTrust DataControl](/docs/vmwaresolutions?topic=vmwaresolutions-htdc_considerations)
* [IBM Cloud Hyper Protect Crypto Services API](https://cloud.ibm.com/apidocs/hs-crypto)
