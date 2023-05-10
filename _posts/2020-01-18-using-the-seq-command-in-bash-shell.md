---
title: "Using the Seq Command in Bash Shell"
description: "The seq command in Bash generates a sequence of numbers, which is helpful for creating ranges of integers, loops, and performing various tasks that require number sequences. This article will explain what the seq command is and provide three examples to demonstrate how it can be used."
date: 2020-01-18
layout: post
---

<article>
  <img alt="low angle photography of Shell gas station at night" src="https://images.unsplash.com/photo-1545262810-77515befe149?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxVc2luZyUyMHRoZSUyMHNlcSUyMENvbW1hbmQlMjBpbiUyMEJhc2glMjBTaGVsbHxlbnwwfDB8fHwxNjgzNjYwOTMx&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>The seq command in Bash generates a sequence of numbers, which is helpful for creating ranges of integers, loops, and performing various tasks that require number sequences. This article will explain what the seq command is and provide three examples to demonstrate how it can be used.</p>
  <h2>What is the seq Command in Bash?</h2>
  <p>The seq command in Bash is used to generate a sequence of numbers within a given range of arguments. By default, the increment value is 1, but it can be modified. The syntax for the seq command is:</p>
  <pre>seq [OPTION]... LAST<br/>seq [OPTION]... FIRST LAST<br/>seq [OPTION]... FIRST INCREMENT LAST</pre>
  <p>Here, the first argument is the starting number, the second argument is the ending number, and the third argument (if provided) is the increment value.</p>
  <h2>Examples</h2>
  <h3>Example 1: Print a Sequence of Even Numbers from 2 to 10</h3>
  <p>The following script demonstrates how to use the seq command to print a sequence of even numbers from 2 to 10:</p>
  <pre>#!/bin/bash
for i in $(seq 2 2 10); do
  echo $i
done
  </pre>
  <p>In this example, the seq command generates a sequence of even numbers from 2 to 10, which is then iterated over by the for loop to print each number.</p>
  <h3>Example 2: Print a Sequence of Numbers from 10 to 2 in Reverse Order</h3>
  <p>The following script demonstrates how to use the seq command to print a sequence of numbers from 10 to 2 in reverse order:</p>
  <pre>#!/bin/bash
for i in $(seq 10 -2 2); do
  echo $i
done
  </pre>
  <p>In this example, the seq command generates a sequence of numbers from 10 to 2, decrementing by 2 at each step. The for loop then prints the numbers in reverse order.</p>
  <h3>Example 3: Using seq in a Command Substitution</h3>
  <p>The following command demonstrates how to use the seq command within a command substitution to generate a list of numbers as arguments to another command:</p>
  <pre>echo $(seq 1 3)</pre>
  <p>The output of this command is:</p>
  <pre>1 2 3</pre>
  <p>In this example, the seq command generates a sequence of numbers from 1 to 3, which are then passed as arguments to the echo command through command substitution.</p>
  <h2>Conclusion</h2>
  <p>The seq command is a useful tool in Bash for generating number sequences. It can be used in various contexts, including loops, lists, and more. By understanding how to use the seq command, you can create complex scripts and perform more advanced tasks in your Bash programming.</p>
</article>