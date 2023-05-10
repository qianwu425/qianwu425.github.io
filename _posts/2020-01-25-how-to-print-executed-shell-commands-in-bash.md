---
title: "How to Print Executed Shell Commands in Bash"
description: "If you're working with Bash scripts, you might want to print out the executed shell commands to debug them. This article covers several ways to achieve this, including using the set command, the DEBUG trap, the -x option, the PS4 variable, and the script command."
date: 2020-01-25
layout: post
---

<article>
  <img alt="low angle photography of Shell gas station at night" src="https://images.unsplash.com/photo-1545262810-77515befe149?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFByaW50JTIwRXhlY3V0ZWQlMjBTaGVsbCUyMENvbW1hbmRzJTIwaW4lMjBCYXNofGVufDB8MHx8fDE2ODM2NjA5NDg&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're working with Bash scripts, you might want to print out the executed shell commands to debug them. This article covers several ways to achieve this, including using the <code>set</code> command, the <code>DEBUG</code> trap, the <code>-x</code> option, the <code>PS4</code> variable, and the <code>script</code> command.</p>
  <h2>Method 1: Using the set Command</h2>
  <p>The <code>set</code> command in Bash can be used to configure shell parameters and enable or disable features. By using the <code>-x</code> option, Bash prints each command before executing it, which is known as shell tracing. Here's an example:</p>
  <pre><code>#!/bin/bash 
set -x 
mkdir my_directory
set +x</code></pre>
  <p>The above script creates a directory named <code>my_directory</code>, and the <code>-x</code> option enables shell tracing, which prints each command before execution.</p>
  <h2>Method 2: Using the DEBUG Trap</h2>
  <p>The <code>DEBUG</code> trap is a special shell trap that runs before each command in a Bash script. By defining a function for the <code>DEBUG</code> trap, users can print each command before it is executed. Here's an example:</p>
  <pre><code>#!/bin/bash 
function debug { 
  echo "Executing: $BASH_COMMAND" 
} 
trap debug DEBUG 
touch my_file.txt
rm my_file.txt
trap - DEBUG</code></pre>
  <p>The above script generates output that includes the executed command. The <code>trap - DEBUG</code> line removes the <code>DEBUG</code> trap when it's no longer needed.</p>
  <h2>Method 3: Using the Bash -x Option</h2>
  <p>Users can enable shell tracing by passing the <code>-x</code> option to the Bash command when executing a script. Here's an example:</p>
  <pre><code>#!/bin/bash 
mkdir my_directory
cp my_file.txt my_directory/</code></pre>
  <p>To execute this script with shell tracing enabled, users can run the script using the following syntax:</p>
  <pre><code>bash -x &lt;script-file-name&gt;</code></pre>
  <p>The <code>-x</code> option enables shell tracing, which prints each command before execution.</p>
  <h2>Method 4: Using the PS4 Variable</h2>
  <p>The <code>PS4</code> variable controls the prompt string used by the shell for the <code>-x</code> option. By customizing the prompt string, users can include additional information about each command. Here's an example:</p>
  <pre><code>#!/bin/bash 
PS4='+ ${BASH_SOURCE}:${LINENO}:${FUNCNAME[0]}: ' 
set -x 
mkdir my_directory
set +x</code></pre>
  <p>In the above example, the <code>PS4</code> prompt string includes the source file name, line number, and function name. The <code>set -x</code> command enables shell tracing with the custom prompt string.</p>
  <h2>Method 5: Using the script Command</h2>
  <p>The <code>script</code> command allows users to record their terminal session, including all executed commands and their output. By default, the script command creates a new file named <code>typescript</code> to save the session recording. Here's an example of how to use the script command:</p>
  <pre><code>$ script 
Script started, file is typescript
$ ls 
file1.txt file2.txt file3.txt 
$ exit 
Script done, file is typescript</code></pre>
  <p>The output from the above example includes the command that was executed, as well as other details such as the source file name, line number, and function name. This method is useful for keeping a record of the entire terminal session, not just the executed commands.</p>
  <h2>Conclusion</h2>
  <p>Printing shell commands as they are executed can be a useful technique for debugging Bash scripts. By using the <code>set</code> command, the <code>-x</code> option, the <code>DEBUG</code> trap, the <code>PS4</code> variable, and the <code>script</code> command, users can easily print each command before it is executed, helping them to identify errors and gain insight into how their code is functioning.</p>
</article>