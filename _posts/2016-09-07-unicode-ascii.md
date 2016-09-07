---
title: Debian 套件 uni2ascii
tags: [Debian]
---

在網路上使用 api 的時候，中文會以 unicode 的方式編碼，
uni2ascii 可以將 unicode 轉換成使用者可以閱讀的形式,
解決的方式有不少個，這裡紀錄兩個。

### 使用 uni2ascii

```bash
sudo apt-get install uni2ascii
echo 'Character 1: \u0144, Character 2: \u00f3' | ascii2uni -a U -q
```

### 使用 native2ascii

```bash
native2ascii -encoding UTF-8 -reverse src.txt dest.txt
```

<!--more-->

參考 [How to convert \uXXXX unicode to UTF-8 using console tools in *nix](http://stackoverflow.com/questions/8795702/how-to-convert-uxxxx-unicode-to-utf-8-using-console-tools-in-nix)
