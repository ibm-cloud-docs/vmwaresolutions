---

copyright:

  years:  2025

lastupdated: "2025-08-06"

keywords: usage meter, download, deployment

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Deploying Usage Meter
{: #usage_meter-deploy}

To deploy a VMware vCloud Usage Meter virtual machine (VM), you must first download the Usage Meter OVA file, and then deploy the OVF template.

## Procedure to download the Usage Meter OVA file
{: #usage_meter-deploy-download}

Complete the following steps:

1. Download the Usage Meter OVA file from the following link: `https://ibm.biz/BdG7QT`

   For newer versions of Usage Meter, two files are available for download: one for the initial installment and another one for the upgrade. These files use different SHA-2 values.
   {: note}

2. Validate the SHA-2 checksum based on the `8297eef8815738ea35111d59a15fb86b45a4f2648339c4548c27753a983593ed` SHA-256 value. Open a command prompt on Windows® or a terminal window on Linux® and MacOS and run the following command:
   * For Windows: `certutil -hashfile <path-to-ova-file> SHA256`
   * For Linux: `sha256sum <path-to-ova-file>`
   * For MacOS: `shasum -a 256 <path-to-ova-file>`

## Procedure to deploy a Usage Meter VM
{: #usage_meter-deploy-proc}

In the VMware vSphere® Web Client, complete the following steps:

1. Log in to your primary vCenter Server instance as the administrator user.
2. Right-click your primary management cluster (the cluster that contains your VMware vCenter Server, VMware NSX, and other management VMs) and select **Deploy OVF Template**.
3. Under **Select an OVF template**, choose **Local file** and click **Upload files** to add the Usage Meter OVA file that you downloaded previously, then click **Next**.
4. Under **Select a name and folder**, provide an appropriate VM name and location within the cluster, then click **Next**.
5. Under **Select a compute resource**, choose an appropriate host or cluster in which to deploy this VM initially.

   You must select a cluster. This action allows vCenter Server to automatically choose the host in the cluster with the most available resources. If the cluster has DRS enabled, the VM is automatically migrated across hosts to balance host resources.
   {: important}

6. Under **Compatibility**, verify that the compatibility checks are successful. If they are not, check the health of your target cluster. Optionally, if you want the VM to start automatically after deployment, select the **Automatically power on deploy VM** checkbox, then click **Next**.
7. Under **Review details**, verify the template details and click **Next**.
8. Under **License agreements**, select the **I accept all license agreements** checkbox.
9. Under **Select storage**, choose the appropriate datastore for your cluster. To allow migration, the datastore must be a storage device that is accessible for all hosts in the cluster. For example, vSAN or NFS that is attached to all hosts.
10. Under **Compatibility**, verify that the compatibility checks are successful. If they are not, check the health of your target storage device and ensure that it is accessible for all hosts that you selected in the **Select a compute resource** step, then click **Next**.
11. Under **Select networks**, the destination network defaults to one of your portgroups. The destination network must be accessible to the target host or to all hosts in the target cluster. Configure it to support the IP address and the subnet that you want to use with Usage Meter then click **Next**.

    You must reuse the same portgroup where your management VMs are located. To find it, open the **Destination network** menu and click **Browse** to select the correct network.
    {: important}

12. Under **Customize template**, create the required passwords and select the **Use Federal Information Processing Standards (FIPS)** checkbox. For network properties, configure the following settings. If you require assistance with the settings for the network properties, contact your network administrator to obtain the values that you need to enter.
    * **Hostname**: Set a unique hostname within your environment.
    * **Host network default gateway**: Enter the IP address of the gateway on your subnet where the IP address of the VMs is located.
    * **Domain name**: Enter the domain name of the VM. It must match the domain of your environment FQDNs and can be searched through your DNS servers.
    * **Domain search path**: Enter the search path for the FQDN within the domain, which must match the VM domain name.
    * **Domain name servers**: Enter the IP addresses (comma separated) of the environment DNS servers.
    * **Network 1 IP address**: Enter the IP address of the Usage Meter VM.
    * **Network 1 Netmask, Netmask in CIDR notation**: Enter the netmask of the subnet that the Usage Meter VM is on CIDR notation.

    The CIDR notation does not include the subnet mask. For example, for a `255.255.255.0` subnet mask, enter `24` only.
    {: important}

13. Under **Ready to complete**, review your selections and click **Finish**.

## Results after Usage Meter VM deployment
{: #usage_meter-deploy-results}

* Under **Recent Tasks**, after the new tasks complete, details such as the VM DNS name and IP address are displayed under **Virtual machine details** in the **Summary** tab.
* If you didn't select the **Automatically power on deploy VM** option in the **Select a compute resource** step, click the new VM in the inventory pane. Then, click the power on icon next to the VM name to see the VM details. If the VM details do not appear, the configuration might be incorrect. To resolve the issue, delete the VM and redeploy the OVF template.

## Related links
{: #usage_meter-deploy-related}

* [Configuring Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-config)
* [Registering Usage Meter with IBM](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register)
* [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add)
