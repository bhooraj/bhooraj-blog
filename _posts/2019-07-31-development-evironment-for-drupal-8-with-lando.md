# Creating a Development Environment for Drupal 8 with Lando.
Developing a Drupal 8 site or blog with a hosting plan that support Drupal 8 installation is relatively easy to do than doing it locally.

This add to the upfront cost, even though you just wanted to see how Drupal 8 works.


If you wish to develop a Drupal 8 blog or site locally, there are few solutions that can help you to do so.


'Acquia Dev Desktop' is one of them, it helps in creating a local development environment for Drupal 8. But, it only have installer for Mac and Windows.

Installing 'Ampps', 'WampServer', or a 'LAMP'/'LEMP' stack can be on the option as well.

But, I have found [Lando](https://docs.devwithlando.io/) makes it easier to do so. Irrespective of the operating system or distro you are working on.
Moreover, it runs as 'an abstraction layer' to spin up docker containers with sane defaults.

**Let us look at the steps on how to install and use Lando for creating a local development environment for Drupal 8.**

### 1. Prerequisites for creating a development environment for Drupal 8 with Lando:

 1. **Install Docker**

	For Lando to work properly, we need to install Docker for Mac / Docker for Windows / Docker CE (if it's not already installed).

  2. **Install Lando**

	1. Download the latest `.deb`, `.dmg`, `.exe`, `.pacman`, or `.rpm` package from [Lando's GitHub repository](https://github.com/lando/lando/releases) (Download the correct package depending on your OS or distro).

	2. Install the package.

	3. If your distro uses a docker group, make sure your user is a member of it.
		
		$ sudo groupadd docker
		
		$ sudo usermod -aG docker $USER
	
	    *Note: Visit here for more details on this: [https://docs.docker.com/install/linux/linux-postinstall/](https://docs.docker.com/install/linux/linux-postinstall/)*
	 
	4. Verify that you can run docker commands without sudo.
		$ docker run hello-world

      For installation on other platforms see the Lando installation documentation here: https://docs.devwithlando.io/installation/installing.html

  3. **Install Composer**
  
  	Composer needs to be installed globally. This will ensure to pull Drupal 8 codebase using composer.
  	
  4. **Install NodeJS and NPM**

	'nodejs' and 'npm' should be installed to install npm packages. Themes or some modules for Drupal 8 might need these packages.

### 2. Creating the Local developement environment for Drupal 8 with Lando.

 1. **Step 1:**
 	1. Open the terminal from home directory. This can be anywhere as well.
 	*Note: You may use Git Bash if you are using windows.*
 	
	2. The following command creates a folder named 'my_site_name_dir' and pull the drupal8 code inside it.
	
		`$ composer create-project drupal-composer/drupal-project:8.x-dev my_site_name_dir --stability dev --no-interaction`
	 
 	     *Note: Change 'my_site_name_dir' to 'drupaldev' for this example.*

 2. **Step 2**
	1. Go inside the created diretory.
	
	2. Add a `.lando.yml` file(inside the) with drupal8 recipe mentioned here: https://docs.devwithlando.io/tutorials/drupal8.html
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

 FEW IMPORTANT LINKS:
- OFFICIAL GITHUB PAGE FOR 'DRUPAL-COMPOSER/DRUPAL-PROJECT':https://github.com/drupal-composer/drupal-project
- OFFICIAL LANDO DOCUMENTION FOR DRUPAL8:https://docs.devwithlando.io/tutorials/drupal8.html
- OFFICIAL DRUPAL DOCUMENTION FOR USING COMPOSER TO MANAGE DRUPAL SITE DEPENDENCIES:https://www.drupal.org/docs/develop/using-composer/using-composer-to-manage-drupal-site-dependencies
- DRUPAL COMPOSER INSTALLATION GUIDE:https://www.drupal.org/docs/user_guide/en/install-composer.html
- THIS BASIC BLOG 'GETTING STARTED WTIH LANDO' IS HELPFUL AS WELL:https://www.jeffgeerling.com/blog/2018/getting-started-lando-testing-fresh-drupal-8-umami-site
