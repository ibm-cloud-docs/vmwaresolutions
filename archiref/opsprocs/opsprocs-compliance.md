---

copyright:

  years:  2016, 2021

lastupdated: "2021-10-28"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Compliance
{: #opsprocs-compliance}

Compliance is a set of requirements necessary to meet the minimum controls established by either a regulatory agency or industry best practices. Regularity compliance frameworks are usually broad frameworks that provide guidance on a broad range of technology, whereas industry best practices from vendors are typically technology specific to address technological risks.

For your vCenter Server® instance, it is recommended that security is managed by using a dedicated team post-deployment. This separation of duties augments and monitors the security posture of your instance. HyTrust® CloudControl™ can assist your teams with role-based separation.

HyTrust DataControl® and KeyControl™ can assist you in delivering workload protection such as at-rest encryption and geo-fencing. You might be interested in deploying the Caveonix RiskForesight™ service to assist you in, not only your compliance requirements but also cyber-risk and forensic management.

The VMware Security Hardening Guides provide prescriptive guidance on how to deploy and operate VMware products in a secure manner. Guides for vSphere are provided in an easy to use spreadsheet format, with rich metadata to allow for guideline classification and risk assessment. They also include script examples for enabling security automation. Comparison documents are provided if the list changes in guidance in successive versions of the guide.

Many of the controls that are documented in the VMware® Security Hardening Guides are incorporated in the {{site.data.keyword.vmwaresolutions_full}} reference architecture and therefore, automatically deployed, ensure that you tailor the security posture of the platform to your own needs and enterprise policy. The VMware Security Hardening Guides provide the technology-specific controls that are required for you to complete this review. Caveonix RiskForesight automates this compliance task and provides additional regulatory agency guidance.

vRealize Operations Manager provides monitoring of VMware objects for violations against the compliance rules in the vSphere Security Configuration Guide. The compliance alerts trigger on the vCenter Server instance, hosts, virtual machines, distributed port groups, or distributed switches, allowing the investigation of the compliance violation. For Health Insurance Portability and Accountability Act (HIPAA) and Payment Card Industry Data Security Standard (PCI DSS) compliance, you can download vRealize Operations Manager Compliance Packs from the VMWare Solutions Exchange website, licensed, and installed. These Compliance Packs provide Alerts, policies, and Reports to validate the vSphere resources against the HIPAA and PCI hardening guides.

## Related links
{: #opsprocs-compliance-links}

* [FortiGate Security Appliance](/docs/vmwaresolutions?topic=vmwaresolutions-fsa_considerations)
* [FortiGate Virtual Appliance](/docs/vmwaresolutions?topic=vmwaresolutions-fortinetvm_considerations)
* [F5 BIG-IP](/docs/vmwaresolutions?topic=vmwaresolutions-f5_considerations)
* [HyTrust CloudControl](/docs/vmwaresolutions?topic=vmwaresolutions-htcc_considerations)
* [HyTrust DataControl](/docs/vmwaresolutions?topic=vmwaresolutions-htdc_considerations)
* [HyTrust KeyControl](/docs/vmwaresolutions?topic=vmwaresolutions-htkc_considerations)
* [Caveonix RiskForesight](/docs/vmwaresolutions?topic=vmwaresolutions-caveonix_considerations)
* [Operations Management on {{site.data.keyword.cloud_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-opsmgmt-intro)
* [VMware security hardening guides](https://www.vmware.com/security/hardening-guides.html){: external}
