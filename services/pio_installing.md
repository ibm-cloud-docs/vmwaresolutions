---

copyright:

  years:  2019, 2022

lastupdated: "2022-08-26"

keywords: primary io hdm, hdm install, download hdm

subcollection: vmwaresolutions


---

{{site.data.keyword.attribute-definition-list}}


# Managing PrimaryIO HDM
{: #pio_installing}

## Downloading HDM
{: #pio_installing-hdm-download}

To access the PrimaryIO Hybrid Cloud Data Management (HDM) software, go to [Hybrid Cloud Data Management](https://www.primaryio.com/hybrid-cloud-data-management/){: external}.

## Installing PrimaryIO HDM
{: #pio_installing-hdm-install}

To install HDM on the hybrid infrastructure, complete the following steps:
* Deploy PrimaryIO Appliance (henceforth called PIO Appliance) on-premises
* Add on-premises vCenter Server to PIO Appliance
* Install HDM components on premises
* Configure on-premises HDM components
* Configure and Add Cloud Endpoint

### Deploying and installing PrimaryIO HDM on-premises
{: #pio_installing-deploy}

The first HDM component to be deployed is the PIO Appliance. This appliance provides interfaces to add an on-premises VMware vCenter Server® and to register the HDM plug-in with it. After successful registration of the HDM plug-in, you can choose one of the clusters in the on-premises data center and install the following HDM components on it:
* PrimaryIO On-premises Manager
* PrimaryIO ESX Manager

### Configuring PrimaryIO HDM on-premises
{: #pio_installing-config}

Only the on-premises components are deployed (the cloud components are not needed yet). The components are in place for HDM to monitor and analyze virtual machines, make recommendations, and gain insights into the workload that runs in the data center. For more information, see the [HDM documentation](https://docs.primaryio.com){: external}.

### Adding an IBM Cloud endpoint
{: #pio_installing-add}

After successful completion of the previous steps, you can add an {{site.data.keyword.cloud}} endpoint to HDM. The following components are installed in the selected cluster in the cloud data center.
* PrimaryIO On-cloud Manager
* PrimaryIO Cloud Cache (one per each VMware® ESXi™ node in cloud cluster)

After the cloud endpoint is successfully configured, a network connection between {{site.data.keyword.cloud_notm}} and the on-premises cluster is established.

For more information, see the [HDM documentation](https://docs.primaryio.com){: external}.

## Troubleshooting PrimaryIO HDM
{: #pio_installing-troubleshooting}

For more information about troubleshooting installation-related issues, see the [HDM documentation](https://docs.primaryio.com){: external}.

## Uninstalling PrimaryIO HDM
{: #pio_installing-uninstallation}

To uninstall HDM from the hybrid infrastructure, complete the installation steps in reverse order:
* Removing the {{site.data.keyword.cloud_notm}} Endpoint
* Uninstalling on-premises components
* Uninstalling the HDM IO filter
* Unregistering the HDM vCenter Server plug-in
* Deleting the PrimaryIO appliance

For more information, see the [HDM documentation](https://docs.primaryio.com){: external}.

## Related links
{: #pio_installing-related}

* [Contacting IBM Support](/docs/vmwaresolutions?topic=vmwaresolutions-trbl_support)
