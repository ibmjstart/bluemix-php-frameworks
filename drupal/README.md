bluemix-php-frameworks
======================

#### Provides guidance for using Drupal within the BlueMix environment

##### Drupal is a free and open-source content management framework written in PHP. It is used as a back-end framework for at least 2.1% of all websites worldwide ranging from personal blogs to corporate, political, and government sites including whitehouse.gov and data.gov.uk. It is also used for knowledge management and business collaboration

In order to have Drupal work on the IBM BlueMix Platform, do the following:

1. Download a current stable version of Druapl from [https://drupal.org/index.html](https://drupal.org/index.html).
2. Untar or unzip the download (e.g. tar -xzf drupal-7.23.tar.gz) and change to the base directory (e.g. drupal-7.23).
3. From the base directory, copy the settings.php file found in [this repository](https://github.com/ibmjstart/bluemix-php-frameworks/tree/master/drupal) into the folder "drupal-7.23/sites/default"<pre><code>bash-3.2$ cp settings.php drupal-7.23/sites/default</code></pre>
4. Using the cf gem, install Drupal into BlueMix with the Heroku PHP buildpack.
<pre><code>cf push --buildpack https://github.com/heroku/heroku-buildpack-php.git</code></pre>
   **NOTE**:  During the application install choose to bind to a mySQL database service.
        
5. After the application is running on BlueMix, browse to http://domain_route_to_your_app>/install.php and complete the installation steps
6. That's it!.
