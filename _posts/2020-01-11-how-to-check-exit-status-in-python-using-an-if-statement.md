---
title: "How to Check Exit Status in Python Using an If Statement"
description: "The exit status of a command or script is crucial in scripting because it indicates whether the command or script was executed correctly or not. In this article, we will explore how to use an if statement in Python to check the exit status of a command or script."
date: 2020-01-11
layout: post
---

<article>
    <img alt="blue and white exit signage mounted on brown brick wall" src="https://images.unsplash.com/photo-1520606393001-b816ded9caac?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENoZWNrJTIwRXhpdCUyMFN0YXR1cyUyMGluJTIwUHl0aG9uJTIwVXNpbmclMjBhbiUyMElmJTIwU3RhdGVtZW50fGVufDB8MHx8fDE2ODM2NjA5MTA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
    <p>The exit status of a command or script is crucial in scripting because it indicates whether the command or script was executed correctly or not. In this article, we will explore how to use an if statement in Python to check the exit status of a command or script.</p>

<h2>Using an If Statement to Check the Exit Status in Python</h2>
<p>To determine if a command or script has executed successfully in Python, we can use an if statement and a special variable. The syntax of the if statement to determine the exit status is as follows:</p>
<pre><code>
if [return_code == 0]:
print("Execution successful")
else:
print("Execution failed")
</code></pre>
<p>The '==' operator is used to determine if the exit status is equal to zero, indicating that the command or script was successful. If the exit status is not equal to zero, the else block is executed, and a message indicating that the command failed is printed. Here's an example to illustrate how we can use an if statement to check the exit status of a command:</p>
<pre><code>
import subprocess
result = subprocess.run(['ls', '/false-directory'])
if result.returncode == 0:
print("Execution successful")
else:
print("Execution failed")
</code></pre>
<p>In the above example, the subprocess module is used to execute the 'ls' command to list the contents of a non-existent directory. Since the directory does not exist, the 'ls' command will fail, and its exit status will be non-zero. The if statement then checks the exit status using the 'returncode' attribute of the subprocess result and prints a message indicating that the command has failed.</p>

<h2>Handling Exceptions in Python</h2>
<p>In addition to using an if statement to check the exit status, we can also use exception handling to handle errors in Python. The 'try-except' block is used to catch and handle exceptions that may occur during the execution of a command or script. Here's an example of how we can use exception handling to handle errors in Python:</p>
<pre><code>
import subprocess
try:
result = subprocess.run(['ls', '/false-directory'])
except subprocess.CalledProcessError as error:
print(f"Execution failed with error code {error.returncode}")
else:
print("Execution successful")
</code></pre>
<p>In the above example, the 'try-except' block is used to catch any exceptions that may occur during the execution of the 'ls' command. If there is an exception, the 'except' block is executed, which produces a message indicating that the execution has failed along with the error code. If no exceptions occur, the 'else' block is executed, which prints a message indicating that the execution has been successful.</p>

<h2>Conclusion</h2>
<p>Checking the exit status of a command or script is an essential part of scripting, and there are various ways to do so in Python. By using an if statement or exception handling, we can easily determine the success or failure of a command or script and take appropriate actions based on the exit status or error message.</p>
</article>
