---
title: "How to Create a Bootable USB Drive of Linux Mint on Windows"
description: "Linux Mint is a popular Linux distribution known for its user-friendly interface and variety of software packages. This guide will walk you through the process of creating a bootable USB drive of Linux Mint on Windows, so you can try out and install it on your computer."
date: 2020-01-08
layout: post
---

<article>
  <img alt="creative decor" src="https://images.unsplash.com/photo-1523837157348-ffbdaccfc7de?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENyZWF0ZSUyMGElMjBCb290YWJsZSUyMFVTQiUyMERyaXZlJTIwb2YlMjBMaW51eCUyME1pbnQlMjBvbiUyMFdpbmRvd3N8ZW58MHwwfHx8MTY4MzY2MDkwNQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Linux Mint is a popular Linux distribution known for its user-friendly interface and variety of software packages. This guide will walk you through the process of creating a bootable USB drive of Linux Mint on Windows, so you can try out and install it on your computer.</p>
  <h2>Table of Contents:</h2>
  <ul>
    <li>Downloading the Linux Mint Installation Image</li>
    <li>Extracting the Linux Mint Installer Archive</li>
    <li>Finding the Device ID of the USB Drive to be Flashed</li>
    <li>Flashing the Linux Mint Installation Image to the USB Drive</li>
    <li>Ejecting the USB Drive Safely</li>
    <li>Booting from the Linux Mint USB Drive</li>
    <li>Installing Linux Mint on Your Computer</li>
    <li>Common Issues and Troubleshooting</li>
  </ul>
  <h2>Downloading the Linux Mint Installation Image</h2>
  <p>To get started, open a web browser and go to the Linux Mint website. From there, navigate to the download page and click on the Linux Mint installer image. The file will download to your default downloads folder.</p>
  <h2>Extracting the Linux Mint Installer Archive</h2>
  <p>After downloading the file, extract it to your downloads folder by right-clicking on it and selecting "Extract Here". Wait for the extraction process to complete, and a new .iso file will appear in your downloads folder.</p>
  <h2>Finding the Device ID of the USB Drive to be Flashed</h2>
  <p>To determine the device ID of your USB drive, open a Command Prompt window and type "diskpart" before and after inserting your USB device. Compare the results to find your USB drive's device ID (for example, "Disk 2").</p>
  <h2>Flashing the Linux Mint Installation Image to the USB Drive</h2>
  <p>Use the Command Prompt to navigate to the downloads folder using the command <code>cd %userprofile%\Downloads</code>. Then, run the following command to flash the installation image to your USB drive: <code>dd if=linuxmint_22.1_cinnamon_x64.iso of=\\.\PhysicalDrive2 bs=4M --progress</code>. Make sure to replace "PhysicalDrive2" with the device ID of your USB drive.</p>
  <h2>Ejecting the USB Drive Safely</h2>
  <p>When the flashing process is complete, open DiskPart by entering the command "diskpart" in the Command Prompt window. Then, type "select disk 2" (or the proper disk number) and hit Enter. Finally, type "remove all dismount" and press Enter to safely eject the USB drive from your computer.</p>
  <h2>Booting from the Linux Mint USB Drive</h2>
  <p>After inserting the USB device, restart your computer. Press the key that opens the boot menu (usually F12 or Del) to choose the USB drive from the list of boot devices. Your PC will now boot into the live environment of Linux Mint.</p>
  <h2>Installing Linux Mint on Your Computer</h2>
  <p>Start the installation process by double-clicking the "Install Linux Mint" icon on the desktop. Follow the on-screen directions to configure your installation. You can choose to install Linux Mint alongside your existing operating system or wipeyour hard drive and install Linux Mint as the sole operating system. During the installation process, you'll be prompted to set up your username, password, and timezone. Make sure to follow the instructions carefully and select your preferences accordingly.
If you encounter any problems during the installation process, here are some solutions to common issues:
</p><ul>
  <li>If your computer does not recognize the USB drive, try using a different USB port or a different USB drive.</li>
  <li>If you receive an error message while flashing the Linux Mint installation image, ensure that you have the correct device ID and that the USB drive is not write-protected.</li>
  <li>If you cannot boot from the USB drive, check that you have selected the correct boot device in the boot menu and that your computer supports booting from USB.</li>
  <li>If you experience graphical issues or system freezes during the live environment, try selecting the "Compatibility Mode" option in the boot menu.</li>
</ul>
<h2>Conclusion</h2>
<p>Creating a bootable USB drive of Linux Mint on Windows is a straightforward process that can be completed in just a few steps. With your new Linux Mint USB drive, you can test out the distribution or install it on your computer. Enjoy the user-friendly interface and the variety of software packages that Linux Mint offers!</p>
<h2>References:</h2>
<ul>
  <li><a href="https://linuxmint.com/">Linux Mint Website</a></li>
  <li><a href="https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#1-overview">Create a USB stick on Windows</a></li>
</ul>
</article>