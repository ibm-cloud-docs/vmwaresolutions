---

copyright:

  years:  2016, 2017

lastupdated: "2017-06-23"

---

# Deployment process of Zerto disaster recovery

The Zerto disaster recovery service provides replication and disaster recovery capabilities, which can be integrated into the deployment offerings to protect and recover data in your VMware virtual environment on IBM® Cloud.

You can order an instance with Zerto disaster recovery included. For more information, see:

* [Ordering Cloud Foundation instances](../sddc/sd_orderinginstance.html)
* [Ordering vCenter Server instances](../vcenter/vc_orderinginstance.html)

You can also deploy the Zerto disaster recovery service into your existing instances after initial deployment. For more information, see:

* [Ordering, viewing, and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Ordering, viewing, and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)

The deployment of Zerto disaster recovery is automated. Whether you order an instance with Zerto disaster recovery included or you deploy the service later into your instance, the following steps are completed for the successful deployment of the service into your instance.

## Procedure

1. Order a private portable subnet from SoftLayer® for use by Zerto Virtual Replication Appliances.
2. Deploy and configure a Windows VSI (Virtual Service Instance), and then install Zerto Virtual Replication on this VSI.
3. Deploy and configure Zerto Virtual Replication Appliances into all ESXi servers.
4. Add the charges of the Zerto disaster recovery service to your IBM Bluemix® billing statement.

## Results

After the deployment of the service is completed, the service is displayed on the **Installed Services** tab with the status of **Installed**. You receive an email confirming that the service was deployed.

## Related links

* [Product overview](prod_overview.html)
* [Cloud Foundation instances](../sddc/sd_cloudfoundationoverview.html)
* [vCenter Server instances](../vcenter/vc_vcenterserveroverview.html)
* [Zerto disaster recovery removal](removingzertodr.html)
* [zerto.com website](https://www.zerto.com){:new_window}
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){:new_window}
