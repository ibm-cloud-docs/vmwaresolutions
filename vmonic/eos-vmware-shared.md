---

copyright:

  years:  2024, 2025

lastupdated: "2025-03-18"

keywords: end of support notice, vmware shared, end of support vmware shared, vmware shared deprecated, vmware shared support

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# End of Support for {{site.data.keyword.vm-shared}} deployments
{: #eos-vmware-shared}

As of 28 March 2024, {{site.data.keyword.vm-shared}} is not available for new deployments. Support for existing instances is extended until 28 February 2025. All customer and management data, including the backups of workloads, will be deleted in March 2025. Migrate all your {{site.data.keyword.vm-shared}} resources to [{{site.data.keyword.vmware-service_full}}](/docs/vmware-service) by 28 February 2025.
{: deprecated}

{{site.data.keyword.cloud}} support for {{site.data.keyword.cloud_notm}} for {{site.data.keyword.vm-shared}} will end on 28 February 2025. As stated in [End of Support for NSX-V instance deployments](/docs/vmwaresolutions?topic=vmwaresolutions-eos-nsx-v), {{site.data.keyword.IBM_notm}}’s exclusive support extension for VMware® NSX-V is ending soon. Because {{site.data.keyword.cloud_notm}} for {{site.data.keyword.vm-shared}} uses NSX-V as the underlying networking software, it will no longer be supported after 28 February 2025.

The upgraded replacement for {{site.data.keyword.vm-shared}} is {{site.data.keyword.vcf-aas-full}}, the next generation {{site.data.keyword.IBM_notm}}-managed VMware Cloud Director offering. {{site.data.keyword.IBM}} strongly recommends that you migrate your workloads to [{{site.data.keyword.vcf-aas}}](/docs/vmware-service).

{{site.data.keyword.vcf-aas}} is based on VMware NSX-T software and is provided at near-identical [pricing](/docs/vmwaresolutions?topic=vmwaresolutions-eos-vmware-shared#eos-vmware-shared-pricing). As of December 2024, {{site.data.keyword.vcf-aas}} multitenant is available in 7 {{site.data.keyword.cloud_notm}} regions, and more regions are added periodically.

As of 28 March 2024, new orders for {{site.data.keyword.cloud_notm}} for {{site.data.keyword.vm-shared}} instances are not accepted. If you are an existing customer, you can continue to use your {{site.data.keyword.vm-shared}} deployments until 28 February 2025 after which access to workloads will end. {{site.data.keyword.IBM_notm}} does not anticipate any further extensions after 28 February 2025 and all existing workloads will be deleted in March 2025. Regardless of the retention period, all backups would also be deleted in March 2025. {{site.data.keyword.IBM_notm}} strongly recommends that you assess your workloads immediately and complete your migration to {{site.data.keyword.vcf-aas}} before 28 February 2025.

{{site.data.keyword.cloud_notm}} offers secure, simple, and cost-effective onboarding and migration options: either self-service or assisted. For more information, see [Migrating from {{site.data.keyword.vm-shared}} to {{site.data.keyword.vcf-aas}}](/docs/vmwaresolutions?topic=vmwaresolutions-shared_migration).

## Pricing changes to consider when you migrate to {{site.data.keyword.vcf-aas}} multitenant
{: #eos-vmware-shared-pricing}

Review the following pricing considerations:

* The prices for vCPU and RAM are rebalanced for {{site.data.keyword.vcf-aas}} multitenant to enable more cost-effective scaling of RAM.
* {{site.data.keyword.vcf-aas}} multitenant uses vSAN-backed Block Storage for Veeam, while the legacy {{site.data.keyword.vm-shared}} offering uses the less expensive 0.25 IOPS File Storage. This difference results in a net increase in price for Veeam Block Storage when you migrate.
* On-demand Base Charge is not applicable for {{site.data.keyword.vcf-aas}}, as it is replaced by the newly introduced network edge tiers. Network edge charges apply to both on-demand and reserved usage.
* The following options are available for [network edges](/docs/vmwaresolutions?topic=vmwaresolutions-shared-vmwaas-migration#shared-vmwaas-migration-edge-type): Efficiency, Medium, Large, and Extra Large. Most customers require an Efficiency edge for their first virtual data center, which is price-matched with the Base Charge in {{site.data.keyword.vm-shared}}.

For more information about pricing, see the [{{site.data.keyword.vcf-aas}} About page](/vmware/vmware_as_a_service/provision/vdc_mt#about).

## Migration considerations
{: #eos-vmware-shared-consider}

Since {{site.data.keyword.vcf-aas}} is based on VMware Cloud Director, it retains the same console that is used for {{site.data.keyword.vm-shared}}. You benefit from performance improvements, greater global coverage, and a small price rebalancing, which make {{site.data.keyword.vcf-aas}} the ideal landing zone for your workloads.

Additionally, {{site.data.keyword.vcf-aas}} multitenant includes different options for network edges: an Efficiency edge, and three types of Performance edges.

Depending on the size and complexity of your workloads, you can migrate them by using a self-service migration tool. If you need assistance, you can choose a partner to help with some migration activities or ask them to do a full migration for you.

## Related links
{: #eos-vmware-shared-related}

* [FAQ about End of Support for {{site.data.keyword.vm-shared}}](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions-shared-eos)
* [Migrating from {{site.data.keyword.vm-shared}} to {{site.data.keyword.vcf-aas}}](/docs/vmwaresolutions?topic=vmwaresolutions-shared_migration)
* [Technical considerations about migrating from {{site.data.keyword.vm-shared}} to {{site.data.keyword.vcf-aas}}](/docs/vmwaresolutions?topic=vmwaresolutions-shared-vmwaas-migration)
* [Migrating {{site.data.keyword.vm-shared}} workloads to {{site.data.keyword.vcf-aas}} with cloud-to-cloud connections](/docs/vmwaresolutions?topic=vmwaresolutions-vcda-migrating-cloudtocloud-shared) (tutorial and video)
* [What is {{site.data.keyword.vmware-service_short}}?](https://www.ibm.com/products/vmware/managed-services)
* [{{site.data.keyword.vmware-service_short}} About page](/vmware/vmware_as_a_service/provision/vdc_mt#about)
* [{{site.data.keyword.vmware-service_short}} Provisioning page](/vmware/vmware_as_a_service/provision/vdc_mt)
