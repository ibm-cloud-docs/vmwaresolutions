---

copyright:

  years:  2024, 2025

lastupdated: "2025-05-01"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Architecture pattern for integrating {{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection with VMware Cloud Foundation deployment in Classic
{: #arch-pattern-sccwpp}

This architecture pattern describes how to use {{site.data.keyword.cloud}} Security and Compliance Center Workload Protection with a {{site.data.keyword.vcf-auto}} with NSX-T instance on the {{site.data.keyword.cloud_notm}} classic infrastructure.

Security and Compliance Center Workload Protection offers functions to protect your Microsoft Windows® and Linux® virtual machines (VMs) that are hosted on your VMware® environment. These functions include compliance, vulnerability scanning, and threat detection.

Although Security and Compliance Center Workload Protection offers functions for your other {{site.data.keyword.cloud_notm}} services, these functions are not discussed in this pattern. For more information, see [Getting started with {{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection](/docs/workload-protection?topic=workload-protection-getting-started).

{{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection implements Sysdig Secure functions. Information that is provided by the Sysdig Secure documentation also applies to Workload Protection.
{: note}

After you provision an instance of the Security and Compliance Center Workload Protection service, you can deploy the Host Shield Agents on your Windows or Linux VMs. The agents collect data that is used for intrusion detection, posture management, and vulnerability scanning capabilities.

## Overview of Security and Compliance Center Workload Protection for VMware workloads
{: #arch-pattern-sccwpp-overview}

Security and Compliance Center Workload Protection enables the following three practices for your VMware workloads:

* Threat detection - Threat detection is managed by defining policies, which consist of rules to detect and respond to security violations, suspicious behavior, or anomalous activities within your Windows and Linux VMs. Security and Compliance Center Workload Protection provides customizable, prebuilt policies, which are created and maintained by Sysdig’s Threat Research team. These policies can detect and prevent various security threats, such as: malware, intrusions, and DDoS attacks. The results of these policies can be viewed in Events. For more information, see [Events Feed](https://docs.sysdig.com/en/docs/sysdig-secure/threats/activity/events-feed/){: external}.
* Vulnerabilities - Security and Compliance Center Workload Protection provides a highly accurate view of the vulnerability risks of your Windows and Linux VMs. The views include rich details on your vulnerability risks, such as: CVSS vector, score, fix age, and insights from multiple expert feeds including the NIST National Vulnerability Database (NVD) and VulnDB.
* Compliance - Posture management provides the framework that includes controls, guidelines, benchmarks, and standards for managing compliance. With Security and Compliance Center Workload Protection, you can evaluate your Windows and Linux VMs against several CIS benchmarks such as CIS Distribution Independent Linux Benchmark and compliance policies or CIS Windows Server 2019/2022 Benchmarks. For more information, see [Analyzing compliance postures from detection to remediation](/docs/workload-protection?topic=workload-protection-compliance). Typical use cases include:
   * Check the current compliance status against predefined policies to understand the magnitude of the compliance gap.
   * Demonstrate to an auditor the compliance status at a specific point in time, by creating a report of the compliance status of the VMs.

## Pattern for integrating Security and Compliance Center Workload Protection
{: #arch-pattern-sccwpp-vcs}

The following diagram shows an example of integrating a vCenter Server with NSX-T instance on {{site.data.keyword.cloud_notm}} classic infrastructure with {{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection.

![Pattern for integrating Security and Compliance Center Workload Protection ](../../images/arch-pattern-scwpp-vcs.svg "Security and Compliance Center Workload Protection."){: caption="Security and Compliance Center Workload Protection" caption-side="bottom"}

This architecture pattern is summarized as follows:

1. The agents, which are installed on your Windows or Linux VMs, collect data that is used for threat detection, posture management, and vulnerability scanning. For more information, see [Sysdig Agents](https://docs.sysdig.com/en/docs/sysdig-secure/integrations-for-sysdig-secure/data-sources/sysdig-agents/){: external}. The Sysdig Host Shield Agents provides threat detection, posture management, and vulnerability scanning. For more information, see:
   * [Managing the Workload Protection agent on Windows Servers](/docs/workload-protection?topic=workload-protection-agent-deploy-windows).
   * [Install Shield on Windows Hosts](https://docs.sysdig.com/en/sysdig-secure/host-shield-linux/){: external}.
   * [Protecting Linux hosts](/docs/workload-protection?topic=workload-protection-protecting-linux-hosts).
   * [Install Shield on Linux Hosts](https://docs.sysdig.com/en/sysdig-secure/host-shield-linux/){: external}.
2. Your DNS servers need to be able to resolve the Security and Compliance Center Workload Protection endpoint URLs. Configure your DNS servers to use {{site.data.keyword.cloud_notm}} DNS resolvers, if needed.
3. Firewall rules enable the downloading of the agents from the Internet and HTTPS connectivity to the Security and Compliance Center Workload Protection private endpoints. For more information about configuring firewall rules, see [Add a Gateway Firewall Policy and Rule](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-1/administration-guide/security/gateway-firewall/add-a-gateway-firewall-policy-and-rule.html){: external}.
4. Source Network Address Translation (SNAT) rules allow your VMs overlay IP addresses to be translated to {{site.data.keyword.cloud_notm}} supplied IP addresses that can be used on the Internet. For more information about configuring SNAT rules, see [Configure NAT/DNAT/No SNAT/No DNAT/Reflexive NAT](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-1/administration-guide/network-address-translation/configure-an-nsx-nat.html){: external}.
5. The {{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection instance. For more information, see:
   * [Provisioning an instance](/docs/workload-protection?topic=workload-protection-provision)
   * [Regions](/docs/workload-protection?topic=workload-protection-regions)
   * [Protecting Linux hosts](/docs/workload-protection?topic=workload-protection-protecting-linux-hosts)
   * [Endpoints](/docs/workload-protection?topic=workload-protection-endpoints)

## Considerations
{: #arch-pattern-sccwpp-considerations}

When you design or deploy this architecture pattern, consider the following information:

* You require only a single SNAT IP address for all your VMs hosted in your virtual data center to communicate with the Security and Compliance Center Workload Protection instance.
* This pattern describes firewall policies and SNAT configured on the T0. Use of the T1 is also possible.
* This pattern does not use the distributed firewall. For more information about configuring the distributed firewall, see [FQDN Filtering](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/vmware-nsx/4-1/administration-guide/security/distributed-firewall/fqdn-filtering.html){: external}.

## Related links
{: #arch-pattern-sccwpp-links}

* [Getting started with {{site.data.keyword.cloud_notm}} Security and Compliance Center Workload Protection](/docs/workload-protection?topic=workload-protection-getting-started)
* [Sysdig Secure](https://docs.sysdig.com/en/docs/sysdig-secure/){: external}
