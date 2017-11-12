---
title: 如何 terminal 下 vim 使用系統的剪貼簿 
tags: [vim]
---

<!--more-->
首先必須先安裝好<code>vim-gtk</code>

```bash
sudo apt-get install vim-gtk
```

### 從 vim 到剪貼簿

用滑鼠將感興趣的範圍圈選起來, 然後再輸入

```bash
"+y
```

### 從剪貼簿到 vim


在系統的剪貼簿已經有內容的情況下輸入

```bash
"+p
```

<!--more-->

參考 [unable-to-copy-from-vim-to-system-clipboard](http://askubuntu.com/questions/347519/unable-to-copy-from-vim-to-system-clipboard)

