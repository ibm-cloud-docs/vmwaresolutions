---

copyright:
  years: 2024, 2025
lastupdated: "2025-03-31"

keywords: log routing, log locations, platform logs, enable logging, log messages, analyze logs

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Logging for VMware Solutions
{: #logging}

{{site.data.keyword.cloud}} services, such as {{site.data.keyword.vmwaresolutions_full}} generate platform logs that you can use to investigate abnormal activity and critical actions in your account, and troubleshoot problems.
{: shortdesc}

You can use {{site.data.keyword.logs_routing_full_notm}}, a platform service to route platform logs in your account to a destination of your choice by configuring a tenant that defines where platform logs are sent. For more information, see [Learning about {{site.data.keyword.logs_routing_full_notm}}](/docs/logs-router?topic=logs-router-about).

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on platform logs that are generated in your account and routed by {{site.data.keyword.logs_routing_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

## Locations where platform logs are generated
{: #log-locations}

{{site.data.keyword.vmwaresolutions_short}} generates platform logs in the regions that are indicated in the following table.

| Dallas (`us-south`) | Washington (`us-east`) | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|------------------------|--------------------|----------------------|
| [Yes]{: tag-green}  | [Yes]{: tag-green}     | [Yes]{: tag-green} | [No]{: tag-red}      |
{: caption="Regions where platform logs are generated in Americas locations" caption-side="bottom"}
{: #la-table-1}
{: tab-title="Americas"}
{: tab-group="la"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)   | Sydney (`au-syd`) | Osaka (`jp-osa`) | Chennai (`in-che`) |
|--------------------|-------------------|------------------|--------------------|
| [Yes]{: tag-green} | [No]{: tag-red}   | [No]{: tag-red}  | [No]{: tag-red}    |
{: caption="Regions where platform logs are generated in Asia Pacific locations" caption-side="bottom"}
{: #la-table-2}
{: tab-title="Asia Pacific"}
{: tab-group="la"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`) | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------|------------------|------------------|
| [Yes]{: tag-green}  | [No]{: tag-red}  | [No]{: tag-red}  |
{: caption="Regions where platform logs are generated in Europe locations" caption-side="bottom"}
{: #la-table-3}
{: tab-title="Europe"}
{: tab-group="la"}
{: class="simple-tab-table"}
{: row-headers}

### Locations where logs are sent by {{site.data.keyword.logs_routing_full_notm}}
{: #lr-locations}



VMware Solutions sends logs by {{site.data.keyword.logs_routing_full_notm}} in the regions that are indicated in the following table.

| Dallas (`us-south`) | Washington (`us-east`) | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|------------------------|--------------------|----------------------|
| [Yes]{: tag-green}  | [Yes]{: tag-green}     | [Yes]{: tag-green} | [No]{: tag-red}      |
{: caption="Regions where platform logs are sent in Americas locations" caption-side="bottom"}
{: #lr-table-1}
{: tab-title="Americas"}
{: tab-group="lr"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)   | Sydney (`au-syd`) | Osaka (`jp-osa`) | Chennai (`in-che`) |
|--------------------|-------------------|------------------|--------------------|
| [Yes]{: tag-green} | [No]{: tag-red}   | [No]{: tag-red}  | [No]{: tag-red}    |
{: caption="Regions where platform logs are sent in Asia Pacific locations" caption-side="bottom"}
{: #lr-table-2}
{: tab-title="Asia Pacific"}
{: tab-group="lr"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`) | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------|------------------|------------------|
| [Yes]{: tag-green}  | [No]{: tag-red}  | [No]{: tag-red}  |
{: caption="Regions where platform logs are sent in Europe locations" caption-side="bottom"}
{: #lr-table-3}
{: tab-title="Europe"}
{: tab-group="lr"}
{: class="simple-tab-table"}
{: row-headers}

## Viewing logs
{: #log-viewing}

To view logs, start {{site.data.keyword.logs_full_notm}} from the Observability page. For more information, see [Launching the UI through the {{site.data.keyword.cloud_notm}} UI](/docs/cloud-logs?topic=cloud-logs-instance-launch#instance-launch-cloud-ui).

## Fields by log type
{: #log-fields}

For information about fields included in every platform log, see [Fields that are included in platform logs](/docs/logs-router?topic=logs-router-about-platform-logs#about-platform-logs-2).

The following fields are included in the log record:

| Field             | Type       | Description             |
|-------------------|------------|-------------------------|
| `logSourceCRN`    | Required   | Defines the account and flow log instance where the log is published. |
| `saveServiceCopy` | Required   | Defines whether IBM saves a copy of the record for operational purposes. |
| `message`         | Required   | Description of the log that is generated. |
{: caption="Log record fields" caption-side="bottom"}

## Log messages
{: #log_messages}

The following tables list the message IDs that are generated and additional information available about these messages.

| Message ID | Type | Learn More |
|------------|------|------------|
| `is.flow-log-collector.00001E` | Error | Failed to write a Flow log file for the past 24 hours. Dropping flow log for Virtual Server _ServerName_ |
{: caption="Additional information about message IDs" caption-side="bottom"}
