---
layout: post
title: "Creating a Development Environment for Drupal 8 with Lando."
excerpt_seperator: "<!--more-->"
categories:
  - technology
tags:
  - web design
  - cms
  - drupal 8
---
Developing a Drupal 8 site or blog with a hosting plan that supports Drupal 8 installation is relatively easy to do than doing it locally.
This adds to the upfront cost, even though you just wanted to see how Drupal 8 works.

<!--more-->

If you wish to develop a Drupal 8 blog or site locally, a few solutions can help you to do so.

'Acquia Dev Desktop' is one of them, it helps in creating a local development environment for Drupal 8. But, it only have the installer for Mac and Windows.

Installing 'Ampps', 'WampServer', or a 'LAMP'/'LEMP' stack could be one of the options as well.

But, I have found [Lando](https://docs.devwithlando.io/) makes it easier to do so. Irrespective of the operating system or distro you are working on.
Moreover, it runs as an 'abstraction layer' to spin up docker containers with sane defaults.

**Let us look at the steps on how to install and use Lando for creating a local development environment for Drupal 8.**

<br>
<aside>
<p>Advertisment:</p> 
{% include ads/amazon-banner-horizontal.html %}
</aside>
<br>

### 1. Prerequisites for creating a development environment for Drupal 8 with Lando:

  **1. Install Docker**

  For Lando to work, we need to install Docker for Mac/Docker for Windows/Docker CE (if it's not already installed).

  **2. Install Lando**

   - Download the latest `.deb`, `.dmg`, `.exe`, `.pacman`, or `.rpm` package from [Lando's GitHub repository](https://github.com/lando/lando/releases) (Download the correct package depending on your OS or distro).

   - Install the package.

   - If your distro uses a docker group, make sure your user is a member of it.

     Commands for doing so will be something like:

     `$ sudo groupadd docker`

     `$ sudo usermod -aG docker $USER`

     *Note: Visit here for more details on this: [https://docs.docker.com/install/linux/linux-postinstall/](https://docs.docker.com/install/linux/linux-postinstall/)*

   - Verify that you can run docker commands without sudo.

     `$ docker run hello-world`

   - To see complete documentation on Installing Lando for your OS, visit appropriate links:
     - Linux: [https://docs.devwithlando.io/installation/linux.html](https://docs.devwithlando.io/installation/linux.html)
     - MacOS: [https://docs.devwithlando.io/installation/macos.html](https://docs.devwithlando.io/installation/macos.html)
     - Windows: [https://docs.devwithlando.io/installation/windows.html](https://docs.devwithlando.io/installation/windows.html)

  **3. Install Composer**

   Composer needs to be installed globally. This will ensure to pull Drupal 8 codebase using composer.

  **4. Install NodeJS and NPM**

   'nodejs' and 'npm' should be installed to install npm packages. Themes or some modules for Drupal 8 might need these packages.

### 2. Creating the Local development environment for Drupal 8 with Lando.

  1. Open the terminal from the home directory. This can be from anywhere as well.
    *Note: You may use Git Bash if you are using windows.*

  2. Use the following command to create a folder named 'my_site_name_dir' and pull the Drupal 8 code inside it.

      `$ composer create-project drupal-composer/drupal-project:8.x-dev my_site_name_dir --stability dev --no-interaction`

       *Note: Change 'my_site_name_dir' to 'drupaldev' for this example.*
  3. Go inside the created directory.

  4. Add a `.lando.yml` file (inside the directory 'drupaldev') with Drupal 8 recipe mentioned here: [https://docs.devwithlando.io/tutorials/drupal8.html](https://docs.devwithlando.io/tutorials/drupal8.html)

  5. Open the terminal from this directory. (Be sure about your path when in terminal. You should be inside the 'drupaldev' directory.)
	Enter the following command:

	   `$ lando start`

  6. The above command will create  services like `apache`, `php` and `mysql` necessary for Drupal 8 development environment. Note the details shown in the output, we will need this to access the Drupal site later.

     We can also use `$ lando info` to get this information.

 7. Use this command to install drush 8.x or downgrade the previous version installed.
  <code>lando composer require drush/drush 8.x</code>

 8. A development environment for Drupal 8 has been created.

#### Now we are ready to experiment and start developing with Drupal 8.

>Note:
 Use the command `$ lando stop` to kill the app (environment) created.
 To completely erase the database and server environment use:
	`$ lando destroy [app name]`

<br>
***Important links:***
 - Official page for 'drupal-composer/drupal-project': [https://github.com/drupal-composer/drupal-project](https://github.com/drupal-composer/drupal-project)
 - Lando documention for Drupal 8: [https://docs.devwithlando.io/tutorials/drupal8.html](https://docs.devwithlando.io/tutorials/drupal8.html)
 - Drupal documentation for using Composer to manage Drupal site dependencies: [https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies)
 - Drupal Composer installation guide: [https://www.drupal.org/docs/user_guide/en/install-composer.html](https://www.drupal.org/docs/user_guide/en/install-composer.html)
 - This blog by Jeff Geerling is helpful: [https://www.jeffgeerling.com/blog/2018/getting-started-lando-testing-fresh-drupal-8-umami-site](https://www.jeffgeerling.com/blog/2018/getting-started-lando-testing-fresh-drupal-8-umami-site)
<br>
<hr>
**You may add your impressions regarding the blog post here:**
  <blockquote class="twitter-tweet"><p lang="en" dir="ltr">Here&#39;s how to create a development environment for Drupal 8 with Lando. <a href="https://t.co/L6XVqNUt1q">https://t.co/L6XVqNUt1q</a><a href="https://twitter.com/hashtag/Drupal8?src=hash&amp;ref_src=twsrc%5Etfw">#Drupal8</a> <a href="https://twitter.com/hashtag/Drupal?src=hash&amp;ref_src=twsrc%5Etfw">#Drupal</a> <a href="https://twitter.com/hashtag/CMS?src=hash&amp;ref_src=twsrc%5Etfw">#CMS</a> <a href="https://twitter.com/hashtag/webdesign?src=hash&amp;ref_src=twsrc%5Etfw">#webdesign</a> <a href="https://twitter.com/hashtag/Lando?src=hash&amp;ref_src=twsrc%5Etfw">#Lando</a> <a href="https://twitter.com/hashtag/Bhooraj?src=hash&amp;ref_src=twsrc%5Etfw">#Bhooraj</a></p>&mdash; bhooraj (@bhoowrites) <a href="https://twitter.com/bhoowrites/status/1156649885040431105?ref_src=twsrc%5Etfw">July 31, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 
<hr>
