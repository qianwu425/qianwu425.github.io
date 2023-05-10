---
title: "A Guide to Installing and Using Monit on Ubuntu 24.04"
description: "Monit is a process monitoring tool for Unix-based systems that lets you keep track of various system resources like CPU usage, memory usage, network connectivity, specific processes, and all running services. It has a native HTTP(S) web server or the command line to display system status and can perform automatic upkeep and consequential actions."
date: 2020-01-25
layout: post
---

<article>
  <img alt="silhouette of man holding flashlight" src="https://images.unsplash.com/photo-1553708881-112abc53fe54?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxBJTIwR3VpZGUlMjB0byUyMEluc3RhbGxpbmclMjBhbmQlMjBVc2luZyUyME1vbml0JTIwb24lMjBVYnVudHUlMjAyNC4wNHxlbnwwfDB8fHwxNjgzNjYwOTQ3&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Monit is a process monitoring tool for Unix-based systems that lets you keep track of various system resources like CPU usage, memory usage, network connectivity, specific processes, and all running services. It has a native HTTP(S) web server or the command line to display system status and can perform automatic upkeep and consequential actions.</p>
  <p>When updating network settings, ensure that a static IP address is configured correctly to avoid connectivity issues. Double-check settings and test connectivity after any changes.</p>
  <h2>Installing and Using Monit on Ubuntu 24.04</h2>
  <p>To prevent errors during installation, first update your system:</p>
  <pre><code>sudo apt update
sudo apt upgrade</code></pre>
  <p>Monit is available in Ubuntu 24.04's base repository. You can install the latest version using the following command:</p>
  <pre><code>sudo apt install monit</code></pre>
  <p>Confirm the Monit version with the following command:</p>
  <pre><code>monit version</code></pre>
  <p>Monit is an essential tool for ensuring critical services function correctly since it allows server administrators to define monitoring settings and track service statuses. This guide offers a simple procedure for setting up and running Monit on Ubuntu 24.04.</p>
  <pre><code>sudo systemctl start monit
sudo systemctl enable monit
sudo systemctl status monit</code></pre>
  <h2>Configuring Monit</h2>
  <p>To configure Monit, open the configuration file in the terminal using this command:</p>
  <pre><code>sudo nano /etc/monit/monitrc</code></pre>
  <p>Set the Monit admin account password and enter the server's IP address or domain name. If you are using a remote machine, make these changes accordingly. If you are using a local host, leave it as is.</p>
  <p>Save and close the file to implement the new configuration, then restart the Monit service:</p>
  <pre><code>sudo monit -t
sudo systemctl restart monit</code></pre>
  <h2>Accessing the Monit Web User Interface</h2>
  <p>After installing and configuring Monit, access the Monit service using the server's IP address:</p>
  <pre><code>http://localhost:2812
http://mydomain.com:2812
http://my-ip-address:2812</code></pre>
  <p>Monit is an effective tool for ensuring the smooth operation of critical services since it allows server administrators to monitor service statuses and create monitoring settings. This guide simplifies the installation and use of Monit on Ubuntu 24.04.</p>
  <p>If you cannot access the web interface, check that Monit is running on the correct port using this command:</p>
  <pre><code>sudo netstat -plnt | grep monit</code></pre>
  <p>You can also check if the firewall is blocking the Monit connection using this command:</p>
  <pre><code>sudo ufw status</code></pre>
  <p>If the Monit port is not allowed, use this command to allow it:</p>
  <pre><code>sudo ufw allow 2812/tcp</code></pre>
  <h2>Using Monit for Process Monitoring</h2>
  <p>Monitlets you monitor specific processes and services running on your Ubuntu 24.04 system. To monitor a process, you need to add it to the Monit configuration file. Here's an example of how to monitor the Apache web server:</p>
  <pre><code>check process apache with pidfile /var/run/apache2/apache2.pid
  start program = "/etc/init.d/apache2 start"
  stop program = "/etc/init.d/apache2 stop"
  if failed host 127.0.0.1 port 80 protocol http then restart
  if cpu &gt; 60% for 2 cycles then alert
  if totalmem &gt; 500 MB for 2 cycles then restart
  if children &gt; 250 then restart
  if loadavg(5min) greater than 10 for 8 cycles then stop</code></pre>
  <p>This configuration file checks the Apache process by its PID file and restarts it if it fails to respond to a request on port 80. Additionally, it sets alerts for high CPU usage, high memory usage, and excessive child processes. If the load average exceeds a specified limit, Monit stops the process.</p>
  <p>You should use the configuration file's username and password to log in. Click on the system to see comprehensive stats on the dashboard.</p>
  <h2>Conclusion</h2>
  <p>This guide provides a straightforward process for installing and using Monit on Ubuntu 24.04. Monit is an excellent tool for monitoring CPU usage, memory usage, server uptime, and server application services, among other system resources. The compact M/Monit program can be used to monitor your Ubuntu system easily. By following the steps outlined in this guide, you can quickly set up Monit on your Ubuntu 24.04 system and configure it to monitor critical system resources and processes.</p>
</article>