---
title: "How to Troubleshoot and Fix DNS Resolution Errors on Linux"
description: "If you encounter an error message on your Linux system when it fails to translate a domain name into its corresponding IP address, this may indicate a DNS resolution error. Such an error can result from various factors, such as an unstable internet connection or improperly configured network settings. This guide provides solutions to help you resolve this issue and restore proper DNS resolution functionality to your Linux system."
date: 2020-01-12
layout: post
---

<article>
  <img alt="person holding green and white pack" src="https://images.unsplash.com/photo-1607400201515-c2c41c07d307?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFRyb3VibGVzaG9vdCUyMGFuZCUyMEZpeCUyMEROUyUyMFJlc29sdXRpb24lMjBFcnJvcnMlMjBvbiUyMExpbnV4fGVufDB8MHx8fDE2ODM2NjA5MTM&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you encounter an error message on your Linux system when it fails to translate a domain name into its corresponding IP address, this may indicate a DNS resolution error. Such an error can result from various factors, such as an unstable internet connection or improperly configured network settings. This guide provides solutions to help you resolve this issue and restore proper DNS resolution functionality to your Linux system.</p>
  <h2>Prerequisites</h2>
  <p>To implement the solutions provided in this guide, you will need to have administrative privileges and a stable internet connection.</p>
  <ul>
    <li>Administrative privileges</li>
    <li>Working internet connection</li>
  </ul>
  <h2>Understanding DNS Resolution Errors</h2>
  <p>When you attempt to connect to a network resource or browse a website, your Linux system sends a request to a DNS server to resolve the associated domain name to its IP address. If the DNS server is unable to deliver the required IP address, an error message may appear. Some common causes of this error include:</p>
  <ol>
    <li>Intermittent or no internet connectivity</li>
    <li>Incorrectly configured DNS settings</li>
    <li>Firewall restrictions blocking necessary traffic</li>
  </ol>
  <h2>Solution 1: Check Internet Connectivity</h2>
  <p>If you encounter a DNS resolution error, start by checking your system's internet connectivity. Slow or disconnected internet connection may cause this error.</p>
  <h2>Solution 2: Verify DNS Configuration</h2>
  <p>The DNS configuration file is responsible for configuring the DNS servers used by your Linux system. To open the DNS configuration file in a text editor, enter the following command:</p>
  <code>sudo nano /etc/resolv.conf</code>
  <p>Ensure that the configuration file contains at least one DNS server entry. Here is an example of a DNS server entry:</p>
  <code>nameserver 8.8.8.8</code>
  <p>If the configuration file has no DNS server entries, you can add one by entering the IP address of a recognized DNS server such as Google's public DNS servers (8.8.8.8 and 8.8.4.4). After editing the configuration file, save it and restart the DNS service with the following command:</p>
  <code>sudo systemctl restart systemd-resolved.service</code>
  <p>You can then test the DNS server's operation by attempting to ping a website:</p>
  <code>ping example.com</code>
  <p>If the DNS server is functioning correctly, you should receive a response indicating successful communication with the website's server.</p>
  <h3>2.1 Fix DNS Configuration File Permissions</h3>
  <p>In some cases, even if the proper DNS server is defined in the configuration file, the DNS resolution error may persist. This can be caused by incorrect file permissions on the configuration file. To fix this issue, ensure that the file is owned by the administrator, and all users have read access by entering the following commands:</p>
  <code>sudo chown root:root /etc/resolv.conf</code>
  <code>sudo chmod 644 /etc/resolv.conf</code>
  <p>After making these modifications, ping the website again to see if the problem has been resolved:</p>
  <code>ping example.com</code>
  <p>If the problempersists, proceed to the next solution.</p>
  <h2>Solution 3: Unblock Firewall Restrictions</h2>
  <p>If you are still experiencing a DNS resolution error after implementing the above solutions, it is possible that the issue is caused by a firewall blocking necessary network traffic. Specifically, the WHOIS lookup (port 43) and DNS resolution (port 53) ports may be blocked. To resolve this issue, you can use your system's firewall utility to unblock these ports.</p>
  <h3>3.1 Allow Traffic on Required Ports</h3>
  <p>If you need to allow traffic on these ports, you can use your system's firewall utility to do so.</p>
  <code>sudo ufw allow 43/tcp</code>
  <code>sudo ufw allow 53/tcp</code>
  <p>If your firewall utility is not enabled by default, you can enable it using the following command:</p>
  <code>sudo ufw enable</code>
  <p>After allowing traffic on these ports, you can reload the firewall to apply the changes:</p>
  <code>sudo ufw reload</code>
  <h3>3.2 Check Firewall Logs</h3>
  <p>If you are using a different firewall utility or are unsure which ports to unblock, you can check your firewall logs for more information. Your firewall logs may provide clues as to which ports are being blocked and why. To view your firewall logs, enter the following command:</p>
  <code>sudo journalctl -u firewalld</code>
  <p>This command displays the log messages for the firewall utility. If you are using a different firewall utility, replace "firewalld" with the name of your firewall utility.</p>
  <h2>Conclusion</h2>
  <p>If you encounter a DNS resolution error on your Linux system, there are several potential causes and solutions to consider. These can include issues with your internet connectivity, DNS configuration, or firewall settings. By following the solutions outlined in this guide, you can troubleshoot and resolve these issues and restore proper DNS resolution functionality to your Linux system.</p>
</article>