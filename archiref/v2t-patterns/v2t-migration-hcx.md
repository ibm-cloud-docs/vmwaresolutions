---

copyright:

  years:  2022, 2024

lastupdated: "2024-06-04"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Workload migration with HCX
{: #v2t-hcx}

You can use VMware HCX™ for the VMware NSX-V to NSX-T™ migration in {{site.data.keyword.cloud}}. You can provision an optional HCX™ service in the new {{site.data.keyword.vcf-auto-short}}® instance with NSX-T, which is running in parallel with the existing {{site.data.keyword.vcf-auto-short}} with NSX-V. HCX deployment is fully automated in the new {{site.data.keyword.vcf-auto-short}} with NSX-T environment. After the HCX provisioning in complete, you need to deploy HCX Manager in the old environment and pair the environments. HCX is fully integrated with vCenter and NSX. HCX provides L2 Network Extension Service for the L2 network extension between environments and has various migration services (Bulk and vMotion) to help you move the workloads.

![Migration with HCX](../../images/v2t-diagrams-hcx.svg "HCX provides L2 Network Extension Service for doing the L2 network extension between the environments and various migration services (Bulk and vMotion) to help you move the workloads."){: caption="Migration with HCX" caption-side="bottom"}

1. Your existing NSX-V based instance was deployed previously and it hosts the current workloads and NSX-V network configurations. Before you start the migration, you need to have a thorough understanding of the environment, the workloads that are deployed, and the NSX-V and underlay network configurations.
2. You can deploy the new {{site.data.keyword.vcf-auto-short}} with NSX-T instance with new VLANs and a new POD, or you can use existing VLANs.
3. On the new NSX-T based {{site.data.keyword.vcf-auto-short}} instance, [order the HCX Service](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_ordering). You can use private deployment, as all HCX traffic between the environments uses private connectivity in {{site.data.keyword.cloud_notm}} private network. You must have outbound internet connectivity for HCX registration and updates.
4. After the HCX was deployed on the new target {{site.data.keyword.vcf-auto-short}}, provision HCX Manager on the old NSX-V based environment. You must have outbound internet connectivity for HCX registration and updates.
5. Establish Site Peering between the two environments from the old {{site.data.keyword.vcf-auto-short}} with NSX-V environment to the new {{site.data.keyword.vcf-auto-short}} with NSX-T environment. Then, create an HCX Service Mesh to enable the required services, such as Interconnect, L2 network extension, and the HCX migration services.
6. You can extend your NSX-V Logical Switches to NSX-T overlay segments with Network Extension service. Each HCX-NE can extend up to eight segments at a time, and you can create multiple HCX-NEs if needed.
7. Read the existing and create new network topology manually, by using scripts Migration Coordinator or third-party tools.
8. After the required networks are extended, you can start planning and migrating VMware workloads. HCX provides multiple ways for migration, such as Bulk Migration, Cold Migration, vMotion, and Replication Assisted vMotion. See the Broadcom® documentation for the differences of these methods and how you can best use them in your workload migration.

## Considerations for migrating with HCX
{: #v2t-hcx-considerations}

Each HCX-NE appliance can extend up to eight segments at a time, and you can create multiple HCX-NEs if needed. You can configure them when you create the service mesh.

## Related links
{: #v2t-hcx-links}

* [Ordering VMware HCX in {{site.data.keyword.cloud_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-hcx_ordering)
* [HCX for {{site.data.keyword.cloud_notm}} for VMware Solutions Guide](/docs/vmwaresolutions?topic=vmwaresolutions-hcxclient-planning-prep-install)
* [VMware HCX User Guide](https://techdocs.broadcom.com/us/en/vmware-cis/hcx.html){: external}
