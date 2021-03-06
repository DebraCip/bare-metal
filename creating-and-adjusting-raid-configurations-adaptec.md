---
copyright:
  years: 1994, 2017
lastupdated: "2017-08-29"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Creating and adjusting Adaptec RAID configurations

The Adaptec RAID Bios allows you to configure and manage your RAID setup. Use this bios if you are using our [No OS](introduction-no-os.html) option and want to set up a specific drive configuration.

## Accessing the IPMI device to interact with the RAID Bios

Regardless of whether your machine has an Adaptec controller or an LSI controller you will need to access the server using IPMI in order to interact with the RAID Bios. In order to interact with IPMI you will first need to connect to the Adaptec {{site.data.keyword.IBM&reg; Cloud}} VPN.
1. Log in to the VPN through either [SSL](https://console.bluemix.net/docs/services/vpn/vpn_customergateway.html) or PPTP. Refer to the [VPN topic page](/infrastructure/vpn/index.html).
* Access the Device List in the [Customer Portal](https://control.softlayer.com/). Refer to [Access the Device List](https://console.bluemix.net/docs/vsi/vsi_index.html#getting-started-with-virtual-servers).
* Click on the device you wish to access.
* Select the Remote Mgmt tab to find your servers IPMI access details.
* Put the IP of your IPMI device in to the browser and log in.
* To start interacting with the remote console click Remote Control > Console Redirection.

## Creating RAID Arrays

During the boot process hit Ctrl+A to access the Raid BIOS.

To start configuring your RAID go in to Logical Device Configuration (first option). This scans the topology of your drives and displays a menu where you can manage arrays, create arrays and complete other drive administration tasks.

The following example shows how to create an array. You are presented with a list of available drives to use in creating your RAID Array.

1. To select the drives press the SPACE bar to populatie the *Selected Drives* box.
* After you select all the drives you would like to use in your array, press ENTER to go to the RAID configuration step.
* Choose the type of RAID you would like. If you need assistance figuring out which RAID set up best suits your needs please see the following [FAQ from Adaptec](http://www.adaptec.com/en-us/_common/compatibility/_education/raid_level_compar_wp.htm).
* Provide an Array Label during the configuration. It is a good practive to include the type of RAID in the label (for example: RAID10-A).
* Press Enter to navigate the remaining settings. Use the default values.

After you complete the configuration select Done and the RAID is created. You can see your new Array by selecting 'Manage Arrays' from the Main Menu. To exit the configuration utility, press the ESC key until you are prompted to Exit the Adaptec BIOS.

## Removing existing Arrays

If you need to remove an existing array you will go to Manage Arrays > Select the Array to remove and press Delete and confirm.

## Example Configurations

1. On a server with 6 total drives, you can set up 2 SSD's in a RAID0 for your Operating System and 4 additional drives in a RAID10 for your actual data. This allows you to quickly reload the servers OS without restoring your site or service data if it is located on the secondary array.

* On a cPanel server, you can have /var and /home on separate SSD RAID Arrays. Since these are the 2 most IO-intensive directories on a cPanel server, you can potentially decrease site response time with the following settings:
  * RAID0 (2 SATA Drives) - /
  * RAID0 (2 SSD Drives) - /var
  * RAID0 (2 SSD Drives) - /home
  * RAID10 (4 SATA Drives) - /backup

* Use a single RAID array to set up multiple logical partitions. For example, use two 4TB drives set up in a RADI1. You can partition the RAID to fit your needs. For example:
  * Primary partition of 100GB for your Operating System
  * Second partition of 500GB for your data
  * Third partition of the remaining space for backups
