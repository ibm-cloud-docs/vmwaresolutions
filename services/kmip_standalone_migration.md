---

copyright:

  years:  2025

lastupdated: "2025-10-21"

keywords: vmware solutions kmip for vmware, kmip for vmware, migration, migration partner, partners for assisted migration

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Migrating from KMIP for VMware to {{site.data.keyword.cloud_notm}} native KMIP providers
{: #kmip_migration}



{{site.data.content.kmip-deprecated-note}}

{{site.data.content.kmip-imp-note}}

## Before you begin
{: #kmip_migration-req}

Review the following information:
* [KMIP for VMware design](/docs/vmwaresolutions?topic=vmwaresolutions-kmip-design)
* [KMIP for VMware implementation and management](/docs/vmwaresolutions?topic=vmwaresolutions-kmip-implementation)

## Migration options
{: #kmip_migration-options}

{{site.data.keyword.cloud}} key management offerings introduce native KMIP providers to replace the Key Management Interoperability Protocol (KMIP™) for VMware® service provider. These new native providers have the following advantages:
- Improved performance because the calls from KMIP to key provider are closer in network distance and no longer cross the service-to-service authorization boundaries.
- Improved visibility and management for the KMIP keys.

The native providers share common code and their behavior is similar. For more information, see [Key Protect: Using the key management interoperability protocol (KMIP)](/docs/key-protect?topic=key-protect-kmip&interface=ui).

The support of native KMIP providers is not available for the [Hyper Protect Crypto Services](/docs/hs-crypto) offering of {{site.data.keyword.cloud_notm}}.
{: important}

## Migrating to the new KMIP provider
{: #kmip_migration-environment}

If you already use the KMIP for VMware provider, switch to the new key provider for improved performance:
1. Go to `https://cloud.ibm.com/infrastructure/vmware-solutions/console/instances/kmip`.
2. Select your existing KMIP for VMware instance and note the Key Manager instance name.
3. Go to `https://cloud.ibm.com/resources`, expand **Security**, and choose the Key Manager instance from step 2.

     To implement this step, your account needs certain privileges. Complete the following steps to check your account privilege:
     1. In the console, **Manage** > **Access (IAM)** > **Users**.
     2. Under **Access policies**, select your user ID, and then select the **Access** tab.
     3. Ensure that the **service - Key Protect** and **Role - Administrator** permissions are added.

4. Select **KMIP adapters** from the left navigation menu, and click **Create KMIP adapter**.
5. Optionally, type a name, and then select a root key.

     Adding certificate details here is optional as vCenter Server generates a new certificate for each key provider that you configure. The certificate is generated in [step 11](#kmipmigratn-step11).
     {: note}

6. Select the **Endpoints** tab from left navigation menu to identify the KMIP endpoint you need to configure. Choose the **Private** endpoint with type as **KMIP**.

      Only one endpoint is available here unlike the KMIP for VMware offering in {{site.data.keyword.cloud_notm}} for VMware Solutions. A single hostname balances the load and it is highly available in each region.
      {: important}

7. In vCenter Server, choose the vCenter object.
8. Select **Configure > Key Providers**, and then add a standard key provider.
9. Verify the details, and click **Trust**.
10. Select the new key provider, and then the single server in that provider.
11. In the **Make KMS trust vCenter** section, click **Establish Trust**. Use the **vCenter Certificate** option that generates a new certificate just for this connection. {: #kmipmigratn-step11}
12. Copy the certificate, and click **Done**.

      Before you copy the certificate, wait for the screen to refresh because the certificate details can vary if you copy too quickly.
      {: important}

13. Return to the **KMIP adapters** page, and view the details of your KMIP adapter.
14. Under **Adapter details**, select the **SSL certificates** tab. Click **Add certificate**, and paste the certificate that you copied from vCenter.

      The key provider health status might take several minutes to change in the vCenter Server.
      {: note}

### Setting the new key provider as default
{: #kmip_migration-environment-setdefault}

Set the new key provider as default so that all new virtual machines (VMs) are encrypted by the new key provider.

1. In vCenter Server, choose the vCenter object.
2. Go to **Configure > Key Providers**, select the new key provider, and click **Set As Default**.

### Migrating encrypted resources to the new key provider
{: #kmip_migration-environment-migratevms}

You can use the vCenter Server console to migrate some of your encrypted resources to the new key provider. However, in some cases, you must use PowerCLI commands, or you can also use the PowerCLI tool if you have many resources to migrate.
{: note}

Install PowerCLI on a convenient server with network access to vCenter, and run the `Connect-VIServer` command to connect to your vCenter. For more information, see [PowerCLI Installation Guide](https://developer.broadcom.com/powercli/installation-guide){: external}.

#### Migrating vSphere encrypted VMs to the new key provider
{: #kmip_migration-environment-migratevms-vsphere}

If you are operating with a mix of vCenter Server 8 and vSphere 7 hosts, or vSphere 8 hosts on versions earlier than 8u3e, the rekey of the virtual machine can cause it to restart. To resolve this issue, see [Encrypted VM with Change Block Tracking (CBT) enabled unexpectedly powers off after shallow rekey operation](https://knowledge.broadcom.com/external/article?articleNumber=387897){: external}.
{: attention}

After you set the new key provider to default, select any VM in the inventory. Then, go to **Actions > VM Policies > Re-encrypt** to do a shallow rekey of the virtual machine to the new key provider.

You can also rekey multiple encrypted virtual machines at the same time by using a PowerCLI script similar to the following sample script:

```text
$kp = Get-KeyProvider <new-kmip>

foreach($vm in Get-VM) {
  if($vm.ExtensionData.Config.KeyId) {
    Set-VM $vm -KeyProvider $kp -Confirm:$false
  }
}
```
{: codeblock}

#### Migrating vSAN encryption to the new key provider
{: #kmip_migration-environment-migratevms-vsan}

After you set the new key provider to default, rekey both your vSAN cluster and your host encryption keys by for your cluster in the vCenter Server console.

1. Select **Configure > vSAN > Services**, then under the Data Services section, click **Edit**.
2. Under **Data-At-Rest encryption**, select your new key provider from the menu, and click **Apply**. A shallow rekey of vSAN and the host encryption keys for that cluster are completed.

#### Migrating host encryption to the new key provider
{: #kmip_migration-environment-migratevms-hosts}

If you are using only vSphere encryption and not vSAN encryption, you must use the PowerCLI tool to rekey the encrypted hosts in your environment. The following sample script shows how to rekey all the encrypted hosts in an environment that is in *safe* mode, meaning that the environment is issued a host key for encryption of core dumps:

```text
$kp = Get-KeyProvider <new-kmip>

foreach($vmhost in Get-VMHost) {
  if($vmhost.ExtensionData.Runtime.CryptoState -eq "safe") {
    Set-VMHost $vmhost -KeyProvider $kp
  }
}
```
{: codeblock}

### Deleting the old KMIP provider
{: #kmip_migration-environment-deletevms}

After you rekey all the VMs, remove the old key provider in the Server console.

#### Verifying key provider settings
{: #kmip_migration-environment-deletevms-verifyold}

Before you remove the original key provider, you must verify that your resources are successfully rekeyed by running the following PowerCLI script to display the key provider for all resources:

```text
$vmlist = @()

foreach($vm in Get-VM) {
  $vmlist += [pscustomobject]@{ vm = $vm.name; provider = $vm.ExtensionData.Config.KeyId.ProviderId.Id}
}

$vmlist | Format-Table
$hostlist = @()

foreach($vmhost in Get-VMHost) {
  $vmhostview = Get-View $vmhost
  $hostlist += [pscustomobject]@{ host = $vmhost.name; provider = $vmhostview.Runtime.CryptoKeyId.ProviderId.Id}
}

$hostlist | Format-Table
$clusterlist = @()
$vsanclusterconfig = Get-VsanView -Id "VsanVcClusterConfigSystem-vsan-cluster-config-system"

foreach($cluster in Get-Cluster) {
  $encryption = $vsanclusterconfig.VsanClusterGetConfig($cluster.ExtensionData.MoRef).DataEncryptionConfig
  $clusterlist += [pscustomobject]@{ cluster = $cluster.name; provider = $encryption.KmsProviderId.Id }
}

$clusterlist | Format-Table
```
{: codeblock}

#### Removing the old key provider
{: #kmip_migration-environment-deletevms-removeold}

1. Go to {{site.data.keyword.cloud_notm}} for VMware Solutions console.
2. Delete the KMIP for VMware instance that is provisioned with the old KMIP provider.

For completeness, delete all the old unused keys that were created by the old KMIP for VMware adapter in the vCenter Server console. You can either delete the keys manually or use a CLI command. You can identify these keys by name, since their names contain `vmware_kmip` as prefix.

The KMIP keys that are created by the new native adapter are displayed under the **Adapter details > KMIP symmetric keys** tab of your KMIP adapter.
{: note}

## Related links
{: #kmip_migration-related}

* [End of Support for KMIP for VMware](/docs/vmwaresolutions?topic=vmwaresolutions-eos-kmip)
* [FAQ for KMIP for VMware migration](/docs/vmwaresolutions?topic=vmwaresolutions-faq-kmip)
* [{{site.data.keyword.IBM}} Key Protect for {{site.data.keyword.cloud_notm}}](/docs/key-protect)
