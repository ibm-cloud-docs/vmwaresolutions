---

copyright:

  years:  2024

lastupdated: "2024-12-10"

keywords: Zerto, Zerto migration, zvm, zvma, windows zvm, linux zvma

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Migrating Zerto from Windows ZVM to Linux ZVMA
{: #zerto_migration}

For Zerto 9.7 and earlier, ZVM (Zerto Virtual Manager) used to run from a Microsoft Windows® virtual machine (VM). 

For Zerto 10.0 and later, Zerto runs in a lightweight Debian Linux® based ZVMA (ZVM Appliance). Therefore, upgrading from Zerto 9.7 to 10.x requires a full lift-and-shift migration of the ZVM data from the Windows ZVM to the Linux ZVMA.

## Before you begin
{: #zerto_migration-before-begin}

1. Verify that the existing Windows ZVM meets the following requirements:

   * The Zerto version for the Windows ZVM is 9.7u4 P2.
   * The ZVM is connected to the internet.
   * The default gateway is enabled for ZVM.

      For more information, see [Zerto Migration Utility](https://help.zerto.com/bundle/Zerto.Migration.Utility.HTML.1.0/page/Migration_Utility_Prerequisites.htm){: external}.

2. Open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support). In the support ticket, ask for the following requirements:

   * Three sets of IPv4 addresses for network configuration.
   * An OVA image file for Linux ZVMA deployment.
   * The availability of the Zerto Migration Utility.
   * To update the backend cloud data after successful migration.
   * To clean up the Windows VM from {{site.data.keyword.cloud}} after successful migration.

## Changing the IP configuration of the Windows ZVM and preserving VPG configuration
{: #zerto_migration_networkconfig}

The following steps are required only when the Zerto Windows VM network configuration needs to be updated so that it is on the same subnet as the Linux ZVMA. Without completing these steps, the migration utility does not communicate with the Linux ZVMA that is hosted on VMware vSphere, while the Windows VM is on {{site.data.keyword.cloud_notm}}. For more information, see [How to change the IP address of a ZVM server and preserve replicated data and VPG configuration](https://help.zerto.com/kb/000004268){: external}.

1. Export the existing VPG (Virtual Protection Group) data.
   1. Log in to the Windows Zerto UI.
   2. Click **Lists the VPGs** on the left side of the menu option.
   3. Select the VPG, and click **Export VPG Settings**. A JSON document is downloaded, which is used later when you import the VPGs.
   4. On the **Export VPG Settings** page, click **Export**.
   5. After the VPG data is exported, delete the VPGs:
      1. Select the VPG, and click **Delete**.
      2. On the **Delete VPG** page, select the **Keep the recovery disks at the peer site** checkbox, and click **Delete**.

2. After you delete the VPG, unpair existing sites from the Windows Zerto UI.
3. Update the Zerto Windows VM network configuration so that it is on the same subnet as the Linux ZVMA. To receive more IPv4 addresses, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).
4. To configure the network settings, run diagnostic on Zerto Windows VM by logging in to the Windows VM, and running the command **Zerto Diagnostic**.
5. After the diagnostic completes successfully, log in to the Zerto Windows UI with the updated Windows IP address for validation.
6. Pair the Zerto sites. After a successful site pairing, import the VPG:
   1. Click **Lists the VPGs** on the left side of the menu option.
   2. Click **Import VPGs**. To import the VPGs, use the JSON document that was exported in Step 1.c.

## Installing Zerto ZVMA on a Linux VM
{: #zerto_migration_installzvma}

For Zerto Linux OVA, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support).

1. Log in to the specific vCenter Server instance, right click **Management Cluster** and select **Deploy OVF Template**.
2. Click **Local file > UPLOAD FILES**, select the Zerto OVA file, and click **Next**.
3. Rename the virtual machine name to `ZertoLinuxVM`, select the **IBMCloud** folder, and click **Next**.
4. Select **Management Cluster**, and click **Next**. On the next page, review the details and click **Next**.
5. Select the applicable data store, and then choose **Thin Provision** on **Select virtual disk format**, and click **Next**.
6. Select the `dpg-mgmt` network, and click **Next**.
7. Review the details and click **Finish**.
8. After the OVA is deployed, click **Launch Web Console** in VMware vCenter Server to open the **ZertoLinuxVM** console. Use the following credentials to log in to the **ZertoLinuxVM** console:

   ```text
   username: zadmin
   password: Zertodata123!
   ```
   {: codeblock}

9. After you log in for the first time, reset the password. Make a note of the new password. Then, log in with the new password.
10. Select **Option 2 (Configure Network Settings)** and press Enter.
11. On the next screen, select **Option 2** to configure the static network for Zerto.
12. In the Zerto VM console, enter the new IP address for Zerto from the management network that you received from IBM Support. Then, press Enter.
13. Enter the **mask** value in **Subnet Mask**, the **gateway** value in **IP4V Gateway**, and the **dns** value in **DNS name server 1**. If you have two values in the **dns** section, enter the other value in the next prompt or enter `NA`.
14. Review the summary details and enter `y` if all information is correct. Then, restart the system.
15. After system restart, log in with the following username and password:
     ```text
     username: zadmin
     password: <Password set previously in Step 9>
     ```
     {: codeblock}

16. To enable `SSH`, enter `7`. After SSH is enabled, enter `0` to exit the shell. An IP address is assigned to the Linux ZVMA from the VMware vSphere Web Client.
17. After the network is configured, enter the following address in a web browser: `https://<zerto ip>/`. Use the following credentials in the Zerto web console:
     ```text
     username: admin
     password: admin
     ```
     {: codeblock}

18. Reset the password after the first login, and make a note of the new password. The same password is used for both the `admin` and `zadmin` users.
19. Set a password for the `keycloak` user. Enter the following address in a web browser: `https://<zerto ip>/auth` and use the following credentials:
     ```text
     username: admin
     password: admin
     ```
     {: codeblock}

20. After you log in for the first time, change the password. Make a note of the new password, as it needs to be updated in the Cloudant data as well.

## Migrating from Windows ZVM to Linux ZVMA
{: #zerto_migration_winzvm_lnxzvma}

For Zerto Migration Utility, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support). Then, fetch the new set of temporary IP addresses for Zerto Migration Utility that you received from the IBM Support team.

1. Run the Zerto Migration Utility. On the **Target ZVM Appliance Credentials** page, enter the Linux ZVMA IP address. Use the following credentials:

   ```text
   username: zadmin
   password: <Password set previously in Step 20>
   ```
   {: codeblock}

2. Check whether the SSH connectivity is working:
   1. Click **Validate SSH Connectivity** on the **Target ZVM Appliance Credentials** page.
   2. When you see a success message such as **Established connection to the ZVM Appliance**, click **Next**.
3. On the **Alternative Host Network Details** page, provide the temporary Windows IP address that you received from IBM Support. Enter the `IP Address`, `Subnet Mask`, `Gateway`, and `DNS Server` details. Then, click **Next**.
4. On the **Summary** page, verify **Upgrade VRAs**. Then, click **Migrate**.

   Notice that the Remote Desktop session connection to the Windows VM with Zerto ZVM installed is lost. You need to use the new IP address as configured in the earlier step to connect to Remote Desktop. Use the same credentials as earlier.

5. Then, login into the Linux Zerto ZVMA, and use the following credentials:

   ```text
   username: admin
   password: admin
   ```
   {: codeblock}

6. Use `admin` for username. Verify the following items:
   * VPG is restored after migration.
   * Site pairing is also restored.
   * VRAs are updated to the Linux ZVMA version.

For more information, see [How to change the IP address of a ZVM server and preserve replicated data and VPG configuration](https://help.zerto.com/kb/000004268){: external}.

## Completing postinstallation steps
{: #zerto_migration_postinstall}

1. Open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) to update the backend information in the {{site.data.keyword.cloud_notm}} automation.
2. Update the DNS entry for Zerto in the AD server, and open an IBM Support ticket to remove the Windows VM from {{site.data.keyword.cloud_notm}}.
3. If you encounter any errors during the Zerto migration process, see [Why does the Zerto Migration from Windows Zerto Virtual Manager to Linux ZVM Appliance fail?](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_zerto_zvma_migration)

## Related links
{: #zerto_migration-related}

* [Zerto overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Managing Zerto](/docs/vmwaresolutions?topic=vmwaresolutions-managingzertodr)
* [Managing Zerto stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses)
* [Why does the Zerto Migration from Windows Zerto Virtual Manager to Linux ZVM Appliance fail?](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_zerto_zvma_migration)
* [How to change the IP address of a ZVM server and preserve replicated data and VPG configuration](https://help.zerto.com/kb/000004268){: external}
