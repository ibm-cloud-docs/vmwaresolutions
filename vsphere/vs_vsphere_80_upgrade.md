---

copyright:

  years:  2024, 2026

lastupdated: "2026-01-21"

keywords: vSphere upgrade, NSX upgrade, PSC upgrade, flexible upgrade, upgrade from vsphere 7 to 8

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Upgrading vSphere software from version 7.0 to 8.0
{: #vs_vsphere_80-upgrade}

{{site.data.content.vms-deprecated-note}}

You can upgrade the VMware vSphere® software on your {{site.data.keyword.vcf-flex-short}} instances to version 8.0.

## Before you begin the upgrade
{: #vs_vsphere_80_upgrade-procedure-before}

* If you encounter a problem during the upgrade process, use the {{site.data.keyword.vmwaresolutions_short}} upgrade ticket that you opened at the beginning of the process to [contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support). If required, {{site.data.keyword.IBM}} Support opens tickets with Broadcom® Support.
* You must follow the support process so that VMware Solutions can provide Broadcom Support with all the information about the VMware vCenter Server® design and setup, and the {{site.data.keyword.cloud_notm}} information.
* By following the support process, accurate information can be shared with Broadcom Support, which shortens the support experience. After {{site.data.keyword.IBM_notm}} Support provides the necessary information to Broadcom Support, you can interact with Broadcom Support directly.
* Keep a record of all the new passwords and credentials that you create as part of the upgrade process. IBM Support requires these credentials at the end of the upgrade process to update its internal database.

## Procedure to set the cluster DRS to manual
{: #vs_vsphere_80_upgrade-procedure-drs}

You must set the cluster DRS (Distributed Resource Schedule) to manual to prevent unexpected migrations during the upgrade process.

Complete the following steps from the vSphere Web Client:
1. Select **Host and Clusters > Cluster > Configure > DRS**.
2. Click **EDIT**.
3. Set the **DRS** field to **Manual**.

## Procedure to create a standard switch for the new vCenter Server Appliance
{: #vs_vsphere_80_upgrade-procedure-vcsa}

Temporarily install the new vCenter Server Appliance that you deploy onto a vSphere Standard Switch. One of the existing `vmnics` is reassigned from the distributed switch during the upgrade.

Complete the following steps from the vSphere Web Client:
1. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Select a host for the new vCenter Server Appliance.
2. For the private network switch, select **Managed Physical Adapters**. The private network switch name ends with `-private`.
3. Select **uplink1/vmnic2**, then click the **Close** icon ![Close icon](../../icons/close-icon.svg "Close") to delete the adapter. Click **OK**.
4. Return to the **Virtual Switches** pane and click **Add Networking**.
   1. Select **Virtual Machine Port Group** for a standard switch and click **Next**.
   2. For **New Standard Switch**, set the MTU to 9000 and click **Next**.
   3. Click the green **Add** icon ![Add icon](../../icons/add.svg "Add") to add an adapter. Click **OK**, then **Next** to accept `vmnic2`.
   4. For **Connection Settings**, keep the **VM Network** and **VLAN ID None** defaults. Click **Next**, then **Finish**. In the list of switches, `Standard Switch: vSwitch0` is displayed.
5. Make a note of the **Network Setting** for the vCenter Server Appliance VM. You must update the new vCenter Server appliance to match.
   * From the vSphere Web Client, click the VM for the vCenter Server appliance. Note the name, ending with `vc`.
   * From the middle pane, click the **Networks** tab. Note the name of the distributed port group, ending with `-dpg-mgmt`. 

## Procedure to upgrade vCenter Server
{: #vs_vsphere_80_upgrade-procedure-vcenter}

Follow the Broadcom instructions for upgrading vCenter Server. For more information, see [Upgrade a vCenter Server Appliance 6.5 or 6.7 with an embedded Platform Services Controller by using the GUI](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/vcenter-upgrade/upgrading-and-updating-the-vcenter-server-appliance/gui-upgrade-of-the-vcsa-and-psc-appliance/upgrade-the-vmware-vcenter-server-appliance-with-embedded-sso.html){: external}.

Complete the following requirements during the upgrade:
* To mount the VMware-VCSA ISO, go to the `visa-ui-installer\win32` directory and run the installer.
* In the vCenter Server installer, select the **Upgrade** flow and complete the steps in the installer.
* You must use the IP address and credentials (`administrator` and `root`) for the current vCenter Server appliance. Use the IP address and the `root` password for the VMware ESXi host of the current vCenter Server Appliance and the host where you want to deploy the new vCenter Server Appliance version 8.0 or later. You must use a new temporary IP address, gateway, and subnet mask for the new vCenter Server Appliance during installation.
* Complete Stage 2 when prompted. Note any warnings and take the appropriate actions.

## Updating vCenter Server licenses
{: #vs_vsphere_80_upgrade-license-update}

After you upgrade the vSphere software to version 8, update the licenses on vCenter Server. If you have a VMware vSAN cluster, you must also update the vSAN license. To access the new licenses, see [Retrieving VCF license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses).

### Procedure to update the vCenter Server license
{: #vs_vsphere_80_upgrade-license-update-vcs}

Complete the following steps from the vSphere Web Client:
1. Click **Administration menu > Licensing > Licenses**.
2. From the **Licenses** page, click **+ Add New Licenses**.
3. Enter the new vCenter Server license key in the **New Licenses** field. Then, enter a name for the license and click **OK**.
4. From the **Assets** page, select the vCenter Server instance under **VCENTER SERVER SYSTEMS** and click **Assign License**. Then, select the new license and click **OK**.
5. From the **Licenses** page, find the license with the product name **VMware vCenter Server 6 Standard** and click **Remove Licenses**.

### Procedure to update the vSAN cluster license
{: #vs_vsphere_80_upgrade-license-update-vsan}

Complete the following steps from the vSphere Web Client:
1. From the **Licenses** page, click **+ Add New Licenses**.
2. Enter the new vSAN license keys in the **New Licenses** field. If you have multiple vSAN license keys, enter all the licenses in the **New Licenses** field, specify a name for each license, and then click **OK**.
3. Complete the following steps from the **Assets** page.
   1. Select **VSAN CLUSTERS**.
   2. Select the vSAN cluster and click **Assign License**.
   3. Select one of the new vSAN license keys and click **OK**.
   4. Repeat this step for each vSAN cluster.
4. From the **Licenses** page, select all the old vSAN cluster licenses and click **Remove Licenses**.

### Procedure to remove the temporary standard switch
{: #vs_vsphere_80_upgrade-procedure-remove-switch}

Reassign the `vmnic` that you temporarily used on the standard switch back to the distributed switch that it was originally associated with.

Complete the following steps from the vSphere Web Client:
1. Go to the new vCenter Server appliance.
2. Under **Actions** click **Edit Settings**.
3. For network adapter 1, browse to the name of the distributed port group that ends with `-dpg-mgmt` that you previously noted. Save the changes.
4. Go to the host where you deployed the new appliance. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Then, click **MANAGE PHYSICAL ADAPTERS** for `vSwitch0`.
5. Select **vmnic2** and click the red **X** to delete the adapter. Click **OK**. The `There are no active physical network adapters for the switch.` warning is displayed. Click **OK**.
6. Click the **...** in the `vSwitch0` display and then select **Remove**. Click **OK** to confirm you want to remove the switch.
7. In the same display, select the private switch and click **MANAGE PHYSICAL ADAPTERS**.
8. Select **uplink1** and click **+**. `vmnic2` is displayed.
9. Click **OK**, and then **OK** again to exit the window.

## Procedure to upgrade the ESXi hosts
{: #vs_vsphere_80_upgrade-procedure-esxi-upgrade}

Review the following information before you upgrade the ESXi hosts:

* Determine whether your servers are eligible to be upgraded to vSphere 8. For more information, see the [VMware by Broadcom Compatibility Guide](https://compatibilityguide.broadcom.com/){: external}.
* Ensure that the vCenter Server version is 8.0 or later.
* Obtain the ISO image and the update files either from Broadcom, if you have a direct support contract with them, or by [opening an IBM Support ticket](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).
* Back up your environment before you start the upgrade.

### Preparing for the upgrade of ESXi hosts
{: #vs_vcs_80_upgrade-procedure-esxi-prep}

To complete the upgrade from version 7 to 8, you must establish a baseline group configuration in VMware vSphere Update Manager (VUM) and attach it to the cluster that contains the hosts to be upgraded.

1. **Import the ISO image and the updates files**.

   Complete the following steps in the vSphere Web Client:
   1. Import the vSphere 8 ISO image. Go to the Lifecycle Manager section of vCenter Server and click the **Imported ISOs** tab. After the import is completed, the ISO image is displayed in the list.
   2. Import the `NSX-LCP` update that matches the version of VMware NSX that is installed. The file name is similar to `nsx-lcp-esxio-4.2.3.0.0.24866350-esx80-unified.zip` (ensure that it has `unified` in the name). After the import is completed, the update is displayed on the **Updates** tab. Ensure that the rollup toggle is off as this update is not a rollup update.
   3. Import the `i40en` network driver by following the previous step. Extract the contents of the `Intel-i40en_2.9.2.0-1OEM.800.1.0.20613240_24226995-package.zip` file and import it from the folder where you extracted it. After the import is completed, the `i40en` driver is displayed on the **Updates** tab.

2. **Set up the NSX connection to vCenter Server**.

   Complete the following steps on the NSX manager UI to allow for communications between vCenter Server and NSX Manager:
   1. Click the **System** tab and click **Fabric > Compute Managers** from the left navigation panel. Click the vCenter Server compute manager and click **EDIT**.
   3. On the **Edit Compute Manager** window, switch the **Create Service Account** and **Enable Trust** toggles to **YES**.
   4. Click **EDIT** next to the **FQDN or IP Address** field, enter the credentials for vCenter Server (`administrator@vsphere.local` and the correct password), and click **SAVE**.

3. **Create baselines and baseline groups**.

   Complete the following steps on the **Create Baseline** window to create an upgrade baseline for the ISO image file:
   1. Under **Name and description**, enter a name for the baseline and select the **Upgrade** option for **Content**. Click **NEXT**.
   2. Under **Select ISO**, choose the imported 8.0u3g ISO image file. Click **NEXT**.
   3. Under **Summary**, click **FINISH**.

   Complete the following steps on the **Create Baseline** window to create an extension baseline for the NSX Local Control Plane (LCP):
   1. Under **Name and description**, enter a name for the baseline and select the **Extension** option for **Content**. Click **NEXT**.
   2. Under **Select Extensions**, choose the imported NSX LCP. Click **NEXT**.
   3. Under **Summary**, click **FINISH**.

   Complete the following steps on the **Create Baseline** window to create an extension baseline for the `i40en` network driver:
   1. Under **Name and description**, enter a name for the baseline and select the **Extension** option for **Content**. Click **NEXT**.
   2. Under **Select extensions**, choose the downloaded `i40en` driver. Click **NEXT**.
   3. Under **Summary**, click **FINISH**.

   Complete the following steps on the **Create Baseline Group** window to combine the previous baselines into a baseline group. A baseline group is a container that allows selection of a set of baselines to apply.
   1. Under **Name and description**, enter a name for the baseline group and click **NEXT**.
   2. Under **Upgrade Baseline**, ensure that the **Add the following baseline to the group** checkbox is selected and click **NEXT**.
   3. Under **Patch Baselines**, click **NEXT**. You don't need to include any patches.
   4. Under **Extension Baselines**, select the previous extension baselines (NSX LCP and `i40en` driver). Click **NEXT**.
   5. Under **Summary**, click **FINISH**.

   On the **Lifecycle Manager** UI, verify that the new baseline group is displayed and select it to verify that its content is correct.

4. **Attach the baseline group to the cluster**.

   Complete the following steps in the vSphere Web Client:
   1. Click the cluster name from the left navigation panel and click the **Updates** tab.
   2. Scroll down the page and under **Attached Baselines** click **ATTACH > Attach Baseline or Baseline Group**.
   3. Select the baseline group that was created in a previous step and click **ATTACH**. The baseline group gets attached to the cluster.

### Remediating the ESXi hosts
{: #vs_vsphere_80_upgrade-procedure-esxi-remed-exist}

Complete the following steps in the vSphere Web Client:
1. Select a host that does not have vCenter Server installed, for example, `host-wd003`. Verify that the vCenter Server VM does not exist on this host.
2. Click the **Updates** tab and scroll down the page. In the **Attached Baseline and Baseline Groups** table, select the baseline group that was attached in a previous step.
3. Right under **Attached Baseline and Baseline Groups**, click **REMEDIATE**.
4. Accept the Foundation Agreement and click **OK**. If you see a warning `HA admission control will be disabled`, you can ignore it.
5. Expand the **Remediation setting** section and ensure that the checkbox `Ignore warnings about unsupported hardware devices` is selected so that any TPM 1.2 warnings are ignored.
6. Click **REMEDIATE**. A number of tasks start to run in the tasks list, for example, `Migrate virtual machines` or `reboot`.
7. Monitor the remediation progress in the **Remediate entity** task:
   * The host is put into maintenance mode and then powered off.
   * As a result, the host status in vCenter Server displays `disconnected`.
   * The entire process for a single host can take 15-20 minutes, with multiple host restarts.

8. Repeat the previous steps to remediate all hosts that do not have vCenter Server installed. After all hosts are remediated, the **Updates** tab of the cluster shows all hosts at version 8.

### Enabling Lifecycle Manager
{: #vs_vcs_80_upgrade-procedure-esxi-lcm}

For ongoing maintenance, convert the upgraded cluster to an LCM (Lifecycle Manager) cluster by enabling single image management through LCM.

Complete the following steps in the vSphere Web Client:
1. Click the cluster name from the left navigation panel and click the **Updates** tab.
2. Click **MANAGE WITH A SINGLE IMAGE**. In the table, ensure that the autodetected network driver is included. Other components, such as the NSX LCP, is not displayed in this table. Click **SAVE**.
3. Under **Check Image Compliance**, a message indicates that the hosts are not compliant because TPM 1.2 exists on the hardware and vSphere FDM is missing. vSphere FDM was not automatically installed when the baseline group was attached. Click **FINISH IMAGE SETUP**.
4. With the cluster selected in the left navigation panel, click **REMEDIATE ALL**.

The process of remediation starts. For each host:
* The VMs are moved off the host.
* The host is put into maintenance mode.
* The host is restarted one or more times.
* The host is taken out of maintenance mode.

Then, the process continues with the next host until all hosts are remediated.

### Remediating new hosts that are added
{: #vs_vcs_80_upgrade-procedure-esxi-remed-new}

If you add a host to a vSphere 8 cluster from the VMware Solutions console, the host is provisioned with vSphere 7. After the host is added, you see errors and alarms in the vSphere Web Client and in NSX Manager, which indicate that the host has compatibility issues or is not available.

To remediate the new host so it matches the current vSphere version of the cluster, complete the following steps in the vSphere Web Client:
1. Click the cluster name from the left navigation panel and click the **Updates** tab. A message indicates that the host is not compliant.
2. Click **REMEDIATE ALL** to review the remediation impact.
3. Accept the Foundation Agreement and click **START REMEDIATION**. A number of tasks start to run in the tasks list.
4. If you see problems with the NSX configuration of the new host on the NSX Manager UI, wait for the additional tasks that are running in the vSphere Web Client to complete.

   You might see the `Apply NSX Solution` task running, which is updating the new host with the NSX VIB bundles needed for the NSX configuration.

5. While tasks are running in the vSphere Web Client, monitor the progress on the NSX Manager UI:
   * If you see errors, click **Install Failed > VIEW ERRORS**.
   * After some time, the errors are resolved and the NSX configuration displays **Success**.

The entire process can take 10-15 minutes after which the operation is complete in vCenter Server and the **Updates** tab of the cluster shows all hosts at version 8.

### Upgrading the disk format post-remediation
{: #vs_vcs_80_upgrade-procedure-esxi-remed-post}

To upgrade the disk format, complete the following steps in the vSphere Web Client:
1. Click the cluster name from the left navigation panel and click the **Configure** tab.
2. Click **vSAN > Services**. On the **vSAN Services** page, click **PRE-CHECK UPGRADE**.
3. On the same page, click **UPGRADE**, and then click **UPGRADE** again on the window that appears.

A number of tasks start to run in the tasks list. Monitor their progress until completion.

## Procedure to update ESXi host licenses
{: #vs_vsphere_80_upgrade-license-update-esxi}

To update the ESXi host licenses, you must first retrieve your new vSphere licenses from the {{site.data.keyword.cloud_notm}} console. For more information, see [Retrieving VCF license keys](/docs/vmwaresolutions?topic=vmwaresolutions-licenses_vcf-licenses).

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
* [vCenter Server upgrade](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/8-0/vcenter-upgrade.html){: external}
* [VMware ESXi upgrade](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/9-0/esx-upgrade.html){: external}
