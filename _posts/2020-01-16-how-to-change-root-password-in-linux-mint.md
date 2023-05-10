---
title: "How to Change Root Password in Linux Mint"
description: "If you're using Linux Mint and need to update the root password, follow these steps:"
date: 2020-01-16
layout: post
---

<article>
  <img alt="Change neon light signage" src="https://images.unsplash.com/photo-1499244571948-7ccddb3583f1?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENoYW5nZSUyMFJvb3QlMjBQYXNzd29yZCUyMGluJTIwTGludXglMjBNaW50fGVufDB8MHx8fDE2ODM2NjA5Mjc&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're using Linux Mint and need to update the root password, follow these steps:</p>
  <h2>Table of Contents</h2>
  <ul>
    <li>Types of Users in Linux</li>
    <li>Root User</li>
    <li>Sudo User</li>
    <li>Normal User</li>
    <li>Changing the Root Password in Linux Mint</li>
    <li>Can Root User Change Sudo User Password?</li>
    <li>Can Normal User Change Root User Password?</li>
    <li>Can Sudo User Change Root User Password?</li>
    <li>How to Change Sudo User Password in Linux Mint</li>
    <li>How to Change Normal User Password in Linux Mint</li>
    <li>Conclusion</li>
  </ul>
  <h2>Types of Users in Linux</h2>
  <p>Linux systems have three types of users: root, sudo, and normal users.</p>
  <h2>Root User</h2>
  <p>The root user is the most privileged user in Linux, with unrestricted access to all system files and directories. However, it is recommended to use the root user only for system administration tasks and not for regular use. By default, the root account is disabled in Linux Mint, and users are required to use the sudo command to execute administrative tasks.</p>
  <h2>Sudo User</h2>
  <p>A sudo user is a user who has been granted temporary administrative privileges to perform system-wide tasks. A sudo user can execute specific commands with administrative privileges by providing their password. This is a secure way to provide temporary administrative privileges without giving the user full access to the system.</p>
  <h2>Normal User</h2>
  <p>A regular user account is created for a regular user to accomplish daily operations on the system. These users have restricted access and cannot make system-wide modifications. They are not permitted to carry out administrative operations such as installing software, changing system settings, or modifying system files.</p>
  <h2>Changing the Root Password in Linux Mint</h2>
  <p>Here are the steps to change the root password in Linux Mint:</p>
  <ol>
    <li>Open the terminal by pressing Ctrl + Alt + T or searching for Terminal in the application menu.</li>
    <li>Switch to the root user from the sudo user by entering the following command: su</li>
    <li>Enter the root user's current password.</li>
    <li>To change the root user password, run the passwd command. This command will prompt you to enter a new password and confirm it.</li>
    <li>If both new passwords match, you will see a message confirming that the password has been updated.</li>
    <li>Switch back to the sudo user by entering the command: su</li>
    <li>Enter a new password for the root user. If the password is successfully changed, you will enter the root user. Type exit to leave the root user.</li>
  </ol>
  <p>You have successfully updated the root user password in Linux Mint by following these steps.</p>
  <h2>Can Root User Change Sudo User Password?</h2>
  <p>Yes, the root user can modify the sudo user password since the root user has full system privileges and can perform any administrative task on the system, including changing the passwords of other users, including those with sudo privileges. To change the sudo user password,enter the passwd command followed by the username of the sudo user. For example, to change the sudo password for the user named Jennifer, run the command: passwd jennifer. You will then be prompted to enter the new password. Once you have entered and confirmed the new password, it will be updated in the system, and the user can use the new password to authenticate and perform administrative tasks with sudo privileges. To confirm the password change, run any command that requires sudo user password authentication, such as apt update.</p>
  <h2>Can Normal User Change Root User Password?</h2>
  <p>A normal user does not have the necessary permissions to change the root user's password on a Linux system by default. This is because the root user has complete control over the system and its configuration, and allowing an ordinary user to alter the root password could jeopardize the system's security. Therefore, if a normal user tries to update the root user password, they will receive a response stating that they do not have the required permissions.</p>
  <h2>Can Sudo User Change Root User Password?</h2>
  <p>Yes, a sudo user can change the password of the root user. To change the root user password, run the following command: sudo passwd root. Now switch to the root user to confirm the password change. Note that if the sudo user does not have permission to change the root password, they can still use the sudo passwd command to change their password or the password of another non-root user on the system.</p>
  <h2>How to Change Sudo User Password in Linux Mint</h2>
  <p>To change the password for a sudo user in Linux Mint, follow these steps:</p>
  <ol>
    <li>Open the terminal by pressing Ctrl + Alt + T or searching for Terminal in the application menu.</li>
    <li>Switch to the root user from the sudo user by entering the following command: su</li>
    <li>Enter the root user's current password.</li>
    <li>Enter the following command: passwd username (replace "username" with the username of the sudo user whose password you want to change)</li>
    <li>Enter a new password when prompted and then confirm the new password.</li>
    <li>If the password is successfully changed, you will see a message indicating that the password has been updated.</li>
  </ol>
  <p>You have successfully changed the password for a sudo user in Linux Mint by following these steps.</p>
  <h2>How to Change Normal User Password in Linux Mint</h2>
  <p>To change the password for a normal user in Linux Mint, follow these steps:</p>
  <ol>
    <li>Open the terminal by pressing Ctrl + Alt + T or searching for Terminal in the application menu.</li>
    <li>Enter the following command: passwd (without any username)</li>
    <li>Enter your current password when prompted.</li>
    <li>Enter a new password when prompted and then confirm the new password.</li>
    <li>If the password is successfully changed, you will see a message indicating that the password has been updated.</li>
  </ol>
  <p>You have successfully changed the password for a normal user in Linux Mint by following these steps.</p>
  <h2>Conclusion</h2>
  <p>Updating the root password is crucial for maintaining the security of your Linux Mint system. Remember that the root user can modify or change the password of any user across the system, while a sudo user can also modify the root user password. In addition, a sudo user can modify the password of anyother user on the system except the root user. However, a normal user cannot change the root user password but can change their password using the passwd command. To ensure that your system remains secure, it's essential to regularly update your passwords and ensure that only authorized users have access to the system.</p>
</article>