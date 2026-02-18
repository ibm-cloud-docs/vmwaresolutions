---

copyright:

  years:  2025

lastupdated: "2026-02-04"

keywords: usage meter, upgrade

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Upgrading Usage Meter
{: #usage_meter-upgrade}

{{site.data.content.vms-deprecated-note}}

Upgrade any existing VMware vCloud Usage Meters to version 9 to integrate with their own access token. For Usage Meter 4.8, the upgrade process involves receiving an access token for your currently registered Usage Meter through the IBM Cloud Usage Meter portal, followed by an in-place upgrade to version 9. After the initial upgrade to version 9 or later, you don't need to provide the access token for further upgrades.
{: important}



## Procedure to upgrade Usage Meter
{: #usage_meter-upgrade-proc}

To upgrade Usage Meter, complete the following steps:

### Enabling SSH login
{: #usage_meter-upgrade-ssh}

1. Log in to the VMware vCloud Usage Meter appliance management console with the `usagemeter` user through `https://<Usage Meter IP>:5480`.
2. Click **Access** from the left navigation panel.
3. Under **Access settings**, click **Edit** on the upper right.
4. In the **Edit access settings** window, toggle the **Enable SSH login** switch on. The SSH login changes to **Enabled**.

### Mounting the upgrade ISO file
{: #usage_meter-upgrade-iso}

1. Download the Usage Meter ISO file from the following link: `https://ibm.biz/BdeSzZ`
2. Validate the SHA-2 checksum based on the `62724df42b5cc8979723f6f25bf61b720d8287ec3510fbfd218232be787877a4` SHA-256 value. Open a command prompt on Windows® or a terminal window on Linux® and MacOS and run the following command:
   * For Windows: `certutil -hashfile <path-to-iso-file> SHA256`
   * For Linux: `sha256sum <path-to-iso-file>`
   * For MacOS: `shasum -a 256 <path-to-iso-file>`

3. In the VMware vSphere® Web Client, log in to your vCenter Server instance.
4. Under the **Storage** menu, select the datastore where your Usage Meter virtual machine (VM) is located.
5. In the **VMs** tab, click **Virtual machines** and verify that the Usage Meter is on your target datastore.
6. In the **Files** tab, click **Upload files**. The ISO file starts uploading.

   You might receive an error about the host certificates. To resolve it, open the specified URL that is shown in the error in another web browser tab and accept the certificate. If it doesn’t load, verify that the host is in your current desktop DNS and then access the URL again.
   {: note}

7. After the upload is complete, the ISO file will appear in the file list.
8. Under the **Hosts and clusters** menu, locate and right click the Usage Meter VM, and select **Edit settings**.
9. In the **Virtual hardware** tab, on **CD/DVD drive**, select **Datastore ISO file**, and click **OK**.

   If you do not see the **CD/DVD drive** option, click **Add new device**.
   {: tip}

10. In the **Select file** window, locate the datastore where you uploaded the ISO file.
11. Select the ISO file and click **OK**.
12. In the **Edit settings** window, under the **Virtual hardware** tab, select the **Connected** checkbox, then click **OK**.

### Running the upgrade command
{: #usage_meter-upgrade-command}

Before you run the upgrade commands for your Usage Meter, complete the following steps:

1. In the VMware vSphere® Web Client, log in to your vCenter Server instance.
2. Under the **Hosts and clusters** menu, locate and right click the Usage Meter VM, and select **Edit settings**.
3. In the **Virtual hardware** tab, on **CD/DVD drive**, clear the **Connected** checkbox, and click **OK**.
4. Under the **Hosts and clusters** menu, locate and right click the Usage Meter VM, and select **Snapshots > Take snapshot**.
5. Enter a name for your snapshot and click **Create**.

Use SSH to log in to the Usage Meter Appliance VM and complete the following steps:

1. Open a command prompt on Windows or a terminal window on Linux and MacOS and run the following commands as the `root` user:
   1. `mkdir /root/upgrade`
   2. `mount -o loop /dev/cdrom /root/upgrade`
   3. `bash /root/upgrade/upgrade-um.sh`

   You might need to run `umount /root/upgrade` to unmount any previous upgrades before you run `mount -o loop /dev/cdrom /root/upgrade` to upgrade the Usage Meter VM.
   {: note}

2. Enter the access token that is generated for the Usage Meter in the {{site.data.keyword.vmwaresolutions_full}} console. For more information, see [Registering Usage Meter with IBM](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register).
3. Enter **y** to agree with the VCF Usage Meter appliance be part of IBM's Provider Organization.
4. Enter **y** to confirm that a snapshot is created to the Usage Meter VM.

   An error message about the Usage Meter hostname might appear. Enter **y** to continue the upgrade path.
   {: note}

5. The upgrade process starts and when it's complete, enter **y** to restart the Usage Meter VM.
6. After the restart is complete, open the Usage Meter URL in a web browser and log in to verify the upgraded version. Then, confirm the health of the Usage Meter appliance.

After you migrate the Usage Meter VM, you might encounter the error `Connection control operation failed for disk` during the upgrade process. This problem might happen due to an active snapshot that retains a lock on the mounted CD/DVD device. To resolve it, complete one of the following procedures. However, you might need to complete all of them for a successful migration of the VM.

1. **Delete any existing snapshots**:
   1. In the VMware vSphere Web Client, log in to your vCenter Server instance as an administrator.
   2. Under the **Hosts and clusters** menu, select the Usage Meter VM.
   3. In the **Snapshots** tab, select **DELETE ALL** or specify any of the snapshots that have the CD/DVD drive mounted and select **DELETE**.
   5. Click **OK**.

2. **Disconnect the mounted drive**:
   1. In the vSphere Web Client, log in to your vCenter Server instance as an administrator.
   2. Under the **Hosts and clusters** menu, locate and right click the Usage Meter VM, and select **Edit settings**.
   3. Clear the box in the CD/DVD drive where you mounted the ISO upgrade file.
   4. Click **OK**.

3. **Disconnect the mounted drive from the hosted ESXi**:
   1. In the vSphere Web Client, log in to your vCenter Server instance as an administrator.
   2. Under the **Hosts and clusters** menu, select the Usage Meter VM.
   3. In the **Summary** tab, locate **Related objects** and determine which host the VM is located.
   4. Log in to the ESXi host as root or an administrator.
   5. Select **Virtual machines** and right click the Usage Meter VM in the list.
   7. Click **Edit settings**.
   8. Under **CD/DVD drive**, clear the **Connected** checkbox.
   9. Click **Save**.

### Replacing the Usage Meter certificate
{: #usage_meter-upgrade-certificate}

If you cannot access the Usage Meter URL or log in to the dashboard after the upgrade, complete the following steps to replace the Usage Meter certificate due to an incompatible hostname:

1. Use SSH to log in to the Usage Meter VM with the `usagemeter` username.
2. Run the command `stop.sh All` to stop all services.
3. Under a root user, run the command `hostnamectl hostname <new hostname>` to update the hostname with the correct value.
4. Run the commands `export $(grep -v '^#' "/opt/vmware/cloudusagemetering/platform/conf/env.properties" | xargs)` and `mv /opt/vmware/cloudusagemetering/platform/security/keystore /opt/vmware/cloudusagemetering/platform/security/keystore.backup` to export the environment variables and backup the existing keystore.
5. If FIPS is enabled, run the command `keytool -changealias -alias "usage-meter-platform" -destalias "usage-meter-platform-backup" -keystore /opt/vmware/cloudusagemetering/platform/security/cacerts -storetype BCFKS -providerclass org.bouncycastle.jcajce.provider.BouncyCastleFipsProvider -providerpath /opt/vmware/cloudusagemetering/platform/lib/bc-fips-*.jar -storepass "${TRUST_STORE_PASSWORD}"`. If it is disabled, run the command `keytool -changealias -alias "usage-meter-platform" -destalias "usage-meter-platform-backup" -keystore /opt/vmware/cloudusagemetering/platform/security/cacerts -storepass "${TRUST_STORE_PASSWORD}"`.

   If you run the FIPS disabled version while FIPS is enabled, the error `keytool error: java.security.KeyStoreException: Unrecognized keystore format.` is displayed. To resolve it, load it with a specified type.
   {: note}

6. Create a temporary directory for the NGINX variable and run the command `export NGINX_FOLDER=$(mktemp -d)` to move it into the **cloudusagemetering** directory, then run `cd /opt/vmware/cloudusagemetering` to access the new directory.
7. Run the command `./platform/bin/create-keystore.sh` to create the new keystore.
8. Run the commands `rm -rf $NGINX_FOLDER` and `rm /opt/vmware/cloudusagemetering/platform/security/keystore.backup` to remove the temporary backup files.
9. If FIPS is enabled, run the command `keytool -delete -alias "usage-meter-platform-backup" -keystore /opt/vmware/cloudusagemetering/platform/security/cacerts -storetype BCFKS -providerclass org.bouncycastle.jcajce.provider.BouncyCastleFipsProvider -providerpath /opt/vmware/cloudusagemetering/platform/lib/bc-fips-*.jar -storepass "${TRUST_STORE_PASSWORD}"` to delete the backup keystore. If it is disabled, run the command `keytool -delete -alias "usage-meter-platform-backup" -keystore /opt/vmware/cloudusagemetering/platform/security/cacerts -storepass "${TRUST_STORE_PASSWORD}"`.
10. Run the command `chmod 0640 /opt/vmware/cloudusagemetering/platform/security/keystore` to update the new keystore permissions and restart the Usage Meter VM.

    Due to the hostname change, you might need to update your DNS entry to the new hostname or add it if it doesn't exist. If you are redirected to the login page with an OAuth error, clear any existing DNS entries for Usage Meter and try again.
    {: note}

11. After the restart is complete, open the Usage Meter URL in a web browser to verify the upgraded version.

## Related links
{: #usage_meter-upgrade-related}

* [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config)
* [Registering Usage Meter with IBM](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register)
