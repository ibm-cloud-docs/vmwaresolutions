---

copyright:

  years:  2016, 2025

lastupdated: "2025-12-03"

keywords: Zerto certificate, Zerto config, update Zerto replication

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Managing {{site.data.keyword.hpe-zerto}}
{: #managingzertodr}

{{site.data.content.vms-deprecated-note}}

After the {{site.data.keyword.hpe-zerto}} service is deployed into your instance, you can configure or update Zerto Virtual Replication. You can also deploy more Virtual Replication Appliances to newly added VMware® ESXi™ servers.

## Managing the configuration of {{site.data.keyword.hpe-zerto}} replications
{: #managingzertodr-manage}

To manage the configuration of {{site.data.keyword.hpe-zerto}} replications, log in to the Zerto Virtual Replication console. For example, re-pairing {{site.data.keyword.hpe-zerto}} instances or configuring virtual protection groups to replicate virtual machines.

When you're replicating between different {{site.data.keyword.cloud}} {{site.data.keyword.hpe-zerto}} instances, you can configure replication directly between the {{site.data.keyword.hpe-zerto}} instances. If you're replicating between the {{site.data.keyword.cloud_notm}} {{site.data.keyword.hpe-zerto}} instance and your own data center, you must install {{site.data.keyword.hpe-zerto}} yourself in your own data center. This instance can license itself automatically when you pair it with the {{site.data.keyword.cloud_notm}} {{site.data.keyword.hpe-zerto}} instance.

{{site.data.keyword.hpe-zerto}} replication doesn't support Network Address Translation (NAT) traversal. Establishing connectivity between the {{site.data.keyword.cloud_notm}} {{site.data.keyword.hpe-zerto}} instance and your own data center might require customization of routes on the Zerto Virtual Manager appliances or Zerto Virtual Replication Appliances (VRAs) on either side. Establishing connectivity might also require secure tunneling between the sites. When you're configuring or reconfiguring routes on Zerto Virtual Manager appliances, you must ensure that all Zerto Virtual Manager appliances can connect successfully to `zerto.com` for usage reporting. You can verify this connection by opening a browser session to `https://www.zerto.com` from the Zerto Virtual Manager appliance.

The Management VMware NSX Edge™ Services Gateway (ESG) is preconfigured to allow outbound HTTPS (TCP port 443) communications that originate from Zerto Virtual Manager.
{: note}

## Updating Zerto Virtual Replication
{: #managingzertodr-update}

To update Zerto Virtual Replication, open an IBM Support ticket by following the steps in [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support) to get the {{site.data.keyword.hpe-zerto}} installation executable file for your environment.

## Deploying VRAs to newly added ESXi servers
{: #managingzertodr-deploy}

When you add or remove ESXi servers for the primary cluster of your instance, VRAs are automatically deployed or removed. VRAs aren't automatically deployed to ESXi servers in the secondary clusters of your instance. You can deploy VRAs yourself from the Zerto Virtual Replication console.

## Related links
{: #managingzertodr-related}

* [{{site.data.keyword.hpe-zerto}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-addingzertodr)
* [Ordering {{site.data.keyword.hpe-zerto}}](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering)
* [Ordering {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_ordering_licenses)
* [Managing {{site.data.keyword.hpe-zerto}} stand-alone licenses](/docs/vmwaresolutions?topic=vmwaresolutions-zerto_managing_licenses)
* [{{site.data.keyword.hpe-zerto}} product documentation](https://www.zerto.com/myzerto/technical-documentation/){: external}
* [{{site.data.keyword.hpe-zerto}} for Disaster Recovery](https://www.hpe.com/psnow/doc/a50012146enw?jumpid=in_hpesitesearch){: external}
