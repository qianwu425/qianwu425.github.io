---
title: "The Comprehensive Guide to Using Yum Command in Linux With Examples"
description: "yum is a powerful utility used for managing packages on Linux-based systems. It simplifies the process of installing, updating, upgrading, and removing packages. However, it is important to note that sudo privileges are required to execute certain tasks."
date: 2020-01-04
layout: post
---

<article>
    <img alt="silhouette of man holding flashlight" src="https://images.unsplash.com/photo-1553708881-112abc53fe54?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxUaGUlMjBDb21wcmVoZW5zaXZlJTIwR3VpZGUlMjB0byUyMFVzaW5nJTIweXVtJTIwQ29tbWFuZCUyMGluJTIwTGludXglMjB3aXRoJTIwRXhhbXBsZXN8ZW58MHwwfHx8MTY4MzY2MDg5NA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
    <p>yum is a powerful utility used for managing packages on Linux-based systems. It simplifies the process of installing, updating, upgrading, and removing packages. However, it is important to note that sudo privileges are required to execute certain tasks.</p>
    <p>This guide provides a comprehensive overview of the yum command in Linux, including examples of how to use it.</p>
    <h2>yum Linux Commands with Examples</h2>
    <p>This article includes an in-depth description of the yum command in Linux, as well as examples of how to use it.</p>
    <pre><code>sudo yum &lt;command&gt;</code></pre>
    <p>The yum command allows you to run the command with different arguments, which are listed below:</p>
    <table>
        <tbody>
            <tr>
                <td>Option</td>
                <td>Description</td>
            </tr>
            <tr>
                <td>-y</td>
                <td>Answer yes to prompts</td>
            </tr>
            <tr>
                <td>-v</td>
                <td>Verbose output</td>
            </tr>
            <tr>
                <td>-h</td>
                <td>Help guide</td>
            </tr>
            <tr>
                <td>remove</td>
                <td>Remove packages</td>
            </tr>
            <tr>
                <td>search</td>
                <td>Search package details</td>
            </tr>
            <tr>
                <td>list</td>
                <td>List installed packages</td>
            </tr>
        </tbody>
    </table>
    <h2>Examples of yum Commands in Linux</h2>
    <h3>Example 1: Installing a Package Using yum Command</h3>
    <p>To install a package from the Linux repository, use the following yum syntax, replacing "package-name" with the name of the package to be installed:</p>
    <pre><code>sudo yum install &lt;package-name&gt;</code></pre>
    <p>For instance, to install VLC media player, use:</p>
    <pre><code>sudo yum install vlc</code></pre>
    <h3>Example 2: Updating the System Using yum Command</h3>
    <p>To update the system using yum, use the following command:</p>
    <pre><code>sudo yum update</code></pre>
    <h3>Example 3: Upgrading Packages Using yum Command</h3>
    <p>The yum update command updates all of the packages in the repository. To obtain the most recent version of a package, always use the following command before installing it on your system:</p>
    <pre><code>sudo yum update &lt;package-name&gt;</code></pre>
    <p>If you only want to upgrade a single package, use the following command:</p>
    <pre><code>sudo yum update httpd</code></pre>
    <h3>Example 4: Searching for a Package Using the yum Command</h3>
    <p>To search for a package using yum, use the following command:</p>
    <pre><code>yum search &lt;package-name&gt;</code></pre>
    <p>For instance, to search for available Python packages, use:</p>
    <pre><code>yum search python</code></pre>
    <h3>Example 5: Cleaning the System Using yum</h3>
    <p>Whenever you run the yum command, the cache is stored in a specific folder on your system. This takes up space and can slow down your system. To free up disk space and remove unused packages, run the following command:</p>
    <pre><code>sudo yum clean all</code></pre>
    <h3>Example 6: Getting the List of Packages via yum Command</h3>
    <p>To check for all available updates on your system, run:</p>
    <pre><code>sudo yum check-update</code></pre>
    <p>And to receive a list of all installed packages, run:</p>
    <pre><code>sudo yum list all</code></pre>
    <h3>Example 7: Removing a Package Using yum Command</h3>
    <p>The yum remove command removes the binaries of a package. To remove a package and all its dependencies from your Linux system, use the following command:</p>
    <pre><code>sudo yum remove &lt;package-name&gt;</code></pre>
    <p>Note that removing packages leaves the user configuration files behind. To remove everything related to a package, including the configuration files, use the following command:</p>
    <pre><code>sudo yum remove --purge &lt;package-name&gt;</code></pre>
    <h2>Conclusion</h2>
    <p>Managing packages is an important part of using Linux, and the yum package manager simplifies this process by allowing you to install, remove, and update packages from the Linux repository. The yum command can be used in various ways, as demonstrated in the examples above, to perform specific tasks on your system.</p>
    <h2>Additional Tips for Using the yum Command</h2>
    <ul>
        <li><strong>Useful yum plugins:</strong> Yum has several plugins that can be used to extend its functionality. Some of the commonly used plugins include fastestmirror, which makes yum download packages from the fastest mirror available, and priorities, which allows you to prioritize certain repositories over others. To install a yum plugin, use the following command: <pre><code>sudo yum install yum-plugin-PLUGIN_NAME</code></pre></li>
        <li><strong>Disable or Enable Repositories:</strong> Sometimes you may want to disable or enable a repository. To do this, go to the repository file in the /etc/yum.repos.d/ directory and set the value of "enabled" to 0 (disabled) or 1 (enabled).</li>
    </ul>
</article>