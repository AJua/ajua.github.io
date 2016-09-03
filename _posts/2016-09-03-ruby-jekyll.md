---
title: Ruby jekyll serve error
category: Dev
tags: [ruby]
---
### jekyll 3.2.1 | Error:  Address already in use - bind(2) for 127.0.0.1:4000

<!--more-->

這是要使用 <code>jekyll serve</code> 遇到的問題,
原因是同一個 port 已經被使用了,
但是當前的 terminal 並沒有看到執行中的程序，
沒辦法用 Ctrl-C 的方式關閉,
但是 _config.yml 必須重啟才能夠生效,
所以需要以指令的方式關閉,
首先找出執行中的程序id,
然後用 <code>sudo kill</code> 中止。

```sh
$ lsof -wni tcp:4000

COMMAND  PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
ruby2.3 9238 ajua    8u  IPv4 112402      0t0  TCP 127.0.0.1:4000 (LISTEN)

$ sudo kill -9238 PID
```

參考 [tcpserver-error-address-already-in-use-bind2](http://stackoverflow.com/questions/10261477/tcpserver-error-address-already-in-use-bind2)
