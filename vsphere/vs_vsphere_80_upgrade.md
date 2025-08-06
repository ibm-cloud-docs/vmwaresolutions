---

copyright:

  years:  2024, 2025

lastupdated: "2025-08-06"

keywords: vSphere migration, NSX upgrade, PSC upgrade, flexible upgrade

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Upgrading VMware vSphere software from vSphere 7.0 to 8.0
{: #vs_vsphere_80-upgrade}

You can upgrade the VMware vCenter Server® vSphere software on your instances to version 8.0.

## Procedure to upgrade vCenter Server vSphere software from 7.0 to 8.0
{: #vs_vsphere_80-upgrade-procedure}

### Before you begin
{: #vs_vsphere_80_upgrade-procedure-before}

* If you encounter a problem during the upgrade process, use the {{site.data.keyword.vmwaresolutions_short}} upgrade ticket that you opened at the beginning of the process to [contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support). If required, IBM Support will open tickets with Broadcom Support.
* You must follow the support process to ensure that {{site.data.keyword.vmwaresolutions_short}} provides Broadcom Support with all the information about the vCenter Server design and setup, and the {{site.data.keyword.cloud_notm}} information.
* By following the support process, you ensure that accurate information is shared with Broadcom Support, which shortens the support experience. After IBM Support provides the necessary information to Broadcom Support, you can interact with Broadcom Support directly.
* Ensure that you keep a record of all the new passwords and credentials that you create as part of the upgrade process. IBM Support requires these credentials at the end of the upgrade process to update their internal database.

### Procedure to set the cluster Distributed Resource Schedule to manual
{: #vs_vsphere_80_upgrade-procedure-drs}

You must set the cluster Distributed Resource Schedule (DRS) to manual to prevent unexpected migrations during the upgrade process.

Complete the following steps from the vCenter Server user interface.

1. Select **Host and Clusters > Cluster > Configure > DRS**.
2. Click **EDIT**.
3. Set the **DRS** field to **Manual**.

### Procedure to create a standard switch for the new vCenter Server Appliance
{: #vs_vsphere_80_upgrade-procedure-vcsa}

Temporarily install the new vCenter Server Appliance that you deploy onto a vSphere Standard Switch. One of the existing `vmnics` is reassigned from the distributed switch during the upgrade.

Complete the following steps from the vCenter Server user interface.

1. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Select a host for the new vCenter Server Appliance.
2. For the private network switch, select **Managed Physical Adapters**. The private network switch name ends with `-private`.
3. Select **uplink1/vmnic2**, then click the **Close** icon ![Close icon](../../icons/close-icon.svg "Close") to delete the adapter. Click **OK**.
4. Return to the **Virtual Switches** pane and click **Add Networking**.
   1. Select **Virtual Machine Port Group** for a standard switch and click **Next**.
   2. For **New Standard Switch**, set the MTU to 9000 and click **Next**.
   3. Click the green **Add** icon ![Add icon](../../icons/add.svg "Add") to add an adapter. Click **OK**, then **Next** to accept `vmnic2`.
   4. For **Connection Settings**, keep the **VM Network** and **VLAN ID None** defaults. Click **Next**, then **Finish**. *Standard Switch: vSwitch0* is displayed in the list of switches.
5. Make a note of the Network Setting for the vCenter Server Appliance VM. You must update the new vCenter appliance to match.
   * From the vCenter Server user interface, click the VM for the vCenter appliance. Note the name, ending with `vc`.
   * From the middle pane, click the **Networks** tab. Note the name of the distributed port group, ending with `-dpg-mgmt`. 

### Procedure to upgrade vCenter Server
{: #vs_vsphere_80_upgrade-procedure-vcenter}

Follow the VMware instructions for upgrading vCenter. For more information, see [Upgrade a vCenter Server Appliance 6.5 or 6.7 with an embedded Platform Services Controller by using the GUI](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/vcenter-server-upgrade-7-0/upgrading-and-updating-the-vcenter-server-appliance/gui-upgrade-of-the-vcsa-and-psc-appliance/upgrade-the-vmware-vcenter-server-appliance-with-embedded-sso.html){: external}.

Ensure to complete the following requirements during the upgrade:

* Mount the VMware-VCSA ISO, go to the `visa-ui-installer\win32` directory, and run the installer.
* In the vCenter Server installer dialog, select the **Upgrade** flow and complete the steps in the installer.
* You must use the IP and credentials (administrator and root) for the current vCenter Server appliance. Use the IP and root password for the ESXi host of the current vCenter Server Appliance and the host where you want to deploy the new 8.0 or later vCenter Server Appliance. You must use a new temporary IP address, gateway, and subnet mask for the new vCenter Server Appliance during installation.
* Complete Stage 2 when prompted. Ensure to note any warnings and take the appropriate actions.

### Updating vCenter Server licenses
{: #vs_vsphere_80_upgrade-license-update}

After you upgrade the vCenter Server to vSphere 8, update the licenses on vCenter Server. If you have a vSAN cluster, you must also update the vSAN license. To access the new licenses, see [Retrieving VCF license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses).

#### Procedure to update the vCenter Server license
{: #vs_vsphere_80_upgrade-license-update-vcs}

Complete the following steps from the vCenter Server user interface.

1. Select **Administration menu > Licensing > Licenses**.
2. From the **Licenses** page, click **+ Add New Licenses**.
3. Enter the new vCenter Server license key in the **New Licenses** field. Then, enter a name for the license and click **OK**.
4. From the **Assets** page, select the vCenter instance under **VCENTER SERVER SYSTEMS** and click **Assign License**. Then, select the new license and click **OK**.
5. From the **Licenses** page, find the license with the product name **VMware vCenter Server 6 Standard** and click **Remove Licenses**.

#### Procedure to update the vSAN cluster license
{: #vs_vsphere_80_upgrade-license-update-vsan}

1. From the **Licenses** page, click **+ Add New Licenses**.
2. Enter the new vSAN license keys in the **New Licenses** field. If you have multiple vSAN license keys, enter all the licenses in the **New Licenses** field, specify a name for each license, and then click **OK**.
3. Complete the following steps from the **Assets** page.
   1. Select **VSAN CLUSTERS**.
   2. Select the vSAN cluster and click **Assign License**.
   3. Select one of the new vSAN license keys and click **OK**.
   4. Repeat this step for each vSAN cluster.
4. From the **Licenses** page, select all the old vSAN cluster licenses and click **Remove Licenses**.

#### Procedure to remove the temporary standard switch
{: #vs_vsphere_80_upgrade-procedure-remove-switch}

Reassign the `vmnic` that you temporarily used on the standard switch back to the distributed switch it was originally associated with.

Complete the following steps from the vCenter Server user interface.

1. Go to the new vCenter Server appliance.
2. Under **Actions** click **Edit Settings**.
3. For network adapter 1, browse to the name of the distributed port group that ends with `-dpg-mgmt` that you previously noted. Save the changes.
4. Go to the host where you deployed the new appliance. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Then, click **MANAGE PHYSICAL ADAPTERS** for *vSwitch0*.
5. Select **vmnic2** and click the red **X** to delete the adapter. Click **OK**. The `There are no active physical network adapters for the switch.` warning is displayed. Click **OK**.
6. Click the **...** in the *vSwitch0* display and then select **Remove**. Click **OK** to confirm you want to remove the switch.
7. In the same display, select the private switch and click **MANAGE PHYSICAL ADAPTERS**.
8. Select **uplink1** and click **+**. `vmnic2` is displayed.
9. Click **OK**, and then **OK** again to exit the window.

### Procedure to upgrade Stor VIB (Broadcom driver)
{: #vs_vsphere_80_upgrade-procedure-broadcom}

You must upgrade the Broadcom driver before you upgrade the ESXi host.

1. Extract the `007.1316.0000.0000_Unified_StorCLI_PUL.zip` file to a directory on your windows jump server.
2. Locate the `vmware-storcli.vib` file in the extracted file contents.
3. Copy the `.vib` file to either a vSAN or NFS data store that is mounted on the ESXi hosts for the instance. Use vCenter Server to reference the extracted file on your jump server.
4. SSH into each ESXi host and run the following VIB Upgrade command:
   `esxcli software vib update -v /<path to vsan or nfs datastore from step 3>/vmware-storcli.vib --no-sig-check`
   The following installation results are displayed.
    `Message: Operation finished successfully.    Reboot Required: false    VIBs Installed: Broadcom_bootbank_vmware-storcli_007.1316.0000.0000-01    VIBs Removed: LSI_bootbank_vmware-storcli_007.0916.0000.0000-01    VIBs Skipped:`
5. Run the following command to validate the installation:
   `> esxcli software vib list |grep vmware-storcli
   vmware-storcli    007.1316.0000.0000-01    Broadcom  PartnerSupported  2020-04-16`
6. Repeat for each host.

### Procedure to upgrade the ESXi hosts
{: #vs_vsphere_80_upgrade-procedure-esxi-upgrade}



1. From the vCenter Server user interface, go to **LCM menu > LifeCycle Manager**.
2. Select **IMPORT ISO > IMPORT ISO**, and then the ISO file.
3. Create the baseline. Select **BASELINE > CREATE** and use the imported ISO from the previous step.
4. For each host, choose the host in the vCenter browser tree. Then, select **update** (located in the far left in the main window).
5. If the Zerto VRA is present on the host, put the host into maintenance mode first. Recent releases of Zerto stop the VRA, which otherwise would prevent the update.
6. Complete the update.
   1. [ATTACH] Baseline, select the previously created baseline.
   2. Select Baseline and [REMEDIATE].
7. Remediate each host in turn. After remediation, ensure to pull the host out of maintenance mode.

Update your IBM Support ticket to indicate that your upgrade is complete and request that the IBM Cloud for VMware database be updated to reflect that the cluster is vSphere 8.

There are several methods to upgrade your ESXi hosts. For more information, see [Overview of the ESXi Host Upgrade Process](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/esxi-upgrade-7-0.html){: external}. If you need to access an ISO file or upgrade bundle as part of your selected method, [contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

If the upgrade process fails immediately and the `host cannot enter maintenance mode` error message is displayed, shut down the Zerto ZVAs and try again. The ZVRA VMs automatically start as each server comes out of remediation. For more information about continuing Zerto replication during the upgrade process, see [How to place a host with an associated VRA into maintenance mode](https://www.zerto.com/myzerto/knowledge-base/how-to-place-a-host-with-an-associated-vra-into-maintenance-mode/){: external}.
{: note}

### Procedure to update ESXi host licenses
{: #vs_vsphere_80_upgrade-license-update-esxi}

To update the ESXi host licenses, you must first retrieve your new vSphere licenses from the IBM Cloud console. For more information, see [Retrieving VCF license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses).

1. From the **Licenses** page, click **+ Add New Licenses**.
2. Enter the new vSphere 8 license keys in the **New Licenses** field. If you have multiple vSphere 8 license keys, input the all of the licenses in the **New Licenses** filed, enter a name for each license, and click **OK**.
3. Complete the following steps from the **Assets** page.
   1. Select **HOSTS**.
   2. Select the host and click **Assign License**.
   3. Select one of the new vSphere 8 license keys and click **OK**.
   4. Repeat this step for each upgraded host.
4. From the **Licenses** page, select all of the old vSphere 6 licenses and click **Remove Licenses**.

## Related links
{: #vs_vsphere_80_upgrade-related}

* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [vCenter Server upgrade](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/vcenter-server-upgrade-7-0.html){: external}
* [ESXi upgrade](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/esxi-upgrade-7-0.html){: external}
