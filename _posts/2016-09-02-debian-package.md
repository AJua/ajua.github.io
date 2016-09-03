---
title: Debian 套件安裝
---
### Docker resolve host not found

<!--more-->
```sh
$ vim /etc/resolv.conf
```

Add name dns server to the top

```sh
nameserver 8.8.8.8
```

### Steam dependencies

```sh
$ apt-get install '^libc6.*' 
$ vim /etc/apt/sources.list
$ dpkg --add-architecture i386
$ apt-get update
$ apt-get install libgl1-nvidia-glx:i386
$ apt-get install libgl1-nvidia-glx:i386

```
