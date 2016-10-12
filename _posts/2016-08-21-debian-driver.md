---
title: Debian 硬體驅動程式 
tags: [Debian]
---
### Nvidia 顯示卡驅動程式

Add non-free to Debian repository

```sh
deb http://ftp.au.debian.org/debian/ jessie main contrib non-free
deb-src http://ftp.au.debian.org/debian/ jessie main contrib non-free
```

Update the repository and install

```sh
$ apt-get update
$ apt-get install nvidia-driver
$ apt-get install nvidia-xconfig
$ nvidia-xconfig
```

### fonts too big after installing nvidia driver

I found the following to be a somewhat clean solution to the problem (found this somewhere on the net - all credits to whomever figured it out). It will only work for lightdm users. If you're on Ubuntu and you don't know what lightdm or an X display manager is in general, you are probably using lightdm.

1.) Run this command in a konsole to find out your current DPI setting:

```
$ cat /var/log/Xorg.0.log | grep -i dpi
```

For me, the output with a freshly installed Kubuntu 14.04 x64 with proprietary nvidia drivers contained:

```
[    11.509] (--) NVIDIA(0): DPI set to (143, 144); computed from "UseEdidDpi" X config
```

To no surprise, all fonts appeared ridiculously huge - even deforming windows and making the desktop pretty much unusable. The issue was also present in the login screen.

2.) Edit this file with superuser permissions:

```
/etc/lightdm/lightdm.conf
```

Look for a line starting with "xserver-command" and append a -dpi XXX argument to it. For me, the line now looks like
Code:

```
xserver-command=X -core -dpi 96
```

3.) Reboot. Logging out and in again won't suffice.

4.) Enjoy fonts of appropriate size. Check again with the above cat/grep command:
Code:

[    11.643] (++) NVIDIA(0): DPI set to (96, 96); computed from -dpi X commandline option

So, this EDID based DPI calculation seems to be broken. Not sure if in xorg, in the nvidia driver, in some Ubuntu package or inherently.

Does anybody know more about this? Can anybody provide a link to some bug on the appropriate tracker? 


參考  [NVIDIA GeForce Driver Installation on Debian Jessie Linux 8 64bit](https://linuxconfig.org/nvidia-geforce-driver-installation-on-debian-jessie-linux-8-64bit) 

參考  [fonts too big after installing nvidia driver](https://ubuntuforums.org/showthread.php?t=2201820) 

