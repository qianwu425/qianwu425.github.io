---
title: "How to Create a Self-Signed SSL Certificate on Linux Command Line"
description: "SSL certificates are crucial for establishing secure encrypted connections between servers and clients. In this tutorial, we will explore how to create a self-signed SSL certificate on Linux using OpenSSL, an open-source command-line utility for SSL certificate management."
date: 2020-01-31
layout: post
---

<article>
  <img alt="creative decor" src="https://images.unsplash.com/photo-1523837157348-ffbdaccfc7de?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENyZWF0ZSUyMGElMjBTZWxmLVNpZ25lZCUyMFNTTCUyMENlcnRpZmljYXRlJTIwb24lMjBMaW51eCUyMENvbW1hbmQlMjBMaW5lfGVufDB8MHx8fDE2ODM2NjA5NjE&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>SSL certificates are crucial for establishing secure encrypted connections between servers and clients. In this tutorial, we will explore how to create a self-signed SSL certificate on Linux using OpenSSL, an open-source command-line utility for SSL certificate management.</p>
  <h2>Creating a Self-Signed SSL Certificate on Linux</h2>
  <p>Creating a self-signed SSL certificate on Linux using OpenSSL is a straightforward process that involves a few steps in the terminal. Below are the steps:</p>
  <h3>Step 1: Install OpenSSL on Linux</h3>
  <p>To create self-signed SSL certificates, you need to install OpenSSL. Depending on your Linux distribution, you can use the following commands to install OpenSSL:</p>
  <ul>
    <li>sudo apt update &amp;&amp; sudo apt install openssl -y (for Debian-based systems)</li>
    <li>sudo pacman -Sy openssl (for Arch Linux)</li>
    <li>sudo dnf install openssl (for RPM-based systems)</li>
  </ul>
  <h3>Step 2: Create a Self-Signed Certificate</h3>
  <p>After installing OpenSSL, you can generate a self-signed SSL certificate using a single command. OpenSSL will create the certificate and its associated encryption key in the current directory. Here's an example command to generate a self-signed SSL certificate for "example.com":</p>
  <pre><code>sudo openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes -out example.crt -keyout example.key</code></pre>
  <p>The above command prompts for information about the organization to process the certificate. The common name field specifies the domain name for which the certificate is installed. You can use any value other than the domain name for testing or personal development. To encrypt the private key, remove the "-nodes" option from the command.</p>
  <h3>Step 3: Read the Contents of the Self-Signed SSL Certificate</h3>
  <p>You can view the contents of the certificate and private key generated in Step 2 using the "ls" command to locate the files in the directory and the following command to read the contents of the PEM-formatted certificate:</p>
  <pre><code>sudo openssl x509 -noout -in example.crt -text</code></pre>
  <p>Alternatively, to extract the public key from the certificate in PEM format, use the "-pubkey" option along with the "-x509" command:</p>
  <pre><code>sudo openssl x509 -pubkey -noout -in example.crt</code></pre>
  <h3>Step 4: Create a Self-Signed SSL Certificate with No Prompts</h3>
  <p>You can create a self-signed SSL certificate without being prompted to answer questions by using the "-subj" option to specify all subject information. Here's an example command that specifies all fields:</p>
  <pre><code>openssl req -newkey rsa:4096 -x509 -sha256 -days 3650 -nodes -out example.crt -keyout example.key -subj "/C=US/ST=California/L=San Francisco/O=Security/OU=IT Department/CN=www.example.com"</code></pre>
  <p>The "-subj" option specifies the following fields: Country (C), State (ST), Locality (L), Organization (O), Organizational Unit (OU), and Common Name (CN).</p>
  &lt;<h3>Step 5: Configure the Web Server to Use the Self-Signed SSL Certificate</h3>
  <p>To use the self-signed SSL certificate on your web server, you need to copy the "example.crt" and "example.key" files to the appropriate directories on the server. The exact location and method of copying these files may vary depending on the web server you are using. However, here are the fundamental steps to setting up Apache to use a self-signed SSL certificate:</p>
  <ol>
    <li>Copy the "example.crt" file to the "/etc/ssl/certs/" directory:</li>
    <pre><code>sudo cp example.crt /etc/ssl/certs/</code></pre>
    <li>Copy the "example.key" file to the "/etc/ssl/private/" directory:</li>
    <pre><code>sudo cp example.key /etc/ssl/private/</code></pre>
    <li>Edit the Apache SSL configuration file "/etc/apache2/sites-available/default-ssl.conf" and add the following lines to configure SSL:</li>
    <pre><code>SSLEngine on
SSLCertificateFile /etc/ssl/certs/example.crt
SSLCertificateKeyFile /etc/ssl/private/example.key</code></pre>
    <li>Restart the Apache web server:</li>
    <pre><code>sudo systemctl restart apache2</code></pre>
  </ol>
  <p>After completing these procedures, your web server should be using the self-signed SSL certificate.</p>
  <h2>Conclusion</h2>
  <p>Creating a self-signed SSL certificate is a convenient way to establish a secure connection between a server and a client for testing or development purposes. Using OpenSSL on Linux, you can create a self-signed SSL certificate with just a few terminal commands. You can specify details such as the certificate's validity period, key size, and other relevant information to create the certificate. Additionally, you need to configure your web server to use the self-signed SSL certificate for secure communication with clients.</p>
</article>