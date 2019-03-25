---

copyright:

  years:  2016

lastupdated: "2016-11-04"

subcollection: vmwaresolutions


---

# Release notes for V1.1
{: #relnotes_v11}

This release includes new features, usability enhancements, and bug fixes. For a list of fixed issues in different releases, known issues with the product, and tips to use {{site.data.keyword.vmwaresolutions_full}}, see [{{site.data.keyword.vmwaresolutions_short}} dW Answers](https://developer.ibm.com/answers/topics/cloudvmw/){:new_window}.

## VLAN spanning requirement
{: #relnotes_v11-vlan-spanning}

If you are using a classic (non-VRF) SoftLayer® account, VLAN spanning must be enabled. If VLAN spanning is not enabled for classic accounts, the various components of the VMware virtualization environment might not be able to communicate with each other. To enable VLAN spanning in your SoftLayer account, see [Enable or Disable VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning){:new_window}.

## Email settings and notifications
{: #relnotes_v11-email}

You can configure email notifications on the **Settings** page. By default, the setting is enabled, which means that you receive a notification by email for any newly ordered instance, when that instance is provisioned and is ready to use. You can also disable email notifications on the **Settings** page. For more information, see [User accounts and settings](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount).

## Detailed status information
{: #relnotes_v11-status-info}

Detailed status information is now available for Cloud Foundation instances. When you click an instance name, the status information that is displayed gives more details about the deployment progress. If an error occurs, messages are displayed to help you with the issue.
