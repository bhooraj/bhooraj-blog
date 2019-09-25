---
layout: post
title: "Installing Trelby on Ubuntu 18.04 or Linux Mint 19.2"
excerpt_seperator: "<!--more-->"
categories:
  - technology
tags:
  - intallation steps
  - trelby
  - ubuntu
  - linux mint
  - screenwriting
---
In this tutorial let us learn how to install Trelby 2.3-dev on Linux Mint 19.2
<!--more-->

# About Trelby
[Trelby](https://www.trelby.org/) is a screenwriting application that can also be used to write comic scripts, video scripts etc. Trelby is multiplatform, feature-rich and open-source application.

*Please, note that Trelby is not under development and the current version 2.3-dev is quite old. But, we found it very intuitive and efficient.*

The Debian package for Trelby 2.2 on the [download](https://www.trelby.org/download/) page is not compatible for Ubuntu 18.04 LTS and other Linux distros based on Ubuntu 18.04 or up.

The reason for this is an unmet dependency  `python-wxgtk2.8`. The `python-wxgtk2.8` package is not in ubuntu's repository and so the `.deb` installer won't  work on Ubuntu 18.04 LTS.

# Installing Trelby 2.3-dev on Ubuntu 18.04 or Linux Mint 19.2

The following steps will install the current development version of the Trelby.

1. Install the `python-lxml` and `python-wxgtk3.0` from the respository:
```
$ sudo apt install python-lxml python-wxgtk3.0
```

2. Download the Zip from the [Trelby's repository on github](https://github.com/oskusalerma/trelby) and extract the downloaded folder.

3. Navigate to the extracted folder and open up a new terminal and enter the following command:
```
$ sudo python setup.py install
```

4. Navigate to the Applications folder using the following command:
```
$ cd /usr/share/applications
```

5. Create a new file named `trelby.desktop`  using:
```
$ sudo nano trelby.desktop
```

6. Paste the following code:
```
[Desktop Entry]
Name=Trelby
Comment=Screenwriting Application
Exec=/opt/trelby/bin/trelby
Icon=/opt/trelby/resources/icon256.png
Type=Application
Categories=Utility;Publishing;


```
7. Press `ctrl+x` and then `y` to save the file.

8. Change the file to an executable using:
```
sudo chmod +x trelby.desktop
```

Now, we have a successful installation of Trelby and we can launch the application.
