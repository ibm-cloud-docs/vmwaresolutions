---

copyright:

  years:  2016, 2024

lastupdated: "2024-06-11"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Detailed design
{: #caveonix-detailed}

The following diagram and descriptions provide information about the RiskForesight™ application components.

![Application components](../../images/caveonix-app-components.svg "Application components"){: caption="Application components" caption-side="bottom"}

- Graphical user interface - The web interface that you can use to access the RiskForesight application.
- Central Collector - Collects different types of data payload that come from the plug-ins and make it available in the messaging store. RiskForesight supports the following types of payloads:
    - Scan
    - Logs
    - Netflow
    - Software
    - Workload metadata
- Central Router - Manages all integration touch points with the VMware® Orchestration layer. All the RiskForesight plug-ins must communicate with the Central Router to get authorized to communicate with the RiskForesight ecosystem.
- Application Routing Server - Is the REST endpoint middleware that connects the GUI and the backend data stores. Also, it validates the user access requests and manages the RBAC.
- vCenter Data Collector - The plug-in extracts the virtual machine (VM) details from vCenter. The generic plug-in uses the VMware APIs to connect to vCenter and extracts workload-relevant information. After the information is available, the plug-in packages the payload and sends it to the Central Collector.
- vCD Data Collector - The plug-in extracts the VM details from the VMware Cloud Director. The generic plug-in uses the VMware APIs to connect to the VMware Cloud Director and extracts the workload-related information. After the information is available, the plug-in packages the payload and sends it to the Central Collector.
- vCD Network Data Collector - The plug-in extracts Netflow details from the VMware vCD. The generic plug-in uses the VMware APIs to connect to the VMware NSX and extracts Network, FW, Security Rules, and Security Groups. After the information is available, the plug-in packages the payload and send it to the Central Collector.
- Network Data Collector - A plug-in that extracts Netflow details from the VMware vCenter. The generic plug-in uses VMware APIs to connect to VMware NSX and extracts network, firewall, security rules, and security groups information. After the information is available, the plug-in packages the payload and sends it to the Central Collector.
-  Remote Collector - Located in the tenant environment or another location where it has network access to the tenant VMs. It handles all compliance and cyberrisk scanning.
- Relational Datastore - Maintains the following types of metadata:
    - Cloud Service Provider
    - Tenant
    - Assets
    - Scan Results
    - Software
    - Daily or weekly aggregated data set
- Messaging Datastore - RiskForesight uses persistent messaging queue to provide zero data loss and offload-back pressure to the components.
- Index Datastore - It indexes and stores the incoming raw data for each tenant for further analysis to support the multitenant capability.
- Plug-ins – Located in the Application Routing server. Plug-ins include the setup and integration with VMware components to synchronize all VMs along with their tenant information.

The following table shows the ports and protocols that are required for each component.

| Component | Port numbers |
|---|---|
| UI | 443 |
| API | 443, 1337 |
| RiskForesight | 8082, 8083, 8084|
| Central collector (cluster) | 8080 |
| Remote collector | 8081 |
| Relational datastore primary or secondary | 5432 |
| Messaging datastore cluster | 9092 |
| Index datastore primary nodes | 9200, 9300, 5601, 443 |
{: caption="Ports and protocols" caption-side="bottom"}

The following diagram shows the network topology with the Caveonix portable private subnet that is associated with Private VLAN A. You are responsible for managing the IP address space for this subnet. If needed, you can scale out from the all-in-one deployment model, through the partially distributed model, and to the fully distributed model.

![Network diagram](../../images/caveonix-network.svg "Network diagram"){: caption="Network diagram" caption-side="bottom"}

The IP Subnet, VLAN assignments are described in the following table.

| VLAN | Subnet type | Description |
|---|---|---|
| Public | Primary | Assigned to physical hosts for public network access. Not used upon initial deployment. |
| Public | Portable | Assigned for uplink and NAT usage on `customer-nsx-esg`. |
| Public | Portable | Assigned for uplink NAT usage on `mgmt-nsx-esg`. |
| Public | Portable | Assigned for uplink NAT usage on `hcx-mgmt-esg`. |
| Private A | Primary | Assigned to physical hosts assigned by {{site.data.keyword.cloud}}. Used by the management interface for vSphere management traffic. |
| Private A | Portable | Assigned to VMs that function as management components. |
| Private A | Portable | Assigned to NSX VTEP. |
| Private A | Portable | Assigned to HCX for internal usage. |
| Private A | Portable | Assigned for uplink usage on the customer-nsx-esg. |
| Private A | Portable | Assigned to HCX. |
| Private A | Portable | Assigned to Zerto VRAs, if the Zerto option is selected. |
| Private A | Portable | Assigned for Caveonix RiskForesight, if the Caveonix option is selected. |
| Private B | Primary | Not used upon initial deployment. |
|  Private B | Portable |Assigned for vSAN, if in use. |
| Private B | Portable | Assigned for NAS, if in use. |
| Private B | Portable | Assigned for vMotion. |
{: caption="VLAN and subnets" caption-side="bottom"}
