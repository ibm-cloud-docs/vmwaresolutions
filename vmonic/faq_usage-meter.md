---

copyright:

  years:  2025

lastupdated: "2025-10-09"

keywords: FAQ, usage meter, metering, licensing, vmware licensing

subcollection: vmwaresolutions

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQ for licensing and metering
{: #faq_usage-meter}

Find answers to frequently asked questions about Usage Meter.

## What does this announcement mean to me?
{: #faq_usage-meter-announce}
{: faq}

With the VMware® acquisition, Broadcom® is modifying license key renewals from perpetual to subscription license keys. If you are an {{site.data.keyword.cloud}} customer who is running {{site.data.keyword.cloud_notm}} for VMware on Classic or VMware Cloud Foundation (VCF) for VPC, you must act to maintain compliance with Broadcom license requirements for VMware Cloud Foundation by Broadcom. This action includes swapping old VMware keys to new VMware by Broadcom subscription keys and to install the VMware vCloud Usage Meter.

## What is Usage Meter?
{: #faq_usage-meter-what-is}
{: faq}

Usage Meter is a new virtual appliance that is designed to track VMware by Broadcom usage, and it must be installed on all VCF deployments. With this new model, the primary function of Usage Meter is to collect consumption data for VMware products within the {{site.data.keyword.cloud_notm}}.

## Why is Usage Meter needed?
{: #faq_usage-meter-why-needed}
{: faq}



It is important to understand and to emphasize that Usage Meter is the only and mandatory tool that VMware cloud service providers like {{site.data.keyword.IBM}} are authorized and required to use for metering. Usage Meter tracks usage of VMware Cloud Foundation, its components, and add-ons with VMware by Broadcom for core utilization. It generates comprehensive reports on what products are in use by customers. VCF product usage is metered and reported as required per the VMware cloud service provider program rules. VMware by Broadcom provides tools, appliances, and processes to meter product usage accurately for monthly reporting.

## As a customer of {{site.data.keyword.cloud_notm}} for VMware, do I need Usage Meter?
{: #faq_usage-meter-do-i-need}
{: faq}

Yes, if you are running a client-managed offering on {{site.data.keyword.cloud_notm}}, it is required for you to ensure accurate tracking of usage and billing on every account. This statement does not apply to VMware Cloud Foundation (VCF) as a Service. Usage Meter provides comprehensive support for independent clusters and effectively measure core utilization in the new VMware by Broadcom solutions. This means that the Usage Meter software manages and tracks the usage of separate clusters efficiently, while also metering core utilization accurately by {{site.data.keyword.IBM_notm}} customers.

## I'm using VCF as a Service; does this information apply to me?
{: #faq_usage-meter-vcf-aas}
{: faq}

No. You do not need to do anything as {{site.data.keyword.IBM_notm}} is the consumer of VMware licenses.

## Does this information apply to all {{site.data.keyword.cloud_notm}} for VMware offerings?
{: #faq_usage-meter-ic4v-offerings}
{: faq}

No. This information applies only to {{site.data.keyword.cloud_notm}} for VMware roll-your-own (RYO), {{site.data.keyword.vcf-classic-short}}, and {{site.data.keyword.vcf-vpc-short}} accounts. Fully managed {{site.data.keyword.vcf-aas}}, {{site.data.keyword.vcf-aas}} single-tenant, and {{site.data.keyword.vcf-aas}} multitenant accounts are automatically updated by {{site.data.keyword.IBM_notm}}.

## I'm using VMware NSX-V; does this information apply to me?
{: #faq_usage-meter-nsx-v}
{: faq}

Licensing and metering are not supported for NSX-V. However, Broadcom requires {{site.data.keyword.IBM_notm}} and {{site.data.keyword.cloud_notm}} customers to use new license keys and to use Usage Meter for compliance purposes. Therefore, if you are running NSX-V, you must migrate to VMware NSX-T™ to become compliant. For more information, see [NSX-V to NSX-T migration overview](/docs/vmwaresolutions?topic=vmwaresolutions-v2t-overview).

## I'm using vSphere 6; does this information apply to me?
{: #faq_usage-meter-vsphere-6}
{: faq}

The adoption of new licensing and metering is applicable to VMware vSphere® 7 and later. Broadcom requires {{site.data.keyword.IBM_notm}} and {{site.data.keyword.cloud_notm}} customers to use new license keys and to use Usage Meter for compliance purposes. Therefore, if you are using an earlier, unsupported vSphere version, you must upgrade to vSphere 7 or later to become compliant. For more information, see [Upgrading vCenter Server vSphere software from vSphere 6.5 or 6.7 to 7.0](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vsphere_70_upgrade).

## I'm not using vCenter Server to manage hosts; how do I add my hosts to Usage Meter?
{: #faq_usage-meter-add-hosts}
{: faq}

Usage Meter cannot connect directly to hosts. You must deploy vCenter Server, connect it to your hosts, and connect Usage Meter to vCenter Server.

## What should I do now?
{: #faq_usage-meter-what-to-do-now}
{: faq}

You are required to order VMware vDefend™ Firewall (formerly VMware NSX® firewall) license keys to cover any firewall usage that you have. You cannot enter these license keys into NSX yet; however it is recommended that you order these license keys to ensure a smooth transition process as you act on 11 April 2025. For more information, see [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons).

## What should I do next?
{: #faq_usage-meter-what-to-do-next}
{: faq}

For accurate cluster and core utilization metering, all {{site.data.keyword.cloud_notm}} for VMware customers must have newly supported Broadcom license keys and the Usage Meter deployed and functioning in their VMware environment.

Starting on 8 August 2025, you must swap any older keys to the new license keys with expiration dates in your environment. For more information, see the following VMware vCloud Usage Meter documentation:

* [Release Notes](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/release-notes.html){: external}
* [Deployment and Administration Guide](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/vcloud-usage-meter-4-8-deployment-and-administration-guide-4-8.html){: external}
* [Security Guide](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/usage-meter-security-guide-4-8.html){: external}

## When do I have to complete this action?
{: #faq_usage-meter-when-to-complete}
{: faq}

By 1 November 2025, all customer accounts must have the new Broadcom license keys installed and Usage Meter v9.0.1 deployed.

Accounts that have not updated to current license keys will be out of compliance and are risked being out of support and in violation of the {{site.data.keyword.cloud_notm}} Services Agreement. If not addressed, violations can result in account disruptions.
{: attention}

## Can {{site.data.keyword.IBM_notm}} do this all for me?
{: #faq_usage-meter-can-ibm-do-it}
{: faq}

No. The {{site.data.keyword.cloud_notm}} for VMware added value is to provide customers with a simple to use automated way of enabling a core foundation of a complete software-defined data center (SDDC) in the cloud. Bare metal systems, storage, networking, and software are all configured at initialization time. After they are in place, {{site.data.keyword.IBM_notm}} gives full management of the virtual environment to the customer to manage. {{site.data.keyword.IBM_notm}} does not go into the customer environment as it is secure to the customer.

## How do I install Usage Meter in my environment?
{: #faq_usage-meter-how-to-install}
{: faq}

All existing customers receive an email about how to install and register Usage Meter. Detailed information and instructions on what actions are required are available in the {{site.data.keyword.cloud_notm}} for VMware Solutions documentation.

## Can Usage Meter be deployed in offline mode?
{: #faq_usage-meter-offline-mode}
{: faq}

No. All Usage Meters must be deployed and registered in online mode. Broadcom expects all Usage Meters to run in online mode and to communicate reporting of usage as required by Broadcom. Customers that cannot run Usage Meter in online mode can contact their respective sales team members about commercial (contract) options to support their offline or isolated business.

{{site.data.keyword.cloud_notm}} can provide a proxy service on the private network to connect your Usage Meter even if your cloud environment does not have public connectivity.

## What information does Usage Meter collect and how is it protected?
{: #faq_usage-meter-collect-protect}
{: faq}

Usage Meter fully supports collection of usage data on separate clusters and core utilization metering only. Its utilization is necessary to meter the environment effectively. Implementing a new instance of Usage Meter that can report valid license keys for VMware Cloud Foundation products is mandatory.

For more information about data privacy, see [VMware vCloud Usage Meter Data Privacy and Sharing Guidelines](https://www.vmware.com/docs/usage-meter-data-privacy-guide){: external}.

For more information about VMware vCloud Usage Meter, see:

* [Release Notes](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/release-notes.html){: external}
* [Deployment and Administration Guide](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/vcloud-usage-meter-4-8-deployment-and-administration-guide-4-8.html){: external}
* [Security Guide](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/usage-meter-security-guide-4-8.html){: external}

## Is there a price or cost change as a result of deploying Usage Meter?
{: #faq_usage-meter-price}
{: faq}

No. There are no extra license key charges for deploying and registering the Usage Meter appliance.

To run the Usage Meter software on VMware, the following hardware infrastructure resources are required:
* 2 vCPU cores
* 8 GB of memory
* 80 GB of storage

## I am a new customer, do I need to install and update Usage Meter?
{: #faq_usage-meter-new-customer}
{: faq}

Yes. This statement applies to you if you are a VMware VCF for Classic or bare metal roll-your-own customer. Usage Meter must be installed and maintenance releases must be applied as they become available.

## Do I need to migrate my workloads or update my workload data?
{: #faq_usage-meter-migrate-workloads}
{: faq}

No; changes to virtual environments are not required. This is only an update of the license key and the mechanism for tracking usage of these license keys. There is no impact to the VMware environment and workloads are not affected.

## Do I need to back up my {{site.data.keyword.cloud_notm}} for VMware environment before I add the new keys and deploy Usage Meter?
{: #faq_usage-meter-backup}
{: faq}

No special backup is needed; continue to use your typical data protection and backup process. If you need a backup or disaster recovery solution, {{site.data.keyword.IBM_notm}} provides options for data protection. For more information, contact your {{site.data.keyword.IBM_notm}} Sales representative.

## As an {{site.data.keyword.cloud_notm}} for VMware customer, am I required to do anything?
{: #faq_usage-meter-existing-customer}
{: faq}

Yes. {{site.data.keyword.cloud_notm}} for VMware requires customers to comply with vendor software agreements as part of the {{site.data.keyword.cloud_notm}} Services Agreement. If you do not provide usage tracking through Usage Meter, you risk falling out of support and compliance and incur billing errors on usage. For more information, see the [{{site.data.keyword.cloud_notm}} Services Agreement](https://www.ibm.com/support/customer/csol/terms/?id=Z126-6304&cc=us&lc=en){: external}.

IBM Cloud Services Agreement (CSA), and applicable attachments and transaction documents are the complete agreement under which customers can order Cloud Services. The services might consist of {{site.data.keyword.cloud_notm}} Services or other services to support use of Cloud Services that {{site.data.keyword.IBM_notm}} provides ({{site.data.keyword.IBM_notm}} products) or cloud or other services that a third-party such as Broadcom provides that customers acquire from {{site.data.keyword.IBM_notm}} (non-{{site.data.keyword.IBM_notm}} products).

## What security and compliance documentation is available for Usage Meter?
{: #faq_usage-meter-sec-compl-doc}
{: faq}

For more information, see the [VMware vCloud Usage Meter Security Guide](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/usage-meter/4-8/usage-meter-security-guide-4-8.html){: external}.

## What guidelines for Usage Meter data privacy and sharing are available?
{: #faq_usage-meter-privacy-sec}
{: faq}

For more information, see the [VMware vCloud Usage Meter Data Privacy and Sharing Guidelines](https://www.vmware.com/docs/usage-meter-data-privacy-guide){: external}.

## Are the VCF perpetual licenses still available for use?
{: #faq_usage-meter-vcf-perpetual}
{: faq}

The VMware Cloud Foundation (VCF) perpetual licenses are entitled to upgrade only until version 5.x. The perpetual licenses are not entitled to upgrade to major versions later than version 5.x. To be compliant, you need to update to a new VCF subscription offer and deploy Usage Meter in your environment

## Are VMware VCF add-on products such as vDefend, included?
{: #faq_usage-meter-add-ons}
{: faq}

Yes. If you use a VMware add-on for VMware loud Foundation such as VMware vDefend Firewall (formerly VMware NSX Firewall), you must include new Broadcom subscription product keys when you are moving to Usage Meter. You must complete this action now if you are using VMware vDefend Firewall to be ready with the new Broadcom license keys. For more information about updating vDefend Firewall, see [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons).

## Where can I find more details about the Bridge Licensing Program?
{: #faq_licensing-bridge}
{: faq}

This program is limited to pre-approved customers. For more information, contact your {{site.data.keyword.IBM}} Sales representative.
{: restriction}

If you are currently using this program, you can open a support case by following these steps:

1. Go to the {{site.data.keyword.cloud_notm}} [Support Center](/unifiedsupport/supportcenter).
2. Log in with your **IBMid** account.
3. In the **Contact Support** section, click **Create a case**.
4. Under **Topic**, select **IBM Cloud On-Prem Bridge Licensing for VMware Cloud Foundation**.
5. Under **Subtopic**, select a subtopic that best fits your needs.
6. Complete all the required fields, upload any attachments, and click **Next**.

Your case is opened, and then reviewed by the {{site.data.keyword.IBM_notm}} Support team.

## How are my service license charges being calculated?
{: #faq_licensing-service-charges}
{: faq}

* For Caveonix RiskForesight™ installed on {{site.data.keyword.rw}} or Security and Compliance Readiness Bundle, each server requires a service license.
* For Entrust CloudControl™ and Entrust DataControl®, service licenses are charged per two CPUs. Dual servers require a single license each. Quad servers require two licenses each.
* For VMware HCX™ and VMware Aria® Operations™, service licenses are included as part of the {{site.data.keyword.vcf-classic-short}} license bundle.
* All other services have static service license charges that do not change based on the number of servers in the instance.

## Related links
{: #faq_usage-meter-links}

* [VMware add-ons for VMware Cloud Foundation](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-add-ons)
