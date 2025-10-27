---

copyright:

  years:  2022, 2025

lastupdated: "2025-10-24"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Configuring the jump server
{: #veeam-cr-sag-jmpcfg}

{{site.data.content.vms-deprecated-note}}

Now that the jump server is ordered and available for connection on its public IP address from your laptop, you can follow these steps:

1. [Change the Domain Name Services (DNS)](#veeam-cr-sag-jmpcfg-dns) client so that it points to the {{site.data.keyword.vcf-auto}} instances - Active Directory™ DNS (AD/DNS) server instead of the {{site.data.keyword.cloud}} DNS resolver. It allows name resolution for components, such as the vCenter appliance and VMware NSX-T™ Manager. The VSI has two Ethernet interfaces, one for the private network and one for the public network.
2. [Download software](#veeam-cr-sag-jmpcfg-sw) that enables administration functions, such as mRemoteNG and Firefox®.
3. [Install PowerCLI](#veeam-cr-sag-jmpcfg-powercli). PowerCLI is a collection of PowerShell Modules to manage VMware® infrastructure, including network, storage, virtual machine (VM), and guest OS.

## Changing DNS
{: #veeam-cr-sag-jmpcfg-dns}

1. {{site.data.content.ol-intro-ui-vcfclassic}}
2. Select the instance and click the **Access information** tab to capture the IP address of your AD/DNS servers `DNS1` and `DNS2`.
3. From your laptop, use an RDP client to access the jump server.
4. When connected to the jump server, open a PowerShell console with admin privileges.
5. Use `Get-DNSClientServerAddress` to display the interfaces and their parameters. You need to capture the Interface Indexes `IF1` and `IF2` for the Ethernet interfaces for use in the next command.
6. Use the following command to change the first interface: `Set-DNSClientServerAddress –interfaceIndex <IF1> –ServerAddresses (“<DNS1>”,“<DNS2>”)`. For example, `Set-DNSClientServerAddress –interfaceIndex 11 –ServerAddresses (“10.38.207.132”, “10.38.207.133”)`.
7. Use the following command to change the second interface: `Set-DNSClientServerAddress –interfaceIndex <IF2> –ServerAddresses (“<DNS1>”,“<DNS2>”)`. For example, `Set-DNSClientServerAddress –interfaceIndex 15 –ServerAddresses (“10.38.207.132”, “10.38.207.133”)`.
8. Use the command `Get-DNSClientServerAddress` to verify the interfaces and their parameters.

## Downloading the software
{: #veeam-cr-sag-jmpcfg-sw}

Open a PowerShell window and use the following commands to download and install mRemoteNG and Firefox.

```text
Invoke-WebRequest -Uri https://github.com/mRemoteNG/mRemoteNG/releases/download/v1.76.20/mRemoteNG-Installer-1.76.20.24615.msi -OutFile C:\Users\Administrator\Downloads\mRemoteNG-Installer-1.76.20.24615.msi
Invoke-WebRequest -Uri "https://download.mozilla.org/?product=firefox-msi-latest-ssl&os=win64&lang=en-GB" -OutFile C:\Users\Administrator\Downloads\firefox-msi-latest.msi
cd C:\Users\Administrator\Downloads
.\mRemoteNG-Installer-1.76.20.24615.msi
.\firefox-msi-latest.msi
```
{: codeblock}

## Installing PowerCLI
{: #veeam-cr-sag-jmpcfg-powercli}

PowerShell is installed by default with Windows® Server. However, PowerCLI needs to be installed from the PowerShell gallery.

1. Install VMware PowerCLI by entering `Install-Module -Name VMware.PowerCLI`.
2. At the prompt, enter `Y`.

## Related links
{: #veeam-cr-sag-jmpcfg-related}

* [Cyber recovery with Veeam architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-veeam-cr-sa-overview)
