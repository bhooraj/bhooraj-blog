# Creating a Development Environtment for Drupal 8 with Lando.
Developling a Drupal 8 site or blog with a hosting plan that support Drupal 8 installation is relatively easy to do than doing it locally. 
This add to the upfront cost, even for to see how Drupal 8 works.


If you wish to develop a drupal 8 blog or site locally, there are few solutions that can help you to do so.


'Acquia Dev Desktop' is one of them, it helps in creating a local development environment for drupal 8. But, it only have installer for Mac and Windows.
Ampps, WampServer, or installing a LAMP/LEMP stack are also a few other options.

But, I found [Lando](https://docs.devwithlando.io/) makes it easier to do so, irrespective of the operating system or distro you are working on. 
Also, as it runs as 'an abstraction layer' to spin up docker container with sane defaults.

**Let us look on the broad steps to install Lando and use it.**

## Prequisites -
### For Lando to work properly, we need to install Docker for Mac / Docker for Windows / Docker CE (if it's not already installed).//
### Install Lando -- Steps are given below for installing it on Ubuntu LTS 18.04:
- Download the latest .deb, .pacman or .rpm package from GitHub (https://github.com/lando/lando/releases)
- Double-click on the package to launch Software Center and install.
- If your distro uses a docker group, make sure your user is a member of it (https://docs.docker.com/install/linux/linux-postinstall/)
  <code>$ sudo groupadd docker</code>
  <code>$ sudo usermod -aG docker $USER</code>
- Verify that you can run docker commands without sudo.
  <code>$ docker run hello-world</code>
- For installation on other platforms see the Lando installation documentation here: https://docs.devwithlando.io/installation/installing.html
Note: Composer needs to be installed globally. This will ensure to pull Drupal8 codebase using composer.
Note: nodejs and npm should be installed to install npm packages.

## Above were the pre-requistes, actuall steps are provided below and numbered.

FEW IMPORTANT LINKS:
- OFFICIAL GITHUB PAGE FOR 'DRUPAL-COMPOSER/DRUPAL-PROJECT':https://github.com/drupal-composer/drupal-project
- OFFICIAL LANDO DOCUMENTION FOR DRUPAL8:https://docs.devwithlando.io/tutorials/drupal8.html
- OFFICIAL DRUPAL DOCUMENTION FOR USING COMPOSER TO MANAGE DRUPAL SITE DEPENDENCIES:https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies
- DRUPAL COMPOSER INSTALLATION GUIDE:https://www.drupal.org/docs/user_guide/en/install-composer.html
- THIS BASIC BLOG 'GETTING STARTED WTIH LANDO' IS HELPFUL AS WELL:https://www.jeffgeerling.com/blog/2018/getting-started-lando-testing-fresh-drupal-8-umami-site

### Step#1
- Open the terminal from home directory. This can be anywhere as well.
- The following command creates a folder named 'my_site_name_dir' and pull the drupal8 code inside it.
<code>$ composer create-project drupal-composer/drupal-project:8.x-dev my_site_name_dir --stability dev --no-interaction</code>
- let's change 'my_site_name_dir' to 'drupaldev' for this example. //

### Step#2
- Go inside the created diretory.
- Add a .lando.yml file(inside the) with drupal8 recipe mentioned here: https://docs.devwithlando.io/tutorials/drupal8.html
- Open the terminal from there. Enter the following command
<code>$ lando start</code>
- Above command will create a apache,php and mysql environment. Note the details mentioned as we will need this to access later.  
- We can also use $ lando info to get this info.

 ### Step#3
- Use this command to install drush 8.x or downgrade the previous version installed.
<code>lando composer require drush/drush 8.x</code>
- Now a developing environment for drupal8 has been created.
- Use the command $ lando stop to kill the app(environment) created
- To completly erase the database and server environment use <code> $ lando destroy [app name] </code>

 ### Do look at the lando documentation online for more recipes,help and commands.
