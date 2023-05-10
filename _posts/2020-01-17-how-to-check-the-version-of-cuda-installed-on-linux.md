---
title: "How to Check the Version of CUDA Installed on Linux"
description: "If you are using NVIDIA GPUs for complex computations, you might have installed CUDA on your Linux system. CUDA is a programming language that accelerates computations on NVIDIA GPUs, including Artificial Intelligence applications. In this guide, we will show you how to check the version of CUDA installed on your Linux system without using any advanced technology."
date: 2020-01-17
layout: post
---

<article>
  <img alt="woman standing near driftwood" src="https://images.unsplash.com/photo-1511237499363-177130e8a933?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMENoZWNrJTIwdGhlJTIwVmVyc2lvbiUyMG9mJTIwQ1VEQSUyMEluc3RhbGxlZCUyMG9uJTIwTGludXh8ZW58MHwwfHx8MTY4MzY2MDkyOQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you are using NVIDIA GPUs for complex computations, you might have installed CUDA on your Linux system. CUDA is a programming language that accelerates computations on NVIDIA GPUs, including Artificial Intelligence applications. In this guide, we will show you how to check the version of CUDA installed on your Linux system without using any advanced technology.</p>
  <h2>Table of Contents:</h2>
  <ul>
    <li>Getting the Maximum Supported CUDA Version on Linux</li>
    <li>Getting the Installed CUDA Version Number on Linux</li>
    <li>Checking CUDA Driver Compatibility with Installed GPU</li>
    <li>Verifying the Path and Environment Variables for CUDA</li>
  </ul>
  <h2>Getting the Maximum Supported CUDA Version on Linux</h2>
  <p>If you want to determine the maximum supported CUDA version on your Linux system, follow these steps:</p>
  <code>nvidia-detect</code>
  <p>The output will display the installed NVIDIA driver version and the highest supported CUDA version for that driver. For instance, if the driver version is 450.119.03, it means that it supports CUDA version 10.1 or lower.<sup>[1][2]</sup></p>
  <h2>Getting the Installed CUDA Version Number on Linux</h2>
  <p>To find out the installed CUDA version number on your Linux system, follow these steps:</p>
  <code>nvcc --version</code>
  <p>The output will show the installed CUDA version number. For example, if the output shows CUDA version v11.2.109, it means that version 11.2.109 of CUDA is installed on your Linux system.</p>
  <h2>Checking CUDA Driver Compatibility with Installed GPU</h2>
  <p>Before installing or updating the CUDA driver, you need to ensure that it is compatible with your installed GPU. To check the compatibility of the installed driver with your GPU, follow these steps:</p>
  <code>nvidia-smi</code>
  <p>The output will display information about the installed NVIDIA driver and the GPU(s) in your system. Check the "CUDA Version" column to confirm that the installed driver supports the desired CUDA version.</p>
  <h2>Verifying the Path and Environment Variables for CUDA</h2>
  <p>After installing CUDA on your Linux system, you need to verify that the path and environment variables are set up correctly. To check the path, follow these steps:</p>
  <code>echo $PATH</code>
  <p>The output will display the current path environment variable. Verify that the CUDA path is included in the output. Similarly, you can check if the environment variable is correctly set by executing the following command:</p>
  <code>echo $LD_LIBRARY_PATH</code>
  <p>The output will display the current LD_LIBRARY_PATH environment variable. Verify that it includes the path to the CUDA library files.</p>
  <h2>Conclusion</h2>
  <p>In this guide, we have shown you how to check the version of CUDA installed on your Linux system without using any advanced technology. We have covered how to determine the maximum supported CUDA version, find the installed CUDA version number, check the compatibility of the CUDA driver with your GPU, and verify the path and environment variables for CUDA.</p>
  <h2>References:</h2>
  <ol>
    <li>NVIDIA GPU Deployment Kit documentation: <a href="https://docs.nvidia.com/deploy/index.html">https://docs.nvidia.com/deploy/index.html</a></li>
<li>CUDA Installation Guide for Linux: <a href="https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html">https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html</a></li>
  </ol>
</article>