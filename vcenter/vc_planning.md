---

copyright:

  years:  2016, 2022

lastupdated: "2022-05-18"

keywords: planning vCenter Server, data center, vCenter Server data centers

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Planning for vCenter Server instances
{: #vc_planning}

Plan your instance based on the {{site.data.keyword.cloud}} data center location, your workload capacity requirements, and add-on services requirements. Review the following requirements before you order your VMware vCenter Server® instance.

* New deployments of vCenter Server instances with VMware vSphere® 6.5 or 6.7 are not supported.
* New deployments of vCenter Server multizone instances are not supported.

## IBM Cloud account requirements
{: #vc_planning-account-req}

The {{site.data.keyword.cloud_notm}} account that you are using must meet certain requirements. For more information, see [Requirements for the {{site.data.keyword.cloud_notm}} account](/docs/vmwaresolutions?topic=vmwaresolutions-cloud-infra-acct-req).

## IBM Cloud data center availability
{: #vc_planning-dc-availability}

The vCenter Server deployment has strict requirements on the physical infrastructure. Therefore, you can deploy instances only in {{site.data.keyword.cloud_notm}} data centers that meet the requirements. The following {{site.data.keyword.cloud_notm}} data centers are available for vCenter Server deployment.

| Geography | Data center | Pod | Server options for NSX-T[^nsx-t-7] | Server options for NSX-V[^nsx-v] |
|:----------------------|:-------|:---------------|:-----------|:------|
| Asia-Pacific| CHE01 | 01 | Skylake, Cascade Lake | Skylake, Cascade Lake, SAP-certified[^sap-che01] |
| Asia-Pacific | HKG02 | 02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | OSA21 | 01 | Cascade Lake, SAP-certified | Cascade Lake, SAP-certified |
| Asia-Pacific | OSA22 | 01 | Cascade Lake, SAP-certified | Cascade Lake, SAP-certified |
| Asia-Pacific | OSA23 | 01 | Cascade Lake, SAP-certified | Cascade Lake, SAP-certified |
| Asia-Pacific | SEO01 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SNG01| 02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SYD01 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SYD04 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | SYD05 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | TOK02 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | TOK04 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Asia-Pacific | TOK05 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | AMS03 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | FRA02 | 01-03 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | FRA04 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | FRA05 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | LON02 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake |
| Europe | LON04 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | LON05 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | LON06 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| Europe | MIL01 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified[^sap-mil01] |
| Europe | PAR01 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified[^sap-par01] |
| NA East | MON01 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified[^sap-mon01] |
| NA East | TOR01 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA East | TOR04 | 01 | Cascade Lake | Cascade Lake |
| NA East | TOR05 | 01 | Cascade Lake | Cascade Lake |
| NA East | WDC04 | 01-05 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA East | WDC06 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA East | WDC07 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA South | DAL09 | 01-06 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA South | DAL10 | 01-04 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA South | DAL12 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA South | DAL13 | 01-03 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| NA South | MEX01 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified[^sap-mex01] |
| NA West | SJC 03 | 01-02 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake |
| NA West | SJC 04 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake |
| South America | SAO 01 | 01 | Skylake, Cascade Lake, SAP-certified | Skylake, Cascade Lake, SAP-certified |
| South America | SAO 04 | 01 | Cascade Lake, SAP-certified | Cascade Lake, SAP-certified |
| South America | SAO 05 | 01 | Cascade Lake, SAP-certified | Cascade Lake, SAP-certified |
{: caption="Table 1. Available {{site.data.keyword.cloud_notm}} data centers for vCenter Server instances" caption-side="bottom"}

[^nsx-t-7]: Skylake is not supported for vSphere 7 instances

[^nsx-v]: Existing NSX-V instances only

[^sap-che01]: Existing vSphere 6.5 clusters only

[^sap-mex01]: Existing vSphere 6.5 clusters only

[^sap-mil01]: Existing vSphere 6.5 clusters only

[^sap-mon01]: Existing vSphere 6.5 clusters only

[^sap-par01]: Existing vSphere 6.5 clusters only

## Backup of management components
{: #vc_planning-backup-mgmt-components}

You are responsible for maintaining and ensuring the availability of all instance components. It is recommended that you plan for backup or high availability of all management components. For more information, see [Backing up components](/docs/vmwaresolutions?topic=vmwaresolutions-solution_backingup).

## Services for vCenter Server instances
{: #vc_planning-addon-services}

You can order services for your instance based on your needs, for example, disaster recovery. For more information, see [Ordering services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices).

Services support varies between vCenter Server with NSX-T and vCenter Server with NSX-V instances.
{: important}

### Planning for VMware HCX
{: #vc_planning-addon-services-hcx}

The VMware HCX™ service can seamlessly extend the networks of on-premises data centers into {{site.data.keyword.cloud_notm}}. This process, which allows virtual machines (VMs) to be moved to and from the {{site.data.keyword.cloud_notm}} without any conversion or change.

When you deploy this service, complete the following settings:
* Specify the **HCX Interconnect type** by selecting one of the following options:
   * **Public network**: HCX creates an encrypted connection between sites over the public network.
   * **Private network**: HCX creates an encrypted connection between sites over the private network.
* Specify the **Public endpoint certificate type**. If you select **CA Certificate**, configure the following settings:
   * **Certificate Contents**: Enter the contents of the CA certificate.
   * **Private Key**: Enter the private key of the CA certificate.
   * (Optional) **Password**: Enter the password for the private key if it is encrypted.
   * (Optional) **Reenter Password**: Enter the password for the private key again.
   * (Optional) **Hostname**: Enter the hostname to be mapped to the common name (CN) of the CA certificate. HCX requires the CA certificate to be in a format that is accepted by NSX Edge. For more information about NSX Edge certificate formats, see [Importing SSL Certificates](https://docs.vmware.com/en/VMware-NSX-Data-Center-for-vSphere/6.3/com.vmware.nsx.admin.doc/GUID-19D3A4FD-DF17-43A3-9343-25EE28273BC6.html){: external}.

## Capacity considerations
{: #vc_planning-capacity-considerations}

For more information about capacity considerations, see [Scaling capacity](/docs/vmwaresolutions?topic=vmwaresolutions-solution_scaling).

## Related links
{: #vc_planning-related}

* [vCenter Server overview](/docs/vmwaresolutions?topic=vmwaresolutions-vc_vcenterserveroverview)
* [Ordering vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-req)
* [Expanding and contracting capacity for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservers)
* [Ordering services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices)
