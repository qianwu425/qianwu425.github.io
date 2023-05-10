---
title: "How to Create Backups of Your Linux System With a GUI Tool"
description: Creating backups of your Linux system doesn't have to be a complex process that requires command-line knowledge. In fact, there are user-friendly graphical user interface (GUI) programs available, such as "backup-tool," an open-source and lightweight utility that simplifies the backup process.
date: 2020-02-02
layout: post
---

<article>
  <img alt="creative decor" src="https://images.unsplash.com/photo-1523837157348-ffbdaccfc7de?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENyZWF0ZSUyMEJhY2t1cHMlMjBvZiUyMFlvdXIlMjBMaW51eCUyMFN5c3RlbSUyMHdpdGglMjBhJTIwR1VJJTIwVG9vbHxlbnwwfDB8fHwxNjgzNjYwOTY3&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Creating backups of your Linux system doesn't have to be a complex process that requires command-line knowledge. In fact, there are user-friendly graphical user interface (GUI) programs available, such as "backup-tool," an open-source and lightweight utility that simplifies the backup process.</p>
  <p>In this article, we'll show you how to use "backup-tool" to create system backups with ease.</p>
  <h2>Creating System Backups with "backup-tool"</h2>
  <p>The first step is to install "backup-tool" on your Linux system. You can easily do this by opening a terminal window and running the following command:</p>
  <pre><code>sudo apt-get install backup-tool</code></pre>
  <p>Once the installation is complete, you can launch the program either by running the command "backup-tool" in the terminal or by finding it in the application menu on your computer.</p>
  <p>When you open "backup-tool," you'll see three options: Basic, Advanced, and Extra. Hover your mouse over each option to see more information about it.</p>
  <p>To create a backup of your system, select the Basic option and specify the source and destination paths. For example, if you want to back up your "Documents" folder to an external hard drive connected to your Linux system, you would enter the appropriate paths.</p>
  <ul>
    <li>Tip: Make sure that your external hard drive is connected and recognized by your system.</li>
  </ul>
  <p>If you prefer, you can also choose from a variety of backup options under the Advanced option, but the default options should be sufficient for most users. Click the Play button on the top menu to start the backup process once you've made your selections.</p>
  <p>Once the backup is complete, you'll see a "Completed successfully" message on your screen. You can check the backup files in the destination directory using the "ls" command.</p>
  <h2>Scheduling Automated Backups with "backup-tool"</h2>
  <p>If you want to schedule automated backups of your system, "backup-tool" can help you do that too. To get started, launch "backup-tool" and select the "Extra" option. From there, you can set the frequency and time of your backups, as well as other settings like email notifications and encryption.</p>
  <p>Note that for automated backups to work, the external hard drive must be connected and turned on at the scheduled backup time.</p>
  <h2>Uninstalling "backup-tool"</h2>
  <p>If you ever want to remove "backup-tool" from your Linux system, you can do so by running the following command in the terminal:</p>
  <pre><code>sudo apt-get remove backup-tool</code></pre>
  <h2>Conclusion</h2>
  <p>"Backup-tool" is a user-friendly GUI tool for creating backups of personal files and directories on Linux systems. It simplifies the backup process and is easy to install using the apt command. To create a backup, select the source and destination directories, set your backup options, and click the Play button. If you want to schedule automated backups, use the "Extra" option to set the frequency and time of your backups.</p>
</article>
