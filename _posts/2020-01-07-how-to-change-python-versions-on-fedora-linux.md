---
title: "How to Change Python Versions on Fedora Linux"
description: "If you're running Fedora Linux and need to switch to a different version of Python, this guide will show you how. Fedora comes with a default Python version preinstalled, but some applications may require a specific version of Python. Here's how to change from the default to an alternative Python version without hassle."
date: 2020-01-07
layout: post
---

<article>
  <img alt="Change neon light signage" src="https://images.unsplash.com/photo-1499244571948-7ccddb3583f1?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENoYW5nZSUyMFB5dGhvbiUyMFZlcnNpb25zJTIwb24lMjBGZWRvcmElMjBMaW51eHxlbnwwfDB8fHwxNjgzNjYwODk5&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're running Fedora Linux and need to switch to a different version of Python, this guide will show you how. Fedora comes with a default Python version preinstalled, but some applications may require a specific version of Python. Here's how to change from the default to an alternative Python version without hassle.</p>
  <h2>Check the Current Version of Default Python on Fedora Linux</h2>
  <p>Before you change the default Python version, you should verify which versions are already installed on your system. The Python directory on Fedora and other Linux-based systems is usually located in /usr/bin/python. To find out which Python versions are installed, run the following command:</p>
  <pre><code>ls /usr/bin/python*</code></pre>
  <p>Note that the output may vary depending on your system.</p>
  <p>To determine the current version of Python on Fedora, run the following command:</p>
  <pre><code>python --version</code></pre>
  <p>The output will show the current default version of Python on your system, such as 3.10.0, but this may differ depending on your system.</p>
  <h2>Change from Default to Alternative Python Version on Fedora Linux</h2>
  <p>There are two ways to switch from the default to an alternative Python version on Fedora Linux:</p>
  <h3>Method 1: Use update-alternatives command</h3>
  <p>The first method involves creating a symlink between different Python version directories and merging them into a group named "python" using the update-alternatives command. For instance, to use Python 3.9 as the alternative version, create a symlink by running:</p>
  <pre><code>sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.9 2</code></pre>
  <p>Similarly, you can establish a symlink for Python version 3.8.2 by running:</p>
  <pre><code>sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.8.2 3</code></pre>
  <p>After creating the symlinks, use the following command to switch between the installed Python versions:</p>
  <pre><code>sudo update-alternatives --config python</code></pre>
  <p>You'll see a list of available Python versions, with the default version (e.g., 3.10) selected. Enter the number corresponding to the version you want to use and press Enter to set it as the default version. Finally, verify the installed version of Python by running:</p>
  <pre><code>python --version</code></pre>
  <h3>Method 2: Use pyenv Tool</h3>
  <p>The second way involves using the pyenv utility to manage several Python versions on Fedora Linux. Follow these steps:</p>
  <p><strong>Step 1:</strong> Update the system and install necessary dependencies using:</p>
  <pre><code>sudo dnf update ; sudo dnf install make gcc openssl-devel bzip2-devel libffi-devel zlib-devel sqlite-devel readline-devel tk-devel libuuid-devel liblzma-devel</code></pre>
  <p><strong>Step 2:</strong> Run the following command to install pyenv:</p>
  <pre><code>curl https://pyenv.run | bash</code></pre>
  <p><strong>Step 3:</strong> Open the source filefor environmental variables using the following command:</p>
  <pre><code>sudo nano ~/.bashrc</code></pre>
  <p>Add the following script to the bottom of the file:</p>
  <pre><code>export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"</code></pre>
  <p><strong>Step 4:</strong> Reload the changes to the environment variable using:</p>
  <pre><code>source ~/.bashrc</code></pre>
  <p><strong>Step 5:</strong> Verify the installation of pyenv using:</p>
  <pre><code>pyenv --version</code></pre>
  <p><strong>Step 6:</strong> Run the following command to see what Python versions are available:</p>
  <pre><code>pyenv install --list</code></pre>
  <p><strong>Step 7:</strong> Install the desired version of Python (e.g., 3.9.7) using:</p>
  <pre><code>pyenv install 3.9.7</code></pre>
  <p><strong>Step 8:</strong> Run the following command to make the installed version the global default for all users:</p>
  <pre><code>pyenv global 3.9.7</code></pre>
  <p>Finally, confirm the changes by running:</p>
  <pre><code>python --version</code></pre>
  <h2>Additional Tips</h2>
  <p>Here are some additional tips to help you manage your Python versions on Fedora Linux:</p>
  <h3>Uninstall Python Versions</h3>
  <p>To uninstall a specific version of Python that you installed through pyenv, use the following command:</p>
  <pre><code>pyenv uninstall VERSION</code></pre>
  <p>Replace VERSION with the version number you want to remove.</p>
  <h3>Switch Python Version Locally</h3>
  <p>If you want to switch the Python version for a specific project or directory, use the following command:</p>
  <pre><code>pyenv local VERSION</code></pre>
  <p>Replace VERSION with the desired version number.</p>
  <h3>Set Python Version for a Shell Session</h3>
  <p>If you want to set the Python version for your current shell session, use the following command:</p>
  <pre><code>pyenv shell VERSION</code></pre>
  <p>Replace VERSION with the version number you want to use.</p>
</article>
