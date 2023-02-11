---
layout: post
title: "Installing Raspberry Pi OS using Raspberry Pi Imager"
excerpt_seperator: "<!--more-->"
image:
 path: /images/02-2023/2023-02-09-InstallingRaspberryPiOS-using-imager-1600x800.png
 thumbnail: /images/02-2023/2023-02-09-InstallingRaspberryPiOS-using-imager-800x400.png
categories:
  - technology
tags:
  - raspberry pi 4b
  - rpi 4b
  - linux
  - raspberry pi os
  - raspberry pi imager
---
[Raspberry Pi Foundation][def] has made changes to where and how one can download their software. There's a new home to their [software page](https://www.raspberrypi.com/software/). With this new homepage, they have a new tool to install the OS. It is called Raspberry Pi Imager.
In this short tutorial let us learn how to install the Raspberry Pi OS using Raspberry Pi Imager. This article will also help if you want to install Ubuntu on a supported Raspberry Pi device (see step 3).
<!--more-->

# Raspberry Pi OS
Raspberry Pi OS (previously called Raspbian) is the officially supported operating system by [Raspberry Pi Foundation](https://www.raspberrypi.org/). It is based on Debian (version 11 at the time of writing this article) and comes with all the necessary software for its functioning.

Currently, the Raspberry Pi OS is available in five variants. You can download it from the Foundation’s new [download](https://www.raspberrypi.com/software/operating-systems/) page. The five variants are:

- Raspberry Pi OS (32-bit) with desktop and recommended software
- Raspberry Pi OS (32-bit) with desktop
- Raspberry Pi OS (32-bit) Lite
- Raspberry Pi OS (64-bit) with desktop
- Raspberry Pi OS (64-bit) Lite

The legacy version of the software is also available on the page.

# Raspberry Pi Imager

<figure class="align-center">
  <a href="#"><img src="{{ '/images/02-2023/2023-02-09-raspberry-pi-imager-v1.73.png' | absolute_url }}" alt="Start screen of Raspberry Pi Imager v1.73"></a>
  <figcaption>Start screen of Raspberry Pi Imager v1.73</figcaption>
</figure>

Using Raspberry Pi Imager is a quick and easy way to install Raspberry Pi OS and other operating systems to a microSD card, ready to use with your Raspberry Pi.


# Installing Raspberry Pi OS
1. Download the Raspberry Pi Imager for your current OS and install it. Here is the [Raspberry Pi Imager download page](https://www.raspberrypi.com/software/). Currently, the OS' supported are Windows, MacOS, Ubuntu for x86 architecture and Raspberry Pi OS itself.

2. After running the program, you will get the start screen as the image showed above.

3. Click on the 'CHOOSE OS' button to select from the list of available Operating systems. The first option is the 'Raspberry Pi OS (32-bit)' desktop version, which is also the recommended OS for most Raspberry Pi devices. If you are not sure which Raspberry Pi OS version is best for your device, you can visit the [Operating system images](https://www.raspberrypi.com/software/operating-systems/) page to read more about the compatibility of devices and OS. We have chosen the Raspberry Pi OS Lite (64-bit) for this example.

  <figure class="align-center">
    <a href="#"><img src="{{ '/images/02-2023/2023-02-09-raspberry-pi-imager-choose-os.png' | absolute_url }}" alt="choose os screen of Raspberry Pi Imager v1.73"></a>
    <figcaption>'CHOOSE OS' screen of Raspberry Pi Imager v1.73</figcaption>
  </figure>

To install any other Raspberry Pi OS version, click on the 'Raspberry Pi OS (other)' button and then select OS of your choice.

  > If you want to install a version of Ubuntu, click 'Other general-purpose OS > Ubuntu > Ubuntu version of your choice'.

4. Next, click on the 'CHOOSE STORAGE' to select the card you want to flash with the image. Make sure you select the correct card. Flashing the image will erase all the data on the chosen card.

  > Note: This step is to be performed with caution.

5. Depending on the OS and version of it, you may or may not see the gear icon at the bottom right corner of the program. This is for setting the Advanced options like hostname, enabling SSH, and setting up username-&-password.

  <figure class="align-center">
    <a href="#"><img src="{{ '/images/02-2023/2023-02-09-raspberry-pi-imager-advanced-options.png' | absolute_url }}" alt="setting advanced option in Raspberry Pi Imager v1.73"></a>
    <figcaption>Advanced options settings</figcaption>
  </figure>

  > Recommendation: Try to keep the settings same as shown in the image above. Just change your username, password, SSID for Wireless LAN and its password. We will use these to login in to device in headless mode (using SSH).

6. Review your selections and click on 'Flash!'. After a while, the OS image would be flashed onto the card.

**We have some steps that we recommend for the first boot. Please follow the steps below.**

## Booting Raspberry Pi OS Lite for the first time on Raspberry Pi 4b.
1. Remove the micro-SD from the micro-SD card reader. Insert the card into the Raspberry Pi SD card slot. Plug in the ethernet cable and power cable. Raspberry Pi OS Lite would boot up.

2. Reserve a local IP address for the Raspberry Pi in your Router's settings. This will make sure that the local IP address remains constant for the device.<br>
*Note: Steps for reserving the local IP are beyond the scope of this tutorial. The steps vary for each router manufacturer and model.*

3. Connect to Raspberry Pi using SSH on a different machine on the same local network.

4. The command we need to use will be something as follow:<br>
`$ ssh useraname@localIPaddress`

5. The username we had set for the Raspberry Pi is `'pi'`. And for this example, the local IP assigned to Rpi 4 is `192.168.0.5`.
  So, our command to SSH into Rpi 4 would be:<br>
  `$ ssh pi@192.168.0.5`

6. We will be shown the following message:

      `pi@192.168.0.5's password:`

7. Type in the password and press enter.

8. After we log in, we may change the default password to something secure. Enter the following command:

      `$ passwd`

      You will be asked to enter your current password and then your new password two times (to double-check that you entered what you wanted).

9. Remember the password you typed in. And, keep it in a safe place. We will need this a lot in future.

10. Let us set the country now. Use the following command:

      `$ sudo raspi-config`

      You will be taken to a CLI-based configuration tool. Select `'4 Localisation Options'` and then set your 'Time Zone' and 'WLAN country' accordingly.


11. Let's update the package list from repositories and upgrade the packages first. This is important from a security point of view. Having the packages up-to-date is a must, there is no exception to that.
Use the following commands to update and upgrade:

    `$ sudo apt-get update && sudo apt-get upgrade`

12. Reboot your Raspberry Pi. Use the following command:

    `$ sudo shutdown -r now`

    After the reboot we will login again using SSH.

> **That is it, our Raspberry Pi with Raspberry Pi OS Lite is now ready. We may install any packages we wish.**


[def]: https://www.raspberrypi.org/