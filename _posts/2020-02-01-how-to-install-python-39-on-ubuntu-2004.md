---
title: "How to Install Python 3.9 on Ubuntu 20.04"
description: "If you're looking to install Python 3.9 on Ubuntu 20.04, this tutorial will guide you through the process. You'll learn how to install Python, modules, extensions, test your installation, upgrade to a newer version, and uninstall Python if necessary."
date: 2020-02-01
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBQeXRob24lMjAzLjklMjBvbiUyMFVidW50dSUyMDIwLjA0fGVufDB8MHx8fDE2ODM2NjA5NjQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're looking to install Python 3.9 on Ubuntu 20.04, this tutorial will guide you through the process. You'll learn how to install Python, modules, extensions, test your installation, upgrade to a newer version, and uninstall Python if necessary. </p>
  <h2>Install Python on Ubuntu 20.04</h2>
  <p>Here are the steps to install Python 3.9 on Ubuntu 20.04:</p>
  <ul>
    <li>Update the system repository with the following commands:</li>
    <code>sudo apt update</code>
    <code>sudo apt upgrade</code>
    <li>Install the required dependencies:</li>
    <code>sudo apt install -y build-essential checkinstall zlib1g-dev libffi-dev</code>
    <li>Download the Python 3.9 source code:</li>
    <code>wget https://www.python.org/ftp/python/3.9.7/Python-3.9.7.tgz</code>
    <li>Extract the downloaded file:</li>
    <code>tar -xf Python-3.9.7.tgz</code>
    <li>Change to the extracted directory:</li>
    <code>cd Python-3.9.7/</code>
    <li>Configure the build:</li>
    <code>./configure --enable-optimizations</code>
    <li>Build and install Python:</li>
    <code>make -j $(nproc)</code>
    <code>sudo make altinstall</code>
    <li>Verify that Python 3.9 is installed by running:</li>
    <code>python3.9 --version</code>
  </ul>
  <h2>Python Modules/Extensions</h2>
  <p>Once you have installed Python 3.9, you can install additional Python modules and extensions using pip:</p>
  <code>sudo apt install python3-pip</code>
  <p>To install a specific module, run:</p>
  <code>pip3 install &lt;module_name&gt;</code>
  <p>You can also install multiple modules at once using this syntax:</p>
  <code>pip3 install &lt;module1_name&gt; &lt;module2_name&gt; &lt;module3_name&gt;</code>
  <p>To list all installed Python modules, run:</p>
  <code>pip3 freeze</code>
  <h2>Testing Python</h2>
  <p>To test your Python installation, create a new Python file:</p>
  <code>sudo nano newfile.py</code>
  <p>Add the following text to the file:</p>
  <code>print("Hello World")</code>
  <p>To execute the file, run:</p>
  <code>python3.9 newfile.py</code><p>If the message is properly displayed, your system is running Python 3.9 correctly.</p>
  <h2>Uninstalling Python</h2>
  <p>If you want to remove Python 3.9 from your Ubuntu 20.04 system, use this command:</p>
  <code>sudo apt-get remove python3.9</code>
  <p>This will uninstall Python 3.9 and all of its dependencies from your system.</p>
  <h2>Upgrading Python</h2>
  <p>To upgrade to anewer version of Python, follow these steps:</p>
  <ol>
    <li>Update the system repository:</li>
    <code>sudo apt-get update</code>
    <li>Upgrade the installed packages:</li>
    <code>sudo apt-get upgrade</code>
    <li>Install the newer version of Python:</li>
    <code>sudo apt-get install python3.10</code>
    <li>Verify that the newer version is installed:</li>
    <code>python3.10 --version</code>
  </ol>
  <h2>Conclusion</h2>
  <p>Python is a powerful programming language with a wide range of applications. Installing Python 3.9 on Ubuntu 20.04 is a straightforward process that can be completed in a few simple steps. Once you've installed Python, you can use pip to install additional modules, test your installation, upgrade to a newer version, or uninstall Python if necessary. By following this tutorial, you should now be able to install and use Python 3.9 on Ubuntu 20.04 with ease.</p>
</article>