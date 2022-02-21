---

copyright:

  years:  2016, 2022

lastupdated: "2022-01-26"

keywords: vSphere order cluster, order vSphere, order vSphere cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Procedure to order vSphere clusters
{: #vs_orderinginstances-procedure}

1. In the {{site.data.keyword.vmwaresolutions_full}} console, click the **VMware Solutions Dedicated** card in the **IaaS platforms** section.
2. On the **VMware Solutions Dedicated** page, click the **VMware vSphere** card. Ensure that you are on the **Create new** tab and that **New cluster** is displayed in the **Cluster configurations** list.
3. Enter the cluster name.
4. Select the VMware® components:
   * If you are an IBM Business Partner, select a license bundle and any additional available VMware components.
   * If you are a non-Business Partner, select the component, edition if any, and specify the licensing option.

   When you choose to Bring Your Own License (BYOL) for VMware vSphere® Enterprise Plus, an {{site.data.keyword.cloud_notm}} ticket is opened automatically on your behalf to request the default vSphere licenses on your ordered bare metal servers to be replaced with your provided licenses.

   You are responsible to track the ticket so that you replace the vSphere license on the newly ordered VMware ESXi® servers. This way the {{site.data.keyword.cloud_notm}} infrastructure grants the cancellation of the initially provided {{site.data.keyword.cloud_notm}} infrastructure vSphere license charge. To replace your ESXi vSphere license, see [Configure license settings for an ESXi host](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.vcenterhost.doc/GUID-1B128360-0060-40F2-A6F0-43CD2534B034.html){: external}.
   {: important}

5. Complete the bare metal server settings:
   1. For data center location, click the **Edit** icon ![Edit icon](../../icons/edit-tagging.svg "Edit") and select the geography, data center, and pod where the cluster is to be hosted.
   2. Select the bare metal server CPU generation.
      * For **Skylake**, **Cascade Lake**, or **SAP-certified** - **HANA** servers, specify the CPU model and the RAM size.
      * For **SAP-certified** - **NetWeaver** server, choose one of the preset configurations.
   3. Specify the number of bare metal servers.
6. If you selected the **VMware vSAN** component, complete the vSAN™ storage configuration.
   * If you want more storage, select the **High performance with Intel Optane** checkbox.
   * Specify the disk types for the capacity and cache disks, and the number of disks.
   * By default, the **Enable vSAN deduplication and compression** checkbox is selected. If you do not want to enable vSAN deduplication and compression, clear the checkbox.
7. Complete the network interface settings:
   1. Enter the host name prefix, subdomain label (vSphere 6.7u3 instances only), and domain name.
   2. Select the network setting of either **Public and private network** or **Private network only**.
   3. Select the uplink speed. The 25 Gb option is available for Cascade Lake servers and for specific data center locations only.
   4. Select the network interface that you want to use.
      * If you want to order new public and private VLANs, click **Order new VLANs**.
      * If you want to reuse the existing public and private VLANs when they are available, click **Select existing VLANs** and specify the VLANs and optionally the subnets.
   5. If you are ordering public VLANs, specify whether to apply the FortiGate Physical Appliance 300 Series HA Pair to secure your cloud environment.
8. In the **Summary** pane, verify the cluster configuration and the estimated price.
   * To save the configuration as a template without placing an order, click **Save configuration**.
   * To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

   Only the {{site.data.keyword.cloud_notm}} bare metal servers are installed. You are responsible for installing and configuring various components after cluster deployment, such as VMware vCenter, VMware NSX®, VMware vSAN.
   {: note}

## Results after you order vSphere clusters
{: #vs_orderinginstances-results}

If you saved the cluster configuration as a template, you get a console notification that the configuration is saved successfully, and then you can find the template in the **Cluster configurations** list.

If you placed an order, the deployment of the cluster starts automatically, and you receive an email confirmation that the order is being processed. When the cluster is ready to use, you are notified by email.

The vSphere clusters, unlike the vCenter Server instances, are not displayed on the **Resources** page.
{: note}

## Related links
{: #vs_orderinginstances-procedure-related}

* [Ordering vSphere clusters based on existing configurations](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingbasedonexistingconfig)
* [Scaling existing clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_scalingexistingclusters)
* [Scaling clusters created outside of the console](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingforclustersoutside)
