---
layout: post
title: "Installing Raspberry Pi OS Lite on Raspberry Pi 4b"
excerpt_seperator: "<!--more-->"
image:
 path: /images/06-2020/2020-06-19-InstallingRaspberryPiOSlite-1600x800.webp
 thumbnail: /images/06-2020/2020-06-19-InstallingRaspberryPiOSlite-800x400.webp
categories:
  - technology
tags:
  - raspberry pi 4b
  - rpi 4b
  - linux
  - raspberry pi os
---
Recently, [Raspberry Pi Foundation](https://www.raspberrypi.org/) released a new version of the Raspberry Pi OS with 8GB RAM. With the release of the new hardware product, they also renamed the officially supported OS from Raspbian to Raspberry Pi OS.
In this short tutorial let us learn how to install the Raspberry Pi OS on Raspberry Pi 4b and see if there are some changes in installation.
<!--more-->

# Raspberry Pi OS
Raspberry Pi OS (previously called Raspbian) is the officially supported operating system from [Raspberry Pi Foundation](https://www.raspberrypi.org/). It is based on Debian Buster and comes with all necessary software for its functioning.

Currently, the Raspberry Pi OS is available in three variants. You can download it from the Foundation’s [download](https://www.raspberrypi.org/downloads/raspberry-pi-os/) page. The three variants are:

- Raspberry Pi OS (32-bit) with desktop and recommended software
- Raspberry Pi OS (32-bit) with desktop
- Raspberry Pi OS (32-bit) Lite

The first two variants come with a GUI (Graphical User Interface). The Raspberry Pi OS Lite is a CLI (Command Line Interface) based OS. It comes with just enough preinstalled packages that are necessary to run web apps and services. In this example, we stick with Raspberry Pi OS Lite.

> If you want to read more about the new Raspberry Pi 4b, you can read my [article](https://bhooraj.com/technology/raspberry-pi-4b/) about it.

# Installation steps
1.  Download the Raspberry Pi OS Lite image from the [Raspberry Pi's Raspbian download page](https://www.raspberrypi.org/downloads/raspberry-pi-os/).

2. Take a micro-SD card (a pre-formatted card or the one that does not have some valuable data) and connect it to a computer using a micro-SD card reader. Prefer, atleast a UHS-I, Grade 1, Class 10 micro-SD card for better performance. We use the following card:

    <iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-in.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=IN&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=altback0e-21&marketplace=amazon&region=IN&placement=B06XWMQ81P&asins=B06XWMQ81P&linkId=d266c7adb9003166b396d7b442ab28c3&show_border=true&link_opens_in_new_window=true"></iframe>

3. We will use 'balenaEtcher' program to flash the image to the card. So, you can download  'balenaEtcher' from their [download page](https://www.balena.io/etcher/). Download the right installation media accordingly for your computer's OS.

4. Start the 'balenaEtcher' program. Click on 'Select image' button and select the 'Raspberry Pi OS Lite' zip.

5. Next, click on the 'Select target' to select the card you want to flash with the image. Make sure you select the correct card. Flashing the image will erase all the data on the chosen card.

6. Review your selections and click on 'Flash!'. After a while, the OS image would be flashed on to the card.

**We have some steps that we recommend for the first boot. Please follow the steps below.**

## Booting Raspberry Pi OS Lite for the first time on Raspberry Pi 4b.
1. Go to the 'boot' partition on the flashed micro-SD card. Create an empty file named **'ssh'** (without the single quotes).<br>
*Note: We are taking this step so that we don't have to connect our Raspberry Pi 4 to an external monitor. We will SSH into our Raspberry Pi 4b to use the CLI.*

2. Remove the micro-SD from the micro-SD card reader, plugin the ethernet cable and power cable. Raspberry Pi OS Lite would boot up.

3. Reserve a local IP address for the Raspberry Pi in your Router's settings. This will make sure that the local IP address remains constant for the device.<br>
*Note: Steps for reserving the local IP are beyond the scope of this tutorial. The steps vary for each router manufacturer and model.*

4. Connect to Raspberry Pi using SSH on a different machine on the same local network.

5. The command we need to use will be something as follow:<br>
`$ ssh useraname@localIPaddress`

6. The default username for Raspberry Pi is `'pi'`. And for this example, the local IP assigned to Rpi 4 is `192.168.0.5`.
  So, our command to SSH into Rpi 4 would be:<br>
  `$ ssh pi@192.168.0.5`

7. We will be shown the following message:

      `pi@192.168.0.5's password:`

8. The default password for Raspberry Pi OS is `'raspberry'` (without the single quotes). Type the password and press enter.

9. When we login for the first time, we are shown the message about changing the default password, wifi being currently disabled and setting the country before use. So let do that. Also, this is only difference from the [Rasbian Buster Lite installation](https://bhooraj.com/technology/install-raspbian-buster-lite/) which we covered earlier.

10. After we login, we will need to change the default password to something secure. Enter the following command:

      `$ passwd`

      You will be asked to enter your current password and then new password two times (to double-check that you entered what you wanted).

11. Remember the password you typed in. And, keep it at a safe place. We will need this a lot in future.

12. Let us set the country now. Use the following command:

      `$ sudo raspi-config`

      You will be taken to a CLI based configuration tool. Select `'4 Localisation Options'` and then set your 'Time Zone' and 'WLAN country' accordingly.


13. Let's update the package list from repositories and upgrade the packages first. This is important from the security point of view. Having the packages up-to-date is must, there is no exception for that.
Use the following commands to update and upgrade:

    `$ sudo apt-get update && sudo apt-get upgrade`

14. Reboot your Raspberry Pi. Use the following command:

    `$ sudo shutdown -r now`

    After the reboot we will login again using SSH.

> **That is it, our Raspberry Pi with Raspberry Pi OS Lite is now ready. We may install any packages we wish.**
