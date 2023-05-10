---
title: "How to Count Words in Command Prompt Output"
description: "When working with command prompt output, it can be helpful to know how many words it contains. This information can help you estimate the progress of a command or check the accuracy of a script or program's output. In this post, we'll explore several command-line tools that can count the number of words in command prompt output."
date: 2020-01-29
layout: post
---

<article>
  <img alt="gray metal framed chalkboard with whatever it takes written" src="https://images.unsplash.com/photo-1491234323906-4f056ca415bc?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENvdW50JTIwV29yZHMlMjBpbiUyMENvbW1hbmQlMjBQcm9tcHQlMjBPdXRwdXR8ZW58MHwwfHx8MTY4MzY2MDk1NA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>When working with command prompt output, it can be helpful to know how many words it contains. This information can help you estimate the progress of a command or check the accuracy of a script or program's output. In this post, we'll explore several command-line tools that can count the number of words in command prompt output.</p>
  <h2>Method 1: Using the find Command</h2>
  <p>The easiest way to count words in command prompt output is by using the <code>find</code> command. This tool can locate files and directories that match specific criteria. To count the number of words in command prompt output, pipe the output to <code>find /c /v ""</code>. For example, to count the number of words in the output of the <code>dir</code> command, use:</p>
  <pre><code>dir
dir | find /c /v ""</code></pre>
  <p>This will display the files and directories in the current folder, along with the number of words in the output of the <code>dir</code> command.</p>
  <h2>Method 2: Using the sed Command</h2>
  <p>The <code>sed</code> command is a powerful tool for processing text files and command prompt output. To count words in command prompt output using <code>sed</code>, pipe the output to <code>sed 's/[^[:alpha:]]/ /g;s/  */ /g' | wc -w</code>. For example, to count the number of words in the output of the <code>dir</code> command, use:</p>
  <pre><code>dir
dir | sed 's/[^[:alpha:]]/ /g;s/  */ /g' | wc -w</code></pre>
  <p>This will show the files and directories in the current folder, along with the number of words in the output of the <code>dir</code> command.</p>
  <h2>Method 3: Using the tr Command</h2>
  <p>The <code>tr</code> command is a useful tool for translating, deleting, or squeezing characters in command prompt output. To count words in command prompt output using <code>tr</code>, pipe the output to <code>tr -s ' ' '\n' | wc -w</code>. For example, to count the number of words in the output of the <code>dir</code> command, use:</p>
  <pre><code>dir
dir | tr -s ' ' '\n' | wc -w</code></pre>
  <p>This will display the files and directories in the current folder, along with the number of words in the output of the <code>dir</code> command.</p>
  <h2>Usage Scenarios</h2>
  <p>Knowing how to count words in command prompt output can be beneficial in various situations. For example, if you're running a command that generates a lot of output, you may want to keep track of the word count to estimate the command's progress. Also, if you're a developer working on a script or program that generates text output, you may want to verify the correctness of the output by counting the number of words.</p>
  <h2>Conclusion</h2>
  <p>Using tools such as find, sed, and tr, we can easily count the number of words in command prompt output. The most appropriate methodwill depend on the specific circumstances and the type of output. By understanding these strategies, we can increase our productivity as system administrators or developers.</p>
</article>