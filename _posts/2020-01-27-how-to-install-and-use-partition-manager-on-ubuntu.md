---
title: "How to Install and Use Partition Manager on Ubuntu"
description: "Ubuntu users have access to a powerful open-source disk partitioning tool called Partition Manager. With this software, you can resize and move partitions without losing any data, making it a valuable tool for managing your storage devices."
date: 2020-01-27
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBhbmQlMjBVc2UlMjBQYXJ0aXRpb24lMjBNYW5hZ2VyJTIwb24lMjBVYnVudHV8ZW58MHwwfHx8MTY4MzY2MDk1MQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Ubuntu users have access to a powerful open-source disk partitioning tool called Partition Manager. With this software, you can resize and move partitions without losing any data, making it a valuable tool for managing your storage devices.</p>
  <h2>Installing Partition Manager on Ubuntu</h2>
  <p>Installing Partition Manager on Ubuntu is a straightforward process. Simply open up your terminal and run the following command:</p>
  <pre><code>sudo apt install partitionmanager</code></pre>
  <p>Once the installation is complete, you can launch Partition Manager from the command line:</p>
  <pre><code>partitionmanager</code></pre>
  <p>You can also find and start the program from the program menu. Once you open it, you'll see a graphical user interface that looks like the screenshot below:</p>
  <img alt="Partition Manager screenshot" src="partition-manager-screenshot.png"/>
  <h2>Using Partition Manager on Ubuntu</h2>
  <p>Using Partition Manager is easy, and all the options are available in the menu bar. To get started, you'll need to unmount the disk you want to work on. You can do this by right-clicking on the drive bar and selecting "Unmount". Then, follow the steps below:</p>
  <h3>Step 1: Select the Storage Device in Partition Manager</h3>
  <p>Choose the storage device you want to work on from the drop-down menu at the top right corner of the window.</p>
  <h3>Step 2: Display Partition Information</h3>
  <p>To view partition information, right-click on a partition and choose "Information". A new window will appear displaying detailed information about the partition.</p>
  <h2>Resizing, Creating, Renaming, and Deleting Partitions with Partition Manager</h2>
  <p>Partition Manager provides several options for managing your partitions. To perform any of the following operations, right-click on the partition and choose the appropriate option:</p>
  <ul>
    <li>Resizing: Choose "Resize/Move", adjust the partition's new size in the "New Size (MiB)" field, and click "Resize" to complete the procedure.</li>
    <li>Creating: Click on "Partition" and choose "New". A new window will appear. Adjust the partition's size and file system, fill in the other information, and click on "Add" to save it.</li>
    <li>Renaming: Choose "Label", type in the new name in the "Label" field, and click "OK" to save the changes.</li>
    <li>Deleting: Choose "Delete", confirm the deletion in the prompt that appears, and the partition will be removed from the disk.</li>
  </ul>
  <h2>Uninstalling Partition Manager on Ubuntu</h2>
  <p>If you no longer need Partition Manager, you can easily uninstall it by running the following command in your terminal:</p>
  <pre><code>sudo apt remove --autoremove partitionmanager</code></pre>
  <h2>Conclusion</h2>
  <p>Partition Manager is a free and user-friendly disk partitioning tool for Ubuntu. You can easily install it using the default package manager and follow the instructions above for easy management of your partitions. With Partition Manager, you can resize, create, rename, and delete partitions without losing any data, making it a valuable tool for anyone who needs to manage their storage devices. By properly managingyour partitions, you can optimize your disk usage and improve your system's performance. Partition Manager is a reliable and efficient tool that can help you achieve this goal.</p>
  <p>One thing to keep in mind when using Partition Manager or any other disk partitioning tool is to be careful not to accidentally delete or modify important data. Always make sure to back up your files before performing any operations on your partitions. Also, if you're not sure what you're doing or if you encounter any issues, don't hesitate to seek help from the Ubuntu community or consult online resources.</p>
  <p>Overall, Partition Manager is an essential tool for Ubuntu users who want to optimize their disk usage and manage their storage devices efficiently. Whether you need to resize, create, rename, or delete partitions, Partition Manager provides an easy-to-use interface and a wide range of options to meet your needs. With its open-source nature and active development community, Partition Manager is also constantly evolving and improving, ensuring that it remains a reliable and effective tool for years to come.</p>
</article>