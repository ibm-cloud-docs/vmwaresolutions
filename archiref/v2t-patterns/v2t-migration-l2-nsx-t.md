---

copyright:

  years:  2023, 2025

lastupdated: "2025-07-28"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Workload migration by using vMotion or third-party tools and NSX-T L2 bridge
{: #v2t-l2-nsx-t}

VMware NSX-V to VMware NSX-T™ migration in {{site.data.keyword.cloud}} is done by following the principles of the VMware® Lift-and-Shift Migration model, which consists of migrating the network configurations and workloads. Migrating workloads during this process can be done in many ways. For example, you can use Advanced Cross vCenter vMotion between the environments, or you can use other optional or existing third-party tools like Veeam® or Zerto.

## Using NSX-T L2 bridge in migration
{: #v2t-l2-nsx-t-bridge}

Regardless of the tool you choose to migrate the workloads, you typically need to extend L2 between the existing NSX-V instance and the new NSX-T instance. The following diagram presents an overview of how to extend the networks with NSX-T L2 bridging capability.

![Migration by using vMotion or third-party tools and NSX-T L2 bridge](../../images/v2t-diagrams-l2-nsx-t.svg "No matter which migration method you choose, you typically need to extend L2 between the existing NSX-V and the new NSX-T instance. This shows how to extend the networks with NSX-T L2 bridging capability."){: caption="Migration by using vMotion or third-party tools and NSX-T L2 bridge" caption-side="bottom"}

1. Your existing NSX-V based instance was deployed previously and it hosts the current workloads and NSX-V network configurations. Before you start the migration, you must have a thorough understanding of the environment, the workloads that are deployed on it, and the NSX-V and underlay network configurations.
2. You can deploy the new {{site.data.keyword.vcf-auto-short}}® with NSX-T instance with new VLANs and a new POD, or you can use existing VLANs.
3. Capture the existing network configuration and create a new network topology manually, by using scripting or Terraform, migration coordinator, or third-party tools.
4. Prepare configurations for failover in NSX-T. Configure NSX-T segments and configure Tier-1 and Tier-0 Gateways.
5. Deploy an NSX-T L2 bridge on a {{site.data.keyword.vcf-auto-short}} instance's NSX-V enabled host. Deploy one bridge per each extended overlay network to extend NSX-V logical switch to NSX-T overlay segment. You can deploy multiple bridges and you can also reuse existing bridges easily.
6. Test migrations to the target with the L2 network extension.
7. Migrate networks to route through NSX-T Tier-1 and Tier-0 Gateways.
8. Migrate the rest of the workloads based on the wave planning.

## Migrating workloads with Advanced Cross vCenter vMotion
{: #v2t-l2-nsx-t-vmotion}

To migrate virtual machines across {{site.data.keyword.vcf-auto-short}} instances in different vCenter Single Sign-On domains, you can use Advanced Cross vCenter vMotion. Тhe {{site.data.keyword.vcf-auto-short}} instance from which you initiate the import or export of virtual machines must be version 7.0 Update 1c or later.

In this method, the existing instance and the new target instance have different data stores. When you migrate, you must take this issue into account, which also applies when you are using {{site.data.keyword.filestorage_full_notm}}. Plan the storage migration as part of the migration process.

It is possible to manually add and allow the existing {{site.data.keyword.filestorage_full_notm}} volumes to be accessible to the new {{site.data.keyword.vcf-auto-short}} with NSX-T instance. However, it is not generally advised leaving the volumes accessible for a longer period. The {{site.data.keyword.vcf-auto-short}} with NSX-T instance's automation is not aware of the old and manually added storage, and when you add new hosts and clusters to the new instance you might see unwanted behavior and the new hosts might not have access to this data store.
{: important}

## Migrating workloads with Veeam
{: #v2t-l2-nsx-t-veeam}

{{site.data.keyword.vcf-auto-short}} offers an optional service for Veeam. The Veeam service seamlessly integrates directly with your VMware® hypervisors and you control both the backup and restore of all virtual machines (VMs) for your infrastructure directly from the Veeam console.

The current Veeam version that is installed by automation is Veeam Backup and Replication 12.3, but you might have an older version in your NSX-V based deployment. You can use Veeam's replication capabilities during the migration.

For more information, see [Ordering services for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices) and [Veeam technical documentation](https://www.veeam.com/support/help-center-technical-documentation.html?ad=in-text-link){: external}.

## Migrating workloads with Zerto
{: #v2t-l2-nsx-t-zerto}

{{site.data.keyword.vcf-auto-short}} instances offer an optional service for Zerto. The Zerto service integrates replication and disaster recovery capabilities into the deployment offerings to protect and recover data in your VMware virtual environment on {{site.data.keyword.cloud_notm}}.

You can use Zerto's replication capabilities during the migration.

For more information, see [Ordering services for {{site.data.keyword.vcf-auto-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices) and [Zerto product documentation](https://help.zerto.com){: external}.

## Considerations for using NSX-T L2 bridge in migration
{: #v2t-l2-nsx-t-considerations}

A recommended practice is to use one NSX-T Edge node to extend one NSX-V Logical Switch. This Edge node must be a virtual appliance because the NSX-T Edge must be deployed on an {{site.data.keyword.cloud_notm}} bare metal server that is prepared for NSX-V.

The Edge node extends the VXLAN Logical Switch to the NSX-T GENEVE overlay segment. The Edge Services Gateways in the NSX-V environment serve as the default gateway for all north-south traffic from the workload VMs on the Logical Switch until disconnect the NSX-V Logical Switch from the Distributed Logical Router (DLR), and connect the NSX-T overlay segment to the Tier-0 or Tier-1 gateway. This switches the default gateway to the NSX-T Tier-0 or Tier-1 gateway, depending on the chosen NSX-T topology.

After all the workloads are migrated from NSX-V to NSX-T, you can remove the bridge.

## Related links
{: #v2t-l2-nsx-t-links}

* [Overview of edge bridging in NSX-T](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/migration-guide/preparing-layer-2-bridging-for-lift-and-shift-migration/overview-of-edge-bridging-in-nsx-t-data-center.html){: external}
* [Extending Layer 2 networks with NSX-T edge bridge](https://techdocs.broadcom.com/us/en/vmware-cis/nsx/nsxt-dc/3-2/migration-guide/preparing-layer-2-bridging-for-lift-and-shift-migration/extending-layer-2-networks-with-nsx-t-edge-bridge.html){: external}
* [Veeam technical documentation](https://www.veeam.com/support/help-center-technical-documentation.html?ad=in-text-link){: external}
* [Zerto product documentation](https://help.zerto.com){: external}
* [Migration between vCenter Server systems](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/7-0/vcenter-and-host-management-7-0/migrating-virtual-machines-host-management/migration-with-vmotion-host-management/vmotion-across-vcenter-server-systems-host-management.html){: external}
* [Introducing the Advanced Cross vCenter Server vMotion capability](https://www.vmware.com/docs/vmw-introducing-the-advanced-cross-vcenter-server-vmotion-capability){: external}
