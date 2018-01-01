---
title: python virtualenv on Windows
category: Memo
tags: [python]
---

<!--more-->
```bash
# 安裝 virtualenv
pip install virtualenv

# 產生新的環境
virtualenv ENV

# within cmd
.\ENV\Scripts\activate.bat

# within powershell 
Set-ExecutionPolicy RemoteSigned
.\ENV\Scripts\activate.ps1

```
參考連結:

 [ virtualenv ]( https://virtualenv.pypa.io/en/stable/), 
