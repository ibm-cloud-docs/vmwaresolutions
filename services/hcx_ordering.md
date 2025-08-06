---

copyright:

  years:  2016, 2025

lastupdated: "2025-08-06"

keywords: VMware HCX deployment, HCX configuration, order HCX

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Ordering VMware HCX
{: #hcx_ordering}

You can include the VMware HCX™ service with a new {{site.data.keyword.vcf-auto}} instance or add the service to your existing instance.

## Considerations when you install HCX
{: #hcx_considerations-install}

Review the following considerations before you install HCX.

### Requirements on the number of ESXi servers
{: #hcx_considerations-esxi-servers}

The HCX service mesh target cluster cannot have more than 51 VMware ESXi servers. HCX requires eight IP addresses in the vMotion subnet from the service mesh target cluster. Because of this requirement, if the number of ESXi servers exceeds 51, no IP addresses in the vMotion subnet are available for HCX.

### Requirements on firewall rules
{: #hcx_considerations-firewall}

Before you install the HCX service, you must add a firewall rule to any existing firewalls.

1. {{site.data.content.ol-intro-ui-vcfclassic}}
2. In the **{{site.data.keyword.vcf-classic}}** table, click the instance to view the clusters from that instance.
3. Click the **Infrastructure** tab and select the cluster where you want to install the HCX service.
4. Go to the **Network interface** section on the cluster page.
5. Collapse the **Public VLAN** option and collapse the subnet with the description that corresponds to the portable subnet of the cluster.
6. Use the IP address from the Service T0 uplink2 Virtual IP address to route the traffic in the firewall rule. The firewall rule is required to allow all outbound HTTPS traffic so that the HCX Manager virtual appliance (HCX Manager) can register itself.
7. After the HCX Manager installation is completed, you can remove the firewall rule.

Access to the HCX Cloud IP address is restricted through a gateway firewall rule. To enable access to the HCX Cloud IP address, you must update the firewall rule to ALLOW the inbound traffic. To do that, log in to the NSX Manager and locate the gateway firewall rule `HCX_Inbound_Traffic_1_for_{{ hcxhostname }}`. Change the action value from REJECT to ALLOW.
{: important}

In addition, you must configure firewall rules to allow HCX to function properly. For more information, see [Port access requirements for VMware HCX](/docs/vmwaresolutions?topic=vmwaresolutions-hcx-archi-port-req#hcx-archi-port-req).

## Ordering HCX for a new instance
{: #hcx_ordering-new}

1. When you [order the instance](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-procedure), scroll down to the **Add-on services** section. HCX is in the **Data resiliency and migration** category.
2. Open the category, locate HCX, and toggle its switch on.
3. Click **Edit** to review and specify [the configuration information](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_ordering#hcx_ordering-config), then click **Save**.

## Ordering HCX for an existing instance
{: #hcx_ordering-existing}

1. On the instance details page, click the **Services** tab.
2. Click **Add** to add the service.
3. On the **Add services** page, locate the **HCX** service in the **Data resiliency and migration** section and toggle its switch on.
4. Click **Edit** to review and specify [the configuration information](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_ordering#hcx_ordering-config), then click **Save**.

## HCX configuration
{: #hcx_ordering-config}

To install HCX, complete the following steps:

1. Select the **HCX Service Mesh target cluster**, either the management or the workload cluster.
2. Specify the **Public endpoint certificate type**. If you select **CA Certificate**, configure the following settings:
   * **Certificate contents** - Enter the contents of the CA certificate.
   * **Private key** - Enter the private key of the CA certificate.
   * **Password** (Optional) - Enter the password for the private key, if it is encrypted.
   * **Reenter password** (Optional) - Enter the password for the private key again.
   * **Hostname** (Optional) - The hostname to be mapped to the common name (CN) of the CA certificate. HCX requires that the format of the CA certificate must be accepted by NSX Edge. For more information about NSX Edge certificate formats, see [Import an SSL certificate](https://techdocs.broadcom.com/us/en/ca-enterprise-software/it-operations-management/capacity-management/2-9-4/administrating/capacity-command-center-administration/using-data-adapters-to-collect-data-from-monitoring-tools/import-an-ssl-certificate.html){: external}.

## Deployment process for HCX
{: #hcx_ordering-deploy}

The deployment of HCX is automated. Whether you order a {{site.data.keyword.vcf-auto-short}} instance with the service included or you deploy the service later into your instance, the following steps are completed by the {{site.data.keyword.vmwaresolutions_short}} automation process:

{{site.data.content.impnote-deploymanual-hcx}}

1. Three subnets are ordered for HCX from the {{site.data.keyword.cloud_notm}} infrastructure:
   * One private portable subnet for HCX management
   * One private portable subnet for HCX interconnects
   * One public portable subnet for HCX interconnects

   The IP addresses in the subnets that are ordered for HCX are intended to be managed by the VMware Solutions automation. These IP addresses cannot be assigned to VMware resources (such as VMs and NSX Edges) that are created by you. If you need more IP addresses for your VMware artifacts, you must order your own subnets from {{site.data.keyword.cloud_notm}}.
   {: restriction}

2. For HCX in a private network, a port group that is named **SDDC-DPortGroup-HCX-Private** is created on the private Distributed Virtual Switch (DVS).
3. An HCX activation key is ordered from VMware.
4. For {{site.data.keyword.vcf-auto-short}} with NSX-T instances, the firewall rules and network address translation (NAT) rules are configured to allow inbound and outbound HTTPS traffic to and from the HCX Manager.

5. The HCX Manager is deployed, activated, and configured:
   * The HCX Manager is registered with the VCSA.
   * The HCX Manager, VCSA, and NSX Manager are configured.
   * The HCX Compute and Network profiles are created.

6. The hostname and IP address of the HCX Manager is registered with the DNS server of the {{site.data.keyword.vcf-auto-short}} instance.

## Related links
{: #hcx_ordering-related}

* [HCX overview](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_considerations#hcx_considerations)
* [Managing HCX](/docs/vmwaresolutions?topic=vmwaresolutions-managinghcx)
* [Ordering services for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices)
* [Glossary of HCX terms](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_glossary)
* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [VMware HCX documentation](https://techdocs.broadcom.com/us/en/vmware-cis/hcx.html){: external}
