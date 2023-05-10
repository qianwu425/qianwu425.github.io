---
title: "How to Rename All Files in a Directory Using Bash"
description: "Managing a large number of files in a directory can be made simpler by renaming them in bulk. In Linux, there are several ways to rename files using Bash scripting. Here are some of the methods:"
date: 2020-01-26
layout: post
---

<article>
    <img alt="a person holding a book" src="https://images.unsplash.com/photo-1664382952681-30fe4b179437?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMFJlbmFtZSUyMEFsbCUyMEZpbGVzJTIwaW4lMjBhJTIwRGlyZWN0b3J5JTIwVXNpbmclMjBCYXNofGVufDB8MHx8fDE2ODM2NjA5NDk&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
    <p>Managing a large number of files in a directory can be made simpler by renaming them in bulk. In Linux, there are several ways to rename files using Bash scripting. Here are some of the methods:</p>
    <h2>Method 1: Using the Rename Command</h2>
    <p>The <code>rename</code> command is a useful tool for renaming files in Linux. To rename all files in a directory from <code>old_suffix</code> to <code>new_suffix</code>, use the following command:</p>
    <pre><code class="language-bash">rename 's/\Qold_suffix\E$/new_suffix/' *</code></pre>
    <p>In the above command, the <code>s</code> flag denotes that a substitution is being performed, and the pattern <code>\Qold_suffix\E$</code> matches the <code>old_suffix</code> string at the end of the filename. The matched string is replaced with <code>new_suffix</code>. The <code>*</code> at the end of the command specifies that the command should be applied to all files in the directory.</p>
    <h2>Method 2: Using a for Loop with the <code>mv</code> Command</h2>
    <p>Bash can also be used to rename all files in a directory. Use the following command:</p>
    <pre><code class="language-bash">for file in *suffix
do
    mv "$file" "${file/suffix/new_suffix}"
done</code></pre>
    <p>The above script iterates through each file that ends with <code>suffix</code> in the current directory and renames the file by replacing <code>suffix</code> with <code>new_suffix</code>.</p>
    <h2>Method 3: Using the Perl Command</h2>
    <p>Perl is a versatile computer language that can be used for file management tasks. Use the following Perl code to change the suffix of all files in a directory from <code>old_suffix</code> to <code>new_suffix</code>:</p>
    <pre><code class="language-bash">perl -e 'for(@ARGV){$new = $_; $new =~ s/\Qold_suffix\E$/new_suffix/; rename($_, $new);}' *</code></pre>
    <p>All files in the current directory that end in <code>old_suffix</code> are renamed to end in <code>new_suffix</code> using the Perl command. The string at the end of the filename, <code>old_suffix</code>, is changed to <code>new_suffix</code> using a regular expression. The <code>*</code> at the end of the command specifies that the command should be applied to all files in the directory.</p>
    <h2>Method 4: Using the <code>mmv</code> Command</h2>
    <p>The <code>mmv</code> command is another useful tool for renaming multiple files in Linux. To rename all files in a directory from <code>old_suffix</code> to <code>new_suffix</code> using <code>mmv</code>, use the following syntax:</p>
<pre><code class="language-bash">mmv 'old_suffix' '#1new_suffix'</code></pre>
<p>The hashtag (<code>#1</code>) in the command above stands for the matched component of the filename, while the asterisk (<code>*</code>)indicates any letter or string of characters. The <code>new_suffix</code> string will be appended to the filename in place of the <code>old_suffix</code> string by the <code>mmv</code> command.</p>
<h2>Method 5: Using Python Scripting</h2>
<p>Python is a popular programming language that can be used for various file management tasks, including renaming files. To rename all files in a directory from <code>old_suffix</code> to <code>new_suffix</code> using Python, use the following code:</p>
<pre><code class="language-python">import os
for filename in os.listdir("."):
if filename.endswith("old_suffix"):
os.rename(filename, filename[:-len("old_suffix")] + "new_suffix")</code></pre>
<p>The above Python script uses the <code>os</code> module to iterate through each file in the current directory and rename files that end with <code>old_suffix</code>. The script first checks if the file ends with <code>old_suffix</code> using the <code>endswith()</code> method, and then renames the file by concatenating the string before the <code>old_suffix</code> with <code>new_suffix</code> using slicing.</p>
<h2>Conclusion</h2>
<p>Renaming files in Linux can be challenging, but there are fast and effective ways to do it using these techniques. Linux users can use <code>rename</code>, <code>mv</code>, <code>perl</code>, <code>mmv</code>, and Python utilities to manipulate files. With these techniques, you can quickly rename every file in a directory, helping your files become more consistent and organized.</p>
</article>