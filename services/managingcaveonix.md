---

copyright:

  years:  2016, 2022

lastupdated: "2022-02-08"

keywords: Caveonix console, Caveonix RiskForesight license, login Caveonix console

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Managing Caveonix RiskForesight
{: #managingcaveonix}

## Accessing the Caveonix RiskForesight console
{: #managingcaveonix-access-console}

To manage the Caveonix RiskForesight™ service, you must access the Caveonix RiskForesight console by completing the following steps:

1. Use the {{site.data.keyword.cloud}} infrastructure VPN or a jump server to allow access to the IP address of the Caveonix RiskForesight virtual machine (VM). You can find the IP address on the service details page for Caveonix RiskForesight in the {{site.data.keyword.vmwaresolutions_short}} console. Complete the following steps:
   1. Create a VPN password from the {{site.data.keyword.cloud_notm}} infrastructure customer portal.
   2. Log in to the data center VPN portal by using the {{site.data.keyword.cloud_notm}} infrastructure VPN credentials.
   3. Add the IP address and the hostname mapping into the `hosts` file from your local computer. Use the following format:

      ```javascript
      RiskForesight_VM_IP_Address      RiskForesight_FQDN
      ```
2. To access the Caveonix RiskForesight console, click **View RiskForesight console** on the service details page for Caveonix RiskForesight. Then, log in by using the credentials that are listed on the same service details page.

## Applying updates to Caveonix RiskForesight
{: #managingcaveonix-update}

You are responsible for maintaining Caveonix RiskForesight to keep it updated to the most recent version. You can download the required updates from the [Caveonix Service Provider Portal](https://support.caveonix.com/login){: external}.

To obtain a login ID for the Caveonix Service Provider Portal for product release notes and downloads, open a support case with the [IBM Cloud Support Center](https://cloud.ibm.com/unifiedsupport/supportcenter){: external}.

Provide the instance name that Caveonix is installed on, your company name, and an email address for your administrator for the support case. IBM Cloud Support will acquire the credentials for your login and email your administrator.

## Updating Caveonix RiskForesight licenses
{: #managingcaveonix-updating-lic}

This information does not apply to Caveonix Foresight that is installed on VMware® Regulated Workloads or Security and Compliance Readiness Bundle instances.
{: note}

The Caveonix RiskForesight license is valid for five years. You can update the Caveonix RiskForesight license when it expires by using the following procedure:
1. Order a new Caveonix RiskForesight license and copy it to the Caveonix RiskForesight console. For more information, see [Procedure to order Caveonix RiskForesight licenses](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_license_ordering#caveonix_license_ordering-procedure).
2. Delete the expired license from the **Caveonix RiskForesight Licenses** table in the {{site.data.keyword.vmwaresolutions_short}} console. For more information, see [Procedure to delete Caveonix RiskForesight licenses](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_license_managing#caveonix_license_managing_procedure-delete).

## Related links
{: #managingcaveonix-related}

* [Caveonix RiskForesight overview](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_considerations)
* [Ordering Caveonix RiskForesight](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_ordering)
