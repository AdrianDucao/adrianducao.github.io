---
layout: post
title:  "Fedora: The myth of stable distribution"
date:   2021-07-03 00:00:00 +0800
categories: blog
---

# Stability Fedora Distro
Fedora OS is one of many distribution of linux kernel by far this is the most stable OS i've used, in Ubuntu this typically breaks after 3-4 months of usage and updates, Pop_OS actually lasted 6-7 months before breaking, but Fedora lasted me almost 2 years before breaking on me, the reason why fedora is stable is due to the huge support of developers who maintain the kernel and is backed by redhat which you'll get a steady updates is providing bleeding edge technology and since Fedora has one of the largest community most if not all issues has been addressed, reported, or experienced everysingle kind of breaks to be able to provide solutions, and since Fedora is following the spirit of software freedom and open source philosophy which makes them actively refuse to include proprietary programs and would rather prefer open sourced software instead.

# Issue and Troubleshooting
The issue that i encounter the most when in comes with linux distro is the kernel update there are times that things might truly break reason may vary, there's alot of variable to consider such as hardware compatibility, broken dependency repositories, and other unknown sh*ts.

After the update from Fedora 33 to Fedora 34 everything seems fine or issue, 2 months after the system upgrade i noticed a sluggish load time of my computer, my bootdrive is encrypted so whenever computer boots up you need to enter the passphrase, typical it will only take less than 5 seconds to load and you'll be directed to login asking for password... but this time the load time after passphrase input took 1-3 minutes... a noticable difference... i worried that my M.2 SSD is dying but that's not the issue since after a day or two boot stucked at
```
....
[OK] starting GNOME display manager

``` 
then i know somethings up, pressed 
```
Ctrl+Alt+F2
``` 
in order for me to access tty2 so i can at least access a terminal and voala! at last i was able to login on a terminal to check things up... tried to 
```
$ sudo dnf update
``` 
if something broke last update then this might resolve said issue and remove the potential broken dependencies and fix the bootup issue... but there's an Error on downloading packages it seemed that i'm not connected to the internet even though my Ethernet is plugged in on my machine... 

tried to 
```
$ ping google.com
ping: google.com: Name or service not known
```

At first i tought that the motherboard might have some issue but then i remembered that i have my network manager set to automatically connect to my VPN when connecting to the internet not sure why my system can't connect to my VPN server i tried to
```
$ nm-connection-editor
```
but it won't pull up since there's no GUI, took me a while to do research and realized that i can use nmcli...
Checking ethernet adapters with
```
$ nmcli con
```
i was able to confirm that ethernet is not connected and had to
```
$ nmcli con add ethernet
```
to test if i was able to connect to the internet
```
$ ping google.com
PING google.com (142.250.66.142) 56(84) bytes of data.
_
--- google.com ping statistics ---
5 packets transmitted, 0 received, 100% packet loss, time 4134ms
```
it seemed connected but with a 100% packet loss is useless... but tried to test it anyway by running an update
```
$ sudo dnf update
```
the update went through and rebooted my machine... but still getting the same issue on boot and the load time is much worse since it's taking at least 4-5 minutes...

Tried to check the update history to see if i can revert back some of the updates done
```
$ sudo dnf history --reverse

...showed the update and installation history...

$ sudo dnf history undo <id>
```
but after several tries and restarts things not getting better, still the same issue...

The only thing that i could think off is to revert or downgrade the current version of my distro to Fedora 33
```
$ sudo dnf system-upgrade download  --releasever=33 --allowerasing --skip-broken
```
finalising the downgrade
```
$ sudo dnf system-upgrade reboot
```
i encountered another issue stating that there's a ```missing shared file Libip4tc.so.2```
after much research and digging about this error found couple unanswered and unresolved queries in StackOverflow and some fedora forums i fanally decided to give up.

# Solution
Logged in to my cherrypi-server and created a bootable Fedora 34 flash drive out of the iso file downloaded from their website and installed a fresh Fedora 34 on my M.2 SSD boot drive... all files important data are archived to seperate 2TB HDD, 1 TB HDD, and Projects files are safe and sound on my 250GB SSD.

# Theory
after much discussion in a fedora forum they asked if i could boot to the other kernel saved up since whenver there's an kernel update the older kernel are set aside and saved as a backup use incase the latest kernel had an issue, in total there are 3 different kernel versions on your bootdrive ready to be used but i did try to use 3 of those kernel version and still got the same issue at the end, Kernel Version are 5.13.xx, 5.12.xx, and 5.11.xx, i could have troubled to use download older kernel versions compile it and install but it would be much safer to install a fresh copy for security reasons, we concluded that there might be an update that broke the kernel version since Fedora 34 was just release back on April 2021, it is farely new and this point

# Conclusion
If ain't broke don't fix it, if it breaks and can't be fixed replace it.

Happy Coding.
