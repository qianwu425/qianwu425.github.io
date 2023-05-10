---
title: "How to Extract Part of a String Using Bash Cut and Split Commands"
description: "Separating a particular section of a string from a larger text is a frequent requirement when dealing with Linux/Unix systems. Bash offers several options, including the cut and split commands, to achieve this goal. This post explores how to extract specific parts of a string using these commands, along with useful examples."
date: 2020-01-24
layout: post
---

<article>
  <img alt="aerial photography of city during daytime" src="https://images.unsplash.com/photo-1564679947263-f2d694434710?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEV4dHJhY3QlMjBQYXJ0JTIwb2YlMjBhJTIwU3RyaW5nJTIwVXNpbmclMjBCYXNoJTIwQ3V0JTIwYW5kJTIwU3BsaXQlMjBDb21tYW5kc3xlbnwwfDB8fHwxNjgzNjYwOTQ0&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Separating a particular section of a string from a larger text is a frequent requirement when dealing with Linux/Unix systems. Bash offers several options, including the cut and split commands, to achieve this goal. This post explores how to extract specific parts of a string using these commands, along with useful examples.</p>
  <h2>The Cut Command</h2>
  <p>The cut command is a powerful tool that extracts sections from each line of a file or string based on a delimiter or a specific character. To use the cut command, use the following syntax:</p>
  <pre><code>cut -d [delimiter] -f [field] [filename]</code></pre>
  <p>Here, the <code>-d</code> option specifies the delimiter used in the input file, the <code>-f</code> option specifies the field(s) to be extracted, and the <code>filename</code> argument is the input file to be processed. For example, consider a file named <code>data.txt</code> containing the following content:</p>
  <pre><code>John,Smith,30
Jane,Doe,25
Bob,Johnson,40</code></pre>
  <p>To extract the last name of each person from the file, you can use the following shell script:</p>
  <pre><code>#!/bin/bash
cat data.txt
echo "Extracted Last Names:"
cut -d ',' -f 2 data.txt</code></pre>
  <p>The above code displays the file and its extracted last names in the output.</p>
  <h2>The Split Command</h2>
  <p>The split command, built into Bash, divides a string into several substrings based on a delimiter. To use the Bash split command, use the following syntax:</p>
  <pre><code>IFS=[delimiter] read -ra [array_name] &lt;&lt;&lt; "$[string]"</code></pre>
  <p>The read command receives the input, separates it into an array, and uses the operator to pass the string as input. The IFS variable determines the delimiter used in the string. For example, let's take the string "apple,banana,orange". We can use the following Bash script to extract the second fruit from the string:</p>
  <pre><code>#!/bin/bash
echo "Extracted Fruit:"
IFS=',' read -ra fruits &lt;&lt;&lt; "apple,banana,orange"
echo ${fruits[1]}</code></pre>
  <p>The Bash split command can also extract multiple fields from a string by using several variables in the read command.</p>
  <h2>The Sed Command</h2>
  <p>The sed command is another useful tool for extracting part of a string in Bash. It is primarily used for text substitution or replacement, but it can also extract specific parts of a string. To use the sed command, use the following syntax:</p>
  <pre><code>sed 's/\(.*\)\([pattern]\)\(.*\)/\2/' [filename]</code></pre>
  <p>The <code>s</code> command in sed is used for substitution, and the regular expression in the command searches for the pattern and extracts it. For example, consider a file named <code>data.txt</code> containing the following content:</p>
  <pre><code>John,Smith,30
Jane,Doe,25
Bob,Johnson,40</code></pre><pthe command="" each="" extract="" file:<="" first="" following="" from="" name="" p="" person's="" script="" sed="" shell="" the="" to="" uses="">
  <pre><code>#!/bin/bash
cat data.txt
echo "Extracted First Names:"
sed 's/\(.*\),\(.*\),\(.*\)/\1/' data.txt</code></pre>
  <p>The above code displays the file and its extracted first names in the output.</p>
  <h2>The Awk Command</h2>
  <p>The awk command is a powerful text processing tool that can also be used for extracting part of a string. It can split input lines into fields, manipulate them, and then output the result. To use the awk command, use the following syntax:</p>
  <pre><code>awk -F [delimiter] '{print $[field]}' [filename]</code></pre>
  <p>Here, the <code>-F</code> option specifies the delimiter used in the input file, and the <code>{print $[field]}</code> command prints the specified field. For example, consider a file named <code>data.txt</code> containing the following content:</p>
  <pre><code>John,Smith,30
Jane,Doe,25
Bob,Johnson,40</code></pre>
  <p>To extract the age of each person from the file using the awk command, use the following shell script:</p>
  <pre><code>#!/bin/bash
cat data.txt
echo "Extracted Ages:"
awk -F ',' '{print $3}' data.txt</code></pre>
  <p>The above code displays the file and its extracted ages in the output.</p>
  <h2>Conclusion</h2>
  <p>Extracting part of a string is a common task in Linux/Unix programming, and Bash provides several methods to accomplish this. In addition to the cut and split commands, the sed and awk commands are also useful tools for this purpose. By understanding how to use these commands, you can become more efficient when working with Bash scripts.</p>
</pthe></article>