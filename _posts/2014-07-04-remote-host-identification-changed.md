---
layout: post
title: remote host identification changed
description: remote host identification changed
categories: ssh, ubuntu
published: true
---

I reinstalled OS to one of my old machine. So I had to setup other softwares on the
system which includes open-ssh. The problem started when I tried to login to the system
via ssh from a different system.

Here is the message generated in the terminal from the system I was trying to log in.

<img src="{{ site.baseurl }}/images/key-verification-failed.png" alt="host-key-verification" style="width: 660px; height: 450px "/><br />

To resolve this run the following command from the terminal.

`ssh-keygen -R <hostname or ip of the system you want to connect to>`