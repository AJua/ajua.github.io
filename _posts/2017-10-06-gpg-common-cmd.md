---
title: GPG 常用指令
tags: [GPG]
---

```bash
# 生成新的公私鑰
gpg --gen-key

# clearsigned 文件
gpg --clearsign doc

# 匯入 Public Key
gpg --import key.asc 

# Turn a directory into a file 
tar czf docs.tar.gz docs/

# 加密
gpg --encrypt --recipient xxx@mail.com ~/xxx/xxx.txt
```
參考連結:

 [ The GNU Privacy Handbook ]( https://www.gnupg.org/gph/en/manual/c14.html ), 
