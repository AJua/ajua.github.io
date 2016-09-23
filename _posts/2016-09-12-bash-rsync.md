---
title: 使用 rsync 時不複製檔案權限 
category: Dev
tags: [bash]
---

### 使用方式

```bash
rsync -avz --no-perms --no-owner --no-group ...
```

參考 [rsync-ignore-owner-group-time-and-perms](http://unix.stackexchange.com/questions/102211/rsync-ignore-owner-group-time-and-perms)
