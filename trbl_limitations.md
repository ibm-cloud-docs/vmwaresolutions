---

copyright:

  years:  2016, 2017

lastupdated: "2017-05-11"

---

# Limitations and considerations

Review the following considerations and limitations when you work with {{site.data.keyword.vmwaresolutions_full}}.

## Disabling Windows automatic installation of updates

You must disable Windows automatic installation of updates because the automatic updates and system restart might interrupt the ongoing Active Directory (AD) server configuration and other backup jobs. To apply Windows updates, install the updates manually.

## Considerations when choosing a root domain name for Cloud Foundation instances

When choosing a domain name during the deployment of a primary or secondary Cloud Foundation instance, you need to verify that the `sddcmanager.<subdomain>` host name does not resolve to an external domain by using the `ping` or `nslookup` commands.

The structure of the Cloud Foundation instance subdomain is `<VCF instance name>.<domain name>`. For example, if your `<domain name>` is `test.local`, and the Cloud Foundation instance name is `mytest`, then the `sddcmanager.mytest.test.local` host name should not resolve to an IP address before deploying the Cloud Foundation instance. Otherwise, the instance deployment might fail.
