---

copyright:

  years:  2016, 2017

lastupdated: "2017-10-04"

---

# Zerto on IBM Cloud components

The Zerto on IBM® Cloud service provides replication and disaster recovery capabilities, which can be integrated into the deployment offerings to protect and recover data in your VMware virtual environment on IBM Cloud.

You can order an instance with the Zerto on IBM Cloud service included. For more information, see:

* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)

You can also deploy the Zerto on IBM Cloud service into your existing instances after initial deployment. For more information, see:

* [Ordering and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Ordering  and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)

## Components of the Zerto on IBM Cloud service

The following components are ordered and included in the Zerto on IBM Cloud service:

* A private portable subnet from IBM Bluemix Infrastructure (SoftLayer) for use by Zerto Virtual Replication Appliances
* A Microsoft Windows VSI (Virtual Service Instance) on which Zerto Virtual Replication is installed
* Zerto Virtual Replication Appliances to be deployed and configured into all ESXi servers

**Note**: Zerto Virtual Manager (ZVM) components will be deployed only into the default cluster and into additional clusters in the same pod in an IBM Cloud data center.

## Related links

* [About {{site.data.keyword.vmwaresolutions_short}}](../vmonic/prod_overview.html)
* [Managing Zerto on IBM Cloud](managingzertodr.html)
* [zerto.com website](https://www.zerto.com){:new_window}
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){:new_window}
