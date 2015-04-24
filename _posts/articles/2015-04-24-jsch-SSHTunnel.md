---
layout: post
title: SSH Tunnel via JSCH Library
excerpt: "Establish a ssh tunnel to retrieve the resources behind the firewall."
modified: 2015-04-24
categories: articles
tags: [ssh, jsch]
<!-- image:
  feature: so-simple-sample-image-1.jpg
  credit: WeGraphics
  creditlink: http://wegraphics.net/downloads/free-ultimate-blurred-background-pack/ -->
comments: true
<!-- share: true -->
---

To retrieve resources behind the firewall, one solution is to connect to a public server first as a middle man, and then via the server to reach the resources. The solution is to establish a ssh tunnel.

One can use a command line like `ssh -L xxx` (google to see details).
However we use a jsch library to (build a [java program](https://github.com/topskychen/SSH_Tunnel) and then) create a simple bash file. 

I have prepared a ssh.jar. To use it, type `java -jar ssh.jar local_port:ssh_server remote_server:remote_port`.

By the way, we can use `lsof -i tcp:'port_no'` to see the the port information, e.g., `lsof -i tcp:9001`.



