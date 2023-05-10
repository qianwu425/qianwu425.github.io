---
title: "How to Install Yarn on Ubuntu: A Comprehensive Guide"
description: "Yarn is a widely used package manager for managing dependencies and libraries in JavaScript applications. It is freely available for use in various applications like Node.js and Java, and offers many features that make it the most reliable and efficient package manager for JavaScript."
date: 2020-01-24
layout: post
---

<article>
  <img alt="green and purple yarn ball" src="https://images.unsplash.com/photo-1595301390417-c66647b47e9f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBZYXJuJTIwb24lMjBVYnVudHUlM0ElMjBBJTIwQ29tcHJlaGVuc2l2ZSUyMEd1aWRlfGVufDB8MHx8fDE2ODM2NjA5NDU&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Yarn is a widely used package manager for managing dependencies and libraries in JavaScript applications. It is freely available for use in various applications like Node.js and Java, and offers many features that make it the most reliable and efficient package manager for JavaScript.</p>
  <h2>Installing Yarn on Ubuntu</h2>
  <p>There are three ways to install Yarn on Ubuntu: using the Apt package manager, Node Package Manager (NPM), or Snap Package Manager. Here's a detailed guide for each method:</p>
  <h3>Method 1: Using Apt Package Manager</h3>
  <ol>
    <li>Update the list of Apt packages on Ubuntu by running the following command: <code>sudo apt update &amp;&amp; sudo apt upgrade</code></li>
    <li>Install Yarn by running the command: <code>sudo apt install yarn</code></li>
    <li>Verify that Yarn is installed by running the command: <code>yarn --version</code></li>
    <li>To remove Yarn, run the command: <code>sudo apt remove yarn</code></li>
  </ol>
  <h3>Method 2: Using NPM</h3>
  <ol>
    <li>Make sure that NPM is up-to-date by running the command: <code>npm --version</code></li>
    <li>Install Yarn using NPM by running the command: <code>sudo npm install -g yarn</code></li>
    <li>Verify that Yarn is installed by running the command: <code>yarn --version</code></li>
    <li>To remove Yarn using NPM, run the command: <code>sudo npm uninstall -g yarn</code></li>
  </ol>
  <h3>Method 3: Using Snap Package Manager</h3>
  <ol>
    <li>Install Snap Package Manager by running the command: <code>sudo apt install snapd</code></li>
    <li>Install Yarn in classic mode by running the command: <code>sudo snap install yarn --classic</code></li>
    <li>Verify that Yarn is installed by running the command: <code>yarn --version</code></li>
    <li>To remove Yarn, run the command: <code>sudo snap remove yarn</code></li>
  </ol>
  <h2>Conclusion</h2>
  <p>Yarn is a powerful and reliable package manager for managing dependencies and libraries in JavaScript applications. By following the instructions provided in this guide, developers can easily install Yarn on their Ubuntu machines using one of the recommended methods. Yarn offers developers deterministic installs, offline mode, and faster installation times, which can improve the overall productivity and efficiency of the development process.</p>
</article>