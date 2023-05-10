---
title: "How to Change Your Username on Ubuntu 20.04"
description: "If you're using Ubuntu on your device, you may want to modify your username at some point. Each user is assigned a unique username in Ubuntu, which can be changed using the following steps."
date: 2020-01-22
layout: post
---

<article><img alt="Change neon light signage" src="https://images.unsplash.com/photo-1499244571948-7ccddb3583f1?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENoYW5nZSUyMFlvdXIlMjBVc2VybmFtZSUyMG9uJTIwVWJ1bnR1JTIwMjAuMDR8ZW58MHwwfHx8MTY4MzY2MDkzOQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
<p>If you're using Ubuntu on your device, you may want to modify your username at some point. Each user is assigned a unique username in Ubuntu, which can be changed using the following steps.</p>
<h2>Change Your Username on Ubuntu 20.04 via the Command Line</h2>
<p>It's important to note that you can't modify an existing username on Ubuntu. Instead, you can create a temporary user with a new name, and then log in to that user account to make the changes.</p>
<p>For example, if your current login is "johnsmith," you can create a new user account called "tempuser," log in to that account, and then modify "johnsmith" to your desired new username.</p>
<p>Here's how to create a new user on Ubuntu using the command line:</p>
<pre><code>sudo adduser mynewuser</code></pre>
<p>After creating the new user, give them sudo access using this command:</p>
<pre><code>sudo usermod -aG sudo mynewuser</code></pre>
<p>To confirm that the user has been created, enter this command to display a list of all users:</p>
<pre><code>cut -d: -f1 /etc/passwd</code></pre>
<h2>Change Your Username on Ubuntu 20.04</h2>
<h3>1: Change Your Username on Ubuntu from the Terminal</h3>
<p>There are two ways to change your username on Ubuntu from the terminal:</p>
<h4>i: Change Your Username on Ubuntu from the Terminal Using the usermod Command</h4>
<p>Before using the usermod command, ensure that the user is not currently logged into the system. Then, execute the following command to change the username:</p>
<pre><code>sudo usermod -l &lt;newname&gt; &lt;oldname&gt;</code></pre>
<p>For instance, to change "mynewuser" to "newnameuser" as your username, run this command:</p>
<pre><code>sudo usermod -l newnameuser mynewuser</code></pre>
<p>Verify that the name has been changed by executing the command to display the list of users.</p>
<h4>ii: Change Your Username on Ubuntu from the Terminal Using the sed Command</h4>
<p>You can also change your username on Ubuntu using the sed command in the terminal. Here's how:</p>
<pre><code>sudo su</code></pre>
<p>Use the following command to change the username in /etc/passwd file:</p>
<pre><code>sed -i s/&lt;old_user&gt;/&lt;new_user&gt;/g /etc/passwd</code></pre>
<p>For example, to change the username "newnameuser" to "mynewuser2", use this command:</p>
<pre><code>sed -i s/newnameuser/mynewuser2/g /etc/passwd</code></pre>
<p>After executing the command, reboot the system to see the new username on the lock screen.</p>
<h3>2: Change Your Username on Ubuntu from the Terminal using the useradd Command</h3>
<p>You can also create a new user account with the desired username using the useradd command, and then copy all of the files from the previous user account to the new one. Here's how:</p>
<pre><code>sudo useradd -m &lt;new_user&gt; -s/bin/bash
sudo cp -r /home/&lt;old_user&gt;/. /home/<new_user>/.</new_user></code></pre>
<p>After copying the files, set a password for the new user account using this command:</p>
<pre><code>sudo passwd &lt;new_user&gt;</code></pre>
<p>Finally, log out of the old user account and log in to the new one to ensure everything is working as expected.</p>
<h2>Change Your Username on Ubuntu 20.04 via the GUI</h2>
<p>The easiest way to change your username on Ubuntu is to use the GUI. Here's how:</p>
<p>Launch the device settings from Activities, and click on "Users" in the left panel to see the list of users on the right side of the screen. You'll need to enter your password first to make changes to the device.</p>
<p>Find the user account you want to modify, and click on the pencil icon to edit it. Enter the new username in the appropriate field, and then click on "Apply" to save the changes.</p>
<h2>Conclusion</h2>
<p>Changing your username on Ubuntu is a simple process, whether you prefer to use the command line or the GUI. However, it's important to create a temporary user account with sudo privileges before making any changes to avoid locking yourself out of the system.</p>
<p>Now that you know how to change your username, you can customize your Ubuntu device to suit your needs more easily.</p>
</article>