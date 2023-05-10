---
title: "How to Install Programs in Ubuntu Using Command Line"
description: "If you're using a Linux-based operating system like Ubuntu, you have the powerful package manager application called apt pre-installed. With apt, you can manage packages from the local Linux system repository, including updates, installations, and removals. Installing packages via apt is generally preferred over using alternative sources such as snap."
date: 2020-01-30
layout: post
---

<article>
<img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBQcm9ncmFtcyUyMGluJTIwVWJ1bnR1JTIwVXNpbmclMjBDb21tYW5kJTIwTGluZXxlbnwwfDB8fHwxNjgzNjYwOTU5&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
<p>If you're using a Linux-based operating system like Ubuntu, you have the powerful package manager application called apt pre-installed. With apt, you can manage packages from the local Linux system repository, including updates, installations, and removals. Installing packages via apt is generally preferred over using alternative sources such as snap.</p>
<p>In this guide, we will provide instructions for installing programs via apt from the command line in Ubuntu. Although we will focus on Ubuntu 22.04, these steps are applicable to other Linux distributions as well.</p>
<h2>Using apt to Install Programs in Ubuntu from Command Line</h2>
<p>In this guide, we will cover the following tasks:</p>
<h2>1. Installing a Package from the Repository</h2>
<p>To install any package from the official Linux repository using apt, use the following syntax:</p>
<pre><code>sudo apt install &lt; Package / Program name &gt;</code></pre>
<p>For instance:</p>
<pre><code>sudo apt install chromium-browser</code></pre>
<h2>2. Installing a Package Using a .deb File</h2>
<p>If the latest version of a package/program is not available in the official Ubuntu repository, you can install a new version using .deb files. To install packages from .deb files, use the following syntax:</p>
<pre><code>sudo apt install . /&lt; filename.deb &gt;</code></pre>
<p>For example:</p>
<pre><code>sudo apt install . / brave-browser.deb</code></pre>
<p>Please note that you need to download the .deb file for that package/program before installing it.</p>
<h2>3. Updating the Repository</h2>
<p>You can use the apt package manager to update the local repository of the system. By running the apt update command, you can view the latest versions of all available programs/packages and their dependencies. It is usually recommended to run the following update command before installing any package from the repository:</p>
<pre><code>sudo apt update</code></pre>
<h2>4. Adding a PPA Repository</h2>
<p>To install apps from an external PPA repository, you need to add the repository first. Use the following syntax in Ubuntu to add a new PPA repository:</p>
<pre><code>sudo add-apt-repository ppa: &lt; repository name &gt;</code></pre>
<p>For example:</p>
<pre><code>sudo add-apt-repository ppa:inkscape.dev/stable</code></pre>
<p>You can install a package from the PPA repository by using the command line after adding the PPA repository:</p>
<pre><code>sudo apt install &lt; package_name &gt;</code></pre>
<h2>5. Removing a Package</h2>
<p>You can remove packages from the system that are no longer required by using the following syntax:</p>
<pre><code>sudo apt remove &lt; package_name &gt;</code></pre>
<p>For example:</p>
<pre><code>sudo apt remove gimp</code></pre>
<p>Keep in mind that removing a package does not remove its associated configuration files. To remove the configuration files as well, use the following syntax:</p>
<pre><code>sudo apt purge &lt; package_name &gt;</code></pre>
<h2>6. Upgrading Packages</h2>
<p>You can update the packages already installed on the system to their most recent versions by using the following syntax:</p>
<pre><code>sudo apt upgrade<p>The upgrade command will update all the installed packages on your system to their most recent versions.</p>
<h2>7. Searching for a Package</h2>
<p>You can search for packages in the local repository by using the following syntax:</p>
<pre><code>sudo apt search &lt; search_term &gt;</code></pre>
<p>For example:</p>
<pre><code>sudo apt search vlc</code></pre>
<p>This command will display a list of packages that match the search keyword.</p>
<h2>Conclusion</h2>
<p>If you're using Ubuntu, apt is a powerful tool for managing packages on your system. In this article, we have provided instructions for using apt to install, remove, update, and search for packages from the command line in Ubuntu. By following these steps, you can keep your Ubuntu system up-to-date with the latest software available in the repository.</p>
</code></pre></article>