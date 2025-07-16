---

copyright:

  years:  2019, 2025

lastupdated: "2025-07-16"

keywords: openshift for vmware, request openshift for vmware, tech specs openshift vmware

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}

# {{site.data.keyword.redhat_openshift_notm}} for VMware overview
{: #ocp_overview}

{{site.data.content.rhos-deprecated-note}}

The {{site.data.keyword.redhat_openshift_full}} for VMware® service is an {{site.data.keyword.redhat_openshift_notm}} cluster by using an automated deployment of the VMware SDDC (Software Defined Data Center) architecture. The {{site.data.keyword.redhat_openshift_notm}} components are deployed as virtual machines (VMs) or appliances by using VMware NSX® software-defined networking.

The {{site.data.keyword.redhat_openshift_notm}} cluster consists of the following components:
* Three primary nodes
* Three worker nodes, all running {{site.data.keyword.redhat_full}} CoreOS
* Two VMware NSX® VMs
* A {{site.data.keyword.redhat_notm}} CoreOS template
* A bastion VM running CoreOS

For more information about the architecture, see [{{site.data.keyword.redhat_openshift_notm}} architecture](/docs/vmwaresolutions?topic=vmwaresolutions-vcs-openshift-redhat-arch).

## Technical specifications for {{site.data.keyword.redhat_openshift_notm}} for VMware
{: #ocp_overview-specs}

The following capacity requirements apply only if your {{site.data.keyword.vcf-auto-short}} instance is using vSAN™ storage. If you are using NFS, a new 2-TB NFS data store, which is dedicated to {{site.data.keyword.redhat_openshift_notm}}, is ordered.

The solution topology has the following specifications:
* 9 CPUs
* 120 GB RAM
* 1,170 GB storage

You must have a {{site.data.keyword.redhat_notm}} account and the pull secret key from your account. All {{site.data.keyword.redhat_notm}} accounts have an associated pull secret, which you can retrieve by [logging in to your {{site.data.keyword.redhat_notm}} account](https://console.redhat.com/openshift/install/vsphere/user-provisioned){: external}. You must purchase {{site.data.keyword.redhat_notm}} support entitlements through {{site.data.keyword.redhat_notm}} and, if needed, send information for all {{site.data.keyword.redhat_openshift_notm}} support issues to {{site.data.keyword.redhat_notm}}.

### Selecting the target cluster for installation
{: #ocp_overview-select-target-cluster}

During deployment and Day 2 operations, you are prompted for the cluster. You can install the service on the management cluster or any workload cluster.

### Bastion details
{: #ocp_overview-bastion}

The bastion VM contains an installation directory with the files and tools that are needed to manage and expand the {{site.data.keyword.redhat_openshift_notm}} cluster.   

You can log in to the bastion VM by using SSH and the credentials that are provided on the {{site.data.keyword.redhat_openshift_notm}} for VMware service details page. To run commands as the `root` user, use the command `sudo -i`.

In addition, most commands for {{site.data.keyword.redhat_openshift_notm}} management must be run from the installation directory. You can change to the installation directory with the command `cd /opt/ocpinstall`.

Any commands that require the `openshift-install`, `oc`, or `kubeadmin` tools must reference the files that are located in the installation directory by prefixing the command name with `./`. For example, `./oc whoami` instead of `oc whoami`.

The {{site.data.keyword.redhat_openshift_notm}}-related files from the bastion include an SSH key, an installation configuration file, command-line tools, and a `kubeconfig` file. The exact location of the installation configuration directory on the bastion is shown on the service details page.

### SSH key
{: #ocp_overview-bastion-ssh-key}

The SSH key on the bastion is installed on all {{site.data.keyword.redhat_openshift_notm}} cluster VMs, which allows SSH login from the bastion into any cluster VM. The full path to the SSH key is displayed on the service details page. For security purposes, it is highly recommended that you generate a new SSH key and update the cluster VMs with the new key. For more information, see [Changing the SSH key on the {{site.data.keyword.redhat_openshift_notm}} bastion VM](/docs/vmwaresolutions?topic=vmwaresolutions-ocp_managing#ocp_managing-change-ssh-key).

When you log in to a cluster VM from the bastion, you must connect as the `core` user as shown in the following example:

`root@bastion# ssh core@control-plane0`

### High availability
{: #ocp_overview-high-avail}

The {{site.data.keyword.redhat_openshift_notm}} VMs are deployed with DRS rules to ensure that they are on physically separate hosts. If a host must be replaced or redeployed, you must adjust the preconfigured DRS rules.

### Red Hat subscriptions
{: #ocp_overview-redhat-subscr}

The {{site.data.keyword.redhat_openshift_notm}} cluster is associated with the {{site.data.keyword.redhat_notm}} account from the pull secret that was provided during installation. To assign subscriptions or manage the cluster, you can view the cluster in the {{site.data.keyword.redhat_notm}} portal under **Systems** or **Clusters**.

## Assigning Red Hat subscriptions and entitlements to your {{site.data.keyword.redhat_openshift_notm}} cluster
{: #ocp_overview-assign-cluster}

1. Log in to your {{site.data.keyword.redhat_openshift_notm}} cluster web console.
2. Click **Home > Dashboards**. Make a note of the cluster ID that is displayed.
3. Click **Administration > Cluster Settings**.
4. Click **OpenShift Cluster Manager** under the channel, version, and update information.
   * Ensure that the cluster ID that is displayed matches the cluster ID from step 2.
   * If the cluster is not attached to a subscription, a message is displayed with a link that you can use to find this cluster in the {{site.data.keyword.redhat_notm}} customer portal. Use the link to assign the appropriate subscription and entitlement to the cluster.

   If you do not have enough subscriptions and entitlements, contact a {{site.data.keyword.redhat_notm}} Sales representative.

For more information, see [{{site.data.keyword.redhat_openshift_notm}} subscriptions information and known issues](https://access.redhat.com/articles/4105561){: external}.

## Configuring authentication
{: #ocp_overview-conf-auth}

By default, the {{site.data.keyword.redhat_openshift_notm}} installer creates a `kubeadmin` user that you can use to log in to the cluster. Create authentication backends or more users, as needed, for security purposes.

For more information about how to configure {{site.data.keyword.redhat_openshift_notm}} authentication, see the {{site.data.keyword.redhat_openshift_notm}} documentation.

## Updating your {{site.data.keyword.redhat_openshift_notm}} cluster
{: #ocp_overview-update-clus}

For more information about updating {{site.data.keyword.redhat_openshift_notm}}, see the {{site.data.keyword.redhat_openshift_notm}} documentation.
