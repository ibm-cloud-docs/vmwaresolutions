---

copyright:

  years:  2025

lastupdated: "2025-05-29"

keywords: usage meter, configuration

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Configuring Usage Meter
{: #usage_meter-config}

After you deployed VMware vCloud Usage Meter, configure it in VMware vSphere® Web Client. Find out how to configure Usage Meter in the following video.

![IBM Cloud licensing for Broadcom Usage Meter: part 2](https://www.kaltura.com/p/1773841/sp/177384100/embedIframeJs/uiconf_id/27941801/partner_id/1773841?iframeembed=true&entry_id=1_y24q2mve){: video output="iframe" data-script="none" id="mediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}

In VMware vSphere® Web Client, complete the following steps:

1. Log in to the VMware vCloud Usage Meter virtual machine (VM).
2. In a web browser, go to the IP address assigned to the Usage Meter VM that starts with `https://`
3. If a certificate warning appears, click **Advanced** and click **Proceed to IP (unsafe)**. This message is displayed due to self-signed certificates.
4. In the Usage Meter initialization window, under **Welcome**, select the **I agree to the terms and conditions** checkbox and click **Next**.
5. Under **Network Connectivity**, select **HTTP proxy**.
6. Clear the **Anonymous** checkbox.
7. Enter information for **URL (http only)**, **Port**, **Username**, and **Password**, then click **Next**.

   You can use the IBM-provided HTTP proxy server `proxy.vmware.cloud.ibm.com` on port number 3128. For this purpose, enter your Usage Meter user credentials for **Username** and **Password**.
   {: note}

   To use the IBM-provided HTTP proxy server, you must first enable [virtual routing and forwarding (VRF)](/docs/account?topic=account-vrf-service-endpoint&interface=ui#vrf) and [service endpoints](/docs/account?topic=account-vrf-service-endpoint&interface=ui#service-endpoint). If you cannot make these configuration changes, you can configure Usage Meter to connect to Broadcom directly over the public network or through your own proxy server.
   {: important}

8. Under **Summary**, verify and save the **Usage Meter ID#** value.



## Related links
{: #usage_meter-config-related}

* [Deploying Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-deploy)
* [Registering Usage Meter with IBM](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-register)
* [Adding VMware products to Usage Meter](/docs/vmwaresolutions?topic=vmwaresolutions-usage_meter-add)
