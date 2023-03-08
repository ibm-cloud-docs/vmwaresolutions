---

copyright:

  years:  2020, 2023

lastupdated: "2023-02-08"

keywords: Juniper vSRX, manage Juniper vSRX, Juniper vSRX console

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Ordering Juniper vSRX
{: #juniper-ordering}

You can include the Juniper® vSRX service with a new VMware vCenter Server® instance or add the service to your existing VMware® vCenter Server instance.

You can install multiple instances of Juniper vSRX on the management cluster. On a single edge gateway cluster, you can install only one instance of Juniper vSRX.

You can now install Juniper vSRX on 25 Gb uplink speed management and edge gateway clusters on VMware vSphere® 7 with NSX-T. On 25 Gb uplink speed clusters, only the Content Security Bundle license is available.

The license that is used depends on the target cluster you choose. For vCenter Server instances with vSphere 7 and NSX-T, management and edge gateway clusters with 25 Gb uplink speed use the 25 Gb uplink speed version of the license selected. For Regulated Workload (including Regulated Workload stretched) and Security & Compliance Readiness Bundle instances, the same license selection process occurs for edge gateway clusters with 25 Gb uplink speeds.

You cannot install Juniper vSRX and FortiGate Virtual Appliance on the same edge gateway cluster.

## Ordering Juniper vSRX for a new instance
{: #juniper-ordering-new-instance}

1. When you [order the instance](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure), scroll down to the Add-on services section. Juniper vSRX is in the Security and compliance category. 
2. Open the category, locate Juniper vSRX, and toggle its switch on.
3. Select **Edit** to review and specify the information. 
4. If you enter or change information, click **Save**.

The Juniper vSRX service is deployed on the management cluster unless you order the edge gateway cluster. For the Juniper vSRX service to function as a gateway for your vCenter Server instance, you must include the edge gateway cluster in your order.

## Ordering Juniper vSRX for an existing instance
{: #juniper-ordering-exist-instance}

1. On the instance details page, click **Services** on the left navigation window.
2. Click **Add** to add the service.
3. On the **Services** page, locate the **Juniper vSRX** service and toggle its switch on.
4. Follow the steps to configure and add the service to your instance.

When you add Juniper vSRX to an existing vCenter Server instance, you can select a cluster on which to install Juniper vSRX. You can install Juniper vSRX on a management cluster or on any edge gateway cluster.
You must deploy Juniper vSRX to an edge gateway cluster for Juniper vSRX to function as a gateway for your vCenter Server instance.

You cannot install Juniper vSRX and FortiGate Virtual Appliance on the same edge gateway cluster.

## Juniper vSRX service configuration
{: #juniper-ordering-service-config}

When you order the service, provide the following settings:

### Name
{: #juniper-ordering-service-config-name}

Specify the nickname for the installed instance in the **Enter a name for the HA deployment** field. Because multiple copies of Juniper vSRX can be in a single vCenter Server instance, this name is used to ensure that the names of all networking components are unique.

### License model
{: #juniper-ordering-service-config-license-model}

Review the features of the two licenses and select either **Standard Edition** or **Content Security Bundle**.

You can't change the license model after service installation. To change the license model, you must delete the existing service and reinstall the service by selecting a different license option.
{: important}

After the service is ordered, the vSRX nodes are automatically ordered with the selected license models.

### Juniper vSRX deployment on an edge gateway cluster
{: #juniper-ordering-service-config-edge-deployment}

If you deploy Juniper vSRX on an edge gateway cluster, after deployment, you must configure Juniper vSRX specifically for your environment. Complete the following steps:
1. Configure the redundant Ethernet (`reth`) 2 interface with the default gateway IP addresses of each subnet in your private trunk VLAN. The IP addresses are assigned to the logical interface, which is in the format of `reth2.VLANid`.
2. Configure the redundant Ethernet (`reth`) 3 interface with the default gateway IP addresses of each subnet in your public trunk VLAN, if you have one. The IP addresses are assigned to the logical interface, which is in the format of `reth3.VLANid`.
3. In the {{site.data.keyword.cloud}} classic infrastructure view, look at the gateway appliance ordered for the edge gateway cluster. From there, assign the VLANs that you want to the gateway appliance and put them in *route-through* mode.

## Related links
{: #juniper-ordering-related-links}

* [Juniper vSRX overview](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-overview)
* [Managing Juniper vSRX](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-managing)
* [Ordering services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices)
* [General FAQ about VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [Juniper vSRX Virtual Firewall](https://www.juniper.net/us/en/products-services/security/srx-series/vsrx/){: external}
* [Juniper vSRX Documentation](https://www.juniper.net/documentation/product/en_US/vsrx){: external}
