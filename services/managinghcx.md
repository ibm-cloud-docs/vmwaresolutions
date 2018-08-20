---

copyright:

  years:  2016, 2018

lastupdated: "2018-07-19"

---

# Managing VMware HCX on IBM Cloud

## Accessing the HCX on IBM Cloud management consoles

To manage the HCX on {{site.data.keyword.cloud}} service, you must access the HCX Cloud Console or the HCX Manager Admin Console:
1. Use the {{site.data.keyword.cloud_notm}} infrastructure VPN or a jump server to allow access to the IP address of the HCX Manager virtual appliance (HCX Manager). You can find the IP address on the HCX on {{site.data.keyword.cloud_notm}} service details page in the {{site.data.keyword.vmwaresolutions_short}} console.
2. To access the HCX Cloud Console, click **View HCX Cloud Console** on the HCX on {{site.data.keyword.cloud_notm}} service details page, and then log in by using the vCenter Server credentials.
3. To access the HCX Manager Admin Console, click **View HCX Manager Admin Console** on the HCX on {{site.data.keyword.cloud_notm}} service details page, and then log in by using the HCX Manager credentials listed on the same service details page.

For more information, see [Ordering, viewing, and removing services for vCenter Server with Hybridity Bundle instances](../vcenter/vc_hybrid_addingremovingservices.html).

## Applying updates to HCX on IBM Cloud

HCX on {{site.data.keyword.cloud_notm}} is deployed with the latest tested build of VMware Hybrid Cloud Extension technology. VMware ships updates to these builds regularly, which include important fixes and new features. These builds are pushed to HCX on {{site.data.keyword.cloud}} installations automatically, including on-premises HCX installations.

To apply any maintenance fixes pushed to your environment, you must use the HCX Manager Admin Console in your on-premises data center and your vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle instance.

If you do not see a build update that you are expecting, if you have problems with HCX, or if want to have the latest HCX build pushed to your system immediately, open a support ticket by following the steps in [Contacting IBM Support](../vmonic/trbl_support.html).

### Related links

* [HCX on {{site.data.keyword.cloud_notm}} overview](hcx_considerations.html)
* [Glossary of HCX terms](hcx_glossary.html)
* [VMware Hybrid Cloud Extension overview](https://cloud.vmware.com/vmware-hcx)
* [VMware Hybrid Cloud Extension documentation](https://hcx.vmware.com/#vm-documentation)
