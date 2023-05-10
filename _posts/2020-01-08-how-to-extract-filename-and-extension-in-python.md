---
title: "How to Extract Filename and Extension in Python"
description: "If you work with files in Python, a common task is to extract the filename and extension from a file path. This article explains how to extract filename and extension in Python and provides examples on how to use these values in your Python scripts."
date: 2020-01-08
layout: post
---

<article>
  <img alt="person holding sticky note" src="https://images.unsplash.com/photo-1526379095098-d400fd0bf935?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEV4dHJhY3QlMjBGaWxlbmFtZSUyMGFuZCUyMEV4dGVuc2lvbiUyMGluJTIwUHl0aG9ufGVufDB8MHx8fDE2ODM2NjA5MDM&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you work with files in Python, a common task is to extract the filename and extension from a file path. This article explains how to extract filename and extension in Python and provides examples on how to use these values in your Python scripts.</p>
  <h2>Extracting Filename and Extension in Python</h2>
  <p>When working with files in Python, you may need to extract the filename and extension from a file path. In this section, we'll discuss three common methods for doing this in Python.</p>
  <h2>Method 1: Using a Module</h2>
  <p>Python provides several modules for working with file paths. One of them is <code>os.path</code>, which has a function called <code>split()</code> that separates a path into its directory and filename components. You can then use the <code>splitext()</code> function to separate the filename and extension. Here's an example:</p>
  <pre><code>import os
Example file path:
file_path = "/path/to/file.txt"
Extract filename and extension:
filename, extension = os.path.splitext(file_path)
print("Filename:", filename)
print("Extension:", extension)</code></pre>
  <h2>Method 2: Using the Path Object</h2>
  <p>The <code>Path</code> object, which is part of the <code>pathlib</code> module, provides an object-oriented way to work with file paths. You can use the <code>name</code> and <code>suffix</code> attributes to extract the filename and extension, respectively. Here's an example:</p>
  <pre><code>import pathlib
Example file path:
file_path = "/path/to/file.txt"
Create Path object:
path = pathlib.Path(file_path)
Extract filename and extension:
filename = path.name
extension = path.suffix
print("Filename:", filename)
print("Extension:", extension)</code></pre>
  <h2>Method 3: Using Regular Expressions</h2>
  <p>If you need more control over the filename and extension extraction process, you can use regular expressions. Here's an example:</p>
  <pre><code>import re
Example file path:
file_path = "/path/to/file.txt"
Extract filename and extension using regular expressions:
match = re.search(r"/([\w\s-]+)\.([A-Za-z]{3})", file_path)
filename = match.group(1)
extension = match.group(2)
print("Filename:", filename)
print("Extension:", extension)</code></pre>
  <h2>Using the Filename and Extension in Python</h2>
  <p>Once you've extracted the filename and extension from a file path, you can use them in various ways in your Python scripts. Here are some examples:</p>
  <ul>
    <li>Perform different operations based on the file extension</li>
    <li>Modify the filename and extension before saving the file</li>
    <li>Use the filename or extension in a log message or output statement</li>
  </ul>
  <p>Here's an example code that demonstrates how to use the filename and extension values:</p>
  <pre><code>import os
Example file path:
file_path = "/path/to/file.txt"
Extract filename and extension:
filename, extension = os.path.splitext(file_path)
if extension == '.txt':
    print("Text file detected!")
else:
    print("File is not a text file.")
new_filename = 'newfile' + extension<code>new_file_path = os.path.join(os.path.dirname(file_path), new_filename)
print("New file path:", new_file_path)</code></code></pre><code>
  <p>In this example, we checked if the file extension is '.txt' and printed a message accordingly. Then, we created a new filename by adding a prefix ('newfile') to the existing extension, and used the <code>os.path.join()</code> function to create a new file path that includes the modified filename.</p>
  <h2>Conclusion</h2>
  <p>Extracting the filename and extension from a file path is a common task when working with files in Python. In this article, we discussed three common methods for extracting the filename and extension in Python, including using the <code>os.path</code> module, the <code>Path</code> object from the <code>pathlib</code> module, and regular expressions. We also provided examples of how to use the extracted filename and extension values in Python scripts. By using these techniques, you can easily and quickly work with file paths in your Python programs.</p>
</code></article>