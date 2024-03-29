---
layout: post
title: "Installing Raspbian Buster Lite on Raspberry Pi 4b"
excerpt_seperator: "<!--more-->"
image: 
 path: /images/10-2019/2019-10-23-InstallingRaspbianBusterLite-1600x800.webp
 thumbnail: /images/10-2019/2019-10-23-InstallingRaspbianBusterLite-800x400.webp
categories:
  - technology
tags:
  - raspberry pi 4b
  - rpi 4b
  - linux
  - raspbian
---
In this short tutorial let us learn how to install the Raspbian Buster on Raspberry Pi 4b.
<!--more-->

# Raspbian Buster
Raspbian Buster is the officially supported operating system by [Raspberry Pi Foundation](https://www.raspberrypi.org/). Soon, after releasing the Raspberry Pi 4b launch, the Raspberry Pi foundation released the Raspbian Buster. 

Currently, the Raspbian Buster is available in three variants. You can download it from the Foundation’s [download](https://www.raspberrypi.org/downloads/raspbian/) page. The three variants are:

- Raspbian Buster with desktop and recommended software
- Raspbian Buster with desktop
- Raspbian Buster Lite

The first two variants come with a GUI (Graphical User Interface). The Raspbian Buster Lite is a CLI (Command Line Interface) based OS. It comes with just enough preinstalled packages that are necessary to run web apps and services. In this example, we stick with Raspbian Buster Lite.

> If you want to read more about the new Raspberry Pi 4b, you can read my [article](/technology/raspberry-pi-4b/) about it. 

# Installation steps
1.  Download the Raspbian Buster Lite image from [Raspberry Pi's Raspbian download page](https://www.raspberrypi.org/downloads/raspbian/).

2. Take a micro-SD card (a pre-formatted card or the one that does not have some valuable data) and connect it to a computer using a micro-SD card reader. Prefer, atleast a UHS-I, Grade 1, Class 10 micro-SD card for better performance. We use the following card: 
    
    {% include ads/amazon-sd-card.html %}

3. We will use 'balenaEtcher' program to flash the image to the card. So, you can download  'balenaEtcher' from their [download page](https://www.balena.io/etcher/). Download the right installation media accordingly for your computer's OS.

4. Start the 'balenaEtcher' program. Click on 'Select image' button and select the 'Raspbain Buster Lite' zip.

5. Next, click on the 'Select target' to select the card you want to flash with the image. Make sure you select the correct card. Flashing the image will erase all the data on the chosen card.

6. Review your selections and click on 'Flash!'. After a while, the OS image would be flashed on to the card. 

**We have some steps that we recommend for the first boot. Please follow the steps below.**

<br>
<aside>
<p>Advertisment:</p> 
{% include ads/amazon-rpi-accessories.html %}
</aside>
<br>

## Booting Raspbian Lite for the first time on Raspberry Pi 4b.
1. Go to the 'boot' partition on the flashed micro-SD card. Create an empty file named **'ssh'** (without the single quotes).<br> 
*Note: We are taking this step so that we don't have to connect our Raspberry Pi 4 to an external monitor. We will SSH into our Raspberry Pi 4b to use the CLI.*

2. Remove the micro-SD from the micro-SD card reader, plugin the ethernet cable and power cable. Rasbian Lite would boot up.

3. Reserve a local IP address for the Raspberry Pi in your Router's settings. This will make sure that the local IP address remains constant for the device.<br>
*Note: Steps for reserving the local IP are beyond the scope of this tutorial. The steps vary for each router manufacturer and model.*

4. Connect to Raspberry Pi using SSH on a different machine on the same local network.

5. The command we need to use will be something as follow:
  
      `$ ssh useraname@localIPaddress`
  
6. The default username for Raspberry Pi is `'pi'`. And for this example, the local IP assigned to Rpi 4 is `192.168.0.5`.
  So, our command to SSH into Rpi 4 would be:
      
      `$ ssh pi@192.168.0.5`
  
7. We will be shown the following message:

      `pi@192.168.0.5's password:`
      
8. The default password for Rasbian Buster is `'raspberry'` (without the single quotes). Type the password and press enter.

9. After we login, we will need to change the default password to something secure. Enter the following command:

      `$ passwd`
      
      You will be asked to enter your current password and then new password two times (to double-check that you entered what you wanted).
   
10. Remember the password you typed in. And, keep it at a safe place. We will need this a lot in future.

11.  Let's update the package list from repositories and upgrade the packages first. This is important from the security point of view. Having the packages up-to-date is must, there is no exception for that. Use the following commands to update and upgrade:

      `$ sudo apt-get update && sudo apt-get upgrade`

12. Reboot your Raspberry Pi. Use the following command:
    
    `$ sudo shutdown -r now`
  
    After the reboot we will login again using SSH.
    
> **That is it, our Raspberry Pi with Raspbian Buster Lite is now ready. We may install any packages we wish.**

## You may view the video tutorial for additional help.
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/Zi1dIXxu_Qw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>
<hr>
**You may add your impressions regarding the blog post here:**
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">How to Install Raspbian Buster Lite on Raspberry Pi 4b.<a href="https://twitter.com/hashtag/raspberrypi4b?src=hash&amp;ref_src=twsrc%5Etfw">#raspberrypi4b</a> <a href="https://twitter.com/hashtag/raspberrypi?src=hash&amp;ref_src=twsrc%5Etfw">#raspberrypi</a> <a href="https://twitter.com/hashtag/rpi4b?src=hash&amp;ref_src=twsrc%5Etfw">#rpi4b</a> <a href="https://twitter.com/hashtag/linux?src=hash&amp;ref_src=twsrc%5Etfw">#linux</a> <a href="https://twitter.com/hashtag/raspbian?src=hash&amp;ref_src=twsrc%5Etfw">#raspbian</a> <a href="https://twitter.com/hashtag/raspbianbuster?src=hash&amp;ref_src=twsrc%5Etfw">#raspbianbuster</a><a href="https://t.co/pTEu7EKuzd">https://t.co/pTEu7EKuzd</a></p>&mdash; bhooraj (@bhoowrites) <a href="https://twitter.com/bhoowrites/status/1168105522882465792?ref_src=twsrc%5Etfw">September 1, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 
<hr>
