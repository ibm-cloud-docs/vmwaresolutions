---

copyright:

  years:  2016, 2025

lastupdated: "2025-03-11"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Troubleshooting
{: #opsprocs-trouble}

Review the following information to troubleshoot your {{site.data.keyword.vcf-auto}} instance issues. Your system administrators must identify the symptoms of the issue, determine which of the solution components are affected, research, and propose a fix or workaround, and test the fix.

* Identifying Symptoms. A number of potential causes might lead to the under-performance or nonperformance of your instance. The first step in efficient troubleshooting is to identify exactly what is going wrong. These symptoms might be reported from VMware vSphere® events and alarms, Operations Management in {{site.data.keyword.cloud}}, or reported from your Service Desk from one of your users.
* Isolating the affected components. After you identify the symptoms of the issue, you must identify the software or hardware components that are affected. Identify whether they might be causing the issue and those components that are not involved. Tools such as vCenter Operations Management in {{site.data.keyword.cloud_notm}} assist with this step.
* Proposing a fix or workaround. After you understand the symptoms and isolate the components, you can research possible fixes and workarounds. Your system administrators also use the {{site.data.keyword.cloud_notm}} portal, including the troubleshooting scenarios in this document, IBM ServiceNow, and VMware Knowledgebase. In addition, you can find many wikis and blogs that might help. For even quicker resolutions, Operations Management in {{site.data.keyword.cloud_notm}} includes a number of remediations for identified issues.
* Testing Possible Solutions. When you know the symptoms, involved components, and have a fix or workaround, your system administrators systematically test the solutions until the issue is resolved.

vSphere includes a user-configurable events and alarms subsystem, which tracks events that occur throughout the vSphere environment and stores the data in log files and the vCenter database. This subsystem also enables system administrators to specify the conditions under which alarms are triggered. Alarms change state from warnings to more serious alerts as system conditions change, and can trigger automated alarm actions such as to email the system administrator team. This function is useful when you want to be informed, or take immediate action, when certain events or conditions occur for a specific inventory object, or group of objects.

More tools such as those incorporated into the Operations Management on {{site.data.keyword.cloud_notm}} architecture provide greater assistance with; identifying symptoms, isolating the affected components and proposing a fix or workaround.

## Guidelines
{: #opsprocs-trouble-guidelines}

The following guidelines are considered best practices for troubleshooting your {{site.data.keyword.vmwaresolutions_short}} issue.
* Approach troubleshooting and problem-solving systematically.
* Are the symptoms related to; availability, usage, or configuration:
   *  Availability - These symptoms relate to the availability of hardware and software components and are typified by a no response. Often high availability (HA) design masks these issues so that they do not impact your workloads and users directly.
   * Usage - These symptoms relate to capacity and performance and are typified by slow-running or in-ability to load. Proactively managing capacity drastically reduces these issues.
   * Configuration - These issues are typically discovered in the provision of new services or as a result to applying a change. Incorrect settings can surface as either availability or usage symptoms. For example, an incorrect IP address is displayed as an availability issue, whereas low virtual machine (VM) RAM settings cause usage symptoms.
* Try to isolate the issue to a component in the environment.
* Take notes so you can trace your steps.
* Understand and document you software versions.
* Document your subnet and IP address usage, including VIP and NAT addresses.
* Have diagrams of your network. You need a number of diagrams that show the physical (underlay) and logical (overlay) layers.
* Understand any recent changes to the environment.
* Research the impact of the fix; do not lock yourself out of any management interfaces.
* Ensure that you have backups of all key components in case they need to be reloaded or reset.
* Do not change more than one thing at a time.
* Document each change and its result.
* When you open a support request, ensure that you document carefully and provide pertinent information. Be clear in the symptoms that you are seeing and identify the components that you believe are faulty. Ensure that you use the correct terminology. Try to minimize any confusion or ambiguity in your choice of words.
* vSphere ESXi and VMware vCenter® configuration files control the behavior of the system. Most configuration file settings are set during installation, but can be modified after installation.
* Log files capture messages that are generated by the kernel and different subsystems and services. vSphere ESXi and vCenter services maintain separate log files. Understand where they are located and how they can be accessed.
* Understand how to use popular system administration tools for help in diagnostics.

## Troubleshooting with log files
{: #opsprocs-trouble-logs}

Log files are an excellent source of information to troubleshoot issues. However, the number of log files and the vast number of entries in each log make it difficult to diagnose. [Location of log files for VMware products (1021806)](https://knowledge.broadcom.com/external/article?legacyId=1021806){: external} details where these log files are located in the VMware environment. Due to the number of log files and the vast number of entries in each log, consider the tools in the Operations Management on {{site.data.keyword.cloud_notm}} to help capture and analyze event logs.

## Troubleshooting common scenarios
{: #opsprocs-trouble-common}

In an aid to isolating the affected components, this documentation on troubleshooting common scenarios is classified into the following categories.

* Virtual machines - these troubleshooting topics provide guidance to potential issues on VMs.
* Hosts  - troubleshooting topics that provide guidance on vSphere ESXi host issues.
* Storage - troubleshooting topics that provide guidance on resolving vSAN and NFS storage issues.
* Network - troubleshooting topics that provide guidance on resolving network issues.
* vCenter - troubleshooting topics that provide guidance on resolving vCenter issues.
* Licenses - troubleshooting topics that provide guidance on resolving license issues, typically related to clients who have their own licenses to {{site.data.keyword.cloud_notm}}.

| Title | Description |
|-------|-------------|
| Generic VM troubleshooting | For more information, see [Troubleshooting virtual machines](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/troubleshooting-virtual-machines-vSphereVirtualMachineAdministration.html){: external}. |
| VM performance issues | You can troubleshoot the symptoms of VM performance issues, including guest OS starting slowly, applications that experience poor performance, applications that take a long time to start, or applications become unresponsive. |
| Recover orphaned VM | Orphaned VMs are VMs that exist in the vCenter database, but are not recognized by the vSphere ESXi host. For more information about recovering orphaned VMs, see [Recover orphaned virtual machines](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/troubleshooting-virtual-machines-vSphereVirtualMachineAdministration/recover-orphaned-virtual-machines-in-the-vsphere-web-client-vSphereVirtualMachineAdministration.html){: external}. |
| VM does not power on | For more information, see [Troubleshooting a virtual machine that is unable to power on (2001005)](https://knowledge.broadcom.com/external/article?legacyId=2001005){: external}. |
| VM does not power on after cloning or deploying from a template | [Deploying Virtual Machines](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/deploying-virtual-machines-vSphereVirtualMachineAdministration.html){: external} looks at issues that affect a VM after it is cloned or deployed from a template. |
| Old VM network devices | For VM network devices that are not kept up-to-date, network performance and application performance might be impacted. For more information about deploying a new virtual network device and driver, see [Choosing a network adapter for your virtual machine (1001805)](https://knowledge.broadcom.com/external/article?legacyId=1001805){: external}. |
| Virtual Machine Memory Limit | Memory limits are often used. However, if a guest OS cannot access the memory that it needs, the applications inside the guest OS might perform poorly. For more information about resolving the issue, see [Configuring resource allocation settings](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-resource-management-6-7/configuring-resource-allocation-settings-vSphereResourceManagement.html){: external}. |
| VM snapshots | While snapshots are useful, the quantity and age of a VM's snapshots directly impact the performance of the VM. For more information about resolving the issue, see [Consolidate snapshots](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/managing-virtual-machines-vSphereVirtualMachineAdministration/using-snapshots-to-manage-virtual-machines-vSphereVirtualMachineAdministration/consolidate-snapshots-vSphereVirtualMachineAdministration.html){: external}. |
| VM logging | When logging is not configured correctly the capacity of the datastore might be adversely impacted. For more information about resolving the issue, see [Configuring logging levels for the guest OS](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-monitoring-and-performance-6-7/system-log-files-monitoring/configuring-logging-levels-for-the-guest-operating-system-monitoring.html){: external}. |
| Troubleshooting network connection issues | Symptoms can include VM fails to connect to the network, or no network connectivity to or from a single VM. For more information about resolving the issue, see [Troubleshooting virtual machine network connection issues (1003893)](https://knowledge.broadcom.com/external/article?legacyId=1003893){: external}.  |
| Determining whether multiple virtual CPUs are causing performance issues  | These issues can include poor transfer speeds when they copy data to or from a VM, if backup jobs timeout or are slow, or a VM performs poorly.  |
| A VM was powered off or restarted  | For more information, see [Determining why a virtual machine was powered off or restarted (1019064)](https://knowledge.broadcom.com/external/article?legacyId=1019064){: external}. |
| One or more of your VMs has a poor response time | Performance issues can be caused by CPU constraints, memory over commitment, storage latency, or network latency. |
{: class="simple-tab-table"}
{: caption="Virtual machine troubleshooting" caption-side="bottom"}
{: #table1}
{: tab-title="Virtual machines"}
{: tab-group="trbl-scenarios"}

| Title | Description |
|-------|-------------|
| ESXi commands | For an overview of the command‐line interfaces in vSphere, the ESXi Shell commands, and the vCLI (VMware® vSphere Command‐Line Interface) commands, see [Getting started with vSphere command-line interfaces](https://vdc-download.vmware.com/vmwb-repository/dcr-public/bc4fa31a-40ac-4aa9-a6a1-7171d1fff7f4/740990ee-4d65-4627-a9d4-0f046cb78aec/vsphere-esxi-vcenter-server-67-command-line-interface-getting-started-guide.pdf){: external}. |
| vSphere HA Host States | If vCenter reports a vSphere HA host state that indicates an error condition on the host, these issues must be remediated. These issues can prevent vSphere HA from restarting VMs after a failure. For more information, see [Troubleshooting vSphere HA host states](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-hosts-host-management/troubleshooting-vsphere-ha-host-states-host-management.html){: external}. |
| vSphere ESXi host is in a nonresponding state | A nonresponding state includes `Not Responding`, `Disconnected`, or the VMs on the host show as `Unavailable` in vCenter. For more information about troubleshooting a vSphere ESXi host that is in a nonresponding state, see [ESX/ESXi hosts do not respond and is grayed out (1019082)](https://knowledge.broadcom.com/external/article?legacyId=1019082){: external}. |
| When you power on a VM, you see a `File not found` error | For more information, search through the [Broadcom Support Portal](https://support.broadcom.com/){: external}. |
| VM Performance issues | Performance issues can be caused by CPU constraints, memory over commitment, storage latency, or network latency. |
| Bare metal server is down | When the bare metal server that is running vSphere ESXi is unresponsive or down, log in to the {{site.data.keyword.cloud_notm}} management UI or console and check the status. If required, open a case to get assistance with your bare metal server. For more information, see [Managing your support cases](/docs/account?topic=account-managing-support-cases&interface=ui). |
| vSphere ESXi host is in disconnected or a not responding state  | For more information, see [Troubleshooting an ESXi/ESX host in non responding state (1003409)](https://knowledge.broadcom.com/external/article?legacyId=1003409){: external}. |
| Purple diagnostic screen | Purple screen errors can signal a kernel panic. The vSphere ESXi kernel `vmkernel` triggers this safety measure in response to an event or error that is unrecoverable. An unrecoverable error means that continuing to run poses a high risk for the services and VMs. When the panic occurs and the vSphere ESXi host crashes, it ends all the services that run on it together with all the VMs hosted. The VMs are not gracefully shut down, but rather abruptly powered off. If the host is part of a cluster and you configured HA, these VMs are restarted on the other hosts in the cluster. For more information, search through the [Broadcom Support Portal](https://support.broadcom.com/){: external}. |
{: caption="Typical vSphere ESXi hosts troubleshooting" caption-side="bottom"}
{: #table2}
{: tab-title="Hosts"}
{: tab-group="trbl-scenarios"}
{: class="simple-tab-table"}

| Title | Description |
|-------|-------------|
| Storage troubleshooting | Issues can be caused by slow performance, unpredictable failures, disk corruption, or VM corruption. |
| vSAN troubleshooting | For more information, see [Failure handling in vSAN](https://techdocs.broadcom.com/us/en/vmware-cis/vsan/vsan/7-0/vsan-monitoring/handling-failures-and-troubleshooting-virtual-san/handling-failures-in-virtual-san/failure-handling-in-virtual-san.html){: external}.  |
| vSAN Disk Failure | For more information about how to identify a specific disk failure in a vSAN deduplication cluster, see [Identifying specific disk failure in a vSAN deduplication cluster (2149067)](https://knowledge.broadcom.com/external/article?legacyId=2149067){: external}. |
| Clear vSAN health issues | In the VMware vSphere Web Client Monitor page, you might see alerts and warnings that relate to vSAN Health issues. For more information about clearing these issues, see [Virtual SAN health alerts and warnings](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_vsan_alerts#trbl_vsan_alerts){: external}.|
| vSAN rebalance | If disks report errors in the health check that indicate the cluster is imbalanced and disks are high on space usage while others are low, and you must run a proactive rebalance. A manually initiated rebalance of the objects in a vSAN cluster begins. For more information about vSAN proactive rebalance and when it might be applicable, see [vSAN proactive rebalance (2149809)](https://knowledge.broadcom.com/external/article?legacyId=2149809){: external}. |
| Initiate vSAN health test | If you suspect an issue with vSAN, you can initiate a health test to verify that the cluster components are working as expected. Running the VM creation test creates a VM on each host in the cluster and then deletes it. If these tasks are successful, then the cluster components are working as expected and the cluster is functional. Then, network performance test is used to detect and diagnose connectivity issues and to ensure that the network bandwidth between the hosts is adequate. For more information, see [Proactive tests](https://techdocs.broadcom.com/us/en/vmware-cis/vsan/vsan/7-0/vsan-monitoring/monitoring-vsan-skyline-health/proactive-tests-on-vsan-cluster.html){: external}. |
| Monitoring vSAN performance | For more information, see [Monitoring vSAN performance](https://techdocs.broadcom.com/us/en/vmware-cis/vsan/vsan/7-0/vsan-monitoring/monitor-virtual-san-performance.html){: external}. Performance charts are available for clusters, hosts, physical disks, VMs, and virtual disks. |
| vSAN troubleshooting | For more information, see [Handling failures and troubleshooting vSAN](https://techdocs.broadcom.com/us/en/vmware-cis/vsan/vsan/7-0/vsan-monitoring/handling-failures-and-troubleshooting-virtual-san.html){: external}. |
{: caption="Typical storage troubleshooting" caption-side="bottom"}
{: #table3}
{: tab-title="Storage"}
{: tab-group="trbl-scenarios"}
{: class="simple-tab-table"}

| Title | Description |
|-------|-------------|
|  NSX Edge `/var/log` is getting full on active Edge | For more information, see [Troubleshooting disk space related issues: NSX for vSphere Nodes](https://knowledge.broadcom.com/external/article/317723/troubleshooting-disk-space-related-issue.html){: external}.  |
| Testing HCX bandwidth  | When you believe that you have a network bandwidth issue with HCX, use `perftest` to find the available bandwidth within the HCX tunnels. For more information, see [Steps to run perftest in HCX (56211)](https://knowledge.broadcom.com/external/article?legacyId=56211){: external}. Bidirectional tests are carried out for each `perftest`. For the pair of gateways, one is inside the source data center (on-premises), and the other one is in {{site.data.keyword.cloud_notm}}. The way `perftest` throughput works is to have the sender try to send as fast as the link can sustain. Therefore, for each test, you see a higher "sender" rate than the "receiver" rate. You can consider the "receiver" rate value as a one-way throughput result. |
| HCX troubleshooting | For more information, see [HCX troubleshooting](/docs/vmwaresolutions?topic=vmwaresolutions-hcxclient-troubleshooting). |
| HCX syncing state with 0% progress and 0 bytes with status error | [HCX - Health Check and Best Practices](https://knowledge.broadcom.com/external/article?articleNumber=371941){: external}. |
| Poor VM network performance | Review the VM virtual NIC settings. VMware recommends VMXNET 3 virtual NICs for VMs as it is the most recent generation of paravirtualized NICs designed for performance. Check for compatibility of VMXNET 3 using the VMware compatibility list, and if supported change the virtual NIC for additional network performance. For more information, see [Troubleshooting networking](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-networking-6-7/troubleshooting-networking-configurations.html){: external}. |
{: caption="Typical network troubleshooting" caption-side="bottom"}
{: #table4}
{: tab-title="Network"}
{: tab-group="trbl-scenarios"}
{: class="simple-tab-table"}

| Title | Description |
|-------|-------------|
| Virtual Machine Console Access | For more information, see [Using a virtual machine console](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/managing-virtual-machines-vSphereVirtualMachineAdministration/using-a-virtual-machine-remote-console-vSphereVirtualMachineAdministration.html){: external}. |
| New vCenter Server Certificate Does Not Appear to Load | After the replacement of the default vCenter certificates, the new certificates might not appear to load. For more information, see [New vCenter Server certificate does not appear to load](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management/new-vcenter-server-certificate-does-not-appear-to-load-host-management.html){: external}. |
| vCenter Server Cannot Connect to Managed Hosts | After the replacement of the default vCenter certificates and restarting the system, VMware vCenter® Server Appliance (VCSA) cannot connect to managed hosts. For more information, see [vCenter Server cannot connect to managed hosts](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management/vcenter-server-cannot-connect-to-managed-hosts-host-management.html){: external}. |
| Cannot Configure vSphere HA When Using Custom SSL Certificates | After the installation of custom SSL certificates, attempts to enable vSphere HA fail. For more information, see [Cannot configure vSphere HA when you use custom SSL certificates](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management/vsphere-ha-and-custom-ssl-certificates-host-management.html){: external}. |
{: caption="Typical vCenter troubleshooting" caption-side="bottom"}
{: #table5}
{: tab-title="vCenter"}
{: tab-group="trbl-scenarios"}
{: class="simple-tab-table"}

| Title | Description |
|-------|-------------|
|  Incompatible or incorrect license configuration | For more information, see [Troubleshooting host licensing](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management/troubleshooting-host-licensing-host-management.html){: external}. |
|  VM does not power on | It ia possible that a license issue exists if you can't power on a VM on a vSphere ESXi host and you receive the ``The 60-day evaluation period of the host is expired or the license of the host is expired`` message. For more information, see [Unable to power on a virtual machine](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management/unable-to-power-on-a-virtual-machine-host-management.html){: external}. |
| A feature is unavailable or inability to change a configuration  | For more information, see [Unable to configure or use a feature](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management/unable-to-configure-a-feature-host-management.html){: external}.  |
{: caption="Typical license troubleshooting" caption-side="bottom"}
{: #table6}
{: tab-title="Licenses"}
{: tab-group="trbl-scenarios"}
{: class="simple-tab-table"}

## Related links
{: #opsprocs-trouble-links}

* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support#trbl_support)
* [vSphere troubleshooting overview](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/troubleshooting-overview-vSphereVirtualMachineAdministration.html){: external}
* [vSphere troubleshooting with logs](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/troubleshooting-overview-vSphereVirtualMachineAdministration/troubleshooting-with-logs-vSphereVirtualMachineAdministration.html){: external}
* [Operations management on {{site.data.keyword.cloud_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-opsmgmt-intro)
* [Support log gathering](https://knowledge.broadcom.com/external/article?legacyId=1010705){: external}
* [Monitoring events, alarms, and automated actions](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-monitoring-and-performance-6-7/monitoring-events-and-alarms-monitoring.html){: external}
* [vSphere System Log files](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-monitoring-and-performance-6-7/system-log-files-monitoring.html){: external}
* [Considerations about changing {{site.data.keyword.vcf-auto-short}} artifacts](/docs/vmwaresolutions?topic=vmwaresolutions-vcenter_chg_impact#vcenter_chg_impact)
