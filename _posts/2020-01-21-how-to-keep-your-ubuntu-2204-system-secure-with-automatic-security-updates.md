---
title: How to Keep Your Ubuntu 22.04 System Secure With Automatic Security Updates
description: Ubuntu is a well-known Linux distribution, and it is crucial to keep your system and packages updated to ensure its security and privacy. One way to automate the process of updating your system is by using the "unattended-upgrades" package, a built-in feature of Ubuntu that can automatically download, install, and configure security updates. Here's a step-by-step guide on how to enable and customize this feature on Ubuntu 22.04 through the terminal.
date: 2020-01-21
layout: post
---

<article>
  <img alt="two bullet surveillance cameras attached on wall" src="https://images.unsplash.com/photo-1496368077930-c1e31b4e5b44?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEtlZXAlMjBZb3VyJTIwVWJ1bnR1JTIwMjIuMDQlMjBTeXN0ZW0lMjBTZWN1cmUlMjB3aXRoJTIwQXV0b21hdGljJTIwU2VjdXJpdHklMjBVcGRhdGVzfGVufDB8MHx8fDE2ODM2NjA5Mzg&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Ubuntu is a well-known Linux distribution, and it is crucial to keep your system and packages updated to ensure its security and privacy. One way to automate the process of updating your system is by using the "unattended-upgrades" package, a built-in feature of Ubuntu that can automatically download, install, and configure security updates. Here's a step-by-step guide on how to enable and customize this feature on Ubuntu 22.04 through the terminal.</p>
  <h2>Activating Unattended-Upgrades on Ubuntu 22.04</h2>
  <p>Enabling unattended-upgrades on Ubuntu 22.04 can be done easily via the terminal. Start by updating your system to the latest version using the following command:</p>
  <pre><code>sudo apt update &amp;&amp; sudo apt upgrade</code></pre>
  <p>Next, install or confirm the installation of the unattended-upgrades package by running the following command:</p>
  <pre><code>sudo apt install unattended-upgrades</code></pre>
  <p>Note that unattended-upgrades are already installed by default on Ubuntu.</p>
  <p>To verify that unattended-upgrades are functioning correctly, run the following command in the terminal:</p>
  <pre><code>sudo unattended-upgrades --dry-run --debug</code></pre>
  <p>You can also check the status of unattended-upgrades on Ubuntu using the systemctl command:</p>
  <pre><code>sudo systemctl status unattended-upgrades.service</code></pre>
  <h2>Modifying the Configuration File of Unattended-Upgrades</h2>
  <p>You can customize the unattended-upgrades configuration file using any text editor. In this example, we'll use the vim editor to access the configuration file:</p>
  <pre><code>sudo vim /etc/apt/apt.conf.d/50unattended-upgrades</code></pre>
  <p>Once you have opened the file, remove the # marks from the lines to enable the updates. You'll see a section in the file that looks like this:</p>
  <pre><code>"origin=Ubuntu,codename=${distro_codename}-updates";</code></pre>
  <pre><code>"origin=Ubuntu,codename=${distro_codename}-proposed-updates";</code></pre>
  <pre><code>"origin=Ubuntu,codename=${distro_codename},label=Ubuntu";</code></pre>
  <pre><code>"origin=Ubuntu,codename=${distro_codename},label=Ubuntu-Security";</code></pre>
  <p>Save the file using :wq.</p>
  <h2>Enabling or Disabling Unattended-Upgrades on Ubuntu 22.04</h2>
  <p>You can enable or disable unattended upgrades on your machine by reconfiguring the file. In the terminal, type the following command:</p>
  <pre><code>sudo dpkg-reconfigure --priority=low unattended-upgrades</code></pre>
  <p>A pop-up will appear on your screen; select "Yes" to enable unattended-upgrades on Ubuntu, and "No" to disable it. It's recommended to reboot the system to apply the changes automatically to Ubuntu.</p>
  <h2>Customizing the Unattended-Upgrades Configuration File</h2>
  <p>The configuration file of unattended-upgrades allows for more customization options that can be added or modifiedas per your preferences. Here are some examples:</p>
  <ul>
    <li><strong>Periodic updates:</strong> You can specify the interval between two update checks by adding this line to the configuration file:</li>
    <pre><code>"Unattended-Upgrade::Periodic::Update-Package-Lists "1";</code></pre>
    <pre><code>"Unattended-Upgrade::Periodic::Unattended-Upgrade "1";</code></pre>
    <li><strong>Email notifications:</strong> You can configure the system to send email notifications to a specified email address after every upgrade by adding this line to the configuration file:</li>
    <pre><code>"Unattended-Upgrade::Mail "user@example.com";</code></pre>
    <li><strong>Automatic removal of old packages:</strong> You can configure the system to remove old packages that are no longer needed after an upgrade by adding this line to the configuration file:</li>
    <pre><code>"Unattended-Upgrade::Remove-Unused-Kernel-Packages "true";</code></pre>
  </ul>
  <h2>Conclusion</h2>
  <p>Enabling and configuring unattended-upgrades is an essential feature in Ubuntu that automates the process of installing updates. This feature helps to keep your system secure and up-to-date. Although unattended-upgrades are already installed by default on Ubuntu, you need to configure and enable the service to ensure that automatic updates are installed on the system. You can also customize the configuration file to add or modify features according to your preferences. By following the steps outlined in this guide, you can easily activate and customize the unattended-upgrades package on your Ubuntu 22.04 system, ensuring that your system is always up-to-date and secure.</p>
</article>
