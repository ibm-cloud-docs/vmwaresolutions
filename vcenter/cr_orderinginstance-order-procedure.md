---

copyright:

  years:  2022

lastupdated: "2022-10-27"

keywords: cyber recovery order procedure, order procedure cyber recovery, cyber recovery order instance, order cyber recovery, order cyber recovery instance

subcollection: vmwaresolutions

---

{{site.data.keyword.attribute-definition-list}}

# Procedure to order a Cyber Recovery instance
{: #cr_orderinginstance-order-procedure}

1. In the {{site.data.keyword.vmwaresolutions_full}} console, click the **Cyber Recovery** card in the Industry regulated offerings section.

2. On the **Cyber Recovery** page, review and complete the items in the *Before you begin* topic.

3. Under the **General Information** section, select the instance configuration.
     * If you want to create a new configuration, select **New configuration**.
     * If you want to update a saved configuration or create a new configuration based on a saved one, select a saved configuration.

4. A generic **Instance name** is set by default. You can change it.

5. The default name for the resource group is **Default**. Consider how you’d like to organize the resources in your account. You cannot change the resource group after the Cyber Recovery environment is created.

      For more information, see [Managing resource group](/docs/account?topic=account-rgs&interface=ui).

6. Select the instance type.
     * Click **Primary instance** to deploy a single instance in the environment or to deploy the first instance in a multisite topology.
     * Click **Secondary instance** to connect the instance with an existing (primary) instance in the environment for high availability. Select the primary instance that you want the secondary instance to be connected with, then enter the Cyber Recovery Administrator password for the primary instance.

7. Under **Licensing**, complete the license settings for the listed components.
     * To use IBM-provided licenses, ensure that the option **Include with purchase** is selected.
     * To use your own licenses, click **I will provide**, and enter the license key.

8. In the **Consolidated cluster** section, the default cluster name is set to the value **_instance name_-consolidated**. You can change it. 

     For information about the requirements for the name, see [Cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-consolidwkld#cr_orderinginstance-consolidwkld-cluster-name).

9. For the data center location, you must select the **Geography**, **Data Center**, and **Pod** to host the clusters. For more information, see [Data center location](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-consolidwkld#cr_orderinginstance-consolidwkld-dc-location).

10. For the CPU generation, select either **Cascade Lake** or **SAP-certified**. Cascade Lake is the default.

11. Select the **CPU model** from the list. Each CPU model shows the CPU generation and the values for the number of cores and GHz.

12. Select **RAM**. The default is 768 GB. Use the dropdown menu to display all the possible values and select one.

13. Select the number of bare metal servers. The default is 3. You can select 3 - 20 bare metal servers.

14. If you want to use **vSAN™ storage**, select the corresponding option.
    1. Select the size for and number of **vSAN capacity disks**.
    2. Select the size for and number of **vSAN cache disks**.
    3. Select the box if you want to **Enable vSAN deduplication and compression**.
    4. For the **vSAN license**, select if you want to include and pay for a vSAN license with your order or you will provide your own license.

    If you will pay for a license, use the dropdown menu to display all the possible license values and select one.

15. If you want to use **NFS storage**, select the corresponding option.
    1. To add and configure file shares individually, select **Configure shares individually**. You must select at least one file share. Then, click **Add shared storage** and select the **Size (GB)** and **Performance** for each file share.
    2. To add and configure the same settings to all file shares, specify the **Number of shares** and then, select the **Size (GB)** and **Performance** for all the shares.

16. Select the **Networking type**. The choices are **Public and private network** or **Private network only**.

17. Select the **Uplink speed**. The 25 Gb option is available only for Cascade Lake servers and specific data centers.

18. **VLANS**. To order new public and private VLANs, select **Order new VLANs**. A new public VLAN and two private VLANs are provisioned.
 
      To reuse existing public and private VLANs, if they are available, select **Select existing VLANs**. Specify the VLANs and the subnets.

      For new orders, you can only select **Order new VLANs**.

      If the consolidated or management cluster and the workload clusters are in the same location, you cannot use existing VLANs. Instead, the workload clusters reuse the VLANs from the management cluster.

19. If you want a workload cluster, select **Include a separate, additional workload cluster**. Specify the settings for the cluster.

      1. You can keep the default **Cluster name** of the workload cluster or you can change it.
      2. For the **Data center location**, you must select the **Geography**, **Data Center**, and **Pod** to host the clusters. For more information, see [Data center location](/docs/vmwaresolutions?topic=vmwaresolutions-cr_orderinginstance-consolidwkld#cr_orderinginstance-consolidwkld-dc-location).
      3. For **CPU generation**, select either **Cascade Lake** or **SAP-certified**. Cascade Lake is the default.
      4. Select the **CPU model** from the list. Each CPU model shows the CPU generation and the values for the number of cores and GHz.
      5. Select **RAM**. The default is 768 GB. Use the dropdown menu to display all the possible values and select one.
      6. Select the **number of bare metal servers**. The default is 2. You can select 2 - 20 bare metal servers.

20. If you want to use **vSAN™ storage**, select the corresponding option.
     1. Select the size for and number of **vSAN capacity disks**.
     2. Select the size for and number of **vSAN cache disks**.
     3. Select the box if you want to **Enable vSAN deduplication and compression**.
     4. For the **vSAN license**, select if you want to include and pay for a vSAN license with your order or you will provide your own license. 
     
     If you will pay for a license, use the dropdown menu to display all the possible license values and select one.

21. If you want to use **NFS storage**, select the corresponding option.
     1. To add and configure file shares individually, select **Configure shares individually**. You must select at least one file share. Then, click **Add shared storage** and select the **Size (GB)** and **Performance** for each file share.
     2. To add and configure the same settings to all file shares, specify the **Number of shares** and then select the **Size (GB)** and **Performance** for all the shares.

22. Select the **Networking type**. The choices are **Public and private network** or **Private network only**.

23. Select the **Uplink speed**. The 25 Gb option is available only for Cascade Lake servers and specific data centers.

24. **VLANS**. To order new public and private VLANs, select **Order new VLANs**. A new public VLAN and two private VLANs are provisioned.
 
      To reuse existing public and private VLANs, if they are available, select **Select existing VLANs**. Specify the VLANs and the subnets.

      For new orders, you can only select **Order new VLANs**.

      If the consolidated or management cluster and the workload clusters are in the same location, you cannot use existing VLANs. Instead, the workload clusters reuse the VLANs from the management cluster.

25. Choose the firewall appliance for your instance and follow the steps, depending on your selection:
     1. For **Edge services cluster with Juniper vSRX**, **Edge services cluster with FortiGate Virtual Appliance**, and **Bring your own gateway appliance**, specify the edge services [cluster name](/docs/vmwaresolutions?topic=vmwaresolutions-cr-orderinginstance-edge#cr-orderinginstance-edge-cluster-name), the CPU model, the RAM size, the uplink speed, and the networking type.                 
     2. For **Edge services cluster with Juniper vSRX** and **Edge services cluster with FortiGate Virtual Appliance**, you must also specify the corresponding service settings in a later step.
     3. For **FortiGate Security Appliance**, you must order the **FortiGate Security Appliance 10 Gbps** service from the [IBM Cloud catalog](https://cloud.ibm.com/catalog/infrastructure/fortigate-security-appliance-10gb). Confirm that you ordered the service and continue with the following steps.

26. Complete the information for the **Edge services cluster**.
    1. You can keep the default **Cluster name** of the edge services cluster or you can change it.
    2. For **Compute capacity**, the values are:
       - Clusters hosts: 2
       - Storage: 2 * 3.8 TB SSD
    3. Select the **CPU model** from the list. Each CPU model shows the values for the CPU generation, the number of cores, and GHz.
    4. Select **RAM**. Use the dropdown menu to display all the possible values and select one. The values are 64 GB - 1.5 TB.
    5. **Uplink speed**. The value that is selected is 10 Gb. A speed of 25 Gb is available only for Cascade Lake servers and specific data centers. For more information, see [Uplink speed](/docs/vmwaresolutions?topic=vmwaresolutions-vc_orderinginstance-edge-services-cluster#vc_orderinginstance-edge-cluster-uplink).
    6. **Networking type**. The choices are **Public and private network** or **Private network only**. The default is Private network only.
    
27. Complete the information for the **Network interface**.
     1. Enter the **Hostname prefix** and the root **Domain name** for the instance you are creating.
     2. Specify the **DNS configuration**.
     3. **Network diagram**. You can customize the hostnames prefix individually by selecting **Configure hostnames individually**.

28. The **Add-on services** section lists the various services you can order for your Cyber Recovery instance.
     * The **Included services** category lists the services that are included in your Cyber Recovery order.
     * The **Recommended services** category lists the services that IBM recommends to fully leverage your resources.
     * You can open each of the remaining categories to select different services for business continuity and migration as well as management tools.

    For more information, see [Add-on services](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addon-services).

## Related Links
{: #cr_orderinginstance-order-procedure-related-links}

* [Adding clusters to Cyber Recovery instances](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingclusters)
* [Expanding and contracting capacity](/docs/vmwaresolutions?topic=vmwaresolutions-cr_addingservers)
