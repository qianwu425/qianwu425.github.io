---
title: "How to Reinstall Packages on Ubuntu 21.04 Using APT or Apt-get"
description: "If you are an Ubuntu 21.04 user, you may need to reinstall packages on your system at times. Reinstalling a package can fix any issues you may be experiencing, such as when the package is not working correctly or has become corrupted. Similarly, reinstalling a package can restore its default configuration files if you have made changes to them."
date: 2020-01-14
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFJlaW5zdGFsbCUyMFBhY2thZ2VzJTIwb24lMjBVYnVudHUlMjAyMS4wNCUyMFVzaW5nJTIwQVBUJTIwb3IlMjBhcHQtZ2V0fGVufDB8MHx8fDE2ODM2NjA5MTk&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you are an Ubuntu 21.04 user, you may need to reinstall packages on your system at times. Reinstalling a package can fix any issues you may be experiencing, such as when the package is not working correctly or has become corrupted. Similarly, reinstalling a package can restore its default configuration files if you have made changes to them.</p>
  <p>APT (Advanced Packaging Tool) is a package manager that simplifies package installation, upgrade, and removal on Ubuntu 21.04. In this guide, we will explain how you can use APT or apt-get commands to reinstall packages on Ubuntu 21.04 easily.</p>
  <h2>Reasons to Reinstall Packages on Ubuntu 21.04</h2>
  <p>There could be multiple reasons to reinstall packages on Ubuntu 21.04. For example, you may want to reinstall a package to fix it when it is not working correctly or has become corrupted. Similarly, if you have changed a package's configuration files, you can reinstall it to restore the default settings.</p>
  <h2>Using APT or apt-get Reinstall on Ubuntu 21.04</h2>
  <p>You can use the APT or apt-get command-line interface to manage packages. Both commands support the reinstall option for package reinstallation.</p>
  <h2>Using apt Reinstall on Ubuntu 21.04</h2>
  <p>To reinstall a package on Ubuntu 21.04 using apt, use the following command:</p>
  <pre><code>sudo apt --reinstall install &lt;package_name&gt;</code></pre>
  <p>Replace &lt;package_name&gt; with the name of the package you want to reinstall. For example, to reinstall the vim package:</p>
  <pre><code>sudo apt --reinstall install vim</code></pre>
  <h2>Using apt-get Reinstall on Ubuntu 21.04</h2>
  <p>The apt-get command can also be used to reinstall packages. To do so, use the following command:</p>
  <pre><code>sudo apt-get --reinstall install &lt;package_name&gt;</code></pre>
  <p>Replace &lt;package_name&gt; with the name of the package you want to reinstall. For instance, to reinstall the git package and its dependencies:</p>
  <pre><code>sudo apt-get --reinstall install git</code></pre>
  <h2>Reinstalling Multiple Packages Through APT or apt-get Reinstall</h2>
  <p>You can also use APT or apt-get to reinstall multiple packages at once. To do so, use the following command:</p>
  <pre><code>sudo apt --reinstall install &lt;package1&gt; &lt;package2&gt; &lt;package3&gt; ...</code></pre>
  <p>Or:</p>
  <pre><code>sudo apt-get --reinstall install &lt;package1&gt; &lt;package2&gt; &lt;package3&gt; ...</code></pre>
  <p>To reinstall multiple packages simultaneously, replace &lt;package1&gt;, &lt;package2&gt;, and &lt;package3&gt; with the names of the packages you want to reinstall. For example, to reinstall the vim and git packages:</p>
  <pre><code>sudo apt-get --reinstall install vim git</code></pre>  <h2>Conclusion</h2>
  <p>Reinstalling packages on Ubuntu 21.04 using APT or apt-get is a straightforward process. By following the above steps, you can easily reinstall packages and fix any issues you may be experiencing or restore default settings on your Ubuntu 21.04 system. </p>
  <p>It is essential to keep your Ubuntu system up to date and ensure that you have the latest version of packages installed. In case you face any issues, you can always use the APT or apt-get command to reinstall packages.</p>
</article>