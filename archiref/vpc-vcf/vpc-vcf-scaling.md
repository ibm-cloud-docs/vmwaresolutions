---

copyright:

  years:  2022

lastupdated: "2022-08-09"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Scaling capacity
{: #vpc-vcf-scaling}

After initial deployment, you can scale out the compute capacity on demand. The design supports the following scale-out paths.

* Addition of new hosts to an existing cluster in the same zone.
* Addition of new clusters or virtual infrastructure (VI) workload domains in the same zone.
* Addition of a new VMware Cloud Foundation™ (VCF) deployment in a new zone in the same or different region.

## Adding ESXi hosts into existing clusters
{: #vpc-vcf-scaling-hosts}

You can scale out an existing cluster by ordering hosts. You must add manually the hosts to your cluster and provision the required VLAN interfaces to the hosts for VMkernel adapters.

## Adding new clusters
{: #vpc-vcf-scaling-clusters}

You can also scale out the compute capacity by ordering new hosts and creating a new cluster. You must add manually the hosts to create the cluster and provision the required VLAN interfaces to the hosts for VMkernel adapters.

This method allows achieving the following configuration.

* Creating an extra, separate cluster in the environment.
* Separating management workloads from application workloads physically and logically.
* Separating workloads based on other characteristics, for example, Microsoft® SQL database cluster.
* Deploying applications in highly available topologies.

## Adding more sites
{: #vpc-vcf-scaling-sites}

You can use other multizone regions and {{site.data.keyword.cloud}} worldwide data center presence to allow for various cross-geographies use cases to be deployed.

This method allows achieving the following configuration.

* Creating an extra, geographically separated deployment for Disaster Recovery use cases.
* Creating an extra, geographically separated deployment for closer proximity to users.
* Creating an extra, geographically separated deployment for Regulatory or Compliance reasons of your business and workloads.

## Related links
{: #vpc-vcf-scaling-links}

* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} bare metal servers](/docs/vpc?topic=vpc-planning-for-bare-metal-servers)
* [{{site.data.keyword.vpc_short}} VMware Cloud Foundation VMware architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-arch-overview)
* [{{site.data.keyword.vpc_short}} VMware Cloud Foundation architectures](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-architectures)
* [{{site.data.keyword.dl_full_notm}} overview](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl)
* [{{site.data.keyword.tg_full_notm}} overview](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [{{site.data.keyword.vpc_short}} VPN overview](/docs/vpc?topic=vpc-vpn-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on bare metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)
