---
title: "How to Get the Process ID (PID) of a Python Script"
description: "If you're working on a Linux or Unix-based operating system, obtaining the Process ID (PID) of a Python script is necessary for various reasons. In this article, we will discuss several techniques that you can use to obtain the PID of a Python script."
date: 2020-01-19
layout: post
---

<article>
  <img alt="woman in white dress shirt and gray pants standing beside green metal railings during daytime" src="https://images.unsplash.com/photo-1599577180513-7dd76ffd9761?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEdldCUyMHRoZSUyMFByb2Nlc3MlMjBJRCUyMCUyOFBJRCUyOSUyMG9mJTIwYSUyMFB5dGhvbiUyMFNjcmlwdHxlbnwwfDB8fHwxNjgzNjYwOTMy&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're working on a Linux or Unix-based operating system, obtaining the Process ID (PID) of a Python script is necessary for various reasons. In this article, we will discuss several techniques that you can use to obtain the PID of a Python script. </p>
  <h2>Method 1: Using os.getpid() Function</h2>
  <p>The built-in os.getpid() function is a simple way to acquire the PID of a Python script. To use this function, add the following line to your script:</p>
  <pre><code>print("The PID of this script is:", os.getpid())</code></pre>
  <p>This will display the PID of the script when you run it.</p>
  <h2>Method 2: Using ps Command</h2>
  <p>The ps command is a powerful tool for displaying information about running processes. To obtain the PID of a Python script, use the following command:</p>
  <pre><code>ps -ef | grep &lt;script name&gt;</code></pre>
  <p>This command lists all running processes and searches for the process containing the Python script name. The awk command extracts the second column (which contains the PID) from the output of the grep command.</p>
  <h2>Method 3: Using ps aux and awk Command</h2>
  <p>You can also use the ps aux and awk functions to determine the PID of a Python script. Here's how:</p>
  <pre><code>ps aux | grep &lt;script name&gt; | grep -v grep | awk '{print $2}'</code></pre>
  <p>The ps aux command displays a list of all active processes on the system. The a option shows all the processes for all users, and the u option provides detailed information about each process. The grep command searches for the process with the given script name in the output of the ps aux command. The -v grep option filters out the process with the name grep itself, which could otherwise appear in the output if the script name matches the grep keyword. The awk command extracts the second field from the output of the previous command, which is the PID of the process.</p>
  <h2>Other Ways to Get the PID of a Python Script</h2>
  <p>There are additional techniques for obtaining the PID of a Python script, such as using a PID file or the lsof command, which shows open files. These methods can be useful for monitoring and troubleshooting purposes.</p>
  <pre><code>lsof -c python | grep &lt;script name&gt;</code></pre>
  <p>The lsof command lists all open files associated with the python command and searches for the process containing the Python script name. In the second column of the output, the PID is listed.</p>
  <h2>Conclusion</h2>
  <p>Obtaining the PID of a Python script is an essential task for various purposes such as monitoring, troubleshooting, and debugging. We have discussed various techniques, including the os.getpid() function, ps command, ps aux command, PID file, and lsof command. However, it is important to note that different Linux distributions and versions may have varying commands and options available, which can cause some methods to not work on certain systems. So, choose the method that works best for your system.</p>
</article>