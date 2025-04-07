---

copyright:

  years: 2024, 2025

lastupdated: "2025-04-07"

keywords: vCenter upgrade, NSX upgrade, PSC upgrade, vcenter 8

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Migrating to vSphere 8.0
{: #vc_vcs_80_upgrade}

You can upgrade the VMware vCenter Server® software on your instances to version 8.0 and migrate your NFS and gateway clusters to VMware vSphere® 8.0.

## Before you begin
{: #vc_vcs_80_upgrade-prereq}

{{site.data.content.para-vcs80upgrade-prereq}}

Complete the following requirements before you begin the upgrade:
* Before you upgrade vCenter Server, you might need to upgrade VMware NSX®. You are responsible to determine the interoperability requirements for all of your software, including all VMware software and third-party software. For more information about VMware interoperability, see [Product interoperability matrix](https://sim.esp.spespg1.vmw.saas.broadcom.com/Interoperability){: external}.
* Open a support ticket with the {{site.data.keyword.vmwaresolutions_full}} team to notify them that an upgrade is being planned. The ticket remains open until the instance is registered at the upgraded level in the {{site.data.keyword.vmwaresolutions_short}} console.
* Verify that the vCenter Server `root` user ID and its credentials are visible on the console. If your instance was initially ordered in a VMware Solutions environment V2.5 to V5.7, only the `customerroot` account is visible on the console. For instances, clusters, hosts, and vCenter Server VMs ordered in VMware Solutions V5.7 and later, the `customerroot` user is no longer created by the VMware Solutions automation.
* If you encounter a problem during the upgrade process, use the {{site.data.keyword.vmwaresolutions_short}} upgrade ticket that you opened at the beginning of the process to contact IBM Support. If required, IBM Support will open tickets with Broadcom Support.
* Follow the support process to ensure that {{site.data.keyword.vmwaresolutions_short}} provides Broadcom Support with all the information about the vCenter Server design and setup, and the {{site.data.keyword.cloud}} information.
* By following the support process, you ensure that accurate information is shared with Broadcom Support, which shortens the support experience. After IBM Support provides the necessary information to Broadcom Support, you can interact with Broadcom Support directly.
* Ensure that you keep a record of all the new passwords and credentials that you create as part of the upgrade process. IBM Support requires these credentials at the end of the upgrade process to update its internal database.

## Procedure to upgrade to vCenter Server 8.0
{: #vc_vcs_80_upgrade-procedure-vcenter}

1. **Set the cluster Distributed Resource Schedule to Manual.** You must set the cluster Distributed Resource Schedule (DRS) to manual to prevent unexpected migrations during the upgrade process.
   Complete the following steps from the vCenter Server user interface.
   1. Select **Host and Clusters > Cluster > Configure > DRS**.
   2. Click **EDIT**.
   3. Set the **DRS** field to **Manual**.
2. **Create a standard switch for the new vCenter Server Appliance.** Temporarily install the new vCenter Server Appliance that you deploy onto a vSphere Standard Switch. One of the existing ``vmnics`` is reassigned from the distributed switch during the upgrade.
   Complete the following steps from the vCenter Server user interface.
   1. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Select a host for the new vCenter Server Appliance.
   2. For the private network switch, select **Managed Physical Adapters**. The private network switch name ends with ``-private``.
   3. Select **uplink1/vmnic2**, then click **Close** ![Close icon](../../icons/close-icon.svg "Close") to delete the adapter. Click **OK**.
   4. Return to the **Virtual Switches** and click **Add Networking**.
      1. Select **Virtual Machine Port Group** for a standard switch and click **Next**.
      2. For **New Standard Switch**, set the MTU to 9000 and click **Next**.
      3. Click the green **Add** icon ![Add icon](../../icons/add.svg "Add") to add an adapter. Click **OK**, then **Next** to accept ``vmnic2``.
      4. For **Connection Settings**, keep the **VM Network** and **VLAN ID None** defaults. Click **Next**, then **Finish**. *Standard Switch: vSwitch0* is displayed in the list of switches.
   5. Make a note of the Network Setting for the vCenter Server Appliance VM. Update the new vCenter appliance to match.
      * From the vCenter Server user interface, click the VM for the vCenter appliance. Note the name that ends with ``vc``.
      * From the middle pane, click the **Networks** tab. Note the name of the distributed port group, ending with ``-dpg-mgmt``.
3. **Upgrade vCenter Server.** Follow the VMware instructions for upgrading vCenter Server. For more information, see [Upgrade a vCenter Server Appliance 6.7 with an Embedded Platform Services Controller or 7.0 by Using the GUI](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/8-0/vcenter-server-upgrade-8-0/upgrading-and-updating-the-vcenter-server-appliance/gui-upgrade-of-the-vcsa-and-psc-appliance/upgrade-the-vmware-vcenter-server-appliance-with-embedded-sso.html#GUID-6A5C596D-103E-4024-9353-5569263EB427-en){: external}.
   Ensure to complete the following requirements during the upgrade:
   * Mount the VMware-VCSA ISO, go to the `visa-ui-installer\win32` directory, and run the installer.
   * In the vCenter Server 8.0 installer window, select the **Upgrade** flow and complete the steps in the installer.
   * Use the IP and credentials (administrator and root) for the current vCenter Server Appliance. Use the IP and root password for the ESXi host of the current vCenter Server Appliance and the host where you want to deploy the new 8.0 vCenter Server Appliance. Use a new temporary IP address, gateway, and subnet mask for the new vCenter Server Appliance during installation.
   * Complete Stage 2 when prompted. Ensure to note any warnings and take the appropriate actions.

   After you upgrade to version 8, in the VMware vCenter Server Appliance, the details pane for the vCenter object takes several minutes to load. This problem is resolved if you enable the connection of the vCenter Server Appliance to the VMware update repository.
   {: important}

4. **Update vCenter Server and ESXi host licenses.** After you upgrade to vCenter Server 8.0, update the licenses on vCenter Server. If you have a vSAN cluster, you must also update the vSAN license. For more information about obtaining a new vCenter Server 8.0 license, see [Ordering VMware licenses](/docs/vmware?topic=vmware-ordering-vmware-license). For assistance with new licenses, [contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).
   * **Procedure to update the vCenter Server license**:
      Complete the following steps from the vCenter Server user interface.
      1. Select the **Administration menu > Licensing > Licenses**.
      2. From the **Licenses** page, click **+ Add New Licenses**.
      3. Enter the new vCenter Server 8.0 license key in the **New Licenses** field. Then, enter a name for the license and click **OK**.
      4. From the **Assets** page, select the instance under **VCENTER SERVER SYSTEMS** and click **Assign License**. Then, select the new license and click **OK**.
      5. From the **Licenses** page, find the license with the product name **VMware vCenter Server 6 Standard** and click **Remove Licenses**.
   * **Procedure to update the vSAN cluster license**:
      1. From the **Licenses** page, click **+ Add New Licenses**.
      2. Enter the new vSAN license keys in the **New Licenses** field. If you have multiple vSAN license keys, enter all the licenses in the **New Licenses** field, specify a name for each license, and then click **OK**.
      3. Complete the following steps from the **Assets** page.
         1. Select **VSAN CLUSTERS**.
         2. Select the vSAN cluster and click **Assign License**.
         3. Select one of the new vSAN license keys and click **OK**.
         4. Repeat this step for each vSAN cluster.
      4. From the **Licenses** page, select all the old vSAN cluster licenses and click **Remove Licenses**.
5. **Remove the temporary standard switch.** Reassign the ``vmnic`` that you temporarily used on the standard switch back to the distributed switch it was originally associated with.
   Complete the following steps from the vCenter Server user interface.
   1. Go to the new vCenter Server appliance.
   2. Under **Actions** click **Edit Settings**.
   3. For network adapter 1, browse to the name of the distributed port group that ends with ``-dpg-mgmt`` that you previously noted. Save the changes.
   4. Go to the host where you deployed the new appliance. Select **Hosts and Clusters > HOST > Configure > Virtual Switches**. Then, click **MANAGE PHYSICAL ADAPTERS** for *vSwitch0*.
   5. Select **vmnic2** and click the red **X** to delete the adapter. Click **OK**. The ``There are no active physical network adapters for the switch.`` warning is displayed. Click **OK**.
   6. Click the **...** in the *vSwitch0* display and then select **Remove**. Click **OK** to confirm you want to remove the switch.
   7. In the same display, select the private switch and click **MANAGE PHYSICAL ADAPTERS**.
   8. Select **uplink1** and click **+**. `vmnic2` is displayed.
   9. Click **OK**, and then **OK** again to exit the window.

## Procedure to migrate from vSphere 7.0 to vSphere 8.0
{: #vc_vcs_80_migrate-procedure-vsphere}

You cannot migrate a vSAN cluster to vSphere 8.0.
{: important}

If you have a gateway cluster with vSphere 7.0 and you want to migrate it to vSphere 8.0, complete the following tasks:
1. Create a new vSphere 8.0 gateway cluster.
2. Carefully coordinate the migration of your gateway virtual machines and configuration from the old cluster to the new cluster. This way your protected VLANs do not lose service or connectivity. This action includes migration of the virtual machines and their configuration, or creation of new virtual machines with duplicate configuration. As part of this sequence, remove your protected VLANs from protection of the old cluster and assign them to the new cluster.
3. Remove the original gateway cluster.

If you have an NFS cluster with vSphere 7.0 and you want to migrate it to vSphere 8.0, perform a rolling replacement of servers in the cluster. For each vSphere 7.0 server, complete the following tasks:
1. Create a new vSphere 8.0 server.
2. Ensure that the vSphere 8.0 server is configured to your needs and remove it from maintenance mode.
3. Put the vSphere 7.0 server into maintenance mode.
4. Remove the vSphere 7.0 server from your cluster.

### Procedure to upgrade the ESXi hosts (Sapphire Rapids only)
{: #vc_vcs_80_upgrade-procedure-esxi-sapphire}

1. From the vCenter Server user interface, go to **LCM menu > LifeCycle Manager**.
2. Select **IMPORT ISO > IMPORT ISO**, and then the ISO file.
3. Create the baseline. Select **BASELINE > CREATE** and use the imported ISO from the previous step.
4. For each host, choose the host in the vCenter browser tree. Then, select **update** (located in the far left in the main window).
5. If the Zerto VRA is present on the host, put the host into maintenance mode first. Recent releases of Zerto stop the VRA, which otherwise would prevent the update.
6. Complete the update.
   1. [ATTACH] Baseline, select the previously created baseline.
   2. Select Baseline and [REMEDIATE].
7. Remediate each host in turn. After remediation, ensure to pull the host out of maintenance mode.

There are several methods to upgrade your ESXi hosts. For more information, see [Overview of the ESXi Host Upgrade Process](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/esxi-upgrade-7-0.html){: external}. If you need to access an ISO file or upgrade bundle as part of your selected method, [contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

If the upgrade process fails immediately and the ``host cannot enter maintenance mode`` error message is displayed, shut down the Zerto ZVAs and try again. The ZVRA VMs automatically start as each server comes out of remediation. For more information about continuing Zerto replication during the upgrade process, see [How to Place a Host with an Associated VRA into Maintenance Mode](https://www.zerto.com/myzerto/knowledge-base/how-to-place-a-host-with-an-associated-vra-into-maintenance-mode/){: external}.
{: note}



### Upgrading vSphere licenses
{: #vc_vcs_80_upgrade-procedure-licenses}

After you upgrade the vSphere and ESXi hosts to vSphere 8, you must upgrade the licenses on the vSphere and the ESXi hosts. If you have a vSAN cluster, you must update the vSAN license. To obtain the new licenses for vSphere 8, [contact IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

#### Procedure to upgrade the vSAN cluster license
{: #vc_vcs_80_upgrade-procedure-vsan-cluster-license}

1. From the **Licenses** page, click **+ Add New Licenses**.
2. Enter the new vSAN license keys in the **New Licenses** field. If you have multiple vSAN license keys, enter all the licenses in the **New Licenses** field, specify a name for each license, and then click **OK**.
3. Complete the following steps from the **Assets** page.
   1. Select **VSAN CLUSTERS**.
   2. Select the vSAN cluster and click **Assign License**.
   3. Select one of the new vSAN license keys and click **OK**.
   4. Repeat this step for each vSAN cluster.
4. From the **Licenses** page, select all the old vSAN cluster licenses and click **Remove Licenses**.

## Related links
{: #vc_vcs_80_upgrade-related}

* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [vCenter Server upgrade](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/8-0/vcenter-server-upgrade-8-0.html){: external}
* [Upgrading vCenter Server vSphere software from vSphere 6.5 or 6.7 to 7.0](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vsphere_70_upgrade)
