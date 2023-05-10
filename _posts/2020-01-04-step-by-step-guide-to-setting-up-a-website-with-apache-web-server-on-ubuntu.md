---
title: "Step-by-Step Guide to Setting Up a Website With Apache Web Server on Ubuntu"
description: "If you're interested in creating and hosting websites using Apache on Ubuntu, this guide will show you how to configure Apache on Ubuntu."
date: 2020-01-04
layout: post
---

<article>
  <img alt="laptop computer on glass-top table" src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxTdGVwLWJ5LVN0ZXAlMjBHdWlkZSUyMHRvJTIwU2V0dGluZyUyMHVwJTIwYSUyMFdlYnNpdGUlMjB3aXRoJTIwQXBhY2hlJTIwV2ViJTIwU2VydmVyJTIwb24lMjBVYnVudHV8ZW58MHwwfHx8MTY4MzY2MDg5Mg&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're interested in creating and hosting websites using Apache on Ubuntu, this guide will show you how to configure Apache on Ubuntu.</p>
  <h2>Installation and Setup of Apache Web Server</h2>
  <p>In this guide, we'll go through the steps to install and configure Apache Web Server on Ubuntu:</p>
  <h3>Step 1: Update/Upgrade Repository</h3>
  <p>Before we begin, let's upgrade the repository by running:</p>
  <code>sudo apt update &amp; sudo apt upgrade</code>
  <h3>Step 2: Install Apache2</h3>
  <p>Install Apache2 from the local repository with this command:</p>
  <code>sudo apt install apache2</code>
  <p>This command installs Apache2 and its dependencies, which may take some time.</p>
  <h3>Step 3: Enable Firewall</h3>
  <p>To access the Apache2 web server, we need to enable the system firewall. Check the firewall's status with:</p>
  <code>sudo ufw status</code>
  <p>If the firewall is not enabled, run this command:</p>
  <code>sudo ufw enable</code>
  <h3>Step 4: Verify Apache2 is Working</h3>
  <p>Check that Apache2 is installed and working properly by typing 'localhost' in the search bar of your local browser:</p>
  <code>localhost</code>
  <p>If everything is working correctly, the output should display the Apache2 default web page.</p>
  <h3>Step 5: Configure Firewall</h3>
  <p>To allow external access to the Apache2 web server, we need to configure the firewall to open the necessary ports. First, list the firewall applications with:</p>
  <code>sudo ufw app list</code>
  <p>To allow external access to the Apache2 web server, use this command to add the necessary ports to the firewall:</p>
  <code>sudo ufw allow 'Apache Full'</code>
  <p>Confirm that 'Apache Full' has been successfully added to the firewall-allowed ports list by running:</p>
  <code>sudo ufw status</code>
  <h2>Configuration of Apache Web Server</h2>
  <p>After installing the Apache web server, let's configure it:</p>
  <h3>Step 1: Check Apache2 Status</h3>
  <p>Check the status of Apache2 with:</p>
  <code>sudo systemctl status apache2</code>
  <h3>Step 2: Set up Virtual Host</h3>
  <p>Create a directory for the desired domain and assign ownership to the new 'www-data' environment variable with the following commands:</p>
  <code>sudo mkdir -p /var/www/mywebsite.com/</code>
  <code>sudo chown -R www-data:www-data /var/www/mywebsite.com</code>
  <p>Replace 'mywebsite.com' with your desired domain.</p>
  <h3>Step 3: Create Configuration File for Virtual Host</h3>
  <p>Create a new '.conf' file for the virtual host using the nano editor:</p>
  <code>sudo nano /etc/apache2/sites-available/mywebsite.com.conf</code>
  <p>Add the following virtual host configuration to the file:<virtualhost *:80="">
ServerAdmin admin@localhost
ServerName mywebsite.com
ServerAlias www.mywebsite.comDocumentRoot /var/www/mywebsite.com
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined

</virtualhost></p><p>Disable the default configuration file and enable the new configuration file with:</p>
<code>sudo a2dissite 000-default.conf</code>
<code>sudo a2ensite mywebsite.com.conf</code>

  <p>Restart Apache2 to allow the new configuration to take effect:</p>
  <code>sudo systemctl restart apache2</code>
  <h3>Step 4: Create Web-Page for Virtual Host</h3>
  <p>Create a webpage for the virtual host with the nano editor. For example, create an 'index.html' file:</p>
  <code>sudo nano /var/www/mywebsite.com/index.html</code>
  <p>Save the file after entering the desired HTML code for the web page.</p>
  <h3>Step 5: Find Host IP</h3>
  <p>Determine the host IP address with:</p>
  <code>hostname -I</code>
  <h3>Step 6: Test Virtual Host</h3>
  <p>Test that the Apache2 server is properly set up by entering the host IP into the browser and running the 'index.html' webpage:</p>
  <code>http://server_IP</code>
  <p>For example, if the host IP is '192.168.17.134', type 'http://192.168.17.134' in the browser. The output should
    display the created webpage, confirming that the Apache web server is running perfectly on Ubuntu.</p>

  <h2>Additional Configuration: Enabling SSL Encryption</h2>
  <p>To enable SSL encryption on your Apache web server, follow these steps:</p>
  <h3>Step 1: Install Certbot</h3>
  <p>Install the Certbot utility to obtain an SSL certificate for your domain:</p>
  <code>sudo apt-get install certbot python3-certbot-apache</code>
  <h3>Step 2: Obtain SSL Certificate</h3>
  <p>Obtain an SSL certificate for your domain using the Certbot utility. Use the following command to obtain a
    certificate:</p>
  <code>sudo certbot --apache</code>
  <p>Follow the instructions to obtain the SSL certificate for your domain. Once the certificate is obtained, Certbot
    will configure Apache to use the SSL certificate.</p>
  <h3>Step 3: Verify SSL Encryption</h3>
  <p>Verify that SSL encryption is enabled on your Apache web server by typing 'https://' followed by your domain name in the search bar of your local browser:</p>
<code>https://mywebsite.com</code>
  <p>If SSL encryption is enabled, your browser's address bar should display a green lock icon.</p>
  <h2>Additional Configuration: Enabling PHP Support</h2>
  <p>Toenable PHP support on your Apache web server, follow these steps:</p>
  <h3>Step 1: Install PHP and Required Modules</h3>
  <p>If you wish to enable PHP support on your Apache web server, do the following:</p>
  <code>sudo apt-get install php libapache2-mod-php php-mysql</code>
  <p>This command installs PHP and the required modules.</p>
  <h3>Step 2: Test PHP Support</h3>
  <p>Test PHP support on your Apache web server by creating a file called 'info.php' with the following content:</p>
  <code>&lt;?php
phpinfo();
?&gt;</code>
  <p>Save the file and exit the editor. Then, open your web browser and type the following URL in the address bar:</p>
  <code>http://localhost/info.php</code>
  <p>If PHP is properly installed and configured, you should see information about the PHP installation in your browser.</p>
  <h3>Step 3: Remove PHP Info File</h3>
  <p>Once you have verified PHP support, remove the 'info.php' file using the following command:</p>
  <code>sudo rm /var/www/html/info.php</code>
  <p>This command removes the 'info.php' file.</p>
  <h2>Conclusion</h2>
  <p>This guide provided steps to configure Apache web server on Ubuntu by installing and setting up Apache web server, configuring the firewall, creating a virtual host, creating a configuration file for the virtual host, creating a webpage for the virtual host, finding the host IP, and testing the virtual host. Additionally, it explained how to enable SSL encryption and PHP support to enhance the security and functionality of your website. Follow these steps to set up a website with Apache web server on Ubuntu.</p>
</article>
