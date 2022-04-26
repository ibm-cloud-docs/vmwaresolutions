---

copyright:

  years:  2019, 2022

lastupdated: "2022-03-25"

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# VMware Solutions SDDC architecture
{: #vcs-openshift-arch}

## Common services components
{: #vcs-openshift-arch-common-services}

Common services provide the services that are used by other services in the cloud management platform. Common services include identity and access services, domain name services, and NTP services.

![Common services](../../images/openshift-commonservices.svg){: caption="Figure 1. Common services" caption-side="bottom"}

### Identity and access services
{: #vcs-openshift-arch-identity}

As part of the VMware® vCenter Server® automation, a Microsoft® Active Directory™ (AD) is employed for Identity Management. A single AD virtual server instance (VSI) is deployed. The vCenter is configured to use AD authentication and you can configure {{site.data.keyword.redhat_openshift_full}} for LDAP authentication.

### Domain Name Services
{: #vcs-openshift-arch-dns}

The vCenter Server deployment uses the deployed AD VSIs as DNS servers for the instance. All deployed components, such as, vCenter, PSC, NSX®, and ESXi™ hosts, are configured to point to AD as their default DNS.

### NTP services
{: #vcs-openshift-arch-ntp}

The vCenter Server deployment uses the {{site.data.keyword.cloud}} infrastructure NTP servers. All deployed components are configured to use these NTP servers. Having all components within the design that uses the same NTP servers is critical for certificates and AD authentication to function correctly.

## Networking
{: #vcs-openshift-arch-networking}

### NSX-V networking
{: #vcs-openshift-arch-nsx-v}

NSX-V is designed so that a single NSX-V manager platform is tied to a single vCenter Server instance. It provides networking services to applications that run within a vSphere environment.

The NSX-V networking that is included in the vCenter Server deployment is used to deploy {{site.data.keyword.redhat_openshift_notm}} into a VXLAN overlay network. The deployment uses NSX functions to provide load balancing, Network Address Translation, and DHCP services.

{{site.data.keyword.redhat_openshift_notm}} is deployed with the default Calico networking stack for Kubernetes, which provides network isolation within your cluster.

![{{site.data.keyword.redhat_openshift_notm}} with NSX networking](../../images/openshift-nsxv-networking.svg){: caption="Figure 2. OpenShift with NSX networking" caption-side="bottom"}

**Next topic:** [{{site.data.keyword.cloud_notm}} networking and infrastructure](/docs/vmwaresolutions?topic=vmwaresolutions-vcs-openshift-sddc-infra)

## Related links
{: #vcs-openshift-arch-related}

* [VMware vCenter Server and {{site.data.keyword.redhat_openshift_notm}} architecture overview](/docs/vmwaresolutions?topic=vmwaresolutions-vcs-openshift-intro)
* [System context for vCenter Server and {{site.data.keyword.redhat_openshift_notm}} architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vcs-openshift-syscontext)
* [{{site.data.keyword.redhat_openshift_notm}} architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vcs-openshift-redhat-arch)
* [Storage options on {{site.data.keyword.cloud_notm}} and {{site.data.keyword.redhat_openshift_notm}}](/docs/vmwaresolutions?topic=vmwaresolutions-vcs-openshift-storage)
