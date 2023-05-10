---
title: "How to Generate SSH Keys on Windows to Access Linux Servers Without Passwords"
description: "If you need to connect to Linux servers frequently, SSH keys can make the process more efficient and secure. This guide provides a step-by-step process to create SSH keys on Windows and use them to access Linux servers without requiring a password. These instructions apply to Windows systems that support OpenSSH, such as Windows 10 and 11."
date: 2020-01-10
layout: post
---

<article>
  <img alt="white concrete building" src="https://images.unsplash.com/photo-1441105501384-23156f198d37?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEdlbmVyYXRlJTIwU1NIJTIwS2V5cyUyMG9uJTIwV2luZG93cyUyMHRvJTIwQWNjZXNzJTIwTGludXglMjBTZXJ2ZXJzJTIwV2l0aG91dCUyMFBhc3N3b3Jkc3xlbnwwfDB8fHwxNjgzNjYwOTA5&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you need to connect to Linux servers frequently, SSH keys can make the process more efficient and secure. This guide provides a step-by-step process to create SSH keys on Windows and use them to access Linux servers without requiring a password. These instructions apply to Windows systems that support OpenSSH, such as Windows 10 and 11.</p>
  <h2>Table of Contents:</h2>
  <ul>
    <li><a href="#install-openssh">Install the OpenSSH Client on Windows</a></li>
    <li><a href="#generate-keys">Generate SSH Keys on Windows</a></li>
    <li><a href="#locate-public-key">Locate the Public SSH Key on Windows</a></li>
    <li><a href="#access-linux">Access Linux Servers from Windows via SSH</a></li>
    <li><a href="#copy-public-key">Copy the SSH Public Key from Windows to Linux Servers</a></li>
    <li><a href="#test-login">Test Passwordless SSH Login to Linux Servers from Windows</a></li>
    <li><a href="#pageant">Using Pageant with SSH Keys</a></li>
    <li><a href="#ssh-config">Setting Up SSH Configurations on Windows</a></li>
  </ul>
  <h2 id="install-openssh">Installing the OpenSSH Client on Windows</h2>
  <p>You must install the OpenSSH client application on Windows to create SSH keys. You can obtain it from the official OpenSSH website or by using a package manager such as Chocolatey.</p>
  <h2 id="generate-keys">Creating SSH Keys on Windows</h2>
  <p>To create a new SSH key, launch a Command Prompt or PowerShell terminal on Windows and execute the following command:</p>
  <pre><code>ssh-keygen</code></pre>
  <p>You will be prompted to enter a passcode to secure the key. If you prefer not to use one, simply leave it blank.</p>
  <h2 id="locate-public-key">Finding the Public SSH Key on Windows</h2>
  <p>On Windows, the created SSH public key can be found in the <code>C:\Users\your-username\.ssh</code> directory. Using File Explorer, navigate to the directory and locate the <code>id_rsa.pub</code> file. Use a text editor to copy its contents.</p>
  <h2 id="access-linux">Accessing Linux Servers from Windows via SSH</h2>
  <p>To access a Linux server from Windows via SSH, launch a terminal and run the following command:</p>
  <pre><code>ssh &lt;username&gt;@&lt;hostname&gt;</code></pre>
  <p>Replace &lt;username&gt; and &lt;hostname&gt; with your Linux server's login username and domain name/IP address, respectively.</p>
  <h2 id="copy-public-key">Copying the SSH Public Key from Windows to Linux Servers</h2>
  <p>After logging in to the Linux server via SSH, paste the SSH public key from Windows into the <code>~/.ssh/authorized_keys</code> file on the Linux server using a text editor such as nano or vi:</p>
  <pre><code>nano ~/.ssh/authorized_keys</code></pre>
  <p>or</p>
  <pre><code>vi ~/.ssh/authorized_keys</code><!--  <p-->Paste the copied SSH public key into the file, save and close it. Confirm that the key has been saved by reading its contents with the following command:<p></p>
  <pre><code>cat ~/.ssh/authorized_keys</code></pre>
  <h2 id="test-login">Testing Passwordless SSH Login to Linux Servers from Windows</h2>
  <p>Open a new terminal on Windows and attempt to SSH into the Linux server using the following command:</p>
  <pre><code>ssh &lt;username&gt;@&lt;hostname&gt;</code></pre>
  <p>You should be able to log in to the Linux server without being prompted for a password.</p>
  <h2 id="pageant">Using Pageant with SSH Keys</h2>
  <p>Pageant is a Windows key management utility that allows you to use SSH keys without having to enter the passphrase each time. To use Pageant with SSH keys, follow these steps:</p>
  <ol>
    <li>Download and install Pageant from the PuTTY website.</li>
    <li>Launch Pageant and add your SSH private key by clicking on the "Add Key" button and selecting your private key file.</li>
    <li>Enter the passphrase for your key when prompted. Pageant will store the key in memory, enabling you to authenticate with remote servers without having to enter the passphrase every time.</li>
    <li>Set the environment variable <code>SSH_AUTH_SOCK</code> to the location of the Pageant named pipe to configure your SSH client to use Pageant. For example, if you installed Pageant in the default location, you can set the variable as follows:</li>
  </ol>
  <pre><code>set SSH_AUTH_SOCK=C:\Program Files\PuTTY\pageant.exe</code></pre>
  <h2 id="ssh-config">Configuring SSH on Windows</h2>
  <p>You can set up SSH configurations on Windows to simplify the process of connecting to remote servers. Follow these steps to configure SSH:</p>
  <ol>
    <li>Open the SSH configuration file <code>config</code> in a text editor. The file is located in the <code>C:\Users\&lt;your-username&gt;\.ssh</code> folder.</li>
    <li>Add a new configuration block for each remote server you want to connect to. For example:</li>
  </ol>
  <pre><code>Host myserver
    HostName myserver.example.com
    User myusername
    IdentityFile C:\Users\myusername\.ssh\id_rsa
</code></pre>
  <ol start="3">
    <li>Save the configuration file.</li>
    <li>To connect to a remote server, simply type the following command in a terminal:</li>
  </ol>
  <pre><code>ssh myserver</code></pre>
  <p>The SSH client will automatically read the configuration file and connect to the remote server with the supplied options.</p>
  <h2>Conclusion</h2>
  <p>By following the instructions provided in this guide, you can create SSH keys on Windows and use them to access Linux servers without having to enter a password. You can also utilize Pageant to manage your SSH keys and configure SSH to simplify the process of connecting to remote servers.</p>
</pre></article>