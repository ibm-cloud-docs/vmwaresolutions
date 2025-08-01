---

copyright:

  years: 2016, 2025

lastupdated: "2025-08-01"

keywords: IBM Cloud for VMware Solutions, getting started, vmware solutions offerings, services for vmwaresolutions, vmwaresolutions use cases

subcollection: vmwaresolutions

content-type: tutorial
account-plan: paid
completion-time: 2h

---

{{site.data.keyword.attribute-definition-list}}

# Getting started with VMware Solutions
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-completion-time="2h"}

In this {{site.data.keyword.vmwaresolutions_full}} getting started tutorial, we take you through the process of ordering an instance and some services for it.
{: shortdesc}

## Before you begin
{: #getting-started-prereqs}

Before you start to work with {{site.data.keyword.vmwaresolutions_short}}, review the following important information about browser requirements, users accounts, deployment options, and services.

### Browser requirements
{: #getting-started-browser-req}

For more information, see [Browsers](/docs/overview?topic=overview-prereqs-platform#browsers-platform).

### User accounts
{: #getting-started-user-accts}

You need an {{site.data.keyword.cloud_notm}} account and an {{site.data.keyword.cloud_notm}} infrastructure account. These accounts must meet certain requirements.

| Account | Description |
|:------- |:---------- |
| IBMid | By using the **IBMid**, you can have a single login username for all IBM products and services that you use, including {{site.data.keyword.cloud_notm}}. {{site.data.keyword.vmwaresolutions_short}} is provided as an infrastructure solution in the {{site.data.keyword.cloud_notm}} catalog. To access the {{site.data.keyword.vmwaresolutions_short}} console, you must have an **IBMid**. \n \n To use your **IBMid** to log in to the {{site.data.keyword.vmwaresolutions_short}} console, you must associate the **IBMid** with an {{site.data.keyword.cloud_notm}} account. When you log in to the console for the first time, you are asked to associate your existing **IBMid** with an {{site.data.keyword.cloud_notm}} account, or to sign up for a new {{site.data.keyword.cloud_notm}} account. The new {{site.data.keyword.cloud_notm}} account is automatically associated with your **IBMid**. You go through this process only one time. \n \n If you have problems when you associate your **IBMid** with an {{site.data.keyword.cloud_notm}} account, see [Why is my password incorrect?](/docs/account?topic=account-ts_logintoibm) |
| {{site.data.keyword.cloud_notm}} account | To order and use {{site.data.keyword.cloud_notm}} services, an {{site.data.keyword.cloud_notm}} account is required. Billing information is associated with the {{site.data.keyword.cloud_notm}} account. The price of the physical and virtual infrastructure and the resulting licenses are charged to your {{site.data.keyword.cloud_notm}} account. |
| {{site.data.keyword.cloud_notm}} infrastructure account | If you have an {{site.data.keyword.cloud_notm}} infrastructure account, link it with your {{site.data.keyword.cloud_notm}} account by following the procedure in [Upgrading your account](/docs/account?topic=account-upgrading-account). If you do not have an {{site.data.keyword.cloud_notm}} infrastructure account, request one by following the procedure in [The {{site.data.keyword.cloud_notm}} infrastructure account](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts#signing_required_accounts-infra). Then, link it to your {{site.data.keyword.cloud_notm}} account by following the previous procedure. \n \n When you link your {{site.data.keyword.cloud_notm}} infrastructure account with your {{site.data.keyword.cloud_notm}} account, you can use the combined IaaS (infrastructure as a service) and PaaS (platform as a service) resources, and access these resources from a single login. It also provides you with a single invoice for all the PaaS and IaaS resources that you use. |
{: caption="Required user accounts" caption-side="bottom"}

### Deployment offerings
{: #getting-started-depl-offerings}

Review and choose your deployment offering.

| Deployment offering | Description |
|:------------------- |:----------- |
| [{{site.data.keyword.vmware-service_short}}](/docs/vmwaresolutions?topic=vmwaresolutions-vmware-aas-overview) | This offering provides the VMware Cloud Director platform as a managed service. {{site.data.keyword.IBM}} performs the configuration, hosting, operations, and lifecycle management of the VMware® by Broadcom software so you can quickly deploy your VMware-based cloud computing environments. |
| {{site.data.keyword.vcf-classic}} | - [Automated](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview): This offering deploys a VMware virtual environment by using custom compute, storage, and network resources to best fit your business needs. \n - [Flexible](/docs/vmwaresolutions?topic=vmwaresolutions-vs_vsphereoverview): This offering provides a customizable virtualization service that combines VMware-compatible bare metal servers, hardware components, and licenses, to build your own IBM-hosted VMware environment. \n - [{{site.data.keyword.cr}}](/docs/vmwaresolutions?topic=vmwaresolutions-cr_overview): This offering provides air-gapped protection, immutable storage, and rapid recovery of applications and data for ransomware protection. |
| [{{site.data.keyword.vcf-vpc}}](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-ovw) | This offering is a full-stack Software Defined Data Center (SDDC) solution that is built on VMware Cloud Foundation™. It delivers compute, storage, networking, management automation, and security in a single platform on {{site.data.keyword.bm_is_full}}. |
{: caption="Deployment offerings" caption-side="bottom"}

### Add-on services
{: #getting-started-add-on-services}

Review and choose services for your deployment.

#### Security and compliance services
{: #getting-started-serv-sec-compl}

The following table describes the security and compliance services that are available.

| Service name | Description |
|:------------ |:----------- |
| [Caveonix RiskForesight](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_considerations) | This service manages cyberrisk and compliance risk with proactive monitoring and automated defense controls to protect against threats and to meet industry or government regulations. |
| [FortiGate Virtual Appliance](/docs/vmwaresolutions?topic=vmwaresolutions-fortinetvm_considerations) | This service deploys a pair of FortiGate Virtual Appliances to your environment, which can help you reduce risk by implementing critical security controls within your virtual infrastructure. |
| [KMIP for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_standalone_considerations) | This service provides a highly available service to manage encryption keys that are used by VMware in {{site.data.keyword.cloud_notm}}. By using the runtime capability, you can manage encryption keys and to maintain the associations between the client credentials and the encryption keys. |
| [Juniper vSRX](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-overview) | This service provides security and networking services at the perimeter or edge in virtualized private or public cloud environments. Within a VMware infrastructure, vSRX runs as a VM within the VMware vSphere® environment. The vSRX provides a complete Next-Generation Firewall (NGFW) solution. |
| [F5 BIG-IP](/docs/vmwaresolutions?topic=vmwaresolutions-f5_considerations) | This service provides intelligent L4-L7 load balancing and traffic management services at a local and global scale, robust network and web application firewall protection, and secure and federated application access. |
{: caption="Security and compliance services" caption-side="bottom"}

#### Data resiliency services
{: #getting-started-serv-dr}

The following table describes the data resiliency services that are available.

| Service name | Description |
|:------------ |:----------- |
| [Veeam](/docs/vmwaresolutions?topic=vmwaresolutions-veeamvm_overview) | This service integrates directly with your VMware hypervisors to help your enterprise achieve high availability. You can control both the backup and restore of all VMs for your infrastructure from the Veeam console. |
| [Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr) | This service provides replication and disaster recovery capabilities, which can be integrated into the deployment offerings to protect and recover data in your VMware virtual environment on {{site.data.keyword.cloud_notm}}. |
| [VMware Cloud Director Availability for Disaster Recovery](/docs/vmware-service?topic=vmware-service-tenant-vcda-dr) | This service delivers simple, secure, and cost-effective onboarding, migration, and disaster recovery support for VCF as a Service. |
| [ProtectIO](/infrastructure/vmware-solutions/console/newserviceentry/ProtectIO/vcs) | This service provides a robust disaster recovery solution while leveraging the latest cloud economics for an attractive Total Cost of Ownership. |
{: caption="Data resiliency services" caption-side="bottom"}

#### Migration services
{: #getting-started-serv-mig}

The following table describes the migration services that are available.

| Service name | Description |
|:------------ |:----------- |
| [VMware Cloud Director Availability for Migration](/docs/vmware-service?topic=vmware-service-tenant-vcda) | This service delivers simple, secure, and cost-effective onboarding, migration, and disaster recovery support for VCF as a Service. |
| [HCX](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_considerations#hcx_considerations) | This service can extend the networks of on-premises data centers into {{site.data.keyword.cloud_notm}}, which allows VMs to be migrated to and from the {{site.data.keyword.cloud_notm}} without any conversion or change. |
| [PrimaryIO Migrations](https://www.primaryio.com/#){: external} | This service offers various capabilities to facilitate the cloud journey for organizations with an investment in VMware. |
{: caption="Migration services" caption-side="bottom"}

#### Featured workload solutions
{: #getting-started-serv-feat-sol}

The following table describes the featured workload solutions services that are available.

| Service name | Description |
|:------------ |:----------- |
| [Dizzion](/docs/vmwaresolutions?topic=vmwaresolutions-dizzion-overview) | This service provides more service-level choices, multicloud integration, compliance, protection, and simplified management for the teams that are in charge with environment optimization. |
| [{{site.data.keyword.IBM_notm}} Security Services for SAP](/docs/vmwaresolutions?topic=vmwaresolutions-managing-ss-sap) | This service offers a cybersecurity solution to automate the monitoring and protection of SAP applications on {{site.data.keyword.cloud_notm}}, and to keep workloads compliant and secure from inside and outside threats. |
{: caption="Featured workload solutions" caption-side="bottom"}

#### Management tools
{: #getting-started-serv-other}

The following table describes the management tools that are available.

| Service name | Description |
|:------------ |:----------- |
| [VMware Aria Operations and VMware Aria Operations for Logs](/docs/vmwaresolutions?topic=vmwaresolutions-vrops_overview) | This service deploys the tools of VMware Aria® Operations™ and VMware Aria Operations™ for Logs Enterprise Edition, which help you operate and monitor the performance, health, and capacity of your IBM-hosted, dedicated VMware environment. |
{: caption="Other services" caption-side="bottom"}

## Accessing the VMware Solutions console
{: #getting-started-step1}
{: step}

The VMware Solutions console is the user interface where you order and manage your deployments. Each deployment is managed as an instance in the console. The console is a stand-alone user interface that is separate from the {{site.data.keyword.slportal}}.

To access the {{site.data.keyword.vmwaresolutions_short}} console:
1. Go to https://cloud.ibm.com/vmware.
2. Log in to the console with your **IBMid**.

## Setting up your environment for your first order
{: #getting-started-step2}
{: step}

Decide upon a deployment offering, which is managed as an instance in the console, and then ensure that your environment is ready for your order. Follow the instructions in the **Before you begin** section on the ordering page. The instructions might vary depending on the instance type that you select.

For more information about how to set up your environment for your first order, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).

## Ordering an instance
{: #getting-started-step3}
{: step}

After you set up your environment properly, begin the ordering process.

For more information about how to order an instance, see the following topics based on your selected deployment:
* [Ordering {{site.data.keyword.vcf-aas}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-ordering)
* [Ordering Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-req)
* [Ordering Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances-req)
* [Ordering {{site.data.keyword.cr}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance_reqs)
* [Ordering {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-order-req)

## Viewing the instance
{: #getting-started-step4}
{: step}

After you place an instance order in **Step 3**, the deployment of the instance starts automatically. You can track the status of the deployment by viewing the instance details. When the instance deployment is completed, you can view the summary and detailed information of the instance and its services on the instance details page too.

For more information about how to view the instance you ordered, see the following topics based on your selected deployment:
* [Viewing {{site.data.keyword.vcf-aas}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-tenant-viewing-sites)
* [Viewing Automated instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_viewinginstances)
* [Viewing Flexible instances](/docs/vmwaresolutions?topic=vmwaresolutions-vs_viewinginstances)
* [Viewing and deleting {{site.data.keyword.cr}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr-view-delete-instance)
* [Viewing {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-viewing)
