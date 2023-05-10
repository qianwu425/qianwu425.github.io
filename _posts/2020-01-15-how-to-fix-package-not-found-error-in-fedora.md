---
title: How to Fix "Package Not Found" Error in Fedora
description: Fedora's package manager, DNF, is used to install packages in the system. However, sometimes you may encounter an error message in the terminal that says "No package found." This error message suggests that your Fedora system is unable to locate the package you want to install. In this article, we will explore the reasons behind this problem and provide possible solutions to fix it.
date: 2020-01-15
layout: post
---

<article>
  <img alt="assorted-color cowboy hat lot" src="https://images.unsplash.com/photo-1529958030586-3aae4ca485ff?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEZpeCUyMCUyMlBhY2thZ2UlMjBOb3QlMjBGb3VuZCUyMiUyMEVycm9yJTIwaW4lMjBGZWRvcmF8ZW58MHwwfHx8MTY4MzY2MDkyMw&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Fedora's package manager, DNF, is used to install packages in the system. However, sometimes you may encounter an error message in the terminal that says "No package found." This error message suggests that your Fedora system is unable to locate the package you want to install. In this article, we will explore the reasons behind this problem and provide possible solutions to fix it.</p>
  <h2>Possible Solutions for "Package Not Found" Error</h2>
  <p>If you encounter the "Package Not Found" error in Fedora, try the following potential solutions:</p>
  <h3>1. Check the Package Name</h3>
  <p>Typographical errors are common while typing instructions in the terminal. Ensure that you have entered the correct package name. For instance, if you want to install "neofetch" but type "neotouch" instead, the program will not work.</p>
  <h3>2. Update the Repository Cache</h3>
  <p>When you run the installation command, DNF searches the cache to obtain package information and then downloads it from the repositories. If the package you want to install is unavailable, the command will not work. Updating the cache is a good idea to ensure that the repository has the most up-to-date version of the package. To update the cache, run the following command:</p>
  <pre><code>sudo dnf makecache</code></pre>
  <h3>3. Check If the Package Is Available for Your Fedora Version</h3>
  <p>It's possible that the package you want to install is not available for your current version of Fedora. To check its availability, run the following command to find the name and version of your system:</p>
  <pre><code>cat /etc/fedora-release</code></pre>
  <p>After running the command, go to the Fedora packages website and navigate to the "Search package contents" section. Enter the name of the package, choose the distribution, and click the "Search" button. The results will indicate if the package is available and which repository it belongs to. For example, if we search for "neofetch" on the "Fedora 35" distribution, we get the following results:</p>
  <h3>4. Check If Your Fedora Version Is Active</h3>
  <p>Fedora releases a new version every six months, and each version is supported for 13 months. If you are using a Fedora release that is about to end, you may not be able to install packages on the system. Use the following command to check if your version is active:</p>
  <pre><code>dnf version-status</code></pre>
  <p>If your version is about to end, consider upgrading to a newer version.</p>
  <h3>5. Use Third-Party Repositories</h3>
  <p>If the package you want to install is not available in the official Fedora repositories, you can use third-party repositories. Some third-party repositories offer packages not found in the official repositories or provide updated versions of the packages. To add a third-party repository, locate its URL and run the following command:</p>
  <pre><code>sudo dnf config-manager --add-repo REPO_URL</code></pre>
  <p>For example, to add the Google Chrome repository, you can use the following command:</p>
  <pre><code>sudo dnf config-manager --add-repo httpsdl.google.com/linux/chrome/rpm/stable/x86_64</code></pre>
  <h2>Conclusion</h2>
  <p>Managing package installation and management in Fedora is usually done through the command line, using DNF. However, encountering the "Package Not Found" error can be frustrating. In this article, we have provided solutions to resolve this error, including checking the package name for typos, updating the repository cache, verifying the availability of the package for your Fedora version, checking if your Fedora version is active, and using third-party repositories. By following these fixes, you can successfully install the package and avoid the error message.</p>
  <h2>Additional Tips</h2>
  <p>If you encounter a package that is not available in the official Fedora repositories, consider the following tips:</p>
  <ul>
    <li>Make sure that your system is up to date by running the following command:</li>
    <pre><code>sudo dnf upgrade</code></pre>

<li>Use the correct repository for your Fedora version. If you are using an older version of Fedora, you may need to use an older repository.</li>

<li>If you are still having trouble installing a package, try searching for a solution online. Many online forums and communities provide help and advice for Linux users.</li>
  </ul>
</article>
