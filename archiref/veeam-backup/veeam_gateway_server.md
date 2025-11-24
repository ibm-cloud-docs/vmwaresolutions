---

copyright:

  years: 2023, 2025

lastupdated: "2025-11-24"

keywords: gateway servers

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Gateway servers
{: #veeam_gateway_server}

{{site.data.content.vms-deprecated-note}}

A gateway server is required when a backup repository cannot host Veeam® Data Movers. The Veeam Data Movers are then hosted on the gateway server. The gateway server is required if you deploy the following types of backup repositories in the backup infrastructure.

* [Shared folder backup repositories](https://helpcenter.veeam.com/archive/backup/120/vsphere/backup_repository.html){: external}
* [Dell Data Domain deduplicating storage appliance](https://helpcenter.veeam.com/archive/backup/120/vsphere/dell_dd.html){: external}
* [HPE StoreOnce deduplicating storage appliance](https://helpcenter.veeam.com/archive/backup/120/vsphere/deduplicating_appliance_storeonce.html){: external}
* [Object storage repository](https://helpcenter.veeam.com/archive/backup/120/vsphere/object_storage_repository.html){: external}

During service deployment, the automation deploys a gateway server onto the Veeam Backup and Replication server. If required more gateway servers can be added.

1. To configure a gateway server, add a virtual machine (VM), virtual server instance, or bare metal server to the backup infrastructure. This process can be done with the help of the **New Windows Server** or **New Linux Server wizard**.
2. Use the **New** or **Edit** option in the backup repository wizard and define the gateway server settings.
3. Select the **gateway server** or instruct Veeam Backup and Replication to select it automatically.

## Related links
{: #veeam_gateway_server-links}

* [Adding Microsoft Windows Servers](https://helpcenter.veeam.com/archive/backup/120/vsphere/runtime_process.html){: external}
* [Adding Linux Servers](https://helpcenter.veeam.com/archive/backup/120/vsphere/add_linux_server.html){: external}
* [Adding backup repositories](https://helpcenter.veeam.com/archive/backup/120/vsphere/dsa_repository_server.html){: external}
* [Gateway servers](https://helpcenter.veeam.com/archive/backup/120/vsphere/gateway_server.html){: external}
