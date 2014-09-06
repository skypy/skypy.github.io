---
layout: post
title: Tata Photon wifi data card for SSH connection
published: true
---

I brought a Tata photon wifi data card which is a upgraded version of Tata photn plus. It claims better connectivity than its predecessor. But I dont see a big difference.
The worst part is that it doesn't have a port forwarding option. And without port forwarding no one can ssh to my system!

<img src="{{ site.baseurl }}/images/photon.jpg" alt="partition" style="width: 460px; height: 350px "/><br />

There was no positive response from Photon customer service. So I decided to find a workaround - use reverse tunnel and allow ssh.


<!--more-->

Here are the steps which will setup reverse tunnel -

Run this on your system -

`ssh -R 9022:localhost:22 your-user-nam@other-machine-ip`

Ask other user who wants to connect to your system to run this -

`ssh -p 9022 localhost`

It is done!

[Here](http://unix.stackexchange.com/questions/46235/how-does-reverse-ssh-tunneling-work) is a nice explanation which I followed.


