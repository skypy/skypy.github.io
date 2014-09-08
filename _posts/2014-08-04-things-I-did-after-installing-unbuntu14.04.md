---
layout: post
title: Things I did after installing Ubuntu 14.04
published: true
description: things to do after Ubuntu40.04 installation
categories: ubuntu14
tags:
- ubuntu14
- linux
---

I have been using Lenevo T410i series laptop for a long time, more than 4 years. It has a strong build quality and good performance.
But recently there were some problem with motherboard which was out of warrenty. So it was a time for upgrade.

<span style="font-size:14px">Thinkpad T410i</span><br />
<img src="{{ site.baseurl }}/images/lenevo_t410jpg.jpg" alt="thinkpad-t410i" style="width: 250px; height: 350px "/><br />
<!--more-->

Got a [Dell Inspiron 15](http://www.flipkart.com/dell-inspiron-15-laptop-4th-gen-ci7-8gb-1tb-win8-2gb-graph/p/itmdpzjm3hyzfbfg?pid=COMDPZJC9STYFRP9) series laptop and installed Ubuntu 14.04 (64 bit). In my old system I used Ubuntu 13. Since I was doing a new
installation so I thought to go for the latest Ubuntu version. And 14.04 is LTS (Long Term Support) so it was safe to get this version.
This new system has 1 TB hard disk and 8 gb of system memory. I allocated ~ 16 gb for swap memory (double of system memory size) and rest goes into one primary
partition having ext3 file system.


Here is the memory map

<img src="{{ site.baseurl }}/images/gp.png" alt="partition" style="width: 460px; height: 350px "/><br />

###### Revert to classic theme
First thing which came to mind is to revert unity theme. I think it was ubuntu version 11 when unity was added. I still do not feel
comfortable with it, rather I prefer classic old theme.


`sudo apt-get update`

`sudo apt-get install gnome-session-fallback`

Now log out and relogin but make sure you select gnome theme.
*image*

###### Fix Alt + tab behavior
Next thing was - Alt + tab was not working which was supposed to switch between windows. I don't know the reason for the behavior.
But later when I installed Ubuntu same version (14.04) in some other system, I didn't see that problem.

However to fix the problem I used ComfizConfig manager

`sudo apt-get install compizconfig-settings-manager`

Now got to System Tools -> Preferences -> CompizconfigSettings Manager -> Window Management
and check the option <strong>Static Application Switcher</strong>.
It will make alt + tab back to it's normal behavior. Compizconfig should be used very carefully!!

<img src="{{ site.baseurl }}/images/compiz.jpg" alt="compiz" style="width: 450px; height: 350px "/><br />

###### Map control to super key
Next, Super (win) key is not useful in Ubuntu. So I decided to map it to control key.
Add the required repository

`sudo add-apt-repository ppa:tualatrix/ppa`

Update

`sudo apt-get update`

Finally, install

`sudo apt-get install ubuntu-tweak`

Now go to System Tools -> Preferences -> Tweak Tool -> Typing.

In typing section there is an option "alt/win behavior". Select "Control is mapped to Win Keys" option.

<img src="{{ site.baseurl }}/images/tweak.jpg" alt="tweak" style="width: 450px; height: 350px "/><br />

###### Download Emacs

`sudo apt-get install emacs`

This command installed emacs version 24 which was latest. I use some emacs color scheme whcih do not go well with version 24
so I have to downgrade emacs version. So to this first I removed comeplete emacs 24 package using the folowing steps

`sudo apt-get purge emacs`

`sudo apt-get purge emacs emacs24`

`sudo apt-get autoremove`

now run this command to make emacs didn't exist anymore
`locate emacs`

When uninstallation process was fine, I again downloaded emacs and specified the version 23

`sudo apt-get install emacs23`

###### Fix Brightness control
On Dell Inspiron, it is fn + f5/f6 to control brightness. Strangely the control was not working.
[This](http://itsfoss.com/fix-brightness-ubuntu-1310/) blog has a simple instruction to fix it. I figured out video card model by the following command

`lspci | grep VGA`

Generally you could find either Intel or Nvidia. It was Intel for my system. So I followed instructions for Intel fix described in the blog. It worked! I could the see the control bar.

<img src="{{ site.baseurl }}/images/brihhtness.png" alt="ubuntu-brightness" style="width: 450px; height: 250px "/><br />


That is all! Time to get started with Ubuntu 14.04!