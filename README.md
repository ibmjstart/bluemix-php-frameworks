bluemix-wordpress
=================

#### Provides guidance for using wordpress within the BlueMix environment

##### WordPress is a [free and open source](http://en.wikipedia.org/wiki/Free_and_open_source) [blogging](http://en.wikipedia.org/wiki/Blog) tool and a [content management system](http://en.wikipedia.org/wiki/Content_management_system) (CMS) based on [PHP](http://en.wikipedia.org/wiki/PHP) and [MySQL](http://en.wikipedia.org/wiki/MySQL) which runs on a [web hosting service](http://en.wikipedia.org/wiki/Web_hosting_service).  Features include a plug-in architecture and a template system.  WordPress is completely customizable and can be used for almost anything.   You can use Wordpress as a foundation of your web application to call social data APIs.

In order to have Wordpress work on the IBM BlueMix Platform, do the following:

1. Download a current stable version of Wordpress from http://wordpress.org/download/.
2. Untar or unzip the download and change to the base directory, usually "wordpress".
3. From the base directory, run<pre><code>echo "<?php" > wp-salt.php
</code></pre>
4. Followed by ....<pre><code>curl https://api.wordpress.org/secret-key/1.1/salt/ >> wp-salt.php
</code></pre>
5. Replace the **_wp-config.php_** with the one in attachments for this page.  If you've searched on how to set up Wordpress with Cloud Foundry v1 you'll notice that
 * Level of **mySQL** has changed (5.1 -> 5.5)
 * Cloud Foundry host variable name has changed (hostname -> host)
 * **DB_HOST** variable requires the port now.
6. Using the cf gem, install Wordpress in Cloud Foundry with the Heroku PHP buildpack. 
<pre><code>cf push --buildpack https://github.com/heroku/heroku-buildpack-php.git
</code></pre>
**NOTE**:  During the install choose a mySQL database.

7. That's it!.
