---
title: "How to Install Kubernetes on Ubuntu"
description: "Kubernetes is a container orchestration platform that allows users to launch and scale containerized applications easily. It operates by coordinating communication among worker nodes that host the containers, and users can interact with the cluster and manage their applications through an API provided by Kubernetes."
date: 2020-01-13
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0NTZ8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBLdWJlcm5ldGVzJTIwb24lMjBVYnVudHV8ZW58MHwwfHx8MTY4MzY2MDkxNg&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>Kubernetes is a container orchestration platform that allows users to launch and scale containerized applications easily. It operates by coordinating communication among worker nodes that host the containers, and users can interact with the cluster and manage their applications through an API provided by Kubernetes.</p>
  <p>Below are the steps to install Kubernetes on Ubuntu using three different methods:</p>
  <h2>Method 1: APT</h2>
  <p>The official Kubernetes repository can be accessed using the apt command for easy installation on Ubuntu, as shown below:</p>
  <pre><code>sudo apt install -y kubelet kubeadm kubectl</code></pre>
  <p>To verify the installation, use the following command:</p>
  <pre><code>kubectl version</code></pre>
  <p>The version of Kubernetes installed will be displayed.</p>
  <p>To uninstall Kubernetes, use the following command:</p>
  <pre><code>sudo apt purge kubelet kubeadm kubectl -y</code></pre>
  <h2>Method 2: Snap</h2>
  <p>Another way to install Kubernetes on Ubuntu is via the Snap store, which offers easy installation and management of software packages, as shown below:</p>
  <p>Step 1: Install the Snap daemon using the following command:</p>
  <pre><code>sudo apt install snapd -y</code></pre>
  <p>Step 2: Install Kubernetes using the Snap command:</p>
  <pre><code>sudo snap install kubectl --classic</code></pre>
  <p>To check the installed version of Kubernetes, use the following command:</p>
  <pre><code>kubectl version</code></pre>
  <p>To remove Kubernetes installed via the Snap command, use the following command:</p>
  <pre><code>sudo snap remove kubectl</code></pre>
  <h2>Method 3: MicroK8s</h2>
  <p>MicroK8s is a lightweight Kubernetes distribution optimized for development and testing on workstations and small-scale deployments. Here's how to install MicroK8s on Ubuntu:</p>
  <p>Step 1: Run the following command to install MicroK8s:</p>
  <pre><code>sudo snap install microk8s --classic</code></pre>
  <p>Step 2: Verify that the installation is successful by checking the status of the MicroK8s service:</p>
  <pre><code>sudo microk8s status --wait-ready</code></pre>
  <p>Step 3: Join the MicroK8s group to gain access to the Kubernetes command-line interface:</p>
  <pre><code>sudo usermod -aG microk8s &lt;username&gt;</code></pre>
  <p>Step 4: Log out and log back in for the group membership changes to take effect.</p>
  <h2>Conclusion</h2>
  <p>These are the three methods for installing Kubernetes on Ubuntu. Each method has its own advantages and disadvantages, so choose the one that best suits your needs. Kubernetes is an excellent platform for managing containerized applications, and once you have it installed, you can enjoy the benefits of easy scaling, deployment, and management of your applications.</p>
</article>