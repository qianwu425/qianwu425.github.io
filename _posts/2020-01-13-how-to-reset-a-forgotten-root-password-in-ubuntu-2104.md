---
title: "How to Reset a Forgotten Root Password in Ubuntu 21.04"
description: "Forgetting your root password in Linux is a common issue that can prevent you from accessing your system. This can happen when the root account has not been used for a while. It's important to remember your root password to ensure your system runs smoothly."
date: 2020-01-13
layout: post
---

<article>
    <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFJlc2V0JTIwYSUyMEZvcmdvdHRlbiUyMFJvb3QlMjBQYXNzd29yZCUyMGluJTIwVWJ1bnR1JTIwMjEuMDR8ZW58MHwwfHx8MTY4MzY2MDkxOA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
    <p>Forgetting your root password in Linux is a common issue that can prevent you from accessing your system. This can happen when the root account has not been used for a while. It's important to remember your root password to ensure your system runs smoothly.</p>
    <p>In this guide, we will walk you through resetting a forgotten root password in Ubuntu 21.04 using the following steps:</p>
    <h2>Steps to Reset a Forgotten Root Password in Ubuntu 21.04</h2>
    <p>Follow these instructions to reset your forgotten root password in Ubuntu 21.04:</p>
    <ol>
        <li>Restart your computer and access the GRUB boot menu by pressing the <code>Esc</code> key.</li>
        <li>Select the first entry in the list and press <code>e</code> to edit the boot configuration.</li>
        <li>Locate the line starting with "linux" and ending with "quiet splash". Replace this line with "linux /bin/bash" to switch to a bash shell.</li>
        <li>Press <code>Ctrl</code>+<code>X</code> or <code>F10</code> to boot into the system with the modified configuration.</li>
        <li>Remount the root partition in read/write mode by running the command: <code>mount -o remount,rw /</code>.</li>
        <li>Reset the root password by running the command: <code>passwd root</code>.</li>
        <li>Enter your new root password twice when prompted.</li>
        <li>Reboot the system by running the command: <code>reboot</code>.</li>
    </ol>
    <h2>Additional Notes</h2>
    <p>If you encounter any issues during the password reset process, you can try booting into the system using a Live USB or CD and repeating the above steps.</p>
    <h2>Preventative Measures</h2>
    <p>To avoid forgetting your root password in the future, you can consider using a password manager to store it or creating a password hint to help you remember it. It's also a good practice to use strong and unique passwords for all your accounts.</p>
    <h2>Conclusion</h2>
    <p>Resetting a forgotten root password in Ubuntu 21.04 is a straightforward process if you follow the steps above. Remember to keep your new password secure to avoid forgetting it again.</p>
</article>