---
title: "How to Install CUDA on Ubuntu 23.04 LTS"
description: "CUDA is NVIDIA's platform and programming model for parallel computing, which speeds up computing programs by utilizing NVIDIA Graphics Processing Units (GPUs). In this article, we'll guide you through the process of installing CUDA on Ubuntu 23.04 LTS from the official Ubuntu package repository. We'll also show you how to write, compile, and run a simple CUDA program on Ubuntu 23.04 LTS."
date: 2020-01-09
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBDVURBJTIwb24lMjBVYnVudHUlMjAyMy4wNCUyMExUU3xlbnwwfDB8fHwxNjgzNjYwOTA2&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>CUDA is NVIDIA's platform and programming model for parallel computing, which speeds up computing programs by utilizing NVIDIA Graphics Processing Units (GPUs). In this article, we'll guide you through the process of installing CUDA on Ubuntu 23.04 LTS from the official Ubuntu package repository. We'll also show you how to write, compile, and run a simple CUDA program on Ubuntu 23.04 LTS.</p>
  <h2>Table of Contents</h2>
  <ul>
    <li>Prerequisites</li>
    <li>Installing NVIDIA Drivers on Ubuntu</li>
    <li>Updating the APT Package Repository Cache</li>
    <li>Installing GCC and Other Build Tools</li>
    <li>Installing CUDA on Ubuntu from the Official Ubuntu Package Repository</li>
    <li>Testing If CUDA Is Installed Successfully on Ubuntu</li>
    <li>Writing, Compiling, and Running a Simple CUDA Program</li>
    <li>Using CUDA with Python</li>
    <li>Conclusion</li>
  </ul>
  <h2>Prerequisites</h2>
  <p>To install and run CUDA programs on Ubuntu 23.04 LTS, you need to have an NVIDIA GPU installed on your computer, as well as NVIDIA GPU drivers installed on your Ubuntu operating system.</p>
  <h2>Installing NVIDIA Drivers on Ubuntu</h2>
  <p>Before installing CUDA, you need to have the NVIDIA GPU drivers installed on your Ubuntu operating system. If you haven't installed them yet, please refer to the NVIDIA documentation for assistance.</p>
  <h2>Updating the APT Package Repository Cache</h2>
  <p>After installing the NVIDIA drivers, refresh the APT package repository cache by running:</p>
  <pre><code>sudo apt update</code></pre>
  <p>Make sure that Ubuntu's APT package repository cache has been successfully updated.</p>
  <h2>Installing GCC and Other Build Tools</h2>
  <p>Install GCC and other build tools on your Ubuntu PC to compile CUDA apps:</p>
  <pre><code>sudo apt install build-essential</code></pre>
  <p>Confirm the installation by pressing Y and Enter. After installation, you should have the necessary build tools for CUDA to work. You can check if GCC C and C++ compilers are accessible by running:</p>
  <pre><code>gcc --version<br/>g++ --version</code></pre>
  <h2>Installing CUDA on Ubuntu from the Official Ubuntu Package Repository</h2>
  <p>To install CUDA from the official package repository of Ubuntu, run:</p>
  <pre><code>sudo apt install nvidia-cuda-toolkit nvidia-cuda-toolkit-gcc</code></pre>
  <p>Press Y and Enter to confirm the installation. CUDA should be installed on your Ubuntu laptop after the installation.</p>
  <h2>Testing If CUDA Is Installed Successfully on Ubuntu</h2>
  <p>Check if CUDA is installed successfully on Ubuntu by running:</p>
  <pre><code>nvcc --version</code></pre>
  <p>If CUDA is installed successfully, you should see the version of CUDA installed on your Ubuntu machine.</p>
  <h2>Writing, Compiling, and Running a Simple CUDA Program</h2>
  <p>We'll teach you how to write, compile, and run a simple CUDA application now that you've installed CUDA on yourUbuntu 23.04 LTS system. Follow these steps to accomplish this:</p>
  <ol>
    <li>Create a new file called hello_world.cu using a code editor of your choice. Save it in the ~/codes directory (or any directory of your choice). Note that CUDA source files end with the .cu extension.</li>
    <li>Copy and paste the provided code into the hello_world.cu file.</li>
    <li>Save the hello_world.cu file and navigate to the ~/codes directory using the Terminal.</li>
    <li>Compile the hello_world.cu program using the nvcc CUDA compiler and create an executable binary file called hello_world using the following command:</li>
  </ol>
  <pre><code>nvcc hello_world.cu -o hello_world</code></pre>
  <p>The command will compile the hello_world.cu program without issues and generate a new executable binary file called hello_world.</p>
  <ol start="5">
    <li>Run the compiled hello_world CUDA program using the following command:</li>
  </ol>
  <pre><code>./hello_world</code></pre>
  <p>If CUDA is working correctly on your Ubuntu machine, you should see the output "Hello world from the CPU!" followed by "Hello world from the GPU!".</p>
  <h2>Using CUDA with Python</h2>
  <p>CUDA can also be used with Python, allowing you to use GPU capabilities from within your Python code. To utilize CUDA with Python, your Ubuntu machine must have both the CUDA toolkit and the Python CUDA driver installed. You can use the following commands to install them:</p>
  <pre><code>sudo apt install nvidia-cuda-toolkit
sudo apt install python3-pycuda</code></pre>
  <p>After installing these packages, you can use the PyCUDA Python module to write and run CUDA programs in Python. To use PyCUDA, you need to import it in your Python code and set up a CUDA context:</p>
  <pre><code>import pycuda.autoinit
import pycuda.driver as cuda
</code></pre>
  <p>Then, with PyCUDA, you can create CUDA code in Python and run it on the GPU. As an example:</p>
  <pre><code>import numpy as np
from pycuda.compiler import SourceModule
Define the CUDA kernel
mod = SourceModule('''
global void add_vectors(float *a, float *b, float *c)
{
int i = threadIdx.x;
c[i] = a[i] + b[i];
}
''')
Create arrays on the CPU and fill them with random values
a = np.random.randn(100).astype(np.float32)
b = np.random.randn(100).astype(np.float32)
c = np.zeros_like(a)
Copy the arrays to the GPU
a_gpu = cuda.to_device(a)
b_gpu = cuda.to_device(b)
c_gpu = cuda.to_device(c)
Launch the CUDA kernel
add_vectors = mod.get_function('add_vectors')
add_vectors(a_gpu, b_gpu, c_gpu, block=(100, 1, 1), grid=(1, 1))
Copy the result back to the CPU and print it
cuda.memcpy_dtoh(c, c_gpu)
print(c)
</code></pre>
  <p>This code defines a basic CUDA kernel that adds two arrays on the GPU and then returns the result to the CPU. It makes use of the PyCUDA module to create a CUDA environment as well as compile and run the CUDA kernel. Utilizing the GPU forthis operation can be significantly faster than using the CPU.</p>
  <h2>Conclusion</h2>
  <p>In this article, we have shown you how to install CUDA on Ubuntu 23.04 LTS from the official package repository of Ubuntu. We have also shown you how to write, compile, and run a simple CUDA program on Ubuntu 23.04 LTS. Additionally, we have demonstrated how to use CUDA with Python by using the PyCUDA module. We hope that this guide has been helpful to you and that you can now start exploring the world of GPU-accelerated computing using CUDA on your Ubuntu machine.</p>
</article>