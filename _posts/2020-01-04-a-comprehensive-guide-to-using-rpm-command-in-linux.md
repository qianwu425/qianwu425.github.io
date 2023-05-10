---
title: "A Comprehensive Guide to Using RPM Command in Linux"
description: "RPM (Red Hat Package Manager) is a command-line utility for managing software packages on Linux systems. This guide provides a detailed description of the RPM command, including its syntax, options, and several examples of how to use it."
date: 2020-01-04
layout: post
---

<article>
  <img alt="silhouette of man holding flashlight" src="https://images.unsplash.com/photo-1553708881-112abc53fe54?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxBJTIwQ29tcHJlaGVuc2l2ZSUyMEd1aWRlJTIwdG8lMjBVc2luZyUyMFJQTSUyMENvbW1hbmQlMjBpbiUyMExpbnV4fGVufDB8MHx8fDE2ODM2NjA4OTQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>RPM (Red Hat Package Manager) is a command-line utility for managing software packages on Linux systems. This guide provides a detailed description of the RPM command, including its syntax, options, and several examples of how to use it. </p>
  <h2>1. Definition of the RPM Command</h2>
  <p>
    RPM is a tool for managing software packages on Linux systems. It enables users to install, remove, upgrade, and verify software packages in the RPM format, which is a binary format that contains all the files required to install and run the software.
  </p>
  <h2>2. RPM Command Syntax</h2>
  <p>The syntax for the RPM command is as follows: </p>
  <p>    rpm [OPTIONS] [PACKAGE]</p>
  <p>
    Here, [OPTIONS] are the command options that can be passed to the RPM command, and [PACKAGE] is the package to manage.
  </p>
  <h2>3. RPM Command Options</h2>
  <p>
    To see the complete list of command options, run:
  </p>
  <p>
    sudo rpm --help
  </p>
  <p>The following are some commonly used RPM command options:
  </p>
  <ul>
    <li>-i: to install a package</li>
    <li>-U: to upgrade a package</li>
    <li>-e: to remove a package</li>
    <li>-q: to query a package</li>
    <li>-V: to verify a package</li>
    <li>-F: to freshen an installed package</li>
    <li>-h: to display help for a specified RPM command</li>
    <li>-v: to enable verbose mode</li>
    <li>--test: to enable test mode</li>
    <li>--nodeps: to skip dependency checks when installing, upgrading, or removing a package</li>
  </ul>
  <p>
    For a complete list of options, refer to the RPM manual page by running:
  </p>
  <p>
    man rpm
  </p>
  <h2>4. Installing RPM Packages</h2>
  <p>To install an RPM package with the RPM command, use the following syntax:</p>
  <p>
    sudo rpm -ivh [PACKAGE]
  </p>
  <p>
    Before installing, ensure that the appropriate package file compatible with the system architecture is downloaded. For example, to install the Apache HTTP server RPM package, use the following command:
  </p>
  <p>
    sudo rpm -ivh apache-httpd-2.4.48-1.x86_64.rpm
  </p>
  <p>
    Alternatively, an RPM package can be installed using a download link with the following command:
  </p>
  <p>
    sudo rpm -ivh [PACKAGE_URL]
  </p>
  <h2>5. Upgrading RPM Packages</h2>
  <p>
    To upgrade packages, use the following syntax:
  </p>
  <p>
    sudo rpm -Uvh [PACKAGE]
  </p>
  <p>
    To upgrade the Apache HTTP server, use:
  </p>
  <p>
    sudo rpm -Uvh apacheHTTPd-2.4.48-1.x86_64.rpm
  </p>
  <p>
    If the new version requires additionaldependencies, you may need to manually install them. When you run the command, RPM will show the required dependencies that are missing in the output. To ignore the message and update without dependencies, the --nodeps option can be added to the command:
  </p>
  <p>
    sudo rpm -Uvh --nodeps [PACKAGE]
  </p>
  <h2>6. Removing RPM Packages</h2>
  <p>To uninstall RPM packages, use the following command:</p>
  <p>
    sudo rpm -e [PACKAGE]
  </p>
  <p>For example, to uninstall the Apache HTTP server RPM, use:
  </p>
  <p>
    sudo rpm -e apache-httpd
  </p>
  <p>
    An alternative option for uninstalling RPM packages is using dnf. For example, to remove apache-httpd using the dnf command, run:
  </p>
  <p>
    sudo dnf remove apache-httpd.x86_64
  </p>
  <h2>7. Listing Installed RPM Packages</h2>
  <p>
    To list all installed RPM packages, run the following command:
  </p>
  <p>
    sudo rpm -qa
  </p>
  <p>
    The command includes the -qa option, which instructs RPM to query all installed packages.
  </p>
  <h2>8. Displaying Package Information Before Installing</h2>
  <p>
    Before installing a package, use the following command to display information about the RPM package:
  </p>
  <p>
    sudo rpm -qip [PACKAGE]
  </p>
  <p>
    To obtain information about a package and confirm its validity, use the following options:
  </p>
  <ul>
    <li>-qi: to query information</li>
    <li>-p: to query/verify a package</li>
  </ul>
  <p>For example, to display information related to the Apache HTTP server RPM package, run:
  </p>
  <p>
    sudo rpm -qip apache-httpd-2.4.48-1.x86_64.rpm
  </p>
  <h2>9. Displaying Package Information After Installing</h2>
  <p>The available information in an RPM package can be seen by using the -qi option, which instructs the application to query the package details:</p>
  <p>
    sudo rpm -qi [PACKAGE]
  </p>
  <p>The output includes details about the package. For example, the following command will provide information on apache-httpd:</p>
  <p>
    sudo rpm -qi apache-httpd
  </p>
  <h2>10. Checking RPM Package Dependencies Before Installing</h2>
  <p>
    The RPM command also allows us to check the dependencies of packages before we can install them. Ensure that the RPM package is already downloaded for which you want to see the list of dependencies.
  </p>
  <p>
    Use the following command syntax:
  </p>
  <p>
    rpm -qpR [PACKAGE]
  </p>
  <p>
    The command includes the following list of options:
  </p>
  <ul>
    <li>-q: to query format</li>
    <li>-p: to query/verify a package</li>
    <li>-R: to list package dependencies</li>
  </ul>
  <p>For example, to see a list of all the dependencies required by the apache-httpd package,type:</p>
  <p>
    rpm -qpR apache-httpd-2.4.48-1.x86_64.rpm
  </p>
  <h2>11. Listing All Files of an Installed Package</h2>
  <p>We may also use the -ql option to list all the files linked with a package, instructing RPM to query the list:</p>
  <p>
    sudo rpm -ql [PACKAGE]
  </p>
  <p>
    For example, we can list apache-httpd RPM package files using:
  </p>
  <p>
    sudo rpm -ql apache-httpd
  </p>
  <h2>12. RPM Command in Different Linux Distributions</h2>
  <p>While the RPM command is functionally equivalent across Linux distributions, there may be minor changes in usage and syntax. Here's a quick rundown of RPM commands in various Linux distributions:</p>
  <h3>RPM Package Management in Red Hat-Based Systems</h3>
  <p>
    In Red Hat-based systems, RPM is the default package manager. The RPM package management system is used to manage software packages in these systems. To install a package in a Red Hat-based system, you can use the following command:
  </p>
  <p>
    sudo dnf install [PACKAGE]
  </p>
  <p>
    To remove a package, you can use the following command:
  </p>
  <p>
    sudo dnf remove [PACKAGE]
  </p>
  <h3>RPM Package Management in Debian-Based Systems</h3>
  <p>
    In Debian-based systems, the default package manager is apt. However, you can still use RPM to manage packages in these systems.
  </p>
  <p>
    RPM is a package manager for the Red Hat system, so by default, it is not installed on Debian. To install the RPM package manager in a Debian-based Linux system, run:
  </p>
  <p>
    sudo apt install rpm
  </p>
  <p>
    sudo apt install alien
  </p>
  <p>
    To install a package in a Debian-based system using RPM, you can use the following command:
  </p>
  <p>
    sudo alien -i [PACKAGE.rpm]
  </p>
  <p>Please keep in mind that the alien utility will convert the RPM package to deb, which you can then install with the following command:</p>
  <p>
    sudo apt install ./&lt;deb_file&gt;
  </p>
  <h3>RPM Package Management in Arch-Based Systems</h3>
  <p>
    In Arch-based systems, the default package manager is pacman. However, you can still use RPM to manage packages in these systems. To install a package in an Arch-based system using RPM, you can use the following command:
  </p>
  <p>
    sudo pacman -U [PACKAGE.rpm]
  </p>
  <h2>Conclusion</h2>
  <p>
    The RPM command is a powerful tool for managing software packages in Linux. Whether you're installing new packages, upgrading existing ones, or removing old ones, RPM makes it easy to keep your system up-to-date and running smoothly. By following the tips and tricks mentioned in this article, you can become proficient in using the RPM command for managing software packages.
  </p>
</article>