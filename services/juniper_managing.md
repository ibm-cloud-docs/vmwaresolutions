---

copyright:

  years:  2020, 2022

lastupdated: "2022-11-16"

keywords: Juniper vSRX, manage Juniper vSRX, Juniper vSRX console

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Managing Juniper vSRX
{: #juniper-managing}

To manage the Juniper® vSRX service, use one of the following ways:
* Log in to the J-Web Web Client by using the credentials that you can find on the Juniper vSRX service details page.
* Access the console through an SSH connection by using the credentials that you can find on the Juniper vSRX service details page.

For more information, see [Ordering services for vCenter Server instances](/docs/vmwaresolutions?topic=vmwaresolutions-vc_addingservices).

## Juniper vSRX security and ease of use features
{: #juniper-managing-security-enhance}

Juniper vSRX provides various features for security and ease of use on VMware® vCenter Server®. The following are some considerations:

* Any Juniper vSRX that is deployed with public access comes with its public interfaces deactivated. The deactivation ensures that the vSRX is not made available to the public internet before users are ready.
* The default deny policy is set to permit, so you can identify any necessary flows before you lock down the vSRX traffic.
* It is recommended that you change the default credentials that {{site.data.keyword.IBM}} created in the service details page for Juniper vSRX: the root and admin passwords.
* On edge services cluster installations, protectable VLANs are associated, but not routed, with the edge gateway.

## Related links
{: #juniper-managing-related-links}

* [Juniper vSRX overview](/docs/vmwaresolutions?topic=vmwaresolutions-juniper-overview)
* [General FAQ about VMware Solutions](/docs/vmwaresolutions?topic=vmwaresolutions-faq-vmwaresolutions)
* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
* [Juniper vSRX Virtual Firewall](https://www.juniper.net/us/en/products-services/security/srx-series/vsrx/){: external}
* [Juniper vSRX Documentation](https://www.juniper.net/documentation/product/en_US/vsrx){: external}
