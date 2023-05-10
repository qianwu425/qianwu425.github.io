---
title: "How to Allow Sudo Access for a User Account in Ubuntu"
description: "If you're using Ubuntu, you may find that you are unable to execute certain commands on the terminal because only the root user has access to sudo by default. In this tutorial, we will guide you through the process of granting sudo access to a user account on Ubuntu."
date: 2020-02-02
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEFsbG93JTIwU3VkbyUyMEFjY2VzcyUyMGZvciUyMGElMjBVc2VyJTIwQWNjb3VudCUyMGluJTIwVWJ1bnR1fGVufDB8MHx8fDE2ODM2NjA5Njg&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're using Ubuntu, you may find that you are unable to execute certain commands on the terminal because only the root user has access to sudo by default. In this tutorial, we will guide you through the process of granting sudo access to a user account on Ubuntu.</p>
  <h2>Enabling Sudo Access for a User Account in Ubuntu</h2>
  <p>If you attempt to run a command with sudo capabilities and receive an error message stating that the user is not authorized to use sudo, you will need to allow sudo access on your current user account. There are two ways to do this:</p>
  <h2>Method 1: Using the usermod Command</h2>
  <p>The usermod command is used to modify user accounts in Ubuntu. To add a user account to the sudo group, use the following command:</p>
  <pre><code>sudo usermod -aG sudo &lt;username&gt;</code></pre>
  <p>Replace &lt;username&gt; with the desired user account. This command will add the specified user account to the sudo group.</p>
  <h3>Verification</h3>
  <p>To check if the user has been added to the sudo group, switch to that user and enter the following command:</p>
  <pre><code>sudo apt update</code></pre>
  <p>If the command executes properly, it means that sudo has been made available for the specified user account in Ubuntu.</p>
  <h2>Method 2: Editing the sudoers File</h2>
  <p>Another way to grant sudo access to a user account is to edit the sudoers file. This file contains information about which users are allowed to use sudo. To edit the sudoers file, use the following command:</p>
  <pre><code>sudo visudo</code></pre>
  <p>This will launch the default editor, which is usually nano, and open the sudoers file.</p>
  <p>Look for the following line in the file:</p>
  <pre><code>%sudo   ALL=(ALL:ALL) ALL</code></pre>
  <p>Add a new line with the desired username under the above line:</p>
  <pre><code>&lt;username&gt;   ALL=(ALL:ALL) ALL</code></pre>
  <p>For example:</p>
  <pre><code>myuser   ALL=(ALL:ALL) ALL</code></pre>
  <p>Save the modified sudoers file by pressing Ctrl+X, then Y, and finally Enter to return to the terminal.</p>
  <h3>Verification</h3>
  <p>To verify that the user has been successfully added to the sudo group, switch to that user and run the following update command:</p>
  <pre><code>sudo apt update</code></pre>
  <p>If the command runs successfully, it means that sudo has been enabled on the user account in Ubuntu.</p>
  <h2>Additional Tips</h2>
  <p>When granting sudo access to a user account, keep the following tips in mind:</p>
  <ul>
    <li>Be cautious when modifying the sudoers file, as a mistake in the file can cause the sudo command to become unusable.</li>
    <li>Only grant sudo access when it is necessary, as this can help prevent accidental damage to the system.</li>
    <li>Always use sudo with caution and make sure youare familiar with the command and its effects on the system before running it with sudo privileges.</li>
  </ul>
  <h2>Conclusion</h2>
  <p>By default, only the root user has sudo access on Ubuntu systems. To enable sudo privileges for a desired user, you need to add that user to the sudo group. You can do this by using the usermod command or by manually editing the sudoers file. Once you have granted sudo access to a user account, you can run commands with sudo privileges as a regular user.</p>
</article>