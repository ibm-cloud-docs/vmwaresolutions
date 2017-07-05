---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-29"

---

# Timeout reached while connecting to the VMware vSphere Web Client

## Problem
When you try to connect to the vSphere Web Client, you might get a timeout error.

The following error might be displayed:

`The server at <IP_address> is taking too long to respond.`

## Resolution
Use the following steps to troubleshoot and fix the problem.

1. Ensure that you completed the steps from the tooltip that gets displayed when you hover over the **vCenter console** button. For
   your convenience, these steps are also listed as follows:   
   1. Install the Adobe Flash Player plug-in for your browser.   
   2. Create a VPN password from the SoftLayer® Customer Portal.    
   3. Log in to the data center VPN portal by using the SoftLayer VPN credentials.    
   4. Add the IP address and the host name mapping of PSC (Platform Services Controller) into the hosts file using the following format:

      ```javascript
      IPAddress              HostName
      ```
      **Note**: The last line is displayed for Cloud Foundation instances only. For vCenter Server instances, see the next step.
2. Take note of the IP address that is displayed, because you need it in one of the next steps. For Cloud Foundation instances, the IP address is displayed in the actual tooltip. For vCenter Server instances, the IP address is displayed in the lower left of your browser window while you hover over the **vCenter console** button.
3. Ensure that you have access to the SoftLayer VPN. Complete the following steps on the SoftLayer Customer Portal:
   1. Click **Account > VPN Access**.
   2. Click the **SSL link** in the **VPN Access** column.
   3. On the **VPN Access for username** page, set the **Subnet Access** option to **Manual**.
   4. On the same page, locate the subnet for the IP address/host name pair (in the Cloud Foundation instance case) or for the IP instance case). See **Step 2** above for more information.    
   
      For example, if the IP address for your instance is `xx.yyy.zz.15` and the IP address for vCenter is `xx.yyy.zz.10`, you must grant access for the subnet `xx.yyy.zz.0/26`.
   
   5. Select the **Grant Access** check box for that subnet and click **Save**.
