---

copyright:

  years:  2016, 2021

lastupdated: "2021-09-10"

keywords: vSphere upgrade, NSX upgrade, PSC upgrade

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Upgrading vCenter Server vSphere software from vSphere 6.5 or 6.7 to 7.0
{: #vc_vsphere_70_upgrade}

The VMware vCenter Server® offering is a fully automated deployment solution for the VMware vSphere® SDDC stack. It includes vSphere, VMware NSX®, and optionally vSAN™ products. While vCenter Server automates the most challenging parts of deploying, expanding, and contracting a VMware® SDDC-based infrastructure, it is not a managed service.

vCenter Server has a policy of supporting the automation of VMware SDDC software versions within the range of N-1. If you want to continue to benefit from the {{site.data.keyword.vmwaresolutions_full}} automation, you must upgrade existing instances of vCenter Server.

If your vCenter Server instance is at a version lower than the version level that is needed for automation support, it continues to be supported as required by the VMware support policy. However, your instance might not function with the current {{site.data.keyword.vmwaresolutions_short}} automation.

You must apply patches and upgrade the VMware software periodically, over the lifecycle of a vCenter Server instance. This maintenance includes upgrading the VMware SDDC software to a version that is supported by the {{site.data.keyword.vmwaresolutions_short}} automation.

The following procedure provides the steps that are required to convert a VMware vSphere 6.5 or 6.7-based instance to a VMware vSphere 7.0-based instance.

## Important considerations
{: #vc_vsphere_70_upgrade-considerations}

* You are responsible to ensure that all VMware ESXi™ servers have proper firmware and drivers to support vSphere 7.0. Broadwell servers are not supported. Research and plan carefully for Skylake and Cascade Lake servers.
* {{site.data.keyword.cloud_notm}} supports only Cascade Lake bare metal servers for newly deployed vSphere 7.0 instances.
* If you add clusters or hosts to a vSphere 7.0 instance from the VMware Solutions console, only Cascade Lake bare metal servers are provisioned.
* If you are using VMware NSX-V, familiarize yourself with VMware’s product lifecycle for NSX-V and make appropriate plans to migrate your workload to NSX-T™.
* Adding and removing services is not supported for instances that are upgraded to vSphere 7.0. Due to this limitation and the changes and improvements in the architecture and topology, {{site.data.keyword.cloud_notm}} recommends that you deploy a new vSphere 7.0 instance and migrate your current network topology and workload to the new instance.
* vCenter Server is designed to allow for a “rolling” upgrade. That is, virtual machine (VM) workloads that are currently functioning continue to function without an outage if you complete the following procedure. Enterprises must engage their change management policies to enable a structured and communicated upgrade and plan for contingencies. However, during the upgrade process of certain management functions, such as vCenter Server and NSX Manager, temporary outages of management functions, configuration changes, powering off and on VMs, might be impacted.

## Before you begin
{: #vc_vsphere_70_upgrade-prereq}

The time to complete the upgrade is unknown. It is possible that it might take several maintenance windows to completely upgrade an environment. Running up-leveled and down-leveled versions of the SDDC software is supported by VMware during the upgrade process. However, some functions such as vMotion, maybe limited during this process.

Complete the following requirements before you begin the upgrade:  
* Upgrade any extensions or snap-ins within the vCenter Server environment. Review the following documentation before you plan your upgrade:
   * [VMware vCenter Server 7.0 Release Notes](https://docs.vmware.com/en/VMware-vSphere/7.0/rn/vsphere-esxi-vcenter-server-70-release-notes.html){: external}
   * [About VMware ESXi Upgrade](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.esxi.upgrade.doc/GUID-65B5B313-3DBB-4490-82D2-A225446F4C99.html){: external}
* Set up vSphere Update Manager (VUM) within your vCenter Server instance to download updates from VMware vSphere. For more information, see [VMware Update Manager introduction](/docs/vmwaresolutions?topic=vmwaresolutions-vum-intro#vum-intro).
* Open a support ticket with the {{site.data.keyword.vmwaresolutions_short}} team to notify them that an upgrade is being planned. The ticket remains open until the instance is registered at the upgraded level in the {{site.data.keyword.vmwaresolutions_short}} console.
* Confirm whether the vCenter Server instance that you are upgrading is linked to another vCenter Server instance as primary or secondary in the {{site.data.keyword.vmwaresolutions_short}} console. All linked instances must have their Platform Services Controllers (PSCs) upgraded first as part of a particular site upgrade.
* Confirm the following requirements for vSAN based instances:
   * Ensure that the vSAN Health tool is enabled and reports no critical errors. If critical errors are present, contact the IBM Support team with the upgrade support ticket ID.
   * Ensure that each node has space to handle rebuilding redundancy of vSAN objects in case an ESXi host fails to come back up during the upgrade. You might need to either reduce disk usage or add an ESXi host before the upgrade.  
   * Verify whether the overall vSAN volume usage is higher than 70%. You might need to either reduce disk usage or add an ESXi host before the upgrade.
* Verify that the PSC and vCenter Server `root` user ID with its credentials are visible on the console. If your vCenter Server instance was initially ordered in V2.5 or later, only the account with `customerroot` access is visible on the console. In this case, contact IBM Support for the **root** user ID password for PSC and vCenter Server.
* Confirm that you have a [My VMware](https://my.vmware.com){: external} user ID for which to download the required binary files to upgrade. If you don't, contact IBM Support with the upgrade support ticket ID.
* Confirm that VUM is configured to reach https://www.vmware.com to download patches. If it can't be configured because of security policies, then you must manually download the most recent patch sets and upload them into VUM. For more information, see [VMware Update Manager introduction](/docs/vmwaresolutions?topic=vmwaresolutions-vum-intro#vum-intro).

### Preparing your jump server
{: #vc_vsphere_70_upgrade-prereq-jumpbox}

Because the {{site.data.keyword.cloud_notm}} client access VPN is limited to 512 Kbps, take one of the following actions.
* Provision an {{site.data.keyword.cloud_notm}} Windows® 2012-2016 server Virtual Server Instance (VSI).
* Set up a similar Windows VM on a separate vCenter Server environment within the same {{site.data.keyword.cloud_notm}} data center.
   The Windows VM is used as a jump server into the vCenter Server instance for the upgrade that downloads the binary files from https://my.vmware.com. Do not place this VM on the vCenter Server instance that is being upgraded.

Complete the following steps to download files to your jump server:
1. From the VMware Portal, download the following product files onto your jump server:
   * For VMware vCenter Server Appliance, ``VMware-VCSA-all-7.0.1-17327517.iso``.
   * For ESXi 7, ``VMware-ESXi-7.0U1c-17325551-depot.zip``.
   * For Hypervisor, ``VMware-VMvisor-Installer-7.0U1c-17325551.x86_64.iso``.
2. Download the ``007.1316.0000.0000_Unified_StorCLI_PUL.zip`` file from https://docs.broadcom.com/docs/007.1316.0000.0000_Unified_StorCLI_PUL.zip.

## Procedure to upgrade vCenter Server vSphere software from 6.5 or 6.7 to 7.0
{: #vc_vsphere_70-upgrade-procedure}

### Before you begin
{: #vc_vsphere_70_upgrade-procedure-before}

* If you encounter a problem during the upgrade process, use the {{site.data.keyword.vmwaresolutions_short}} upgrade ticket that you opened at the beginning of the process to contact IBM Support. IBM Support then opens tickets with VMware Support if required.
* You must follow the support process to ensure that {{site.data.keyword.vmwaresolutions_short}} provides VMware Support with all the information about the vCenter Server design and setup, and the {{site.data.keyword.cloud_notm}} information.
* By following the support process, you ensure that accurate information is shared with VMware Support, which shortens the support experience. After IBM Support provides the necessary information to VMware Support, you can interact with VMware Support directly.
* Ensure that you keep a record of all the new passwords and credentials that you create as part of the upgrade process. IBM Support requires these credentials at the end of the upgrade process to update their internal database.

### Procedure to set the cluster Distributed Resource Schedule to manual
{: #vc_vsphere_70_upgrade-procedure-drs}

You must set the cluster Distributed Resource Schedule (DRS) to manual to prevent unexpected migrations during the upgrade process.

Complete the following steps from the vCenter Server user interface.

1. Select **Host and Clusters > Cluster > Configure > DRS**.
2. Click **EDIT**.
3. Set the **DRS** field to **Manual**.

### Procedure to create a standard switch for the new vCenter Server Appliance
{: #vc_vsphere_70_upgrade-procedure-vcsa}

Temporarily install the new vCenter Server Appliance that you deploy onto a vSphere Standard Switch. One of the existing ``vmnics`` is reassigned from the distributed switch during the upgrade.

Complete the following steps from the vCenter Server user interface.

1. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Select a host for the new vCenter Server Appliance.
2. For the private network switch, select **Managed Physical Adaptors**. The private network switch name ends with ``-private``.
3. Select **uplink1/vmnic2**, then click the **X** icon to delete the adapter. Click **OK**.
4. Return to the **Virtual Switches** panel and click **Add Networking**.
   1. Select **Virtual Machine Port Group** for a standard switch and click **Next**.
   2. For **New Standard Switch**, set the MTU to 9000 and click **Next**.
   3. Click the green **+** icon to add an adapter. Click **OK**, then **Next** to accept ``vmnic2``.
   4. For **Connection Settings**, keep the **VM Network** and **VLAN ID None** defaults. Click **Next**, then **Finish**. *Standard Switch: vSwitch0* is displayed in the list of switches.
5.  Make a note of the Network Setting for the vCenter Server Appliance VM. You must update the new vCenter appliance to match.
   * From the vCenter Server user interface, click the VM for the vCenter appliance. Note the name, ending with ``vc``.
   * From the middle pane, click the **Networks** tab. Note the name of the distributed port group, ending with ``-dpg-mgmt``. 

### Procedure to upgrade vCenter Server
{: #vc_vsphere_70_upgrade-procedure-vcenter}

Follow the VMware instructions for upgrading vCenter. For more information, see [Upgrade a vCenter Server Appliance 6.5 or 6.7 with an Embedded Platform Services Controller by Using the GUI](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vcenter.upgrade.doc/GUID-6A5C596D-103E-4024-9353-5569263EB427.html){: external}.

Ensure to complete the following requirements during the upgrade:

* Mount the VMware-VCSA ISO, go to the ``visa-ui-installer\win32`` directory, and run the installer.
* In the vCenter Server 7.0 installer dialog, select the **Upgrade** flow and complete the steps in the installer.
* You must use the IP and credentials (administrator and root) for the current vCenter Server appliance. Use the IP and root password for the ESXi host of the current vCenter Server Appliance and the host where you want to deploy the new 7.0 vCenter Server Appliance. You must use a new temporary IP address, gateway, and subnet mask for the new vCenter Server Appliance during installation.
* Complete Stage 2 when prompted. Ensure to note any warnings and take the appropriate actions.

### Procedure to upgrade Stor VIB (Broadcom driver)
{: #vc_vsphere_70_upgrade-procedure-broadcom}

You must upgrade the Broadcom driver before you upgrade the ESXi host.

1. Extract the ``007.1316.0000.0000_Unified_StorCLI_PUL.zip`` file to a directory on your windows jump server.
2. Locate the ``vmware-storcli.vib`` file in the extracted file contents.
3. Copy the ``.vib`` file to either a vSAN or NFS data store that is mounted on the ESXi hosts for the instance. Use vCenter Server to reference the extracted file on your jump server.
4. SSH into each ESXi host and run the following VIB Upgrade command:  
   ``esxcli software vib update -v /<path to vsan or nfs datastore from step 3>/vmware-storcli.vib --no-sig-check``  
   The following installation results are displayed.
    ``Message: Operation finished successfully.
    Reboot Required: false
    VIBs Installed: Broadcom_bootbank_vmware-storcli_007.1316.0000.0000-01
    VIBs Removed: LSI_bootbank_vmware-storcli_007.0916.0000.0000-01
    VIBs Skipped:``
5. Run the following command to validate the installation:  
   ``> esxcli software vib list |grep vmware-storcli
   vmware-storcli    007.1316.0000.0000-01    Broadcom  PartnerSupported  2020-04-16``
6. Repeat for each host.

### Procedure to upgrade the ESXi hosts
{: #vc_vsphere_70_upgrade-procedure-esxi-upgrade}

1. From the vCenter Server user interface, go to **LCM menu > LifeCycle Manager**.
2. Select **IMPORT ISO > IMPORT ISO**, then select the ``VMware-VMvisor-Installer-7.0U1c-17325551.iso`` file.
3. Create the baseline. Select **BASELINE > CREATE** and use the imported ISO from the previous step.
4. For each host, select the host in the vCenter browser tree, then select **update** (located in the far left in the main window).
5. If the Zerto VRA is present on the host, put the host into maintenance mode first. Recent releases of Zerto stop the VRA, which otherwise would prevent the update.
6. Complete the update.  
   1. [ATTACH] Baseline, select the previously created baseline.
   2. Select Baseline and [REMEDIATE].
7. Remediate each host in turn. After remediation, ensure to pull the host out of maintenance mode.

If the upgrade process fails immediately and the ``host cannot enter maintenance mode`` error message is displayed, shut down the Zerto ZVAs and try again. The ZVRA VMs automatically start as each server comes out of remediation. For more information about continuing Zerto replication during the upgrade process, see [How to Place a Host with an Associated VRA into Maintenance Mode](https://www.zerto.com/myzerto/knowledge-base/how-to-place-a-host-with-an-associated-vra-into-maintenance-mode/){: external}.
{: note}

### Updating vCenter Server and ESXi host licenses
{: #vc_vsphere_70_upgrade-license-update}

After you upgrade the vCenter Server and ESXi hosts to vSphere 7.0, you must update the licenses on the vCenter Server and the ESXi hosts. If you have a vSAN cluster, you must update the vSAN license. Contact [IBM Cloud for VMware Solutions Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) to obtain the new licenses for vSphere 7.0.

#### Procedure to update the vCenter Server license
{: #vc_vsphere_70_upgrade-license-update-vcs}

Complete the following steps from the vCenter Server user interface.

1. Select **Administration menu > Licensing > Licenses**.
2. From the **Licenses** page, click **+ Add New Licenses**.
3. Enter the new vCenter Server 7.0 license key in the **New Licenses** field. Then, enter a name for the license and click **OK**.
4. From the **Assets** page, select the vCenter instance under **VCENTER SERVER SYSTEMS** and click **Assign License**. Then, select the new license and click **OK**.
5. From the **Licenses** page, find the license with the product name **VMware vCenter Server 6 Standard** and click **Remove Licenses**.

#### Procedure to update ESXi host licenses
{: #vc_vsphere_70_upgrade-license-update-esxi}

1. From the **Licenses** page, click **+ Add New Licenses**.
2. Enter the new vSphere 7.0 license keys in the **New Licenses** field. If you have multiple vSphere 7.0 license keys, input the all of the licenses in the **New Licenses** filed, enter a name for each license, and click **OK**.
3. Complete the following steps from the **Assets** page.
   1. Select **HOSTS**.
   2. Select the host and click **Assign License**.
   3. Select one of the new vSphere 7 license keys and click **OK**.
   4. Repeat this step for each upgraded host.
4. From the **Licenses** page, select all of the old vSphere 6 licenses and click **Remove Licenses**.

#### Procedure to update the vSAN cluster license
{: #vc_vsphere_70_upgrade-license-update-vsan}

1. From the **Licenses** page, click **+ Add New Licenses**.
2. Enter the new vSAN license keys in the **New Licenses** field. If you have multiple vSAN license keys, enter all the licenses in the **New Licenses** field, specify a name for each license, and then click **OK**.
3. Complete the following steps from the **Assets** page.
   1. Select **VSAN CLUSTERS**.
   2. Select the vSAN cluster and click **Assign License**.
   3. Select one of the new vSAN license keys and click **OK**.
   4. Repeat this step for each vSAN cluster.
4. From the **Licenses** page, select all the old vSAN cluster licenses and click **Remove Licenses**.

### Procedure to remove the temporary standard switch
{: #vc_vsphere_70_upgrade-procedure-remove-switch}

Reassign the ``vmnic`` that you temporarily used on the standard switch back to the distributed switch it was originally associated with.

Complete the following steps from the vCenter Server user interface.

1. Go to the new vCenter Server appliance.
2. Under **Actions** click **Edit Settings**.
3. For network adapter 1, browse to the name of the distributed port group that ends with ``-dpg-mgmt`` that you previously noted. Save the changes.
4. Go to the host where you deployed the new appliance. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Then, click **MANAGE PHYSICAL ADAPTERS** for *vSwitch0*.
6. Select **vmnic2** and click the red **X** to delete the adapter. Click **OK**. The ``There are no active physical network adapters for the switch.`` warning is displayed. Click **OK**.
7. Click the **...** in the *vSwitch0* display and then select **Remove**. Click **OK** to confirm you want to remove the switch.
8. In the same display, select the private switch and click **MANAGE PHYSICAL ADAPTERS**.
9. Select **uplink1** and click **+**. `vmnic2` is displayed.
10. Click **OK**, and then **OK** again to exit the dialog.

## Related links
{: #vc_vsphere_70_upgrade-related}

* [About vCenter Server upgrade](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vcenter.upgrade.doc/GUID-9ED7B32A-019F-4A97-BC58-1A9BF7D16C57.html){: external}
* [About VMware ESXi upgrade](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.esxi.upgrade.doc/GUID-65B5B313-3DBB-4490-82D2-A225446F4C99.html){: external}
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
