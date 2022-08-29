---

copyright:

  years:  2022

lastupdated: "2022-08-09"

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Deploying VLAN interfaces for VMware Cloud Foundation appliances in {{site.data.keyword.vpc_short}}
{: #vpc-vcf-mgmt-appliances}

The topic provides an overview of how to deploy VLAN interfaces for VMware Cloud Foundation™ (VCF) appliances in {{site.data.keyword.vpc_short}}. You might alter this architecture for your needs, but it is important to follow the VCF requirements for the appliance network locations.

## VLAN interfaces for Cloud Builder, SDDC manager, and VMware vCenter Server
{: #vpc-vcf-mgmt-appliances-vlan-nics}

The VMware® Cloud Builder appliance automates the deployment of the entire software-defined stack. VMware Cloud Builder is a virtual appliance that is used to deploy and configure the first cluster of the management domain and transfer inventory and control to SDDC manager. During the deployment process, the VMware Cloud Builder appliance validates network information that you provide in the deployment parameter workbook, such as DNS, network (VLANS, IP addresses, MTUs), and credentials. The VMware Cloud Builder appliance must have network access to all hosts on the management network.

VMware vCenter Server® is deployed to manage the hosts and clusters.

SDDC manager automates the entire system lifecycle, that is, from configuration and provisioning to upgrades and patching, which includes host firmware and simplifies day-to-day management and operations.

The following table summarizes the required VLAN interfaces in {{site.data.keyword.vpc_short}} for these appliances.

Interface name         | Interface type | VLAN ID | Subnet              | Allow float  | VCF appliance     | Distributed port group name
-----------------------|----------------|---------|---------------------|--------------|-------------------|------------------------------
vlan-nic-cloud-builder | vlan           | 1611    | vpc-mgmt-subnet     | true         | Cloud Builder     | pg-mgmt
vlan-nic-vcenter       | vlan           | 1611    | vpc-mgmt-subnet     | true         | vCenter Server    | pg-mgmt
vlan-nic-sddc-manager  | vlan           | 1611    | vpc-mgmt-subnet     | true         | SDDC Manager      | pg-mgmt
{: caption="Table 1. VLAN interfaces for VCF appliances" caption-side="bottom"}

In addition, you must provision the required VLAN interfaces for NSX-T appliances.

## Related links
{: #vpc-vcf-mgmt-appliances-links}

* [{{site.data.keyword.vpc_short}} getting started](/docs/vpc?topic=vpc-getting-started)
* [{{site.data.keyword.vpc_short}} bare metal servers](/docs/vpc?topic=vpc-planning-for-bare-metal-servers)
* [{{site.data.keyword.vpc_short}} RYO VMware reference architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-ryo-arch-overview)
* [{{site.data.keyword.dl_full_notm}} overview](/docs/dl?topic=dl-get-started-with-ibm-cloud-dl)
* [{{site.data.keyword.tg_full_notm}} overview](/docs/transit-gateway?topic=transit-gateway-getting-started)
* [{{site.data.keyword.vpc_short}} VPN overview](/docs/vpc?topic=vpc-vpn-overview)
* [VPC IaaS endpoints](/docs/vpc?topic=vpc-service-endpoints-for-vpc#infrastructure-as-a-service-iaas-endpoints)
* [VMware on bare metal VPC tutorial](/docs/solution-tutorials?topic=solution-tutorials-vpc-bm-vmware)
