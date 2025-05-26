---

copyright:

  years:  2023, 2025

lastupdated: "2025-05-24"

keywords: vmware cloud foundation, IBM Cloud, vpc, faq

subcollection: vmwaresolutions

content-type: faq

---

{{site.data.keyword.attribute-definition-list}}

# FAQ about {{site.data.keyword.vcf-vpc-short}}
{: #vpc-vcf-faq}

## I am not used to {{site.data.keyword.vcf-vpc-short}} and it uses new terms for me, where can I get more information?
{: #vpc-vcf-faq-vcf-glossary}
{: faq}

You can use the VMware Cloud Foundation™ documentation for most Day 2 operations. For more information, see [Getting started with VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/5-2/getting-started-with-vcf-5-2.html){: external}.

Exceptions apply, some of which are documented in this FAQ. If you need assistance for the administration of your {{site.data.keyword.vcf-vpc}} instance, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

To understand the terms used in VMware Cloud Foundation, see [VMware Cloud Foundation glossary](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/5-2/getting-started-with-vcf-5-2/cloud-foundation-glossary.html){: external}.

## How can I reduce or expand my {{site.data.keyword.vcf-vpc-short}} instance capacity?
{: #vpc-vcf-faq-expanding-capacity}
{: faq}

You can add or remove hosts to the cluster by using the VMware Solutions console. The minimum number of hosts per cluster is 4 and the maximum is 25.

Adjust the VMware Cloud Foundation management and workload host pool sizes when you deploy the instance.
{: note}

## Can I have more than one VI Workload Domains in my {{site.data.keyword.vcf-vpc-short}} instance?
{: #vpc-vcf-faq-domains-limitations}
{: faq}

Currently, only one VI Workload Domain is supported.

## Can I have more than a cluster per Workload Domain?
{: #vpc-vcf-faq-domains-clusters}
{: faq}

Currently, only one cluster per Domain is supported. This limitation is valid for both Management and Workload Domains.

## How do I keep my {{site.data.keyword.vcf-vpc-short}} instance software up to date?
{: #vpc-vcf-faq-vcf-updates}
{: faq}

SDDC Manager automates the entire system lifecycle, that is, from configuration and provisioning to upgrades and patching. SDDC Manager is connected to the VMware Depot after initial provisioning. You can select the bundles to download and you can apply updates and upgrades on your own.

Before you complete an update, review the release notes and the FAQ section.

## What is the Async Patch tool and how can I use it with my {{site.data.keyword.vcf-vpc-short}} instance?
{: #vpc-vcf-faq-async-patch}
{: faq}

You can use the Async Patch tool to apply critical patches to certain VMware Cloud Foundation components (VMware NSX Manager, VMware vCenter Server, and VMware ESXi) outside of {{site.data.keyword.vcf-vpc-short}} releases.

For example, you can use the Async Patch tool to get a vCenter Server patch that addresses a critical security issue as described in a VMware Security Advisory (VMSA). You can use the Async Patch tool to download the patch and upload it to the internal LCM repository on the SDDC Manager appliance. Then, you use the SDDC Manager UI to apply the patch to your instance.

As the {{site.data.keyword.vcf-vpc-short}} instance does not provide you with the credentials to log in to VMware software depot, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support). The {{site.data.keyword.cloud_notm}} Support team can provide you access to these Async Patch bundles.
{: important}

For more information, see [Async Patch tool](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/ap-tool-4-5.html){: external}.

## How do I keep the Aria Suite software in my {{site.data.keyword.vcf-vpc-short}} instance up to date?
{: #vpc-vcf-faq-aria-updates}
{: faq}

In {{site.data.keyword.vcf-vpc-short}}, VMware Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager) provides lifecycle management capabilities for Aria Suite components and VMware Workspace ONE Access, including automated deployment, configuration, patching, and upgrade, and content management across these products. Aria Suite Lifecycle Manager is deployed as part of the automation.

For more information about the Aria Suite supported upgrade paths in VMware Cloud Foundation, see [vRealize Suite (Aria Suite) install and upgrade paths on VMware Cloud Foundation](https://knowledge.broadcom.com/external/article?legacyId=88829){: external}.

## How do I manage certificates in Aria Suite installations?
{: #vpc-vcf-faq-aria-certificates}
{: faq}

For Aria Suite (formerly vRealize Suite) certificates, you must manually generate self-signed certificates in Aria Suite Lifecycle Manager (formerly vRealize Suite Lifecycle Manager).

For more information about how to generate self-signed certificates in vRealize Suite Lifecycle Manager (currently Aria Lifecycle Manager) 8.8.2P6, see [Replace the certificate of the vRealize Suite Lifecycle Manager instance](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/administering/vrealize-suite-lifecycle-manager-in-cloud-foundation-admin/vrealize-suite-lifecycle-manager-implementation-admin/replace-the-certificate-of-the-vrealize-suite-lifecycle-manager-instance-in-first-region-admin.html){: external}.

## How do I manage certificates in SDDC manager?
{: #vpc-vcf-faq-sddc-certificates}
{: faq}

You can use the SDDC Manager UI to manage certificates in a {{site.data.keyword.vcf-vpc-short}} instance, including integrating a certificate authority, generating and submitting certificate signing requests (CSR) to a certificate authority, and downloading and installing certificates.

For more information, see [Managing certificates in VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/administering/certificate-management-admin.html){: external}.

Starting with the VMware Cloud Foundation 4.4 release, SSH Service on ESXi hosts is disabled on new and upgraded VMware Cloud Foundation deployments. You must enable the SSH service for each ESXi host.
{: important}

## Can I add edge nodes to an NSX Edge Cluster?
{: #vpc-vcf-faq-nsx-edge-nodes}
{: faq}

In {{site.data.keyword.vcf-vpc-short}} instances, the high availability setting for and Tier 0 Gateway is set as Active-Standby and uses HA VIP. For this reason, the process that is documented in [Add edge nodes to an NSX edge cluster](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/administering/deploying-nsx-edge-clusters-admin/add-edge-nodes-to-an-nsx-edge-cluster-admin.html){: external} cannot be used.

When you deploy the solution, it is recommended to select a large enough NSX and edge node size.

## Can I deploy more clusters in another zone in my {{site.data.keyword.vpc_short}} instance?
{: #vpc-vcf-faq-vpc-zones}
{: faq}

Currently, {{site.data.keyword.vcf-vpc-short}} instances support {{site.data.keyword.vcf-vpc-short}} deployments with a Single Availability Zone. One vCenter Server is deployed to the Management Domain and that vCenter and its ESXi hosts provide the compute capacity to all management components for the SDDC, such as the SDDC Manager, vCenter for the Workload Domain and the NSX Manager clusters for management and workload domains.

## What storage options do I have with my {{site.data.keyword.vcf-vpc-short}} instance?
{: #vpc-vcf-faq-storage}
{: faq}

Currently, for {{site.data.keyword.vcf-vpc-short}} instances, all principal and supplemental storage that is deployed as part of automation is vSAN storage only.

## What are the password policies and how do I manage passwords in {{site.data.keyword.vcf-vpc-short}}?
{: #vpc-vcf-faq-passwords-vcf}
{: faq}

The initial passwords for your {{site.data.keyword.vcf-vpc-short}} instance are randomly generated as part of the provisioning and starting procedure.

During initial deployment, the VMware Solutions automation creates an IBM automation account that is named **ibm_admin**, which will be used only to get your updated password. If you changed the initial password, retrieving the updated password is necessary for running Day 2 operations, such as adding or removing hosts.

It's recommended not to change the **ibm_admin** account password.
{: important}

However, if you changed it, you must follow these steps so that you can complete the Day 2 operations successfully:

1. Go to the {{site.data.keyword.vcf-vpc-short}} instance details page.
2. Click the **Access information** tab and scroll down to the **SDDC Manager** section.
3. Under the **IBM Automation** account, click **Update password** and enter your updated **ibm_admin** password.

For more information about the supported password policies in VMware Cloud Foundation, see [Configuring password complexity policies in VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/vmware-cloud-foundation-operations-4-5/password-policy-configuration-operations/configuring-password-complexity-policies-for-vmware-cloud-foundation-operations.html#GUID-22C6746A-6703-47E5-B17A-313EC959EC62){: external}.

You can rotate and update some of these passwords by using the password management functions in the SDDC Manager UI. You can rotate passwords for the following accounts:

* The accounts used for service consoles, such as the ESXi root account.
* The single sign-on administrator account.
* The default administrative user account used by virtual appliances.
* Service accounts that are automatically generated during powering on, host commissioning, and workload creation.

   Service accounts have a limited set of privileges and are created for communication between products. Passwords for service accounts are randomly generated by SDDC Manager. You cannot manually set a password for the service accounts. To update the credentials for service accounts, you can rotate the passwords.

To provide optimal security and proactively prevent any passwords from expiring, rotate passwords every 80 days.

For more information, see:

* [Password management](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/administering/manage-passwords-admin.html){: external}
* [Password policy configuration for VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/vmware-cloud-foundation-operations-4-5/password-policy-configuration-operations.html){: external}

## I have an issue with my {{site.data.keyword.vcf-vpc-short}} passwords, what can I do?
{: #vpc-vcf-faq-passwords}
{: faq}

Passwords are shown on the **Access information** tab. These passwords are the passwords that were randomly generated during the provisioning. If you changed the passwords post initial provisioning and you have password issues, you can use SDDC Manager to get these passwords for the components.

SSH into the SDDC manager by using user `vcf`. You can view the passwords by using one of the following mechanisms:

* Using the `lookup_passwords` command on the SDDC manager virtual machine. You can run the command in the following ways:

   * Run the command: `lookup_passwords -u username@domain -p password -e entityType -n pageNo -s pageSize` providing proper values to arguments.
   * Use `lookup_passwords -h` to view help information, which lists details about each of the arguments. Run the command and enter the value when prompted: `lookup_passwords`

* Using password management SDDC APIs:

   1. Request a bearer token to access the APIs: `curl -X POST -H "Content-Type: application/json" -d '{"username": "username@domain","password": "password"}' --insecure https://localhost/v1/tokens | json_pp`
   2. Run the lookup API: `curl -X GET -H "Content-Type:application/json" -H  "Authorization: Bearer <token value>"  'localhost/v1/credentials?resourceType=PSC' | json_pp`

      For more information, see [{{site.data.keyword.vcf-vpc-short}} API reference](https://developer.broadcom.com/xapis/vmware-cloud-foundation-api/4.5.1/credentials/){: external}.

## How do I back up and restore {{site.data.keyword.vcf-vpc-short}} components?
{: #vpc-vcf-faq-operations-backups-vcf}
{: faq}

{{site.data.keyword.vcf-vpc-short}} system backups are configured to use SDDC manager. Backups are configured to use the folder `/nfs/vmware/vcf/nfs-mount/backup` on the SDDC manager. You can change this configuration post-deployment to fit your own backup requirements.

For more information about how to back up and restore {{site.data.keyword.vcf-vpc-short}}, see [Backup and restore of VMware Cloud Foundation](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/4-5/administering/backup-and-restore-of-cloud-foundation-admin.html){: external}.

## What are the best practices to operate {{site.data.keyword.vcf-vpc-short}}?
{: #vpc-vcf-faq-operations-best-practice}
{: faq}

For more information about best practices and step-by-step instructions to operate {{site.data.keyword.vcf-vpc-short}}, see [VMware Cloud Foundation operations guide](https://techdocs.broadcom.com/us/en/vmware-cis/vcf/vcf-5-2-and-earlier/5-2/vmware-cloud-foundation-operations-5-2.html){: external}.
