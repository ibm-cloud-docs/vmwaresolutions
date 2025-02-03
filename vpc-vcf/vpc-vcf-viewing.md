---

copyright:

  years: 2023, 2025

lastupdated: "2025-02-03"

keywords: view vmware cloud foundation instance, vmware cloud foundation instance, view instance, view vmware cloud edition instance

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Viewing {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-viewing}

View the summary and detailed information of the {{site.data.keyword.vcf-vpc}} instances that are provisioned in your account.

## Procedure to view a summary of {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-viewing-summary}

1. From the VMware Solutions console, click **Resources > {{site.data.keyword.vcf-vpc-short}}** from the left navigation pane.
2. In the **{{site.data.keyword.vcf-vpc}}** table, review the name, location, creation time, and status of the provisioned instances.

## Procedure to view details for {{site.data.keyword.vcf-vpc-short}} instances
{: #vpc-vcf-viewing-details}

1. In the **{{site.data.keyword.vcf-vpc}}** table, click an instance name.
2. On the **Summary** tab, review the general information of the instance: the deployment infrastructure type, the resource group in which the resources are deployed, the {{site.data.keyword.vpc_full}} ({{site.data.keyword.vpc_short}}) region, and the zone where the instance is deployed.

3. Click the **Infrastructure** tab:
   1. In the **Domains** table, review the domain name and type, the number of clusters, the NSX-T Edge cluster uplinks and nodes, and the public floating IP addresses in the domain.
   2. Click the table row to view the detailed information of the selected domain.
      * On the cluster details, view the number of hosts in this cluster.
      * Click the host profile to view the detailed information of the profile.
      * Click the storage type to view the disk information.
      * Click the subnets to view the {{site.data.keyword.vpc_short}} subnets created for this cluster. On the subnets table, click a subnet name to go to the subnet detail page.
      * On the hosts table, view the bare metal server name, the root user password, and the creation time. To go to the bare metal server details page on the {{site.data.keyword.vpc_short}} console, click the bare metal server name.

4. On the **Access Information** tab, view the default username and password for the {{site.data.keyword.vcf-vpc-short}} instance.
   * In the **Management domain** section, view the hostname, FQDN, and IP addresses for vCenter Server, VMware NSX-T Data Center, SDDC Manager, and VMware Aria Suite Lifecycle Manager. For **Backup server**, view the name, IP address, SSH key, and server OS. You can view or copy the password by clicking the icons.
   * In the **Windows jump server** section, you can view the public and private IP addresses and admin user password of the Windows jump server. If you did not select to create the jump server, the section is not displayed.

## Related links
{: #vpc-vcf-viewing-links}

* [{{site.data.keyword.vcf-vpc-short}} overview](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-ovw)
* [Ordering {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-ordering)
* [Deleting {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-deleting)
* [Getting help and support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
