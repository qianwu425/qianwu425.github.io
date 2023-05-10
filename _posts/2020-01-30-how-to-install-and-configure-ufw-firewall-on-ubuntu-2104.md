---
title: "How to Install and Configure UFW Firewall on Ubuntu 21.04"
description: "Uncomplicated Firewall (UFW) is a command-line utility that makes it easy to manage a net filter firewall when configured with Ubuntu 21.04. It can be used to block or allow connections to P2P servers and individually specified ports. Additionally, UFW includes GUI tools for simpler management."
date: 2020-01-30
layout: post
---

<article>
    <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBhbmQlMjBDb25maWd1cmUlMjBVRlclMjBGaXJld2FsbCUyMG9uJTIwVWJ1bnR1JTIwMjEuMDR8ZW58MHwwfHx8MTY4MzY2MDk2MA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
    <p>Uncomplicated Firewall (UFW) is a command-line utility that makes it easy to manage a net filter firewall when configured with Ubuntu 21.04. It can be used to block or allow connections to P2P servers and individually specified ports. Additionally, UFW includes GUI tools for simpler management.</p>
    <h2>Installation of UFW Firewall on Ubuntu 21.04</h2>
    <p>UFW is included by default in Ubuntu 21.04. However, if it is not installed on your system, you can install it by running:</p>
    <code>sudo apt install ufw</code>
    <h2>Configuration of UFW Firewall on Ubuntu 21.04</h2>
    <p>Before configuring UFW, you need to ensure that IPv6 is enabled on your Ubuntu system to allow UFW to manage firewalls for both IPv4 and IPv6. To enable IPv6, edit the following file:</p>
    <code>sudo nano /etc/default/ufw</code>
    <p>Find the IPV6 line in the file and ensure that it is set to 'yes'. Save the file to enable UFW for both IPv6 and IPv4.</p>
    <p>By default, UFW blocks all incoming connections and allows all outgoing connections. To enable incoming connections, you need to create rules to allow incoming SSH or HTTP connections.</p>
    <p>To enable incoming SSH connections, run:</p>
    <code>sudo ufw allow ssh</code>
    <p>To enable incoming HTTP connections, run:</p>
    <code>sudo ufw allow http</code>
    <h2>Enabling UFW on Ubuntu 21.04</h2>
    <p>To enable UFW on Ubuntu 21.04, run the following command. You will be prompted with a warning that enabling UFW may disrupt existing SSH connections. Type 'y' to proceed:</p>
    <code>sudo ufw enable</code>
    <p>The firewall is now active on your system. Run the verbose command to check all the rules you have set:</p>
    <code>sudo ufw status verbose</code>
    <h2>Configuring All UFW Incoming and Outgoing Connections on Ubuntu 21.04</h2>
    <p>To block all incoming connections, run:</p>
    <code>sudo ufw default deny incoming</code>
    <p>Use the 'allow' option if you want to accept all inbound connections:</p>
    <code>sudo ufw default allow incoming</code>
    <p>To allow all outgoing connections, run:</p>
    <code>sudo ufw default allow outgoing</code>
    <p>To prevent all outgoing connections, run:</p>
    <code>sudo ufw default deny outgoing</code>
    <p>The firewall is now configured on Ubuntu 21.04, allowing only the connections that your system needs and limiting unnecessary connections.</p>
    <h2>Disabling the Firewall on Ubuntu 21.04</h2>
    <p>The following command will disable UFW if you no longer require it:</p>
    <code>sudo ufw disable</code>
    <p>The reset command can also be used to start over:</p>
    <code>sudo ufw reset</code>
    <h2>Using UFW to Enable Specific Services on Ubuntu 21.04</h2>
    <p>UFW enables you to use particular services orports by establishing rules for them. For instance, you may use the following command to enable the FTP service on your Ubuntu system:</p>
<code>sudo ufw allow ftp</code>
<p>This will allow incoming connections on the standard FTP port (21) and enable the FTP service. Similarly, you can enable other services or ports by replacing 'ftp' with the name of the service or the port number.</p>
<h2>Viewing UFW Logs on Ubuntu 21.04</h2>
<p>Every connection that UFW blocks and approves is logged in the syslog file. To view the UFW logs, run the following command:</p>
<code>sudo tail -f /var/log/syslog | grep 'UFW'</code>
<p>This will display the UFW logs in real-time, showing all blocked and allowed connections. You can use this information to troubleshoot issues with UFW or to monitor network activity on your Ubuntu system.</p>
<h2>Conclusion</h2>
<p>UFW is a powerful firewall tool that can help enhance the security of your Ubuntu 21.04 system. By following the steps in this guide, you can install and configure UFW, enable specific services, and view UFW logs to monitor network activity. With UFW, you can control incoming and outgoing network traffic and ensure that your system is protected against unauthorized access.</p>
<p>Remember to always keep your firewall updated and configured properly to prevent any security threats.</p>
</article>