---
layout: post
title: port forwarding
description: port forwading
categories: port-forwarding
published: true
---

I have a d-link router. Here I will show how I configured port forwarding to let other users access my desired system. I have dynamic ip, that is, every time internet connection
is established, there is a new ip which is generated for the connection. I connect multiple notebooks, tablet, phone to the router, I will describe how others connect to
one of my system via ssh.

What is port forwarding ? Let's say you have two systems which are connected to the router. One has internal ip 192.168.0.100 and other one has 192.168.0.101. Now you want
other to connect to the system which has ip 192.168.0.101. So how does other user's request will be forwarded to the right system? this is controlled by port forwarding
configuration which you can set in the router's admin page. Here is the image representation. one system running a webserver on 8080 and other one has ssh which is on port 22

<img src="{{ site.baseurl }}/images/port-forwarding.png" alt="partition" style="width: 600px; height: 450px "/>

How to configure this in d-lnk router? Open the the router admin panel in browser and go to Advanced option, there you could see the potion for port forwaridng.
here you could find what are the values I entered for ssh port forward, that is, forward ssh incoming request (port 22) to the desired internal ip.

<img src="{{ site.baseurl }}/images/d-link.png" alt="partition" style="width: 600px; height: 450px "/><br />
