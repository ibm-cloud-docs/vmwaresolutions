---

copyright:

  years:  2016, 2022

lastupdated: "2022-02-18"

keywords: FAQ vmware solutions dedicated, vmware solutions dedicated questions, user account, patch management

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# General FAQ about VMware Solutions Dedicated
{: #faq-vmwaresolutions}

Find answers to frequently asked questions about the VMware® Solutions Dedicated offering.

## What user accounts do I need for VMware Solutions?
{: #faq-user-accts}
{: faq}
{: support}

* **IBMid account**. This account is required to access the {{site.data.keyword.vmwaresolutions_full}} console. The console is a stand-alone user interface that is separate from the {{site.data.keyword.slportal}}. For more information, see [Getting started](/docs/vmwaresolutions?topic=vmwaresolutions-getting-started).
* **{{site.data.keyword.cloud}} account**. This account is required for provisioning. You can sign up for an {{site.data.keyword.cloud_notm}} account by using an existing **IBMid** or by creating a new **IBMid**.
* **{{site.data.keyword.cloud_notm}} infrastructure account**. This account is used to log in to the {{site.data.keyword.cloud_notm}} infrastructure customer portal that provides some additional function to manage infrastructure products and services. You can get an {{site.data.keyword.cloud_notm}} infrastructure account by upgrading your **{{site.data.keyword.cloud_notm}} account** to a billable account, or by linking your existing {{site.data.keyword.cloud_notm}} infrastructure account with your {{site.data.keyword.cloud_notm}} account. The {{site.data.keyword.cloud_notm}} infrastructure account that you are using must meet certain requirements. For more information, see [Signing up for required accounts](/docs/vmwaresolutions?topic=vmwaresolutions-signing_required_accounts) and [{{site.data.keyword.cloud_notm}} infrastructure account requirements](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).

## How do I associate my IBM Cloud infrastructure credentials with the VMware Solutions console?
{: #faq-associate-credentials}
{: faq}
{: support}

When you order your instance for the first time, follow the instructions on the **Settings** page in the console to locate and copy the {{site.data.keyword.cloud_notm}} infrastructure username and API key from the {{site.data.keyword.slportal}}. The {{site.data.keyword.cloud_notm}} infrastructure credentials are stored in the {{site.data.keyword.vmwaresolutions_short}} console after the first order. Future orders automatically use the stored credentials.

## How are my VMware virtual platform consumptions billed?
{: #faq-billing}
{: faq}

All costs for the physical and virtual infrastructure and the licenses that result from the instance are charged to your {{site.data.keyword.cloud_notm}} account. When you order an instance, you must have an {{site.data.keyword.cloud_notm}} account and provide the {{site.data.keyword.slapi_short}} key that is associated with the account.

## What is the difference between vCenter Server and VMware vSphere?
{: #faq-vcs-cf-vss}
{: faq}
{: support}

All instance types provide deployment choices for VMware virtual environments. However, the difference is the extent of customizability and automation.

* When you order a VMware vCenter Server® instance, you deploy a VMware virtual environment with customized compute, storage, and network resources. For more information about the deployed components, see [Technical specifications for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview#vc_vcenterserveroverview-specs).
* When you order a VMware vSphere® cluster, you obtain the maximum of flexibility to design and build your hosted VMware environment while you incorporate VMware-compatible hardware. However, {{site.data.keyword.cloud_notm}} does not automate the installation, configuration, and bring-up of the optional VMware components for the VMware vSphere cluster.
* The functions that are supported by vCenter Server instances and vSphere clusters are different. For more information, see [Offering comparison chart](/docs/vmwaresolutions?topic=vmwaresolutions-inst_comp_chart).

## What is included in a vCenter Server instance?
{: #faq-vcs}
{: faq}

For more information, see [Technical specifications for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview#vc_vcenterserveroverview-specs).

## What is included in a VMware vSphere cluster?
{: #faq-vss}
{: faq}

For more information, see [Technical specifications for VMware vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_vsphereclusteroverview#vs_vsphereclusteroverview-specs).

## Is a two-node vCenter Server instance highly available?
{: #is-a-two-node-vcenter-server-instance-highly-available}
{: faq}

It is recommended to deploy production workloads into environments that have at least three nodes.

The VMware vSphere DRS (Distributed Resource Scheduler) and VMware HA (High Availability) are enabled by default. However, best practices from VMware suggest that you place each of the three NSX Controllers on an individual node.

In the two-node minimum deployment, one node has one NSX Controller, and the other node has two NSX Controllers. If the node with two NSX Controllers goes down, NSX Controller operations are placed in read-only mode, and new VMs (virtual machines) or vMotion VMs might experience networking issues.

When a third node is added to a two-node cluster, vCenter Server automatically rebalances the three NSX Controllers across the three nodes and creates a highly available environment.

## Can I set up VMware vCenter HA configuration?
{: #faq-ha}
{: faq}

You can configure vCenter HA, but configuration support is not provided by {{site.data.keyword.vmwaresolutions_short}}.

## Can clusters be renamed?
{: #faq-rename-cluster}
{: faq}

For a new vCenter Server instance, you can set the name of the initial cluster that is created during deployment. When you add a cluster to a vCenter Server instance, you can specify the name that you want on the {{site.data.keyword.vmwaresolutions_short}} console.

## How are patches managed?
{: #faq-patches}
{: faq}

IBM provides ongoing updates to the IBM code by deploying the IBM CloudDriver virtual server instance (VSI) on demand. Updates and patches for the IBM management components are applied automatically, as needed.

When you review the summary details for each instance, the **Properties** section displays the **Current version**. The current version is the IBM code version that is set when the instance is initially ordered. Day 2 operations such as adding or removing hosts, storage, services, or clusters are automatically updated with the latest IBM code. Customer upgrade to the latest IBM code version is never required. \
The IBM code version is separate from the VMware and service software versions. When the IBM code version is updated, the VMware software and service versions already installed for the instance remain unchanged.
{: note}

IBM does not provide ongoing updates to add-on services such as Zerto or Veeam®. Obtaining and installing these updates is your responsibility.

Newly deployed VMware ESXi™ servers and clusters are patched with recent, but not necessarily the most recent, VMware ESXi updates.

For all other VMware component updates, you must ensure that newly deployed ESXi servers and clusters have the most recent updates that you require. {{site.data.keyword.vmwaresolutions_short}} does not offer support for applying updates and patches for VMware components. You must monitor and apply these updates yourself.
{: important}

To download ESXi updates from VMware, you can configure VMware Update Manager (VUM), which is integrated into your vCenter Server. For more information, see [VMware Support](https://www.vmware.com/support.html){: external}.

## Does the management services NSX Edge pose a security risk?
{: #faq-mgmt-nsx}
{: faq}

Although the VMware NSX Edge™ for management services is on a public subnet, the following security measures are in place to ensure that it does not pose a security risk:
*  The NSX Edge firewall is configured to allow only outgoing HTTPS (TCP port 443) traffic that is initiated by the management virtual machines.
*  SNAT (Source Network Address Translation) is used so that private IP addresses are not visible outside the private network.
*  Remote access for the management services NSX Edge appliance is disabled.
*  Passwords for accessing the management services NSX Edge from the private network are randomized and encrypted.

## Does the customer-managed NSX Edge pose a security risk?
{: #faq-customer-nsx}
{: faq}

Although the customer-managed NSX Edge is connected to the public VLAN, security measures are in place to ensure that it does not pose a security risk. The following security measures are in place:
*  A firewall rule is in place to allow only outgoing traffic from the private subnet range of IP addresses.
*  A SNAT rule (disabled by default) is in place to translate all IP addresses from the private subnet to a single IP address on the public subnet.
*  Remote access for the customer-managed NSX Edge appliance is disabled.
*  Passwords for accessing the customer-managed NSX Edge from the private network are randomized and encrypted.

## How do I choose the data centers for my instances?
{: #faq-data-center}
{: faq}

The instance deployments have strict physical infrastructure requirements, which vary among {{site.data.keyword.cloud_notm}} data centers. When you place your instance order, the available data centers are listed within regions and you can select the one that you want from the list.

For more information, see the _IBM Cloud data center availability_ sections in:
* [Requirements and planning for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_planning)
* [Requirements and planning for VMware vSphere](/docs/vmwaresolutions?topic=vmwaresolutions-vs_planning)

## How long does it take for my instance to be deployed?
{: #faq-deploy}
{: faq}

You can check the status of the instance deployment by viewing the deployment history on the instance details page from the {{site.data.keyword.vmwaresolutions_short}} console.

## How do I add a public network to a vCenter Server instance ordered as private network only?
{: #faq-private-only}
{: faq}

Cancel the order, and then place a new order with the configuration that you want for a public IP address or public VLAN. You cannot add a public network after it was ordered as private network only.

## How do I request a RAM upgrade for ESXi hosts?
{: #faq-ram-upgrade}
{: faq}

The account owner can increase the RAM on ESXi servers by following these steps:
1. Log in to the {{site.data.keyword.cloud_notm}} console and go to the device list.
2. Select the ESXi server to be modified.
3. From the details page, click **Modify** next to RAM or memory.
4. Specify the higher limit, then confirm the change to place your order.
5. Repeat these steps, as needed, for each additional ESXi server.

An {{site.data.keyword.cloud_notm}} representative confirms the billing change and contacts you to schedule a maintenance window for adding the memory.

You must manage the VMware Solutions components that are created in your {{site.data.keyword.cloud_notm}} account only from the VMware Solutions console, not any other means outside of the console. If you change these components outside of the VMware Solutions console, the changes are not synchronized with the console.
{: note}

## Does VMware vSphere use automation to install, configure, and bring up the VMware stack?
{: #faq-vss-automation}
{: faq}

No. VMware vSphere does not use the advanced automation from the vCenter Server platform. Based on what you order, the platform delivers optional VMware licenses, ESXi servers, and, optionally, an HA-pair of FortiGate® physical firewalls. If a new cluster is created, three new VLANs are also provisioned: a public VLAN and two private VLANs.

VMware ESXi is automatically installed on each {{site.data.keyword.cloud_notm}} bare metal server, but you are responsible for installing any additional VMware components like vCenter Server or NSX. While VMware vSphere ensures that VMware-compatible hardware is ordered based on the VMware components selected, no automation exists to configure and bring up the VMware environment. You are responsible for designing and architecting the IBM-hosted environment.

## How can I view a list of all notifications?
{: #faq-notification}
{: faq}

To view the complete notification history, click **Notifications** from the left navigation pane.

## What if I have issues with VMware Solutions Dedicated?
{: #faq-support}
{: faq}
{: support}

If you need assistance with {{site.data.keyword.vmwaresolutions_short}}, contact IBM Support through one of the support channels. For more information, see [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

## Related links
{: #faq-related}

* [Notifications](/docs/vmwaresolutions?topic=vmwaresolutions-notifications)
* [vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview)
* [Accessing the console](/docs/vmwaresolutions?topic=vmwaresolutions-loginmethod)
* [User accounts and settings](/docs/vmwaresolutions?topic=vmwaresolutions-useraccount)
