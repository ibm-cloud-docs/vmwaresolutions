---

copyright:

  years:  2016, 2017

lastupdated: "2017-08-22"

---

# Managing Zerto on IBM Cloud

After the Zerto on IBM® Cloud service is deployed into your instance, you can configure or update Zerto Virtual Replication, and deploy more Virtual Replication Appliances to newly added ESXi servers.

## Using your own certificate for Zerto

As a best practice, you should use your own SSL certificate for Zerto Virtual Manager (ZVM). After you deployed Zerto on IBM Cloud, replace the SSL certificate for ZVM with your own certificate by following the instructions at [How to use a CER SSL Certificate to Replace the Self-Signed Certificate for the ZVM, ZSSP, or ZCM](https://www.zerto.com/myzerto/knowledge-base/how-to-use-a-cer-ssl-certificate-to-replace-the-self-signed-certificate-for-the-zvm-zssp-or-zcm/){:new_window}.

## Managing the configuration of Zerto replications

To manage the configuration of Zerto replications (such as re-pairing Zerto instances or configuring virtual protection groups to replicate virtual machines), log in to the Zerto Virtual Replication console by using the vCenter credentials with administrator permissions.

## Updating Zerto Virtual Replication

To update Zerto Virtual Replication, log in to the Zerto Virtual Replication console.

## Deploying Zerto Virtual Replication Appliances to newly added ESXi servers

When you add or remove ESXi servers for your instance, Zerto Virtual Replication Appliances are automatically deployed or removed.

## Related links

* [Zerto on IBM Cloud components](addingzertodr.html)
* [zerto.com website](https://www.zerto.com){:new_window}
* [Zerto technical documentation](https://www.zerto.com/myzerto/technical-documentation/){:new_window}
* [Zerto disaster recovery](https://www.ibm.com/devops/method/content/architecture/virtCloudFoundationPlatform/zerto){:new_window}
