---

copyright:

  years:  2024

lastupdated: "2025-10-21"

keywords: troubleshooting, Zerto ZVMA, zvm, zvma, windows zvm, linux zvma, zerto migration

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Why does the Zerto migration from Windows ZVM to Linux ZVMA fail?
{: #trbl_zerto_zvma_migration}
{: troubleshoot}
{: support}



The Zerto Migration Utility fails with the following error message.
{: tsSymptoms}

```text
For migration, the Windows ZVM machine must have a default gateway configured.
```
{: codeblock}

The default gateway is missing from the Microsoft Windows® VM (virtual machine).
{: tsCauses}

Assign the default gateway to the Windows VM.
{: tsResolve}

The Zerto Migration Utility fails with the following error message.
{: tsSymptoms}

```text
<date> <timestamp>,Error,ZvmlMigrationTool.Analytics.AnalyticsSender.SendToGoogleAnalytics,Failed to send analytics event to GA,Flurl.Http.FlurlHttpException: Call failed. A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond. (www.google-analytics.com:443): POST https://www.google-analytics.com/mp/collect?api_secret=QK77SUfBTOyecZFB6x2kCg&measurement_id=G-CYQEFJ4DSP
---> System.Net.Http.HttpRequestException: A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond. (www.google-analytics.com:443)
---> System.Net.Sockets.SocketException (10060): A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
at System.Net.Sockets.Socket.AwaitableSocketAsyncEventArgs.ThrowException(SocketError error, CancellationToken cancellationToken)
at System.Net.Sockets.Socket.AwaitableSocketAsyncEventArgs.System.Threading.Tasks.Sources.IValueTaskSource.GetResult(Int16 token)
```
{: codeblock}

The Windows VM is not connected to the internet.
{: tsCauses}

Connect your ZVM (Zerto Virtual Manager) to the internet by connecting it to your internet gateway or proxy.
{: tsResolve}

The Zerto Migration Utility fails with the following error message.
{: tsSymptoms}

```text
<timestamp>,Info,ZvmlMigrationTool.Accessors.SshConnection.Connect,Connecting to 10.87.26.130, username: zadmin,
<date> <timestamp>,Error,ZvmlMigrationTool.Accessors.SshConnection.EstablishConnection,Failed to connect to 10.87.26.130,System.Net.Sockets.SocketException (10060): A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.
at Renci.SshNet.Abstractions.SocketAbstraction.ConnectCore(Socket socket, IPEndPoint remoteEndpoint, TimeSpan connectTimeout, Boolean ownsSocket)
```
{: codeblock}

The Windows VM is not on the same subnet as the Linux® ZVMA (Zerto Virtual Manager Appliance).
{: tsCauses}

Ensure that you configured your Windows and Linux ZVMs correctly by using the addresses that are provided to you by IBM Support.
{: tsResolve}
