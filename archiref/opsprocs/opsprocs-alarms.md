---

copyright:

  years:  2016, 2025

lastupdated: "2025-04-14"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Alarms
{: #opsprocs-alarms}

## Introduction
{: #opsprocs-alarms-intro}

VMware vSphere® includes an events and alarms subsystem, which tracks events that occur in the vSphere environment and makes this information available in vCenter. The following terminology is used in this subsystem.

### Events
{: #opsprocs-alarms-events}

Events are records of system or user actions that occur on objects in vCenter such as hosts and virtual machines (VMs). Event data includes details about the event such as who generated it, when it occurred, and what type of event it is. In the vSphere Web Client, event data is displayed in the Monitor tab.

The following are event classifications.
* Error - Indicates that an unrecoverable problem occurs in the system and ends the process or operation.
* Warning - Indicates a potential risk to the system, which needs to be fixed. This event does not end the process or operation.
* Information - Describes that the user or system operation is completed successfully.
* Audit - The audit log data includes information about what is the action, who did it, when it occurred, and the IP address of the user.

### Alarms
{: #opsprocs-alarms-alarms}

Alarms are notifications that are activated in response to an event, a set of conditions, or the state of an inventory object.

An alarm definition consists of the following elements in the vSphere Client.
* Name and description - Provides an identifying label and description.
* Targets - Defines the type of object that is monitored.
* Alarm Rules - Defines the event, condition, or state that triggers the alarm and defines the notification severity. It also defines operations that occur in response to triggered alarms.
* Last modified - The last modified date and time of the defined alarm.

Alarms have the following severity levels.
* Normal – green.
* Warning – yellow.
* Alert – red.

### Alarm definition
{: #opsprocs-alarms-def}

Alarm definitions are associated with the object that is selected in the inventory and monitors the type of inventory objects that are specified in its definition.

An alarm definition consists of the following elements.
* Name and description - Provides an identifying label and description.
* Alarm type - Defines the type of object that is monitored.
* Triggers - Defines the event, condition, or state that triggers the alarm and defines the notification severity.
* Tolerance thresholds (Reporting) - Provides more restrictions on condition and state triggers thresholds that must be exceeded before the alarm is triggered.
* Actions - Defines operations that occur in response to triggered alarms. VMware provides sets of predefined actions that are specific to inventory object types.
* Alarm Actions - Alarm actions are operations that occur in response to the trigger. For example, you can send an email notification to one or more administrators when an alarm is triggered.
* Acknowledge triggered alarms - After you acknowledge an alarm, the alarm actions are discontinued. Alarms are not cleared, or reset when acknowledged. Acknowledging an alarm signals to other users know that you are taking ownership of the issue.
* Reset triggered alarms - An alarm that is triggered by an event might not reset to a normal state if vCenter does not retrieve the event that identifies the normal condition. In such cases, reset the alarm manually.
* Preconfigured vSphere alarms - The vSphere event and alarm subsystem has a number of default alarms, which monitor the operations of vSphere inventory objects. You must set up actions only for these alarms.

## Alarm setup workflow
{: #opsprocs-alarms-setup-workflow}

VMware provides preconfigured vCenter alarms that are described in the following tables, but they are set with an action to display within the vCenter web client only. Configure the SMTP server details and then set the alert actions to send an email to the system administrators for the following alarms only initially so not to inundate the system administrator team. For more information, see [Send email as an alarm action](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-monitoring-and-performance-6-7/monitoring-events-and-alarms-monitoring/set-an-alarm-monitoring/specify-alarm-actions-in-the-vsphere-web-client-monitoring/send-email-as-an-alarm-action-in-the-vsphere-web-client-monitoring.html){: external}.

The setting alarms workflow is as follows.
* Configure the SMTP server details.
* Configure the alert actions for clusters, hosts, datastores, and critical virtual appliances, such as VMware vCenter®, PSC, NSX Manager, and controllers.
   * Cluster - a VMware high availability (HA) error.
   * Hosts - CPU status, memory status, storage status, hardware status that is, voltage, temperature, or power status changes.
   * Datastore  - low on available disk space.
   * Critical virtual appliance -  CPU usage, memory usage, disk latency
* Use the proactive daily task to review the following information.
   * Review the alerts sent - are the alerts required?
   * Review the alerts that weren't sent - do you need to know about them?
   * Review the metrics - are the metrics correct? For example, confirm that CPU usage must be set to 75% rather than 90% now that you understand your baseline.
   * Do you need to configure your own alarms?
   * Do you need to include virtual machines?

## Typical alarm workflow
{: #opsprocs-alarms-alarm-workflow}

After setup, review the following example of an alarm workflow, typically adopted by system administrators, when an alarm is triggered.

1. A host has an alarm set to monitor CPU usage and the alarm has an alarm action to send an email to the administrators when the alarm is triggered, as described in the previous section.
2. The host CPU usage spikes, triggering the alarm, which sends an email to the administrators.
3. One of the administrators logs in to vCenter and acknowledges the triggered alarm to allow the other administrators know that the problem is being addressed, and to prevent the alarm from sending more email messages. However, the alarm is still visible in the system.
4. The administrator finds the cause of the CPU spike and rectifies.
5. The alarm is reset automatically.

## Preconfigured alarms - standard
{: #opsprocs-alarms-preconfigured-std}

* Alarm name - The name of the alarm visible in vCenter.
* Guidance - {{site.data.keyword.vmwaresolutions_short}} guidance on the use of this alarm.
* More Information - Additional information available from IBM or VMware to help with the resolution of these alarms when they are triggered.

The following table describes the standard preconfigured alarms.

| Alarm name | Guidance | Details |
|:---------- |:-------- |:------- |
| Host connection and power state | Configure to send an email one time when set to Not Responding or Standby. | ["Host connection and power state" alarm when an ESXi host wakes from standby](https://knowledge.broadcom.com/external/article?articleNumber=322793){: external} |
| Host CPU usage | Configure to send an email one time when host CPU usage > 90% for 5 mins. | [Knowledge - KB0012707 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=342e3d6adbc5730030c93a1b7c961976){: external} |
| Host memory usage | Configure to send an email one time when host memory usage > 95% for 5 mins. | [Knowledge - KB0012712 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=30110ee2db49730030c93a1b7c96194f){: external} |
| Virtual machine CPU usage | Configure to send an email one time when VM CPU usage > 90% for 5 mins for critical appliances. | [Setting an alarm for virtual machine hard disk usage](https://knowledge.broadcom.com/external/article?articleNumber=322857){: external} |
| Virtual machine memory usage | Configure to send an email one time when VM memory usage > 95% for 5 mins for critical appliances. | [Memory usage alarm triggers for certain types of Virtual Machines in ESXi](https://knowledge.broadcom.com/external/article?articleNumber=318857){: external} |
| Datastore usage on disk | For vSAN, configure to send email one time when datastore usage > 70%. For non-vSAN, configure to send email one time when datastore usage > 85%. | [Knowledge - KB0012713 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=ddb3422edb89730030c93a1b7c9619f6){: external} |
| Virtual machine CPU ready | Configure to send email one time when VM CPU ready > 2000 ms for 5 mins for critical appliances. | [Knowledge - KB0012718 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=7056426adb0d730030c93a1b7c9619e6){: external} |
| Virtual machine total disk latency | Configure to send email one time when VM total disk latency > 30 ms for 5 mins for critical appliances. | [Knowledge - KB0012729 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=15dddea2db857300d5a971198c961995){: external} |
| Virtual machine disk commands canceled | Do not set initially. Consider for critical appliances at the second stage. | No additional information |
| Virtual machine disk reset | Do not set initially. Consider for critical appliances at the second stage. | No additional information |
| License inventory monitoring | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [Troubleshooting licensing](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management.html){: external} |
| License user threshold monitoring | Not considered essential for notification. THe alarm is reviewed as part of proactive daily checks. | [Troubleshooting licensing](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management.html){: external} |
| License capacity monitoring | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [Troubleshooting licensing](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management.html){: external} |
| The host license edition is not compatible with the vCenter Server license edition | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [Troubleshooting host licensing](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management/troubleshooting-host-licensing-host-management.html){: external} |
| Timed out starting Secondary VM * | Not configured as it monitors VMware Fault Tolerance, which is not recommended for {{site.data.keyword.vcf-auto}} instances. | No additional information |
| No compatible host for Secondary VM | Not configured as it monitors VMware Fault Tolerance, which is not recommended for {{site.data.keyword.vcf-auto-short}} instances. | No additional information |
| Virtual machine Fault Tolerance state changed | Not configured as it monitors VMware Fault Tolerance, which is not recommended for {{site.data.keyword.vcf-auto-short}} instances. | No additional information |
| Virtual machine fault tolerance vLockStep interval status changed | Not configured as it monitors VMware Fault Tolerance, which is not recommended for {{site.data.keyword.vcf-auto-short}} instances. | No additional information |
| Host processor status | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host memory status | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host hardware fan status | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host hardware voltage | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host hardware temperature status | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host hardware power status | Configure to send an email one time when monitor changes from green to red.| [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host hardware system board status | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host battery status | Configure to send an email one time when monitor changes from green to red.| [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Status of other host hardware objects |  Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host storage status | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host IPMI System Event Log status | Not configured as it is not service impacting. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host Baseboard Management Controller status | Configure to send an email one time when monitor changes from green to red. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Host error * | Configure to send an email one time when monitor changes to error. | [Contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) |
| Virtual machine error * | Configure to send email one time when critical for critical appliances. | [Troubleshooting virtual machines](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/troubleshooting-virtual-machines-vSphereVirtualMachineAdministration.html){: external} |
| Host connection failure * | Configure to send an email one time when the event is `Cannot connect host - network error` or `Cannot connect host - timeout` or `Host connection lost`zs. | ["Host connection and power state" alarm when an ESXi host wakes from standby](https://knowledge.broadcom.com/external/article?articleNumber=322793){: external} |
| Unmanaged workload detected on SIOC-enabled datastore | Not configured as it is not service impacting. | [Unmanaged workload is detected on datastore running SIOC (1020651)](https://knowledge.broadcom.com/external/article?legacyId=1020651){: external} |
| Thin-provisioned volume capacity threshold exceeded | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support VASA storage. | No additional information |
| Datastore capability alarm | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support VASA storage. | No additional information |
| VASA provider disconnected | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support VASA storage. | No additional information |
| VASA Provider certificate expiration alarm | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support VASA storage. | No additional information |
| VM storage compliance alarm | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [VM storage compliance alarm (2061940)](https://knowledge.broadcom.com/external/article?legacyId=2061940){: external} |
| Datastore compliance alarm | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [Working with datastores](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-storage-6-7/working-with-datastores-in-vsphere-storage-environment.html){: external} |
| Refreshing CA certificates and CRLs for a VASA provider failed | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support VASA storage. | No additional information |
| Insufficient vSphere HA failover resources | Configure to send email one time when critical. | [Knowledge - KB0012739 v0.01](https://watson.service-now.com/nav_to.do?uri=kb_knowledge.do?sys_id=fe1f0beedb8db300d5a971198c96191a){: external} |
| vSphere HA failover in progress | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | No additional information |
| Cannot find vSphere HA primary agent | Configure to send email one time when unable to find or communicate with the HA primary agent. | [vSphere availability](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-5/vsphere-availability.html){: external} |
| vSphere HA host status  | Configure to send an email one time when: vSphere HA agent on a host has an error, vSphere HA detects a network-isolated host, vSphere HA detects a network-partitioned host, or vSphere HA detects a host failure. | [Troubleshooting vSphere HA host states](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview/troubleshooting-hosts/troubleshooting-vsphere-ha-host-states.html){: external} |
| vSphere HA virtual machine failover failed | Configure to send email one time when critical for critical appliances. | [Creating and using vSphere HA Clusters](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-availability/creating-and-using-vsphere-ha-clusters-vSphereAvailability.html){: external} |
| vSphere HA virtual machine monitoring action | Configure to send email one time when critical for critical appliances. | [Creating and using vSphere HA clusters](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-availability/creating-and-using-vsphere-ha-clusters-vSphereAvailability.html){: external} |
| vSphere HA virtual machine monitoring error | Configure to send email one time when critical for critical appliances. | [Creating and using vSphere HA clusters](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-availability/creating-and-using-vsphere-ha-clusters-vSphereAvailability.html){: external} |
| vSphere HA VM Component Protection could not power off a virtual machine | Configure to send email one time when critical for critical appliances. | [Creating and Using vSphere HA Clusters](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-availability/creating-and-using-vsphere-ha-clusters-vSphereAvailability.html){: external} |
| License error * |  Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Troubleshooting licensing](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management.html){: external} |
| Health status changed * | Configure to send an email one time if status changes to critical. | [Troubleshooting hosts](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-hosts-host-management.html){: external} |
| Storage DRS recommendation | Not considered essential for notification. Alarm is reviewed as part of proactive daily checks. | [DRS troubleshooting information](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-resource-management-6-7/drs-troubleshooting-information-vSphereResourceManagement.html){: external} |
| Storage DRS is not supported on a host | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [DRS troubleshooting information](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-resource-management-6-7/drs-troubleshooting-information-vSphereResourceManagement.html){: external} |
| Datastore cluster is out of space | Configure to send email one time when critical when disk usage is over 85%. | [Adding NFS storage to {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingnfs) |
| Datastore is in multiple data centers | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSphere Distributed Switch VLAN trunked status | Configure to send email one time when critical when not all the configured VLANs in the vSphere Distributed Switch were trunked by the physical switch. | [Enabling vSphere Distributed Switch health check in the vSphere Web Client (2032878)](https://knowledge.broadcom.com/external/article?legacyId=2032878){: external} |
| vSphere Distributed Switch MTU matched status  | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Enabling vSphere Distributed Switch health check in the vSphere Web Client (2032878)](https://knowledge.broadcom.com/external/article?legacyId=2032878){: external} |
| vSphere Distributed Switch MTU supported status | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Enabling vSphere Distributed Switch health check in the vSphere Web Client (2032878)](https://knowledge.broadcom.com/external/article?legacyId=2032878){: external} |
| vSphere Distributed Switch teaming matched status | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Enabling vSphere Distributed Switch health check in the vSphere Web Client (2032878)](https://knowledge.broadcom.com/external/article?legacyId=2032878){: external} |
| Virtual machine network adapter reservation status | Configure to send an email only if you enabled network adapter reservation. | [Configure bandwidth allocation for a virtual machine](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-networking-6-7/network-io-control/bandwidth-allocation-for-virtual-machine-traffic/configure-bandwidth-allocation-for-a-virtual-machine.html){: external} |
| Virtual machine Consolidation Needed status | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Using Snapshots To Manage Virtual Machines](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-single-host-management-vmware-host-client-6-7/virtual-machine-management-with-the-vsphere-host-client/managing-virtual-machines-in-the-vsphere-host-client/using-snapshots-to-manage-virtual-machines.html){: external} |
| Host virtual flash resource status | Host virtual flash is not supported in {{site.data.keyword.vcf-auto-short}} instances. | No additional information |
| Host virtual flash resource usage | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support host virtual flash. | [About Virtual Flash Resource](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-storage-6-7/using-flash-devices-with-esxi-hosts/using-virtual-flash-resource-in-vsphere-environment.html){: external} |
| Registration or unregistration of a VASA vendor provider on a vSAN host fails | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support VASA storage. | [Broadcom Compatibility Guide](https://compatibilityguide.broadcom.com/search?program=vasa&persona=live){: external} |
| Registration or unregistration of third-party IO filter storage providers fails on a host | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support VASA storage. | [Broadcom Compatibility Guide](https://compatibilityguide.broadcom.com/search?program=vasa&persona=live){: external} |
| Service Control Agent Health Alarm | Configure to send an email one time when component ID equal to sca and New status equal to red. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Identity Health Alarm | Configure to send an email one time when component ID equal to identity and New status equal to red. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| vSphere Web Client Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Enabling debug logging on the VMware vSphere 5.x/6.x/7.x/8.0 Web Client services](https://knowledge.broadcom.com/external/article/326324/enabling-debug-logging-on-the-vmware-vsp.html){: external} |
| ESX Agent Manager Health Alarm | Configure to send an email one time when component ID equal to `eam` and New status equal to `red`. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Message Bus Config Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Cis License Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Inventory Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| vCenter Server Health Alarm | Configure to send an email one time when component ID equal to vpxd and New status equal to red. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Database Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Data Service Health Alarm | Configure to send an email one time when component ID equal to vmware-dataservices-sca and New status equal to red. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| RBD Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| vService Manager Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Performance Charts Service Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Content Library Service Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| Transfer Service Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| VMware vSphere ESXi Dump Collector Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks.| [VMware ESXi Dump Collector Support](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-networking-6-7/introduction-to-vsphere-networking/esxi-dump-collector-support.html){: external} |
| VMware vAPI Endpoint Service Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| VMware System and Hardware Health Manager Service Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Troubleshooting with Logs](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-virtual-machine-administration-guide-6-7/troubleshooting-overview-vSphereVirtualMachineAdministration/troubleshooting-with-logs-vSphereVirtualMachineAdministration.html){: external} |
| VMware vSphere Profile-Driven Storage Service Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| VMware vFabric Postgres Service Health Alarm | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [How to stop, start, or restart vCenter Server 6.x services (2109881)](https://knowledge.broadcom.com/external/article?legacyId=2109881){: external} |
| ESXi Host Certificates Update Failure Status | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Troubleshooting vCenter Server and ESXi Host Certificates](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management.html){: external} |
| ESXi Host Certificate Status | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Troubleshooting vCenter Server and ESXi Host Certificates](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management.html){: external} |
| ESXi Host Certificate Verification Failure Status | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Troubleshooting vCenter Server and ESXi Host Certificates](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management.html){: external} |
| vSphere vCenter Host Certificate Management Mode | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Troubleshooting vCenter Server and ESXi Host Certificates](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management.html){: external} |
| Root Certificate Status |  Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks.  | [Troubleshooting vCenter Server and ESXi Host Certificates](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-vcenter-server-certificates-host-management.html){: external} |
| GPU ECC Uncorrected Memory Alarm | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support GPU. | No additional information |
| GPU ECC Corrected Memory Alarm | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support GPU. | No additional information |
| GPU Thermal Condition Alarm | Not configured in {{site.data.keyword.vcf-auto-short}} instances as they do not support GPU. | No additional information |
| Network connectivity lost | Configure to send an email one time when the `Lost Network Connectivity` or `Lost Network Connectivity to DVPorts` critical events occur. | [Troubleshooting networking](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-networking-6-7/troubleshooting-networking-configurations.html){: external} |
| Network uplink redundancy lost | Configure to send an email one time when the `Lost Network Redundancy` or `Lost Network Redundancy on DVPorts` critical events occur.| [Troubleshooting networking](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-networking-6-7/troubleshooting-networking-configurations.html){: external} |
| Network uplink redundancy degraded * | Configure to send an email one time when the `Network Redundancy Degraded` or `Network Redundancy Degraded on DVPorts` critical events occur. | [Troubleshooting networking](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-networking-6-7/troubleshooting-networking-configurations.html){: external} |
| VMKernel NIC not configured correctly * | Configure to send an email one time when the Invalid `vmknic` specified in `/Migrate/VMknic` critical event occurs. | [Troubleshooting networking](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-networking-6-7/troubleshooting-networking-configurations.html){: external} |
| Cannot connect to storage * | Configure to send an email one time when the `Lost Storage Connectivity`, `Lost Storage Path Redundancy`, `Degraded Storage Path Redundancy`, or `Lost connection to NFS server critical events occur`.| [Identifying Fibre Channel, iSCSI, and NFS storage issues on ESX/ESXi hosts (1003659)g](https://knowledge.broadcom.com/external/article?legacyId=1003659){: external} |
| Migration error * | Configure to send an email one time when the `Cannot migrate VM`, `Migration error`, `Migration host error`, `Cannot relocate VM`, or `VM orphaned` critical events occur. | [vMotion or Storage vMotion of a VM fails with the error: The migration has exceeded the maximum switchover time of 100 seconds (2141355)](https://knowledge.broadcom.com/external/article?legacyId=2141355){: external} |
| Exit standby error | Not configured in {{site.data.keyword.vcf-auto-short}} instances as the use of DPM is not recommended. | vSphere Distributed Power Management (DPM) provides power savings in on-premises deployments by dynamically consolidating workloads during periods of low resource usage. VMs are migrated onto fewer hosts and the needed ESX hosts that are not needed are powered off. No power consumption savings can be realized by powering off {{site.data.keyword.cloud_notm}} bare metal servers. |
{: caption="Preconfigured alarms" caption-side="bottom"}

The asterisk (*) denotes a stateless alarm. vCenter does not keep data on stateless alarms, does not compute, or display their status. Stateless alarms cannot be acknowledged or reset.
{: note}

## Preconfigured alarms - vSAN
{: #opsprocs-alarms-preconfigured-vsan}

* Alarm name - The name of the alarm visible in vCenter.
* Guidance - {{site.data.keyword.vmwaresolutions_short}} guidance on the use of this alarm.
* More Information - Additional information available from {{site.data.keyword.IBM}} or VMware to help with the resolution of these alarms when triggered.

If you have a vSAN cluster, the additional preconfigured alarms in the following table apply.

| Alarm name | Guidance | Details |
|:---------- |:-------- |:------- |
| Host flash capacity exceeds the licensed limit for vSAN | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| Expired vSAN license | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Troubleshooting licensing](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/troubleshooting-overview-host-management/troubleshooting-licensing-host-management.html){: external} |
| Errors occurred on the disks of a vSAN host | Configure to send an email one time when a permanent error is on a vSAN disk. | No additional information  |
| Errors occurred on the disks of a vSAN host | Configure to send an email one time when the `Virtual SAN device is under permanent failure` critical event occurs. | No additional information |
| Expired vSAN license | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Configure License Settings for a vSAN Cluster](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/license-management-host-management/managing-licenses-host-management/configuring-license-settings-for-assets-in-the-vsphere-client-host-management/assign-a-license-key-to-a-virtual-san-cluster-host-management.html){: external} |
| Expired vSAN time-limited license | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Configure License Settings for a vSAN Cluster](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vcenter-and-host-management-6-7/license-management-host-management/managing-licenses-host-management/configuring-license-settings-for-assets-in-the-vsphere-client-host-management/assign-a-license-key-to-a-virtual-san-cluster-host-management.html){: external} |
| vSAN hardware compatibility issues | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Check Information (2114803)](https://knowledge.broadcom.com/external/article?legacyId=2114803){: external} |
| vSAN health alarm `Active multicast connectivity check` | Configure to send an email one time for a critical event. | No additional information |
| vSAN health alarm `Advanced vSAN configuration in sync` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Cluster Health - Advanced vSAN configuration in sync (2107713)](https://knowledge.broadcom.com/external/article?legacyId=2107713){: external} |
| vSAN health alarm `After one additional host failure` | Configure to send an email one time for a critical event. | No additional information |
| vSAN health alarm `All hosts contributing stats` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - performance service - All hosts contributing stats check (2144400)](https://knowledge.broadcom.com/external/article?legacyId=2144400){: external} |
| vSAN health alarm `All hosts have a vSAN vmknic configured` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Network Health - All hosts have a vSAN vmknic configured (2108062)](https://knowledge.broadcom.com/external/article?legacyId=2108062){: external} |
| vSAN health alarm `All hosts have matching multicast settings` |  Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `All hosts have matching subnets` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Basic (unicast) connectivity check (normal ping)` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Network Health - Hosts small ping test (connectivity check) and Hosts large ping test (MTU check) (2108285)](https://knowledge.broadcom.com/external/article?legacyId=2108285){: external} |
| vSAN health alarm `Cluster health` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Component metadata health` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Congestion` | Configure to send an email one time for a critical event.| [vSAN Health Service - Physical Disk Health – Congestion (2109255)](https://knowledge.broadcom.com/external/article?legacyId=2109255){: external} |
| vSAN health alarm `Controller disk group mode is VMware certified` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - vSAN HCL Health – SCSI Controller on vSAN HCL (2109871)](https://knowledge.broadcom.com/external/article?legacyId=2109871){: external} |
| vSAN health alarm `Controller driver is VMware certified` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service – vSAN HCL Health – Controller Driver (2109263)](https://knowledge.broadcom.com/external/article?legacyId=2109263){: external} |
| vSAN health alarm `Controller firmware is VMware certified` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [Controller firmware health check warning for the 2nd (and more) controller managed by “sas3flash” vendor tool](https://knowledge.broadcom.com/external/article?articleNumber=319913){: external} |
| vSAN health alarm `Controller is VMware certified for ESXi release` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - vSAN HCL Health - Controller Release Support (2109262)](https://knowledge.broadcom.com/external/article?legacyId=2109262){: external} |
| vSAN health alarm `CPU AES-NI is disabled on hosts` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Encryption - CPU AES-NI Host Enablement Check (2149499)](https://knowledge.broadcom.com/external/article?legacyId=2149499){: external} |
| vSAN health alarm `Current cluster situation` | Configure to send an email one time for a critical event. | [vSAN Health Service - Limits Health – Current Cluster Situation (2108740)](https://knowledge.broadcom.com/external/article?legacyId=2108740){: external} |
| vSAN health alarm `Customer Experience Improvement Program (CEIP)` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Online Health - CEIP Check (2148866)](https://knowledge.broadcom.com/external/article?legacyId=2148866){: external} |
| vSAN health alarm `Data health` | Configure to send an email one time for a critical event. | [vSAN Health Service - Data Health – vSAN Object Health (2108319)](https://knowledge.broadcom.com/external/article?legacyId=2108319){: external} |
| vSAN health alarm `Disk capacity` | Configure to send an email one time for a warning event. | [vSAN Health Service - Physical Disk Health - Disk Capacity (2108907)](https://knowledge.broadcom.com/external/article?legacyId=2108907){: external} |
| vSAN health alarm `Disk format version` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Cluster - Disk format version (2146135)](https://knowledge.broadcom.com/external/article?legacyId=2146135){: external} |
| vSAN health alarm `ESXi vSAN Health service installation` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Home object` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - vSAN iSCSI target service - Home object (2147601)](https://knowledge.broadcom.com/external/article?legacyId=2147601){: external} |
| vSAN health alarm `Host component limit` | Configure to send an email one time for a critical event. | [vSAN Health Service - Limits - Host component (2146130)](https://knowledge.broadcom.com/external/article?legacyId=2146130){: external} |
| vSAN health alarm `Host issues retrieving hardware info` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - HCL Health - Host issues retrieving hardware information (2149290)](https://knowledge.broadcom.com/external/article?legacyId=2149290){: external} |
| vSAN health alarm `Host Maintenance Mode and Decommission State` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Host Maintenance Mode is in sync with vSAN Node Decommission State (51464)](https://knowledge.broadcom.com/external/article?legacyId=51464){: external}|
| vSAN health alarm `Hosts disconnected from VC` | Configure to send an email one time for a critical event. | [vSAN Health Service - Network Health - Hosts disconnected from vCenter Server (2108004)](https://knowledge.broadcom.com/external/article?legacyId=2108004){: external} |
| vSAN health alarm `Hosts with connectivity issues` | Configure to send an email one time for a critical event.  | [vSAN Health Service - Network Health - Hosts with connectivity issues (2108317)](https://knowledge.broadcom.com/external/article?legacyId=2108317){: external} |
| vSAN health alarm `Invalid preferred fault domain on witness host` | Consider alarm only if vSAN is stretched. | [vSAN Health Service - Invalid preferred fault domain on witness host (2130589)](https://knowledge.broadcom.com/external/article?legacyId=2130589){: external} |
| vSAN health alarm `Invalid unicast agent` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Invalid unicast agent test (2144398)](https://knowledge.broadcom.com/external/article?legacyId=2144398){: external} |
| vSAN health alarm `iSCSI target service` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - vSAN iSCSI target service – Network configuration (2147602)](https://knowledge.broadcom.com/external/article?legacyId=2147602){: external} |
| vSAN health alarm `Limits health` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Memory pools (heaps)` | Configure to send an email one time for a critical event. | [vSAN Health Service - Physical Disk Health – Memory pools (2109256)](https://knowledge.broadcom.com/external/article?legacyId=2109256){: external} |
| vSAN health alarm `Memory pools (slabs)` | Configure to send an email one time for a critical event. | [vSAN Health Service - Physical Disk Health – Memory pools (2109256)](https://knowledge.broadcom.com/external/article?legacyId=2109256){: external} |
| vSAN health alarm `MTU check (ping with large packet size)` | Configure to send an email one time for a critical event. | [vSAN Health Service - Network Health - Hosts small ping test (connectivity check) and Hosts large ping test (MTU check) (2108285)](https://knowledge.broadcom.com/external/article?legacyId=2108285){: external} |
| vSAN health alarm `Multicast assessment based on other checks` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Network configuration` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Network health` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Network latency check` | Configure to send an email one time for a warning event. | [vSAN Health Service - Network Health - Network Latency Check (2149511)](https://knowledge.broadcom.com/external/article?legacyId=2149511){: external} |
| vSAN health alarm `No disk claimed on witness host` | Consider alarm only if vSAN is stretched. | [vSAN Health Service - No disk claimed on witness host (2130584)](https://knowledge.broadcom.com/external/article?legacyId=2130584){: external} |
| vSAN health alarm `Online health connectivity` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Online Health - Internet Connectivity Check (2149196)](https://knowledge.broadcom.com/external/article?legacyId=2149196){: external} |
| vSAN health alarm `Operation health` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Performance Data Collection` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Performance service status` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Physical disk component limit health` | Configure to send an email one time for a critical event. | [vSAN Health Service - Physical disk - Component limit (2146086)](https://knowledge.broadcom.com/external/article?legacyId=2146086){: external} |
| vSAN health alarm `Physical disk health retrieval issues` | Configure to send an email one time for a critical event. | [vSAN Health Service - Physical Disk Health - Physical disk health retrieval issue (2149291)](https://knowledge.broadcom.com/external/article?legacyId=2149291){: external} |
| vSAN health alarm `Physical disk health - Metadata Health` | Configure to send an email one time for a critical event. | No additional information |
| vSAN health alarm `Preferred fault domain unset` | Consider alarm only if vSAN is stretched. | [vSAN Health Service - Preferred fault domain unset (2130590)](https://knowledge.broadcom.com/external/article?legacyId=2130590){: external} |
| vSAN health alarm `Resync operations throttling` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Cluster Health - Resynchronization Operations Throttling Check (2149504)](https://knowledge.broadcom.com/external/article?legacyId=2149504){: external} |
| vSAN health alarm `SCSI controller is VMware certified` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service – vSAN HCL Health – Controller Driver (2109263)](https://knowledge.broadcom.com/external/article?legacyId=2109263){: external} |
| vSAN health alarm `Service runtime status` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Site Latency Health` | Consider alarm only if vSAN is stretched. | [vSAN Health Service - Stretched cluster - Site latency (2146133)](https://knowledge.broadcom.com/external/article?legacyId=2146133){: external} |
| vSAN health alarm `Software version compatibility` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Cluster - Software version compatibility (2146134)](https://knowledge.broadcom.com/external/article?legacyId=2146134){: external} |
| vSAN health alarm `Space efficiency configuration consistency` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Space efficiency usage health` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Stats DB object conflicts` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - Performance Service - Stats DB object conflicts check (2144405)](https://knowledge.broadcom.com/external/article?legacyId=2144405){: external} |
| vSAN health alarm `Stats DB object` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - Performance Service - Stats DB object check (2144403)](https://knowledge.broadcom.com/external/article?legacyId=2144403){: external} |
| vSAN health alarm `Stats master election` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - Performance Service - Stats master election check (2144408)](https://knowledge.broadcom.com/external/article?legacyId=2144408){: external} |
| vSAN health alarm `Stretched cluster health` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `Time is not synchronized across hosts and VC` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - Cluster Health - Time Synchronization Across Hosts and VC (2149505)](https://knowledge.broadcom.com/external/article?legacyId=2149505){: external} |
| vSAN health alarm `Unexpected number of fault domains` | Consider alarm only if vSAN has been stretched.| [vSAN Health Service - Unexpected number of fault domains (2130581)](https://knowledge.broadcom.com/external/article?legacyId=2130581){: external} |
| vSAN health alarm `Unicast agent configuration inconsistent` | Consider alarm only if vSAN has been stretched. | [vSAN Health Service - Unicast agent configuration inconsistent (2130580)](https://knowledge.broadcom.com/external/article?legacyId=2130580){: external} |
| vSAN health alarm `Unicast agent not configured` | Consider alarm only if vSAN has been stretched. | [vSAN Health Service - Unicast agent not configured (2130582)](https://knowledge.broadcom.com/external/article?legacyId=2130582){: external} |
| vSAN health alarm `vCenter or hosts are not connected to Key Management Servers` | Consider alarm only if vSAN encryption is enabled. | [vSAN Health Service - Encryption - Key Management Servers Connection Check (2149497)](https://knowledge.broadcom.com/external/article?legacyId=2149497){: external} |
| vSAN health alarm `vCenter state is authoritative` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - Cluster health – vCenter state is authoritative (2150916)](https://knowledge.broadcom.com/external/article?legacyId=2150916){: external} |
| vSAN health alarm `Verbose mode` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [Performance Service - Verbose Mode in the vSAN health service (51527)](https://knowledge.broadcom.com/external/article?legacyId=51527){: external} |
| vSAN health alarm `vSAN Build Recommendation Engine build recommendation` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - vSphere Update Manager - vSAN build recommendation engine health (2150914)](https://knowledge.broadcom.com/external/article?legacyId=2150914){: external} |
| vSAN health alarm `vSAN Build Recommendation Engine Health` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - vSphere Update Manager - vSAN build recommendation engine health (2150914)](https://knowledge.broadcom.com/external/article?legacyId=2150914){: external} |
| vSAN health alarm `vSAN Build Recommendation Engine Health` configuration issues | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - vSphere Update Manager - vSAN build recommendation engine health (2150914)](https://knowledge.broadcom.com/external/article?legacyId=2150914){: external} |
| vSAN health alarm `vSAN CLOMD liveness` | Configure to send an email one time for a critical event. | [vSAN Health Service - Cluster Health – CLOMD liveness check (2109873)](https://knowledge.broadcom.com/external/article?legacyId=2109873){: external} |
| vSAN health alarm `vSAN cluster configuration consistency` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Cluster Configuration Consistency (2149506)](https://knowledge.broadcom.com/external/article?legacyId=2149506){: external} |
| vSAN health alarm `vSAN cluster partition` | Configure to send an email one time for a critical event. | [vSAN Health Service - Network Health - vSAN Cluster Partition (2108011)](https://knowledge.broadcom.com/external/article?legacyId=2108011){: external} |
| vSAN health alarm `vSAN disk balance` | Configure to send an email one time for a warning event. | [vSAN Health Service - Cluster health - vSAN disk balance (2144278)](https://knowledge.broadcom.com/external/article?legacyId=2144278){: external} |
| vSAN health alarm `vSAN HCL DB Auto Update` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - Hardware compatibility - vSAN HCL DB Auto Update (2146132)](https://knowledge.broadcom.com/external/article?legacyId=2146132){: external} |
| vSAN health alarm `vSAN HCL DB up-to-date` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks | [vSAN Health Service - vSAN HCL Health – vSAN HCL DB up-to-date (2109870)](https://knowledge.broadcom.com/external/article?legacyId=2109870){: external} |
| vSAN health alarm `vSAN HCL health` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `vSAN Health Service up-to-date` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - vSAN Build Recommendation - vSAN release catalog up-to-date (58891)](https://knowledge.broadcom.com/external/article?legacyId=58891){: external} |
| vSAN health alarm `vSAN object health` | Configure to send an email one time for a critical event. | [vSAN Health Service - Data Health – vSAN Object Health (2108319)](https://knowledge.broadcom.com/external/article?legacyId=2108319){: external} |
| vSAN health alarm `vSAN Performance Service health` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | [vSAN Health Service - Performance Service - Status Check (2149406)](https://knowledge.broadcom.com/external/article?legacyId=2149406){: external} |
| vSAN health alarm `vSAN VM health` | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | No additional information |
| vSAN health alarm `vSphere cluster members do not match vSAN cluster members` | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | [vSAN Health Service - Cluster Health - vSphere and vSAN Cluster Members Match vSAN (2149507)](https://knowledge.broadcom.com/external/article?legacyId=2149507){: external} |
| vSAN health alarm `Witness host fault domain misconfigured` | Consider alarm only if vSAN is stretched. | [vSAN Health Service - Witness host fault domain misconfigured (2130586)](https://knowledge.broadcom.com/external/article?legacyId=2130586){: external} |
| vSAN health alarm `Witness host not found` | Consider alarm only if vSAN is stretched. | [vSAN Health Service - Witness host not found (2130585)](https://knowledge.broadcom.com/external/article?legacyId=2130585){: external} |
| vSAN health alarm `Witness host within vCenter cluster` | Consider alarm only if vSAN is stretched. | [vSAN Health Service - Witness host within vCenter cluster (2130587)](https://knowledge.broadcom.com/external/article?legacyId=2130587){: external} |
| vSAN health alarm for vMotion `Basic (unicast) connectivity check (normal ping)` | Configure to send an email one time for a critical event. | No additional information |
| vSAN health alarm for vMotion `MTU check (ping with large packet size)` | Configure to send an email one time for a critical event. | [vSAN Health Service - Network Health - Hosts small ping test (connectivity check) and Hosts large ping test (MTU check) (2108285)](https://knowledge.broadcom.com/external/article?legacyId=2108285){: external} |
| vSAN Health Service Alarm | Not considered essential for notification. The alarm is reviewed as part of proactive daily checks. | No additional information |
| vSAN health service alarm for Overall Health Summary | Not considered essential for notification. Alarm that is reviewed as part of proactive daily checks. | No additional information |
{: caption="Preconfigured alarms - vSAN" caption-side="bottom"}

## Events and alarms procedures
{: #opsprocs-alarms-procedures}

The following table describes a number of procedures for events and alarms.

| Title | Description |
|:----- |:----------- |
| View events | To view events, navigate to vCenter and select an inventory object. Click the **Monitor** tab, **Task & Events**, and **Events**. Select an event to see the details. You can use the filter and select a column heading to sort the list. |
| Export events | You might need to export events to use tools in MS Excel to assist. Select the required inventory object. Click the **Monitor** tab, **Events**, and the **Export** icon. In the **Export Events** window, specify what types of event information you want to export. Select **Generate CSV Report** and click **Save**. Specify a file name and location and save the file. |
| Event retention |  By default, the event retention is set to 30 days. You need to change this setting in the VMware vSphere Web Client. Click the **Configure** tab, **Settings**, and **General**. Click **Edit**, change the Event Retention to the required number of days, and click **OK**. |
| View Triggered Alarms | To view the triggered alarms, navigate to vCenter and select either **All** or **New** in the **Alarms** pane. This list refreshes every 120 seconds. To view alarms triggered on a selected inventory object, select the object. Click the **Monitor** tab, **Issues**, and select **Triggered Alarms**. |
{: caption="Events and alarms procedures" caption-side="bottom"}

## Related links
{: #opsprocs-alarms-links}

* [vSphere monitoring and performance](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/6-7/vsphere-monitoring-and-performance-6-7.html){: external}
