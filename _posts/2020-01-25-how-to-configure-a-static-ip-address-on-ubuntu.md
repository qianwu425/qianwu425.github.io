---
title: "How to Configure a Static IP Address on Ubuntu"
description: "In certain situations, such as running servers like FTP, database, or web servers, you may need to set up a static IP address. While most networks use the Dynamic Host Configuration Protocol (DHCP) to assign IP addresses automatically, this tutorial will guide you through the process of configuring a static IP address on Ubuntu."
date: 2020-01-25
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENvbmZpZ3VyZSUyMGElMjBTdGF0aWMlMjBJUCUyMEFkZHJlc3MlMjBvbiUyMFVidW50dXxlbnwwfDB8fHwxNjgzNjYwOTQ2&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>In certain situations, such as running servers like FTP, database, or web servers, you may need to set up a static IP address. While most networks use the Dynamic Host Configuration Protocol (DHCP) to assign IP addresses automatically, this tutorial will guide you through the process of configuring a static IP address on Ubuntu.</p>
  <h2>Configuring a Static IP Address on Ubuntu</h2>
  <p>Although most networks use DHCP to assign IP addresses automatically, certain circumstances, particularly when running servers like FTP, database, or web servers, may require a static IP address. This article will explain how to set up a static IP address if you're using Ubuntu.</p>
  <h2>Step 1: Verify Your Current IP Address</h2>
  <p>Ubuntu usually gets its IP address from the DHCP server by default. Before configuring a static IP address, you should verify your current IP configuration. Use the following command to check the IP address on the active network interface:</p>
  <pre><code>ifconfig</code></pre>
  <p>This command displays the active interface with the name ens160 and its assigned IP address, such as 192.168.0.100. Once you have verified your current IP address, you can proceed with the process of setting up a static IP address.</p>
  <h2>Step 2: Set Up the Static IP Address</h2>
  <p>The static network or DHCP configuration is defined in the <code>/etc/netplan/</code> directory. You can check the configuration file by using the following command:</p>
  <pre><code>cat /etc/netplan/00-installer-config.yaml</code></pre>
  <p>The first configuration in the file should be the loopback interface. In the second entry, DHCP is the default IP configuration for the active network interface.</p>
  <p>To create a static IP address of 192.168.0.200 with a router IP address of 192.168.0.1 and disable DHCP addressing, create a new configuration file by using the following command:</p>
  <pre><code>sudo nano /etc/netplan/01-static-ip.yaml</code></pre>
  <p>Copy and paste the following lines, adjusting the IPv4 address and gateway to match the IP subnet of your environment:</p>
  <pre>network:
    version: 2
    renderer: networkd
    ethernets:
        ens160:
            dhcp4: no
            addresses: [192.168.0.200/24]
            gateway4: 192.168.0.1
            nameservers:
              addresses: [8.8.8.8, 8.8.4.4]</pre>
  <p>Once you have made the necessary changes, apply the new configuration file:</p>
  <pre><code>sudo netplan apply</code></pre>
  <p>Finally, use the following command to confirm the new static IP address on your network interface:</p>
  <pre><code>ifconfig</code></pre>
  <h2>Bonus Tips</h2>
  <p>1. To set up a static IPv6 address, use the following lines:</p>
  <pre>network:
    version: 2
    renderer: networkd
    ethernets:
        ens160:
            dhcp6: no
            addresses: [2001:db8::1/64]
            gateway6: fe80::1</pre>  <p>2. To assign multiple IP addresses to a single network interface, such as an additional IP of 192.168.0.250 to the <code>ens160</code> interface, use the following command:</p>
  <pre><code>sudo nano /etc/netplan/02-additional-ip.yaml</code></pre>
  <p>Copy and paste the following lines:</p>
  <pre>network:
    version: 2
    renderer: networkd
    ethernets:
        ens160:
            addresses: [192.168.0.200/24, 192.168.0.250/24]
            gateway4: 192.168.0.1</pre>
  <p>Once you have made the necessary changes, apply the new configuration file:</p>
  <pre><code>sudo netplan apply</code></pre>
  <p>To confirm the IP configuration, use the following command:</p>
  <pre><code>ip a</code></pre>
  <p>The output displays that the interface is now connected to two IP addresses.</p>
  <h2>Step 3: Configure the DNS or Nameserver IP</h2>
  <p>The DNS or nameserver IP information is stored in the <code>/etc/systemd/resolved.conf</code> file. If you are already using DHCP configuration, there is no need to make any changes. Simply verify the entries using the following command:</p>
  <pre><code>cat /etc/systemd/resolved.conf</code></pre>
  <p>The DNS server's IP address is typically the router's. In our example, the DNS server is the router's IP address. To make the modifications to the <code>/etc/systemd/resolved.conf</code> file effective, you must restart the systemd-resolved service:</p>
  <pre><code>sudo systemctl restart systemd-resolved.service</code></pre>
  <p>If you want to switch back to DHCP for some reason, remove the configuration file created in Step 2 and revert the changes to the <code>/etc/netplan/00-installer-config.yaml</code> file. Finally, apply the changes:</p>
  <pre><code>sudo netplan apply</code></pre>
  <h2>Conclusion</h2>
  <p>A static IP address is necessary for tasks like hosting servers, firewalling, and port forwarding. This tutorial provided a step-by-step guide for configuring a static IP address on Ubuntu. We hope that this information has been helpful and that you can now easily set up a static IP on Ubuntu.</p>
  <p>For more information on networking on Ubuntu, you may find the following resources helpful:</p>
  <ul>
    <li><a href="https://ubuntu.com/server/docs/network-configuration" rel="noopener" target="_blank">Ubuntu Server documentation: Network Configuration</a></li>
    <li><a href="https://help.ubuntu.com/lts/serverguide/network-configuration.html" rel="noopener" target="_blank">Ubuntu Server Guide: Network Configuration</a></li>
    <li><a href="https://linuxconfig.org/ubuntu-20-04-network-proxy-settings" rel="noopener" target="_blank">Ubuntu 20.04 Network Proxy Settings</a></li>
  </ul>
</article>