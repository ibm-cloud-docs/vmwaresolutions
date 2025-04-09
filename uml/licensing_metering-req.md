---

copyright:

  years:  2025

lastupdated: "2025-04-09"

keywords: licenses, usage meter, requirements

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Requirements for licensing and metering
{: #licensing_metering-req}

Broadcom requires {{site.data.keyword.IBM}} and {{site.data.keyword.cloud_notm}} customers to use new license keys and to use the VMware vCloud Usage Meter tool for compliance purposes. As an {{site.data.keyword.cloud}} customer, you must adopt these new license keys and you must deploy Usage Meter. No exceptions are allowed and the ability to use VMware software on {{site.data.keyword.cloud_notm}} might be revoked at any time if you do not meet these requirements.

The adoption of new licensing and metering is applicable to the {{site.data.keyword.cloud_notm}} commercial environments with VMware vSphere® 7 and later. If you are using an unsupported vSphere version, you must upgrade to vSphere 7 or later to become compliant.

As of May 2024, {{site.data.keyword.IBM_notm}} requires that you order sufficient capacity for the VMware vDefend™ Firewall (formerly VMware NSX  Firewall) add-on to represent your usage of vDefend Firewall functionality. If you do not meet this requirement, you must purchase the required quantity of vDefend Firewall add-on. For more information, see [VMware vDefend Firewall add-on](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons#vmware-add-ons-nsx-firewall).

Broadcom will release updates to Usage Meter from time to time. {{site.data.keyword.IBM_notm}} and {{site.data.keyword.IBM_notm}} customers must apply these updates in a timely manner.
{: important}

Depending on your use case, review the following information and complete the appropriate steps.

## VCF as a Service (formerly VMware as a Service)
{: #licensing_metering-req-vcfaas}

For VMware Cloud Foundation as a Service (VCF as a Service), you do not need to take any action as {{site.data.keyword.IBM_notm}} is the consumer of VMware licenses.

## {{site.data.keyword.vcf-auto-short}} (formerly VMware vCenter Server)
{: #licensing_metering-req-automated}

For your existing Automated instances, complete the following steps:

1. Obtain new Broadcom license keys and [retrieve VMware Cloud Foundation (VCF) license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses) from the VMware Solutions console.
2. Retrieve VMware add–on keys. For more information, see [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons).
3. Add new license keys to all VMware products and assign licenses to them as applicable. For more information, see [Managing VMware product licenses](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_manage).

For the {{site.data.keyword.vcf-auto-short}} offering, {{site.data.keyword.cloud_notm}} automation will install Usage Meter. After you apply the correct license keys to your instance, complete the following steps:

1. {{site.data.content.ol-intro-ui-vcfclassic}}
2. In the **{{site.data.keyword.vcf-classic}}** table, click an instance name.
3. On the **Summary** tab, click **Deploy Usage Meter**.
4. Click **Deploy**.

The deployment process might take some time to complete.

It is important to note that:

* You must have sufficient capacity in your environment to deploy the Usage Meter virtual machine (VM), which requires 2 vCPUs, 8 GB of memory, and 80 GB of disk.
* The Usage Meter VM is configured by automation to connect to a proxy server on the {{site.data.keyword.cloud_notm}} service endpoint network, which is `166.8.0.0/14`. Your firewalls must allow communication between your VMware management network and this network.

Starting on 11 April 2025, all new hosts or instances that you deploy will be provisioned by {{site.data.keyword.cloud_notm}} automation with new Broadcom license keys and will install and configure Usage Meter as needed.

## {{site.data.keyword.vcf-flex-short}} (formerly VMware vSphere)
{: #licensing_metering-req-flexible}

For your existing Flexible instances, complete the following steps:

1. Obtain new Broadcom license keys and [retrieve VMware Cloud Foundation (VCF) license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses) from the VMware Solutions console.
2. Retrieve VMware add–on keys. For more information, see [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons).
3. Add new license keys to all VMware products and assign licenses to them as applicable. For more information, see [Managing VMware product licenses](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_manage).

Then, to connect your instance to Usage Meter, complete the following steps:

1. Install Usage Meter in your non–automated environments. For more information, see [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy).
2. Configure Usage Meter to use the {{site.data.keyword.cloud_notm}} proxy server.

   {{site.data.keyword.cloud_notm}} provides a proxy server so that Usage Meter can connect to Broadcom over the {{site.data.keyword.cloud_notm}} private network. Unless you are running Usage Meter on-premises as part of the IBM Bridge to Cloud program, you can optionally configure Usage Meter to use this {{site.data.keyword.IBM_notm}} proxy server. Alternatively, you can configure Usage Meter to connect to Broadcom directly over the public network or through your own proxy server if you want. For more information, see [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config).
   {: important}

3. Register Usage Meter with {{site.data.keyword.cloud_notm}}. Complete this step to obtain the Usage Meter ID from Usage Meter and register it in the {{site.data.keyword.cloud_notm}} console. For more information, see [Registering Usage Meter with {{site.data.keyword.IBM_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register).
4. Add VMware products to Usage Meter. For more information, see [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add).

Starting on 11 April 2025, all new hosts that you deploy will be provisioned with new VCF license keys. You will obtain license keys as described in the previous steps. These new hosts must be covered by the Usage Meter that you deployed or by a new Usage Meter.

## {{site.data.keyword.vcf-vpc-short}} (formerly VMware Cloud Foundation)
{: #licensing_metering-vcf-vpc}

For your existing {{site.data.keyword.vcf-vpc-short}} instances, complete the following steps:

1. Obtain new Broadcom license keys and [retrieve VMware Cloud Foundation (VCF) license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses) from the VMware Solutions console.
2. Retrieve VMware add–on keys. For more information, see [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons).
3. Add new license keys to all VMware products and assign licenses to them as applicable. For more information, see [Managing VMware product licenses](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_manage).

Then, to connect your instance to Usage Meter, complete the following steps:

1. Install Usage Meter in your non–automated environments. For more information, see [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy).
2. Configure Usage Meter to use the {{site.data.keyword.cloud_notm}} proxy server.

   {{site.data.keyword.cloud_notm}} provides a proxy server so that Usage Meter can connect to Broadcom over the {{site.data.keyword.cloud_notm}} private network. Unless you are running Usage Meter on-premises as part of the IBM Bridge to Cloud program, you can optionally configure Usage Meter to use this {{site.data.keyword.IBM_notm}} proxy server. Alternatively, you can configure Usage Meter to connect to Broadcom directly over the public network or through your own proxy server if you want. For more information, see [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config).
   {: important}

3. Register Usage Meter with {{site.data.keyword.cloud_notm}}. Complete this step to obtain the Usage Meter ID from Usage Meter and register it in the {{site.data.keyword.cloud_notm}} console. For more information, see [Registering Usage Meter with {{site.data.keyword.IBM_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register).
4. Add VMware products to Usage Meter. For more information, see [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add).

Starting on 11 April 2025, all new hosts or instances that you deploy will be provisioned by {{site.data.keyword.cloud_notm}} automation with new Broadcom license keys. At some point in the future, the {{site.data.keyword.cloud_notm}} automation is expected to deploy Usage Meter to new instances automatically. Until then, you must deploy Usage Meter for any new instances that you create.

## Roll-your-own (RYO) servers deployed from the Classic Bare Metal order form
{: #licensing_metering-req-ryo}

For your existing instances, complete the following steps:

1. Obtain new Broadcom license keys and [retrieve VMware Cloud Foundation (VCF) license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses) from the VMware Solutions console.
2. Retrieve VMware add–on keys. For more information, see [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons).
3. Add new license keys to all VMware products and assign licenses to them as applicable. For more information, see [Managing VMware product licenses](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_manage).

Then, to connect your environment to Usage Meter, complete the following steps:

1. Install Usage Meter in your non–automated environments. For more information, see [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy).
2. Configure Usage Meter to use the {{site.data.keyword.IBM_notm}} Cloud proxy server.

   {{site.data.keyword.cloud_notm}} provides a proxy server so that Usage Meter can connect to Broadcom over the {{site.data.keyword.cloud_notm}} private network. Unless you are running Usage Meter on-premises as part of the IBM Bridge to Cloud program, you can optionally configure Usage Meter to use this {{site.data.keyword.IBM_notm}} proxy server. Alternatively, you can configure Usage Meter to connect to Broadcom directly over the public network or through your own proxy server if you want. For more information, see [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config).
   {: important}

3. Register Usage Meter with {{site.data.keyword.cloud_notm}}. Complete this step to obtain the Usage Meter ID from Usage Meter and register it in the {{site.data.keyword.cloud_notm}} console. For more information, see [Registering Usage Meter with {{site.data.keyword.IBM_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register).
4. Add VMware products to Usage Meter. For more information, see [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add).

Starting on 11 April 2025, all new hosts that you deploy will be provisioned with new VCF license keys. You will obtain license keys as described in the previous steps. These new hosts must be covered by the Usage Meter that you deployed or by a new Usage Meter.

## BYOL for VMware
{: #licensing_metering-req-byol}

If you are a BYOL (Bring Your Own License) user and if all hosts in your environment are licensed with your own licenses, {{site.data.keyword.IBM_notm}} does not require you to take any action as you are contracted directly with Broadcom.

However, if some of the hosts in your environment are licensed with {{site.data.keyword.IBM_notm}}-provided licenses, complete the following steps:

1. Obtain new Broadcom license keys and [retrieve VMware Cloud Foundation (VCF) license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses) from the VMware Solutions console.
2. Retrieve VMware add–on keys. For more information, see [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons).
3. Add new license keys to all VMware products and assign licenses to them as applicable. For more information, see [Managing VMware product licenses](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_manage).

   Assign {{site.data.keyword.IBM_notm}} licenses only to hosts for which you are paying {{site.data.keyword.IBM_notm}} for VMware Cloud Foundation (VCF) entitlement.
   {: important}

Then, to connect your mixed–licensing environment to Usage Meter, complete the following steps:

1. Install Usage Meter in your non–automated environments. For more information, see [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy).
2. Configure Usage Meter to use the {{site.data.keyword.cloud_notm}} proxy server.

   {{site.data.keyword.cloud_notm}} provides a proxy server so that Usage Meter can connect to Broadcom over the {{site.data.keyword.cloud_notm}} private network. Unless you are running Usage Meter on-premises as part of the IBM Bridge to Cloud program, you can optionally configure Usage Meter to use this {{site.data.keyword.IBM_notm}} proxy server. Alternatively, you can configure Usage Meter to connect to Broadcom directly over the public network or through your own proxy server if you want. For more information, see [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config).
   {: important}

3. Register Usage Meter with {{site.data.keyword.IBM_notm}}. Complete this step to obtain the Usage Meter ID from Usage Meter and register it in the {{site.data.keyword.cloud_notm}} console. For more information, see [Registering Usage Meter with {{site.data.keyword.IBM_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register).
4. Add VMware products to Usage Meter. For more information, see [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add).

## Broadcom license portability
{: #licensing_metering-req-broadcom}

{{site.data.keyword.IBM_notm}} does not require you to take any action as you are contracted directly with Broadcom. Do not mix your Broadcom licenses and {{site.data.keyword.IBM_notm}} licenses in the same environment.

## On-premises VMware licenses as part of the IBM Bridge to Cloud program
{: #licensing_metering-on-premises}

You must work with {{site.data.keyword.cloud_notm}} product management to obtain new Broadcom license keys, which include receiving new keys for products such as vSphere, VMware Avi Load Balancer, and vDefend Firewall. If needed, you can order new add-on keys and apply them to your VMware environment. Next, deploy one or more instances of Usage Meter to your environments to ensure that usage is reported to Broadcom.

For new licensed environments, you will continue to work with {{site.data.keyword.cloud_notm}} product management to obtain license keys and ensure that each environment is monitored by Usage Meter. You can connect these new environments to an existing Usage Meter or deploy a new Usage Meter.

To connect your environment to Usage Meter, complete the following steps:

1. Install Usage Meter in your non–automated environments. For more information, see [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy).
2. Configure Usage Meter. For more information, see [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config).
3. Register Usage Meter with {{site.data.keyword.IBM_notm}}. Complete this step to obtain the Usage Meter ID from Usage Meter and register it in the {{site.data.keyword.cloud_notm}} console. For more information, see [Registering Usage Meter with {{site.data.keyword.IBM_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register).
4. Add VMware products to Usage Meter. For more information, see [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add).

## Related links
{: #licensing_metering-req-related}

* [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config)
* [Registering Usage Meter with {{site.data.keyword.IBM_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register)
* [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add)
* [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons)
* [Retrieving VCF license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses)
* [Managing VMware product licenses](/docs/vmwaresolutions?topic=vmwaresolutions-licensing_manage)
