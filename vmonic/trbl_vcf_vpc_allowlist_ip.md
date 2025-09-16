---

copyright:

  years:  2025

lastupdated: "2025-09-15"

keywords: troubleshooting, vcf for vpc, authorization header, authorization error

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Why is my {{site.data.keyword.vcf-vpc-short}} order failing with "The user has configured IP address restriction for login"?
{: #trbl_vcf_vpc_allowlist_ip}
{: troubleshoot}

When you attempt to deploy a new {{site.data.keyword.vcf-vpc}} instance, you are getting an error message.
{: tsSymptoms}

`An error has occurred when sending the request to create an instance. The user has configured IP address restriction for login. None of the given IP addresses is contained in the list of allowed IP addresses.`

Your {{site.data.keyword.vcf-vpc-short}} order might fail due to access restrictions that are enforced in your account settings.
{: tsCauses}

To investigate and fix the problem, complete the following steps:
{: tsResolve}

1. Ensure that the IP addresses used by Schematics are added to the list of allowed IP addresses. For more information, see [Firewall access - allowed IP addresses](/docs/schematics?topic=schematics-allowed-ipaddresses).
2. Add the following gateway IP addresses of the VMware gateway to the list of allowed IP addresses: `52.117.5.235`, `52.116.203.32`, `52.116.129.199,169.62.22.51`, `169.59.166.18`, and `150.239.86.7`.
3. Add the IP address `10.0.0.0/8` of the {{site.data.keyword.cloud}} private network range to the list of allowed IP addresses.

## Related links
{: #trbl_vcf_vpc_allowlist_ip-links}

* [Requirements for {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-order-req)
* [Ordering {{site.data.keyword.vcf-vpc-short}} instances](/docs/vmwaresolutions?topic=vmwaresolutions-vpc-vcf-ordering)
