---
title: "How to Check Installed Package Version on Fedora"
description: "If you're using Fedora, keeping your software up-to-date is essential to maintaining a secure and efficient system. Before updating any software, however, you need to determine which version is currently installed. This guide explains several methods you can use to check the installed package version on Fedora."
date: 2020-01-14
layout: post
---

<article>
  <img alt="assorted-color cowboy hat lot" src="https://images.unsplash.com/photo-1529958030586-3aae4ca485ff?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENoZWNrJTIwSW5zdGFsbGVkJTIwUGFja2FnZSUyMFZlcnNpb24lMjBvbiUyMEZlZG9yYXxlbnwwfDB8fHwxNjgzNjYwOTIw&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're using Fedora, keeping your software up-to-date is essential to maintaining a secure and efficient system. Before updating any software, however, you need to determine which version is currently installed. This guide explains several methods you can use to check the installed package version on Fedora.</p>
  <h2>How to Check Installed Package Version on Fedora</h2>
  <p>There are several ways to check the version of an installed package on Fedora:</p>
  <h2>Method 1: Check Version with Package Option</h2>
  <p>You can use either the -v or --version option with the package name to check its installed version, depending on which package is installed on your system. For example:</p>
  <code>chromium-browser --version</code> or <code>chromium-browser -v</code>
  <h2>Method 2: Use dnf Command</h2>
  <p>The dnf command is the default package manager for Fedora. You can use it with the info option and the package name to check the installed package version. The general syntax of the command is:</p>
  <code>dnf info &lt;package_name&gt;</code>
  <p>You can use the --allversions flag to check all available options for the specific package in the repository. For example:</p>
  <code>dnf info curl --allversions</code>
  <h2>Method 3: Use rpm Command</h2>
  <p>The rpm command is used to query the installed packages on Fedora. To get the output of the version of the installed package, run the following command:</p>
  <code>rpm -q &lt;package_name&gt;</code>
  <p>You can use this command to check the version of curl:</p>
  <code>rpm -q curl</code>
  <p>The output shows the installed version of curl. If the package is not installed on your system, you will see the "none" value for an installed option.</p>
  <h2>Method 4: Use repoquery Command-Line Tool</h2>
  <p>The repoquery command-line tool from the yum-utils package can also be used to check for the installed package version on Fedora. Before using it, you need to install it on the Fedora system using the following command:</p>
  <code>sudo dnf install yum-utils -y</code>
  <p>Once yum-utils is installed, use the following syntax command to get the version of the package:</p>
  <code>repoquery --installed &lt;package_name&gt;</code>
  <p>Replace the package with the name of the package you want to check. For example:</p>
  <code>repoquery --installed curl</code>
  <h2>Method 5: Use rpmconf Command-Line Utility</h2>
  <p>You can also install the rpmconf command-line utility using the following command to check the version of the installed package on Fedora:</p>
  <code>sudo dnf install rpmconf -y</code>
  <p>Input the name of the package with the rpmconf command to get the list of available packages:</p>
  <code>rpmconf -a --query &lt;package_name&gt;</code>
  <h2>Method 6: Use dnf Command with grep Option</h2>
  <p>The installed version of the package can be returned using the dnf command with the info and grep package name options. For example:<!--<code-->dnf info <package_name> | grep Version
  </package_name></p><h2>Method 7: Use package-cleanup Command</h2>
  <p>You can use the package-cleanup command from the yum-utils package to check for installed package versions on Fedora. This command can also be used to delete obsolete or unused packages from the system. Run the following command to determine the installed package version:</p>
  <code>sudo package-cleanup --qf %{VERSION}-%{RELEASE} &lt;package_name&gt;</code>
  <p>Replace the package with the name of the package you want to check. For example:</p>
  <code>sudo package-cleanup --qf %{VERSION}-%{RELEASE} curl</code>
  <h2>Method 8: Check Installed Package Version with Release Number</h2>
  <p>If you want to check the installed package version along with its release number, you can use the following command:</p>
  <code>rpm -qa --queryformat "%{NAME} %{VERSION}-%{RELEASE}\n" &lt;package_name&gt;</code>
  <p>Replace the package with the name of the package you want to check. For example:</p>
  <code>rpm -qa --queryformat "%{NAME} %{VERSION}-%{RELEASE}\n" curl</code>
  <h2>Wrap-Up</h2>
  <p>Knowing the version of the installed package is important for maintaining the stability and security of your system. You can check the installed package version on Fedora using any of the eight techniques described in this guide. Whether you're a beginner or an advanced user, these methods allow you to check the installed version of any package and keep your system up-to-date and secure.</p>
</article>