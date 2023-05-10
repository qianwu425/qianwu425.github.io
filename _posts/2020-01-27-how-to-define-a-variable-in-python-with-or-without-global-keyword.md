---
title: How to Define a Variable in Python With or Without Global Keyword
description: Python is a versatile programming language that can be used for various purposes, such as automation, data analysis, and web development. One of its key features is the ability to define variables, which hold data and can be used across different functions or areas of a program. However, it is important to understand the difference between defining a variable with or without the "global" keyword.
date: 2020-01-27
layout: post
---

<article>
  <img alt="person holding black and brown globe ball while standing on grass land golden hour photography" src="https://images.unsplash.com/photo-1476304884326-cd2c88572c5f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMERlZmluZSUyMGElMjBWYXJpYWJsZSUyMGluJTIwUHl0aG9uJTIwd2l0aCUyMG9yJTIwd2l0aG91dCUyMEdsb2JhbCUyMEtleXdvcmR8ZW58MHwwfHx8MTY4MzY2MDk1MA&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Python is a versatile programming language that can be used for various purposes, such as automation, data analysis, and web development. One of its key features is the ability to define variables, which hold data and can be used across different functions or areas of a program. However, it is important to understand the difference between defining a variable with or without the "global" keyword.</p>
  <p>In this article, you'll learn how to define a variable in Python with or without "global."</p>
  <h2>Defining a Variable without Global in Python</h2>
  <p>When defining a variable without the "global" keyword in Python, it becomes a local variable that is only accessible within the current function or module. Local variables are useful for storing temporary data required only within a specific part of a program. For example:</p>
  <pre><code>def my_function():
    my_var = "Hello, Python!"
    print(my_var)
    another_function()
def another_function():
# This line would cause an error since "my_var" is a local variable within "my_function"
# print(my_var)
pass
my_function()</code></pre>
  <p>In this case, "my_var" is a local variable accessible only within the "my_function" function. When the function runs, it prints "Hello, Python!" to the console. However, when it calls the "another_function," the function won't be able to access the value of "my_var."</p>
  <p>It is important to note that using local variables can help avoid confusion and unexpected results, especially in larger programs.</p>
  <h2>Defining a Variable with Global in Python</h2>
  <p>When defining a variable with the "global" keyword in Python, it becomes a global variable that can be used across different functions or areas of a program. For instance:</p>
  <pre><code>def my_function():
    global my_var
    my_var = "Hello, Python!"
    print(my_var)
    another_function()
def another_function():
print(my_var)
my_function()</code></pre>
  <p>In this case, "my_var" is a global variable that can be accessed by functions or modules called from within the current module. When the "my_function" runs, it prints "Hello, Python!" to the console. When it calls the "another_function," the function can access the value of "my_var."</p>
  <p>It is important to use global variables only when necessary to avoid unexpected results in the program.</p>
  <h2>Scoping Rules for Python Variables</h2>
  <p>When declaring variables in Python, you should be aware of the unique scoping constraints that apply. The areas of the program where a variable is accessible are referred to as its scope.</p>
  <p>Without the "global" keyword, a variable defined inside of a function is referred to as a local variable. Local variables are only accessible within the function where they're defined.</p>
  <p>On the other hand, a variable is regarded as a global variable when it is defined using the "global" keyword inside of a function. Any portion of the program, including other functions or modules, can access global variables.</p>
  <p>It is generally recommended to use local variables wherever possible and only use global variables when necessary to avoid unexpected results in the program.</p>
  <h2>Defining a Variable in Python Classes</h2><p>In addition to functions and modules, you can also define variables within Python classes. When you define a variable within a class, it's referred to as a class variable.</p>
  <p>Class variables are shared across all instances of the class, meaning that they're accessible by all the objects created from that class.</p>
  <pre><code>class MyClass:
    my_var = "Hello, Python!"

def my_method(self):
print(MyClass.my_var)</code></pre>

  <p>In this example, the class variable "my_var" is defined inside the "MyClass" class. The "my_method" method can access the class variable using the class name followed by the variable name.</p>
  <p>You can also define instance variables within Python classes. Instance variables are unique to each instance of the class, meaning that each object created from the class has its own set of instance variables. To define an instance variable, you can use the "self" keyword within a method:</p>
  <pre><code>class MyClass:
    def __init__(self):
        self.my_var = "Hello, Python!"

def my_method(self):
print(self.my_var)</code></pre>

  <p>In this example, "my_var" is an instance variable defined within the "__init__" method of the "MyClass" class. Each object created from the class will have its own "my_var" instance variable, initialized to "Hello, Python!".</p>
  <h2>Conclusion</h2>
  <p>In Python, defining variables is a crucial component of programming. Based on your requirements and the variable's scope, you should decide whether to define a variable with or without the "global" keyword. Keep in mind that global variables can be accessed from anywhere in the program, whereas local variables can only be accessed from the function or module where they are defined.</p>
  <p>Additionally, you can specify variables inside of Python classes as either instance variables, which are specific to each instance of the class, or class variables, which are shared by all instances of the class.</p>
</article>
