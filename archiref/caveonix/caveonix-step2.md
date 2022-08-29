---

copyright:

  years:  2016, 2022

lastupdated: "2022-08-26"

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# Step 2 - Virtual machine deployment
{: #caveonix-step2}

The {{site.data.keyword.vmwaresolutions_full}} automation requests an additional portable private IP subnet and the “all-in-one” virtual machine to be configured with an IP address from this subnet.

Therefore, the Caveonix RiskForesight™ components can complete the following operations:
* Connect to vCenter and NSX Manager through the BCR.
* Connect to Remote Collectors, either on VXLANs or hosted off-premise.
* Allow the client to manage the IP address space when you scale up.
