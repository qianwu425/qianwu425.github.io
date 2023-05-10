---
title: "A Guide to Installing and Using Node.js on Ubuntu 20.04"
description: "If you're interested in using an open-source JavaScript runtime environment on Ubuntu, Node.js is a great choice. It is a versatile environment that can handle both front-end and back-end development, making it ideal for creating data-intensive applications and building servers. Node.js is capable of dynamically generating web page content, modifying database data, and manipulating files on servers."
date: 2020-02-05
layout: post
---

<article>
  <img alt="silhouette of man holding flashlight" src="https://images.unsplash.com/photo-1553708881-112abc53fe54?crop=entropy&amp;cs=tinysrgb&amp;fit=max&amp;fm=jpg&amp;ixid=Mnw0NDU0ODV8MHwxfHNlYXJjaHwxfHxBJTIwR3VpZGUlMjB0byUyMEluc3RhbGxpbmclMjBhbmQlMjBVc2luZyUyME5vZGUuanMlMjBvbiUyMFVidW50dSUyMDIwLjA0fGVufDB8MHx8fDE2ODM2NjA5NzQ&amp;ixlib=rb-4.0.3&amp;q=80&amp;w=1080"/>
  <p>If you're interested in using an open-source JavaScript runtime environment on Ubuntu, Node.js is a great choice. It is a versatile environment that can handle both front-end and back-end development, making it ideal for creating data-intensive applications and building servers. Node.js is capable of dynamically generating web page content, modifying database data, and manipulating files on servers.</p>
  <h2>Prerequisites</h2>
  <p>Before installing Node.js on Ubuntu 20.04, ensure that you have the following:</p>
  <ul>
    <li>An Ubuntu 20.04 server</li>
    <li>A non-root user with sudo privileges</li>
  </ul>
  <h2>Installing Node.js on Ubuntu 20.04</h2>
  <p>Follow these simple steps to install Node.js on Ubuntu 20.04:</p>
  <ol>
    <li>Update and upgrade the repository by running the command: <code>sudo apt update &amp;&amp; sudo apt upgrade</code></li>
    <li>Install Node.js by running the command: <code>sudo apt install nodejs</code></li>
    <li>Verify the installation by running: <code>node --version</code></li>
  </ol>
  <h2>Using Node.js on Ubuntu</h2>
  <p>After installing Node.js on Ubuntu, you can create and execute JavaScript (.js) files. Here's how to create a Node.js server file called "examplefile.js":</p>
  <ol>
    <li>Use a text editor like nano to create a .js file: <code>nano examplefile.js</code></li>
    <li>Inside the file, write the JavaScript code:</li>
  </ol>
  <pre>    <code>
const http = require('http');
const host = '&lt;localhost/IP&gt;';
const port = 5000;
const server = http.createServer((req, res) =&gt; {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello world!');
});
server.listen(port, host, () =&gt; {
  console.log('The web server is running at http://%s:%s', host, port);
});
    </code>
  </pre>
  <ol start="3">
    <li>Save the file using <code>Ctrl+X</code>, type <code>Y</code> and press <code>Enter</code>.</li>
    <li>Run the .js file using the command: <code>node examplefile.js</code></li>
    <li>To display the message, go to your browser and type the following URL: <code>http://&lt;IP-address&gt;:5000</code></li>
    <li>Note: You can find the Ubuntu IP address by running the command <code>hostname -I</code></li>
  </ol>
  <h2>Removing Node.js from Ubuntu</h2>
  <p>To remove Node.js from Ubuntu, run the following command:</p>
  <code>sudo apt remove nodejs</code>
  <h2>Conclusion</h2>
  <p>If you want to install Node.js on Ubuntu, update the system and install it from the official Ubuntu repository using the <code>apt install</code> command. Once installed, you can use it to create multiple JavaScript applications and run them on the browser via port 5000. To run aNode.js file, simply type the <code>node</code> command followed by the file name.</p>
  <h2>Additional Resources</h2>
  <p>Here are some additional resources that can help you get started with Node.js:</p>
  <ul>
    <li><a href="https://nodejs.org/en/docs/">Official Node.js documentation</a></li>
    <li><a href="https://www.w3schools.com/nodejs/">W3Schools Node.js tutorials</a></li>
    <li><a href="https://www.npmjs.com/">NPM package registry</a></li>
    <li><a href="https://github.com/">GitHub repository hosting</a></li>
  </ul>
</article>