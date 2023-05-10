---
title: "How to Install Pip3 and Pip2 on Ubuntu 20.04"
description: "Pip is a popular package management tool for Linux-based operating systems like Ubuntu, widely used for installing and managing Python applications. There are two variations of Pip available for Ubuntu - pip3 for Python 3 and pip2 for Python 2."
date: 2020-01-21
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBQaXAzJTIwYW5kJTIwUGlwMiUyMG9uJTIwVWJ1bnR1JTIwMjAuMDR8ZW58MHwwfHx8MTY4MzY2MDkzNw&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Pip is a popular package management tool for Linux-based operating systems like Ubuntu, widely used for installing and managing Python applications. There are two variations of Pip available for Ubuntu - pip3 for Python 3 and pip2 for Python 2.</p>
  <h2>Installation Process</h2>
  <p>Before installing Pip on Ubuntu, it is recommended to update the package list. To do so, run the following command:</p>
  <code>sudo apt update &amp;&amp; sudo apt upgrade -y</code>
  <p>Ensure that Python 3 is installed on your system by running:</p>
  <code>python3 -V</code>
  <p>If you want to use Pip with Python 2, you'll need to install Python 2 on Ubuntu. To do so, run either of the following commands:</p>
  <code>sudo apt install python</code>
  <p>or</p>
  <code>sudo apt install python2</code>
  <h3>Installing Pip3 on Ubuntu 20.04</h3>
  <p>To install Pip3 and its dependencies on Ubuntu 20.04, run:</p>
  <code>sudo apt install python3-venv python3-pip</code>
  <p>You can then upgrade Pip3 using:</p>
  <code>sudo -H pip3 install --upgrade pip</code>
  <p>To check if Pip3 is properly installed, run:</p>
  <code>pip3 --version</code>
  <h3>Installing Pip2 on Ubuntu 20.04</h3>
  <p>To install Pip2 on Ubuntu 20.04, run the following commands:</p>
  <code>wget https://bootstrap.pypa.io/pip/2.7/get-pip.py <br/>python2 get-pip.py</code>
  <p>To verify the installation of Pip2, run:</p>
  <code>python2 -m pip --version</code>
  <h2>Using Pip on Ubuntu 20.04</h2>
  <p>To install a package using Pip3, run:</p>
  <code>pip3 install &lt; package_name &gt;</code>
  <p>For example, to install NumPy, type:</p>
  <code>pip3 install numpy</code>
  <p>To install the same package using Pip2, run:</p>
  <code>pip install numpy</code>
  <h2>Uninstalling Pip3 or Pip2 Packages on Ubuntu 20.04</h2>
  <p>To uninstall a package installed using Pip3, run:</p>
  <code>pip3 uninstall &lt; package_name &gt;</code>
  <p>To uninstall a Pip2-installed package, type:</p>
  <code>pip uninstall &lt; package_name &gt;</code>
  <h2>Conclusion</h2>
  <p>Installing Pip3 and Pip2 on Ubuntu 20.04 is a straightforward process. Once you have installed Python 3 and/or Python 2, you can follow the given commands to install Pip3 and Pip2, respectively. Once the installation is done, you can use Pip3 or Pip2 with the package name to install a Python package on Ubuntu. If you want to uninstall a package, use the appropriate pip uninstall command.</p>
</article>