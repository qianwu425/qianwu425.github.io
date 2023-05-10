---
title: "How to Extract Filename Without Path and Extension in Bash"
description: "If you're working with Bash and need to extract the filename without its path and extension, there are several ways to do it. In this article, we will explore three approaches using different Bash commands and techniques."
date: 2020-01-20
layout: post
---

<article>
  <img alt="empty street in between of tall trees during golden hour" src="https://images.unsplash.com/photo-1505028106030-e07ea1bd80c3?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEV4dHJhY3QlMjBGaWxlbmFtZSUyMFdpdGhvdXQlMjBQYXRoJTIwYW5kJTIwRXh0ZW5zaW9uJTIwaW4lMjBCYXNofGVufDB8MHx8fDE2ODM2NjA5MzU&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>
    If you're working with Bash and need to extract the filename without its path and extension, there are several ways to do it. In this article, we will explore three approaches using different Bash commands and techniques.
  </p>
  <h2>Approach 1: Using "basename" Command with Parameter Substitution</h2>
  <p>
    The "basename" command can be used to extract the filename or directory name from a path. To extract the filename without its path and extension using "basename", we can use the suffix option to remove the extension from the filename. Here's an example Bash code:
  </p>
  <pre><code>#!/bin/bash
filepath="/home/user/documents/file.txt"
filename=$(basename "$filepath" .txt)
echo "$filename"
  </code></pre>
  <p>
    In this code, we define a variable called "filepath" that holds the path to the file we want to extract the filename from. Then we use the "basename" command to extract the filename without the extension and assign the result to a variable called "filename". Finally, we print the value of "filename" using the "echo" command.
  </p>
  <h2>Approach 2: Using Parameter Expansion</h2>
  <p>
    Another way to extract the filename without its path and extension is by using parameter expansion. Here's an example Bash code:
  </p>
  <pre><code>#!/bin/bash
filepath="/home/user/documents/file.txt"
filename="${filepath##*/}"
echo "${filename%.*}"
  </code></pre>
  <p>
    In this code, we define a variable called "filepath" that holds the path to the file we want to extract the filename from. Then we use parameter expansion to remove the path from the filename and assign the result to a variable called "filename". Finally, we use parameter expansion again to remove the extension from the filename and print the result using the "echo" command.
  </p>
  <h2>Approach 3: Using "awk" Command</h2>
  <p>
    Another option to extract the filename without its path and extension is by using the "awk" command. Here's an example Bash code:
  </p>
  <pre><code>#!/bin/bash
filepath="/home/user/documents/file.txt"
filename=$(echo $filepath | awk -F"/" '{print $NF}' | awk -F"." '{print $1}')
echo "$filename"
  </code></pre>
  <p>
    In this code, we define a variable called "filepath" that holds the path to the file we want to extract the filename from. Then we use the "awk" command to extract the filename without its path and extension. The first "awk" command is used to extract the last field after the last forward slash "/" which is the filename with extension, and the second "awk" command is used to remove the extension from the filename. Finally, we print the value of "filename" using the "echo" command.
  </p>
  <h2>Conclusion</h2>
  <p>
    In this article, we explored three different approaches to extract the filename without its path and extension in Bash. Depending on your use case and personal preference, you can choose any of these methods to achieve your goal. The "basename" command with parameter substitution is a simple and efficient approach, while parameter expansion and "awk" command give you more flexibility and control over the process. 
  </p>
</article>