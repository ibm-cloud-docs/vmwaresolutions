---

copyright:

  years:  2019, 2025

lastupdated: "2025-01-03"

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# BOM for {{site.data.keyword.vcf-auto-short}} multizone
{: #mcv-archi-bom}

New deployments of multizone instances are no longer supported. You can still add and delete clusters, add and remove ESXi servers, and add and delete storage for existing multizone instances.
{: deprecated}

Review the Bill of Materials (BOM) for {{site.data.keyword.vcf-auto}} multizone instances.

## Components
{: #mcv-archi-bom-components}

The following components are part of your existing {{site.data.keyword.vcf-auto-short}} multizone instance:
* VMware vSphere®
* VMware Aria components
   * VMware Aria® Operations™
   * VMware Aria Operations™ for Logs
   * VMware Aria Operations™ for Networks
* VMware NSX-T™
* VMware vSAN™ with the options of RAID 1, RAID 5, and RAID 6. Optane drives are the only supported option for vSAN cache disks.
* Licensing:
   * vSAN Enterprise
   * VMware NSX® Enterprise or Enterprise Plus
* High availability Active Directory with two virtual machines or two VSIs distributed between the two workload sites.

### Component naming conventions
{: #mcv-archi-bom-components-naming}

| Component | Format | Example |
|:--------- |:------ |:------- |
| Hostname| `<host_prefix><host_number>` | host01.subdomain.domain |
| Stretched cluster name | `<instance>-mgmt-<datacenter-region>` | mcv1-dal |
| Cluster and management component | `<instance>-<cluster>-<datacenter>-<component>` | mcv1-mgmt-dal10-private \n DAL10-DVS |
{: caption="Component naming conventions" caption-side="bottom"}

## Instance sizing considerations
{: #mcv-archi-bom-sizing}

The witness and management clusters can be deployed either by using NFS storage, with a minimum of two nodes required, or by using vSAN storage, with a minimum of four nodes required. Conversion of the witness or management clusters from NFS to vSAN is not supported or offered.

Your choice of effective RAID level determines the minimum number of hosts that must be deployed to Sites A and B.

* FTT levels are the default and are not monitored or managed by automation for Day 2 operations
* Minimum host count is determined by:
 Site A (workload) + Site B (workload) + Site A (management) + Site B (management) + witness

 The following table provides the Redundant Array of Independent Disks (RAID) and Failures to Tolerate (FTT) levels.

| RAID level | FTT | Erasure Coding | Minimum host count |
|:---------- |:--- |:-------------- |:------------------ |
| RAID 1 | PFTT=1 SFTT=1 | No | 3+3+2+2+2 |
| RAID 5 | PFTT=1 SFTT=1 | Yes | 4+4+2+2+2 |
| RAID 6 | PFTT=1  SFTT=2 | Yes | 6+6+2+2+2 |
{: caption="RAID and FTM levels" caption-side="bottom"}

## Day 2 operations
{: #mcv-archi-bom-ordering-daytwo}

Multizone instance automation provides provisioning, installation, and configuration of hardware and VMware components only. Automation is not available for Day 2 operations other than scale-up and scale-down.

### Witness site
{: #mcv-archi-bom-ordering-daytwo-witness}

The witness site can be scaled up and down with a maximum of 51 hosts.

### Management and resource clusters
{: #mcv-archi-bom-ordering-daytwo-mgmt}

Scale-up and scale-down are done in tandem across the two sites with a single user interface interaction.

The management cluster can be scaled up and down with a maximum of 51 hosts. The stretched cluster can be scaled up and down with a maximum of 32 hosts.

For example, you can add capacity by adding pairs of hosts, one in Site A and one in Site B to maintain uniformity in the configuration across the two sites. The status reflects that capacity is being added or removed to both sites simultaneously.
