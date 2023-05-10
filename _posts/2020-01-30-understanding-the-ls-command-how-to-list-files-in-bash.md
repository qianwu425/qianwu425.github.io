---
title: "Understanding the Ls Command: How to List Files in Bash"
description: "The Bash shell's ls (list) command is a command-line tool that allows you to view the files and folders in a specified directory. It is a commonly used utility in Unix-based systems and is supported by several modern operating systems, including Linux, macOS, and Windows Subsystem for Linux."
date: 2020-01-30
layout: post
---

<article>
  <img alt="seashore" src="https://images.unsplash.com/photo-1576324374260-c64736180172?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxVbmRlcnN0YW5kaW5nJTIwdGhlJTIwbHMlMjBDb21tYW5kJTNBJTIwSG93JTIwdG8lMjBMaXN0JTIwRmlsZXMlMjBpbiUyMEJhc2h8ZW58MHwwfHx8MTY4MzY2MDk1OQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>The Bash shell's ls (list) command is a command-line tool that allows you to view the files and folders in a specified directory. It is a commonly used utility in Unix-based systems and is supported by several modern operating systems, including Linux, macOS, and Windows Subsystem for Linux.</p>
  <h2>What Does the ls Command Do?</h2>
  <p>The ls command-line tool lets you view file and directory information, including permissions, ownership, size, and more. You can modify the output and get the necessary information using various options.</p>
  <p>To use the ls command, navigate to the directory where your file is located using your terminal or command prompt, and then enter the following command:</p>
<code>ls <directory-path></directory-path></code>
  <p>The command above shows the list of files and folders in the directory that was supplied. By default, the output displays the names of the files and directories in alphabetical order. For instance, if the following files and subdirectories are present in the directory "mydir":</p>
  <pre>    <code>mydir/
    ├── file1.txt
    ├── file2.txt
    └── subdir/
        ├── file3.txt
        └── file4.txt</code>
  </pre>
  <p>You can use the ls command to list the files and directories in the "mydir" directory, and the output will be as follows:</p>
  <pre>    <code>file1.txt file2.txt subdir/</code>
  </pre>
  <p>The output shows that there are two files (file1.txt and file2.txt) and one subdirectory (subdir/) in the mydir directory.</p>
  <p>The ls command has various options that can modify its behavior. Here are some of the most common options:</p>
  <ul>
    <li><code>-l</code> displays detailed information about the files and directories, including permissions, ownership, size, and modification time.</li>
    <li><code>-a</code> displays all files, including hidden files that start with a dot (.)</li>
    <li><code>-h</code> displays file sizes in a human-readable format (e.g., 1K, 2M, 3G).</li>
    <li><code>-t</code> sorts the files and directories by modification time, with the most recently modified files and directories appearing first.</li>
    <li><code>-R</code> lists files and subdirectories recursively.</li>
  </ul>
  <h2>How to Use the ls Command with Options</h2>
  <p>Let's look at how to use the ls command's most popular options:</p>
  <h3>Using the -l Option</h3>
  <p>The ls command's <code>-l</code> option shows comprehensive details, such as ownership, size, and modification time, about the files and directories that are being examined. Here's an example:</p>
<code>ls -l <directory-path></directory-path></code>
  <p>This command displays the following information for each file and directory in the specified directory:</p>
  <ul>
    <li>File type and permissions</li>
    <li>Number of links</li>
    <li>Name of the owner</li>
    <li>Name of the group</li>
<li>File size</li>
<li>Date and time of the last modification</li>
<li>File/directory name</li>
  </ul>
  <p>Here is an example output for the directory "mydir":</p>
  <pre>    <code>total 8
    -rw-r--r--  1 user  staff    0 May  1 10:30 file1.txt
    -rw-r--r--  1 user  staff    0 May  1 10:30 file2.txt
    drwxr-xr-x  3 user  staff   96 May  1 10:30 subdir</code>
  </pre>
  <p>The first line (total 8) shows the total number of blocks (in this case, 8 blocks of 512 bytes apiece) consumed by the files in the directory. The detailed information for each file and directory is shown in the following lines.</p>
  <h3>Using the -a Option</h3>
  <p>The <code>-a</code> option of the ls command displays all files, including hidden files that start with a dot (.). Here is an example:</p>
<code>ls -a <directory-path></directory-path></code>
  <p>This command shows every file and directory in the directory that was supplied, including any hidden files that are not normally shown. For instance, if you have a hidden file named .hidden in your directory, it will be displayed in the output.</p>
  <h3>Using the -h Option</h3>
  <p>The ls command's <code>-h</code> option shows file sizes in a human-readable format, such as 1K, 2M, and 3G. Here's an example:</p>
<code>ls -h <directory-path></directory-path></code>
  <p>This command shows file sizes using a more legible format. For instance, a file with a size of 1024 bytes will appear as 1K on the screen.</p>
  <h2>Conclusion</h2>
  <p>The ls command is an essential utility that enables you to list files and directories in a specified location. It is supported in almost all modern operating systems, and you can use various options to customize the output and get the required information.</p>
</article>
