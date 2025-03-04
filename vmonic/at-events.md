---

copyright:
  years: 2024, 2025
lastupdated: "2025-03-04"

keywords: activity tracking, tracking locations, enable events, view events, analyze events

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Activity tracking events for VMware Solutions
{: #at_events}

{{site.data.keyword.cloud}} services, such as {{site.data.keyword.vmwaresolutions_full}}, generate activity tracking events.
{: shortdesc}

Activity tracking events report on activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use the events to investigate abnormal activity and critical actions and to comply with regulatory audit requirements.

You can use {{site.data.keyword.atracker_full_notm}}, a platform service to route auditing events in your account to destinations of your choice by configuring targets and routes that define where activity tracking events are sent. For more information, see [About {{site.data.keyword.atracker_full_notm}}](/docs/atracker?topic=atracker-about).

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in your account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

{{site.data.content.impnote-at-deprecation}}

## Locations where activity tracking events are generated
{: #at-locations}

{{site.data.keyword.vmwaresolutions_short}} generates activity tracking events in the regions that are indicated in the following table.

| Dallas (`us-south`) | Washington (`us-east`) | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|------------------------|--------------------|----------------------|
| [Yes]{: tag-green}  | [Yes]{: tag-green}     | [Yes]{: tag-green} | [No]{: tag-red}      |
{: caption="Regions where activity tracking events are generated in Americas locations" caption-side="bottom"}
{: #at-table-1}
{: tab-title="Americas"}
{: tab-group="at"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)   | Sydney (`au-syd`) | Osaka (`jp-osa`) | Chennai (`in-che`) |
|--------------------|-------------------|------------------|--------------------|
| [Yes]{: tag-green} | [No]{: tag-red}   | [No]{: tag-red}  | [No]{: tag-red}    |
{: caption="Regions where activity tracking events are generated in Asia Pacific locations" caption-side="bottom"}
{: #at-table-2}
{: tab-title="Asia Pacific"}
{: tab-group="at"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`) | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------|------------------|------------------|
| [Yes]{: tag-green}  | [No]{: tag-red}  | [No]{: tag-red}  |
{: caption="Regions where activity tracking events are generated in Europe locations" caption-side="bottom"}
{: #at-table-3}
{: tab-title="Europe"}
{: tab-group="at"}
{: class="simple-tab-table"}
{: row-headers}

## Locations where activity tracking events are sent to {{site.data.keyword.at_full_notm}} hosted event search
{: #at-legacy-locations}



VMware Solutions sends activity tracking events to {{site.data.keyword.at_full_notm}} hosted event search in the regions that are indicated in the following table.

| Dallas (`us-south`) | Washington (`us-east`) | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|------------------------|--------------------|----------------------|
| [Yes]{: tag-green}  | [Yes]{: tag-green}     | [Yes]{: tag-green} | [No]{: tag-red}      |
{: caption="Regions where activity tracking events are sent in Americas locations" caption-side="bottom"}
{: #at-legacy-table-1}
{: tab-title="Americas"}
{: tab-group="at-legacy"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)   | Sydney (`au-syd`) |  Osaka (`jp-osa`) | Chennai (`in-che`) |
|--------------------|-------------------|-------------------|--------------------|
| [Yes]{: tag-green} | [No]{: tag-red}   | [No]{: tag-red}   | [No]{: tag-red}    |
{: caption="Regions where activity tracking events are sent in Asia Pacific locations" caption-side="bottom"}
{: #at-legacy-table-2}
{: tab-title="Asia Pacific"}
{: tab-group="at-legacy"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`) | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------|------------------|------------------|
| [Yes]{: tag-green}  | [No]{: tag-red}  | [No]{: tag-red}  |
{: caption="Regions where activity tracking events are sent in Europe locations" caption-side="bottom"}
{: #at-legacy-table-3}
{: tab-title="Europe"}
{: tab-group="at-legacy"}
{: class="simple-tab-table"}
{: row-headers}

## Events for {{site.data.keyword.vcf-classic-short}} instance management
{: #at-events-instance-mgmt}

When you manage user accounts, instances, clusters, and services in VMware Solutions, an event is generated.

The following table provides the actions that generate and send management events to {{site.data.keyword.at_short}}.

| Action | Description |
|:------ |:------------|
| `vmware-solutions.account-apikey.update` | The infrastructure API key for an account is updated. |
| `vmware-solutions.account-notification.update` | The notification setting for an account is updated. |
| `vmware-solutions.instance-secure-data.wipe` | The instance-secure data is wiped. |
| `vmware-solutions.instance-bss-account.migrate` | An instance is migrated to a BSS account. |
| `vmware-solutions.vcs.create` | A {{site.data.keyword.vcf-classic}} instance is created. |
| `vmware-solutions.vcs.delete` | A {{site.data.keyword.vcf-classic-short}} instance is deleted. |
| `vmware-solutions.vcs-host.add` | A host is added to a {{site.data.keyword.vcf-classic-short}} instance. |
| `vmware-solutions.vcs-host.remove` | A host is removed from a {{site.data.keyword.vcf-classic-short}} instance. |
| `vmware-solutions.vcs.update` | A {{site.data.keyword.vcf-classic-short}} instance is updated. |
| `vmware-solutions.vcs-cluster.create` | A cluster is created for a {{site.data.keyword.vcf-classic-short}} instance. |
| `vmware-solutions.vcs-cluster.delete` | A cluster is deleted for a {{site.data.keyword.vcf-classic-short}} instance. |
| `vmware-solutions.vcs-nsx-license.update` | The VMware NSX® license is updated for a {{site.data.keyword.vcf-classic-short}} instance. |
| `vmware-solutions.vcs-nfs-storage.add` | NFS storage is added to a {{site.data.keyword.vcf-classic-short}} instance. |
| `vmware-solutions.vcs-nfs-storage.remove` | NFS storage is removed from a {{site.data.keyword.vcf-classic-short}} instance. |
| `vmware-solutions.vcs-plan.update` | A {{site.data.keyword.vcf-classic-short}} instance's plan is updated. |
| `vmware-solutions.vss.create` | A {{site.data.keyword.vcf-flex}} instance is created. |
| `vmware-solutions.vss.update` | A {{site.data.keyword.vcf-flex-short}} instance is updated. |
| `vmware-solutions.vss-template.remove` | A {{site.data.keyword.vcf-flex-short}} template is removed. |
| `vmware-solutions.service.create` | A service is created. |
| `vmware-solutions.service.delete` | A service is deleted. |
{: caption="Description of actions that generate management events" caption-side="bottom"}

## Events for KMIP for VMware
{: #at-events-kmip}

When you manage keys for the KMIP™ for VMware® service, an event is generated.

The following table provides the actions that generate and send events for KMIP for VMware. The initiator completes these actions from vCenter Server and they do not include the initiator's IP address. The requests for these actions run from within the {{site.data.keyword.cloud_notm}} private network.

The initiator ID is derived from the TLS (Transport Layer Security) certificate of the vCenter Server that is used to authenticate the connection to the KMIP server. The initiator ID is in the format `CertificateID-<value>`, where the value matches the fingerprint of the corresponding TLS certificate. Using the fingerprint, you can identify the vCenter Server that triggered the action.

| Action | Description |
|:------ |:----------- |
| `vmware-solutions.kmip-key.create` | A KMIP key is created. |
| `vmware-solutions.kmip-key.read` | A KMIP key is retrieved. |
| `vmware-solutions.kmip-key-attributes.retrieve` | A KMIP key's attributes are retrieved. |
| `vmware-solutions.kmip-key.activate` | A KMIP key is activated. |
| `vmware-solutions.kmip-key.revoke` | A KMIP key is revoked. |
| `vmware-solutions.kmip-key.destroy` | A KMIP key is destroyed. |
{: caption="Description of actions that generate events for the KMIP for VMware service" caption-side="bottom"}

## Events for {{site.data.keyword.vm-shared}}
{: #at-events-vdc}

{{site.data.content.shared-deprecated-note}}

When you use {{site.data.keyword.vm-shared}}, an event is generated to track how users and applications interact with virtual data centers.

The following table lists the actions that generate and send an event to {{site.data.keyword.at_short}}.

| Action | Description | Outcome |
|:------ |:----------- |:------- |
| `vmware-solutions.vdc.create` | An event is generated when a virtual data center instance is created. |`pending` \n `success` \n `failure` |
| `vmware-solutions.vdc.delete` | An event is generated when a virtual data center instance is deleted. | `pending` \n `success` \n `failure` |
| `vmware-solutions.vdc.update` | An event is generated when capacity is added to a virtual data center instance. \n An event is generated when capacity is removed from a virtual data center instance. | `pending` \n `success` \n `failure` |
{: caption="Description of actions that generate {{site.data.keyword.vm-shared}} events" caption-side="bottom"}

## Related links
{: #at-events-links}

* [KMIP for VMware overview](/docs/vmwaresolutions?topic=vmwaresolutions-kmip_standalone_considerations)
