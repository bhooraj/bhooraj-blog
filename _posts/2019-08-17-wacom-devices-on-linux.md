---
layout: post
title: "Wacom tablets work better on Linux than Windows?"
excerpt_seperator: "<!--more-->"
image: 
 path: /images/08-2019/2019-08-17-wacom-devices-on-linux-1600x800.webp
 thumbnail: /images/08-2019/2019-08-17-wacom-devices-on-linux-800x400.webp
 caption: "Credits: [Ravi Gupta](https://www.ravigupta.me/)"
categories:
  - art-and-design
tags:
  - wacom
  - drawing tablets
  - linux
  - windows
  - artists
  - designers
  - krita
  - clip studio paint
---
Wacom drivers and windows have a past full of issues. Let's see if the experience is better on Linux or not.

<!--more-->

# Windows and Wacom devices

Wacom drivers and windows have struggled to work together for long. Our Intous 4 (Model: PTK-840) used to have a lot of issues while working on windows 7. Uninstalling the Wacom driver and then installing back the driver would solve the problem for a while. But, despite after doing so, some issue or other would reoccur on the next reboot. Issues like weird artefacts while drawing on the tablet, and the errors similar to "THE TABLET DRIVER NOT FOUND" were common. Sometimes, a fix found on forums would work for a few days, but the problem would reoccur.

A year back we switched to Windows 10 Pro, and we added the ‘One by Wacom’ device to our toolset in addition to the old Intous 4. But, the story remained more or less the same. We didn't notice the error "THE TABLET DRIVER NOT FOUND", but we noticed few issues on some apps.

Below is a screenshot of an attempt to draw a circle on Windows 10 Pro using [KRITA](https://krita.org/en/) with our ‘One by Wacom’ (Model: CTL-671).

<figure class="align-center">
  <a href="#"><img src="{{ '/images/08-2019/wacom-artifact-on-windows10-and-krita.JPG' | absolute_url }}" alt="a circle drawn in KRITA on windows using Wacom CTL-671"></a>
  <figcaption>An artifact produced while trying to draw a cirlce in KRITA on Windows 10 Pro.</figcaption>
</figure>

We tried using CLIP STUDIO PAINT EX on Windows 10 Pro with Wacom CTL-671, below is result.

<figure class="align-center">
  <a href="#"><img src="{{ '/images/08-2019/wacom-no-pressure-sensitivty-windows10-and-clipstudiopaint.JPG' | absolute_url }}" alt="few strokes drawn in CLIP STUDIO PAINT EX on windows using Wacom CTL-671"></a>
  <figcaption>No pressure sensitivity while trying to draw in CLIP STUDIO PAINT EX on Windows 10 Pro.</figcaption>
</figure>

The result remains the same on Windows 10 Pro while we switch to Intuos 4 for our drawing tablet.

*Note: We do not know how the Wacom devices perform while using Adobe Photoshop on Window 10 Pro.*

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-in.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=IN&source=ac&ref=tf_til&ad_type=product_link&tracking_id=altback0e-21&marketplace=amazon&region=IN&placement=B07BPDGF32&asins=B07BPDGF32&linkId=72732ef6601e8e78cb9796f88e25cbe8&show_border=true&link_opens_in_new_window=true&price_color=333333&title_color=0b467d&bg_color=ffffff">
    </iframe><iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-in.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=IN&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=altback0e-21&marketplace=amazon&region=IN&placement=B01MQU5LW7&asins=B01MQU5LW7&linkId=c361910751a8b2a11175f50fd3726a9b&show_border=true&link_opens_in_new_window=true"></iframe><iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//ws-in.amazon-adsystem.com/widgets/q?ServiceVersion=20070822&OneJS=1&Operation=GetAdHtml&MarketPlace=IN&source=ss&ref=as_ss_li_til&ad_type=product_link&tracking_id=altback0e-21&marketplace=amazon&region=IN&placement=B07RXWY67K&asins=B07RXWY67K&linkId=97b08522747627c7fb122a7f5d37329c&show_border=true&link_opens_in_new_window=true"></iframe>

# Linux and Wacom Devices
**We have used the Wacom devices on UBUNTU 18.04 LTS and LINUX MINT. So our findings below are based on these two distros only.**

Initially, we installed the Ubuntu 18.04 LTS for catering in our needs for coding. We were developing a website, and it was getting cumbersome for us to install and manage packages on Windows. So, we decided to give Linux (Ubuntu) a try. It helped us a lot in achieving our goals. And, we started reading more about Ubuntu and other Linux distributions.

Finally, we came across Linux Mint, a distro based on Ubuntu. We loved it, not because of its UI resembling with windows. But, because we found it more stable and fast as compared to Ubuntu.

Few reasons why we liked the Wacom experience on Linux Mint:
 
- Linux Mint (Ubuntu as well) comes preinstalled with driver support for Wacom graphic tablets. So, we didn't have to worry about installing drivers for Wacom.

- We didn't find any artefacts while we drew on the tablet.

- Similar experience while drawing across all the Art Apps that we installed on Linux Mint.

Below is a screenshot of an attempt to draw a circle on Linux Mint using KRITA with our 'One by Wacom' (Model: CTL-671)

<figure class="align-center">
  <a href="#"><img src="{{ '/images/08-2019/circle-on-krita-and-linuxmint-using-wacom.JPG' | absolute_url }}" alt="a circle drawn in KRITA on windows using Wacom CTL-671"></a>
  <figcaption>No artifacts found while drawing a circle on Linux Mint using KRITA.</figcaption>
</figure>

***Note: Although there is one caveat while using this approach. The driver which comes installed with Linux mint doesn’t come with the customization options that come with Wacom drivers on Windows.***

Do let us know if you found this article helpful or not? If you want to read more on these subjects. You can follow us on our social handle for more updates.

<br>
<hr>
**You may add your impressions regarding the blog post here:**
  <blockquote class="twitter-tweet"><p lang="en" dir="ltr">Wacom tablets work better on Linux than windows?<br>Let&#39;s find out.<a href="https://twitter.com/hashtag/wacom?src=hash&amp;ref_src=twsrc%5Etfw">#wacom</a> <a href="https://twitter.com/hashtag/drawingtablets?src=hash&amp;ref_src=twsrc%5Etfw">#drawingtablets</a> <a href="https://twitter.com/hashtag/linux?src=hash&amp;ref_src=twsrc%5Etfw">#linux</a> <a href="https://twitter.com/hashtag/windows?src=hash&amp;ref_src=twsrc%5Etfw">#windows</a> <a href="https://twitter.com/hashtag/artists?src=hash&amp;ref_src=twsrc%5Etfw">#artists</a> <a href="https://twitter.com/hashtag/designers?src=hash&amp;ref_src=twsrc%5Etfw">#designers</a> <a href="https://twitter.com/hashtag/krita?src=hash&amp;ref_src=twsrc%5Etfw">#krita</a> <a href="https://twitter.com/hashtag/clipstudiopaint?src=hash&amp;ref_src=twsrc%5Etfw">#clipstudiopaint</a><a href="https://t.co/ro7a3Kbv3m">https://t.co/ro7a3Kbv3m</a></p>&mdash; bhooraj (@bhoowrites) <a href="https://twitter.com/bhoowrites/status/1162693049299820544?ref_src=twsrc%5Etfw">August 17, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 
<hr>
