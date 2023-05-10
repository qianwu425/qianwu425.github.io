---
title: "How to Retrieve Command Line Arguments With Flags in Python"
description: "Python is a powerful and versatile programming language that offers flexibility for various applications. One useful feature is the ability to use flags to send optional parameters to scripts. Here's how you can retrieve command-line arguments with flags in Python."
date: 2020-01-28
layout: post
---

<article>
  <img alt="the shadow of a person holding a cell phone" src="https://images.unsplash.com/photo-1541347362070-a5aef68d403a?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFJldHJpZXZlJTIwQ29tbWFuZCUyMExpbmUlMjBBcmd1bWVudHMlMjB3aXRoJTIwRmxhZ3MlMjBpbiUyMFB5dGhvbnxlbnwwfDB8fHwxNjgzNjYwOTUx&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Python is a powerful and versatile programming language that offers flexibility for various applications. One useful feature is the ability to use flags to send optional parameters to scripts. Here's how you can retrieve command-line arguments with flags in Python.</p>
  <h2>Retrieving Command Line Arguments with Flags in Python</h2>
  <p>The argparse module is a built-in package in Python that can help retrieve command-line arguments with flags. Here's an example of how to use it:</p>
  <pre><code>import argparse
parser = argparse.ArgumentParser()
parser.add_argument("-a", "--argument1", help="description of argument 1")
parser.add_argument("-b", "--argument2", help="description of argument 2")
args = parser.parse_args()
print(f"Argument 1: {args.argument1}")
print(f"Argument 2: {args.argument2}")</code></pre>
  <p>In this example, the argparse module is used to define two parameters (-a and -b) that can be given as flags. The help argument provides a description of each parameter, which can be accessed by typing --help or -h. The parse_args() method parses the arguments and returns an object containing their values, which are accessed using their names.</p>
  <p>To use this with flags, run the script with the flag options and arguments as follows:</p>
  <pre><code>python &lt;script-name&gt; -a &lt;argument1&gt; -b &lt;argument2&gt;</code></pre>
  <p>If an argument is not supplied, its value is None. To ensure that a value is supplied, use the required=True parameter when specifying the argument.</p>
  <p>The argparse module provides a simple way to add and parse command-line arguments with flags, making your Python scripts more flexible and user-friendly.</p>
  <h2>Using Default Values for Arguments</h2>
  <p>You can also set default values for command-line arguments by providing a default parameter when defining the argument using the add_argument() method. Here's an example:</p>
  <pre><code>import argparse
parser = argparse.ArgumentParser()
parser.add_argument("-a", "--argument1", help="description of argument 1", default="default_value")
args = parser.parse_args()
print(f"Argument 1: {args.argument1}")</code></pre>
  <p>In this example, the default value of "default_value" is assigned to argument1 if it is not provided when the script is run. Default values can also be set for other types of arguments, such as integers and boolean values.</p>
  <h2>Using Aliases for Arguments</h2>
  <p>You can define aliases for command-line arguments by providing a list of aliases as the first parameter when defining the argument using the add_argument() method. Here's an example:</p>
  <pre><code>import argparse
parser = argparse.ArgumentParser()
parser.add_argument("-a", "--argument1", help="description of argument 1", aliases=["--alias1"])
args = parser.parse_args()
print(f"Argument 1: {args.argument1}")</code></pre>
  <p>In this example, both -a and --alias1 can be used to specify the argument1 value when the script is run. Aliases can be useful when providing users with multiple ways to specify the same argument.</p>
</article>