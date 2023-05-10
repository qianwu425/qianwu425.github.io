---
title: "How to Use Scp Command to Transfer Files Between Unix Servers"
description: "If you need to transfer files between Unix servers, the scp command can come in handy. Here's a guide on how to use it."
date: 2020-01-08
layout: post
---

<article>
  <img alt="a person holding a book" src="https://images.unsplash.com/photo-1664382952681-30fe4b179437?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFVzZSUyMHNjcCUyMENvbW1hbmQlMjB0byUyMFRyYW5zZmVyJTIwRmlsZXMlMjBCZXR3ZWVuJTIwVW5peCUyMFNlcnZlcnN8ZW58MHwwfHx8MTY4MzY2MDkwMw&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you need to transfer files between Unix servers, the scp command can come in handy. Here's a guide on how to use it.</p>
  <p>First, let's understand the basic syntax of the scp command:</p>
  <code>scp [options] source_file_location username@destination_host:destination_file_location</code>
  <p>In this command, <code>source_file_location</code> is the path of the file you want to transfer, <code>username</code> is the username of the destination host, and <code>destination_host</code> is the IP address or hostname of the server you want to transfer the file to. The <code>destination_file_location</code> is the path where you want to copy the file.</p>
  <p>The scp command also has some optional flags:</p>
  <ul>
    <li>-p: specifies the SSH port of the host.</li>
    <li>-q: suppresses the progress of the transfer.</li>
    <li>-c: compresses the data to be sent to the host machine.</li>
    <li>-r: recursively copies the directories.</li>
  </ul>
  <p>To copy a file, use the following command:</p>
  <code>scp /home/user/Documents/example_file.txt jdoe@192.168.0.100:/home/jdoe/Shared</code>
  <p>To copy a directory, use the following command:</p>
  <code>scp -r /home/user/Documents jdoe@192.168.0.100:/home/jdoe/Shared</code>
  <p>It's important to note that using password authentication with scp can be less secure than using key-based authentication. So, use password authentication only when necessary and make sure to use strong and secure passwords.</p>
  <h2>Conclusion</h2>
  <p>The scp command is a simple yet powerful tool for transferring files securely between Unix servers. By following the above steps, you can easily transfer your files from one server to another. Try it out and simplify your file transfer process.</p>
</article>