---
title: Create self-signed certificate
tags: [Debian]
---

<!--more-->
檔案的權限設定錯誤會導致 ssh 認證失敗

```sh
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes
```
參考連結:

[ how-to-create-a-self-signed-certificate-with-openssl ]( http://stackoverflow.com/questions/10175812/how-to-create-a-self-signed-certificate-with-openssl )
