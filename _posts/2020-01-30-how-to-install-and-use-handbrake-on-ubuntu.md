---
title: "How to Install and Use HandBrake on Ubuntu"
description: "HandBrake is a powerful video conversion software that can convert videos to multiple codecs and formats, such as MP4, MKV, and WebM. It also includes features to compress video files, restore old videos, and adjust audio levels. In this guide, we will show you how to install and use HandBrake on Ubuntu."
date: 2020-01-30
layout: post
---

<article>
  <img alt="green and black digital device" src="https://images.unsplash.com/photo-1629654291663-b91ad427698f?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODN8MHwxfHNlYXJjaHwxfHxIb3clMjB0byUyMEluc3RhbGwlMjBhbmQlMjBVc2UlMjBIYW5kQnJha2UlMjBvbiUyMFVidW50dXxlbnwwfDB8fHwxNjgzNjYwOTU4&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>HandBrake is a powerful video conversion software that can convert videos to multiple codecs and formats, such as MP4, MKV, and WebM. It also includes features to compress video files, restore old videos, and adjust audio levels. In this guide, we will show you how to install and use HandBrake on Ubuntu.</p>
  <h2>Installation of HandBrake on Ubuntu</h2>
  <p>You can install HandBrake on Ubuntu using either the Ubuntu repository or Flatpak. Here are the steps for both methods:</p>
  <h3>Install HandBrake from the Ubuntu Repository</h3>
  <p>First, update your system:</p>
  <code>sudo apt update</code>
  <p>Next, run the following command to install HandBrake:</p>
  <code>sudo apt install handbrake -y</code>
  <h3>Install HandBrake from Flatpak</h3>
  <p>If Flatpak is not installed on your system, you can install it with this command:</p>
  <code>sudo apt install flatpak -y</code>
  <p>After installing Flatpak, restart your system. Then, run this command to install HandBrake:</p>
  <code>flatpak install flathub org.handbrake.HandBrake -y</code>
  <p>You can launch HandBrake from the terminal with either of the following commands:</p>
  <code>handbrake</code>
  <code>ghb</code>
  <p>You can also launch HandBrake from the Application Menu by searching for it.</p>
  <h2>Using HandBrake on Ubuntu</h2>
  <p>To convert a video file using HandBrake, click "Open Source" and select the video file you want to convert. Then, choose the desired format from the "Presets" menu and click "Start" to begin the conversion process.</p>
  <h2>Uninstallation of HandBrake on Ubuntu</h2>
  <p>If you want to remove HandBrake from your Ubuntu computer, run the following command in the terminal:</p>
  <code>sudo apt-get remove handbrake -y</code>
  <p>If you installed HandBrake via Flatpak, use the following command to determine the Application ID:</p>
  <code>flatpak list</code>
  <p>Then, use the subsequent command to delete HandBrake:</p>
  <code>flatpak uninstall &lt;application-id&gt;</code>
  <h2>Customizing HandBrake</h2>
  <p>HandBrake includes a range of customizable settings that can be used to fine-tune your video conversions. Some of the settings you can adjust include video quality, codec, and file size. You can also create your own custom presets to use in future conversions.</p>
  <h3>Creating Custom Presets in HandBrake</h3>
  <p>To create a custom preset in HandBrake, first select the video file you wish to convert. Next, choose the settings you want for your own preset. Once you have chosen your settings, click the "Add" button and enter a name for your custom preset. You can now utilize your personal preset for upcoming conversions.</p>
  <h2>Troubleshooting HandBrake on Ubuntu</h2>
  <p>If you run into problems installing or using HandBrake on Ubuntu, there arevarious troubleshooting techniques you can use. Here are some common issues and their fixes:</p>
  <h3>HandBrake is not opening</h3>
  <p>If HandBrake is not opening on your Ubuntu machine, try launching it from the terminal using one of the commands mentioned in the "Installation of HandBrake on Ubuntu" section of this guide. If the problem persists, try reinstalling HandBrake using one of the methods outlined in that section.</p>
  <h3>HandBrake is crashing during conversion</h3>
  <p>If HandBrake is crashing during a video conversion, try adjusting the settings for the conversion to see if that resolves the issue. You may also want to try converting a different video file to see if the issue is specific to the file you are trying to convert. If the issue persists, try reinstalling HandBrake using one of the methods outlined in the "Installation of HandBrake on Ubuntu" section of this guide.</p>
  <h2>Conclusion</h2>
  <p>HandBrake is a valuable tool for video conversion and compression on Ubuntu. In this guide, we have shown you how to install and use HandBrake on Ubuntu, as well as how to customize and troubleshoot the program. HandBrake makes it easy to convert your video files to various formats and codecs, making it a necessary tool for Ubuntu users who work with video content.</p>
</article>