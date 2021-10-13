---

copyright:

  years:  2016, 2021

lastupdated: "2021-09-10"

keywords: vSphere scale cluster, scale vSphere, scale vSphere cluster

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Scaling existing vSphere clusters
{: #vs_scalingexistingclusters}

You can scale out a VMware vSphere® cluster that you ordered or saved in the {{site.data.keyword.vmwaresolutions_full}} console. To do so, add VMware ESXi™ servers or order a FortiGate® 300 Series Security Appliance HA pair for the cluster.

## Requirements for vSphere clusters
{: #vs_scalingexistingclusters-req}

Ensure that you complete the following tasks:
* If you are ordering an instance for the first time, complete the tasks in the **Before you begin** section on the ordering page. For more information, see [Setting up your environment for your first order](/docs/vmwaresolutions?topic=vmwaresolutions-completing_checklist).
*  Review the requirements and considerations in [Requirements and planning for vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_planning).
*  Verify that you received an email with the confirmation that the cluster you want to scale is ready to use.

## Procedure to scale existing clusters
{: #vs_scalingexistingclusters-procedure}
{: help}
{: support}

1. In the {{site.data.keyword.vmwaresolutions_short}} console, click the **VMware Solutions Dedicated** card in the **IaaS platforms** section.
2. On the **VMware Solutions Dedicated** page, click the **VMware vSphere** card.
3. Click the **Scale existing** tab and select the cluster that you want to scale from the **Cluster configurations** list.
4. Review the cluster settings that are automatically completed, update the settings according to your needs, and complete any required fields. For more information about the settings, see [Ordering new vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances).
5. If the cluster does not include the FortiGate 300 Series Security Appliance HA Pair on its public VLAN, you can order the appliance. To do so, select the **Include with purchase** checkbox under **FortiGate Physical Appliance 300 Series HA Pair**.
6. In the **Summary** pane, verify the instance configuration and the estimated price.
   * To save the configuration as a template without placing an order, click **Save configuration**.
   * To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Create**.

### Results
{: #vs_scalingexistingclusters-results}

The cluster scaling starts automatically. You receive an email confirmation that the order is being processed. When the cluster is ready to use, you are notified by email. If the cluster that you are scaling is not ready to use, you might receive an error message.

The vSphere clusters, unlike the VMware vCenter Server® instances, are not displayed on the **Resources** page.
{: note}

## Related links
{: #vs_scalingexistingclusters-related}

* [Ordering new vSphere clusters](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderinginstances)
* [Ordering vSphere clusters based on existing configurations](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingbasedonexistingconfig)
* [Scaling clusters created outside of the console](/docs/vmwaresolutions?topic=vmwaresolutions-vs_orderingforclustersoutside)
