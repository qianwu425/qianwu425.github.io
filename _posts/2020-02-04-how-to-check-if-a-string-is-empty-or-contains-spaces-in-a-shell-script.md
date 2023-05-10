---
title: "How to Check If a String Is Empty or Contains Spaces in a Shell Script"
description: "When working with strings in Shell scripting, it's crucial to check if they are not empty or solely composed of spaces to avoid unexpected results. In this article, we'll discuss multiple methods to detect whether a string is empty or includes spaces in a Shell script."
date: 2020-02-04
layout: post
---

<article>
  <img alt="low angle photography of Shell gas station at night" src="https://images.unsplash.com/photo-1545262810-77515befe149?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENoZWNrJTIwaWYlMjBhJTIwU3RyaW5nJTIwaXMlMjBFbXB0eSUyMG9yJTIwQ29udGFpbnMlMjBTcGFjZXMlMjBpbiUyMGElMjBTaGVsbCUyMFNjcmlwdHxlbnwwfDB8fHwxNjgzNjYwOTcx&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>When working with strings in Shell scripting, it's crucial to check if they are not empty or solely composed of spaces to avoid unexpected results. In this article, we'll discuss multiple methods to detect whether a string is empty or includes spaces in a Shell script.</p>
  <h2>Ways to Check if a String is Empty or Contains Spaces in a Shell Script</h2>
  <p>Here are two methods you can use in a Shell script to determine if a string is empty or solely composed of spaces:</p>
  <h3>Method 1: Using -n and -z Operators</h3>
  <p>In Shell scripting, the -n operator checks if a string's length is greater than zero, while the -z operator checks if a string's length is zero. You can combine these operators to determine whether a string is not empty and does not contain only spaces. Here's an example:</p>
  <pre><code>#!/bin/bash
string="Hello World"
if [ -n "${string}" ] &amp;&amp; [ -z "$(echo ${string} | tr -d '[:digit:]')" ]
then
echo "The string is not empty and does not solely contain spaces."
else
echo "The string is either empty or solely contains spaces."
fi</code></pre>
  <p>In this example, the -n operator checks if the string's length is greater than zero. Then, the tr command removes all digits from the string, and the -z operator verifies if the resulting string's length is zero. If both conditions are met, we can conclude that the string is not empty and does not contain only spaces.</p>
  <h3>Method 2: Using Regular Expressions</h3>
  <p>You can use regular expressions in a Shell script to determine if a string is empty or solely composed of spaces. Here's an example:</p>
  <pre><code>#!/bin/bash
string="Hello World"
if [[ "${string}" =~ ^[[:digit:]]*$ ]]
then
echo "The string is either empty or solely contains spaces."
else
echo "The string is not empty and does not solely contain spaces."
fi</code></pre>
  <p>In this example, the regular expression [[:digit:]]*$ matches strings that begin and end with zero or more digits. We can deduce that the string is empty or solely contains spaces if it matches this regular expression.</p>
  <h2>Additional Information</h2>
  <p>Here are some additional things to keep in mind when checking for empty or space-only strings in Shell scripts:</p>
  <h3>Method 3: Using the -o Operator</h3>
  <p>The -o operator can be used with the -z operator to determine if a string is either empty or solely composed of spaces. Here's an example:</p>
  <pre><code>#!/bin/bash
string="Hello World"
if [ -z "${string// }" -o -z "${string}" ]
then
echo "The string is either empty or solely contains spaces."
else
echo "The string is not empty and does not solely contain spaces."
fi</code></pre>
  <p>In this example, the parameter expansion removes all spaces from the string, and the -z operator checks if the resulting string's length is zero. Additionally, the same operator checks if the original string's length is zero. If either condition is met, we can conclude that the string is either empty or solely contains spaces.</p>
  <h3>Trimming Leading and Trailing Spaces</h3>
  <p>A string may contain spaces at the beginning or end, which can affect how it's handled in a Shell script. To remove leading and trailing spaces from a string, you can use the following syntax:</p>
  <pre><code>string="  Hello World   "
trimmed_string=${string##*( )}
trimmed_string=${trimmed_string%%*( )}
echo "The trimmed string is: ${trimmed_string}"</code></pre>
  <p>The first line initializes the "string" variable with a string containing leading and trailing spaces. The second and third lines use parameter expansion to remove leading and trailing spaces, respectively. Finally, the "trimmed_string" variable stores the resulting trimmed string, which is then printed to the console.</p>
  <h2>Conclusion</h2>
  <p>When working with Shell scripts, it's crucial to verify that strings do not include any characters or solely contain spaces before performing any operations on them. This article presented three distinct ways to check for empty or space-only strings in Shell scripts: the -n/-z operators, regular expressions, and the -o operator in conjunction with the -z operator. We also discussed how to remove leading and trailing spaces from a string. By utilizing these methods, we can ensure that our Shell scripts handle strings appropriately and avoid unexpected issues.</p>
</article>