---
title: Debian Live CD/DVD
category: Dev
tags: [Debian]
---

今天在設定 /etc/fstab 完之後重新開機時發現中間有一段程式碼會導致系統出現錯誤，
系統此時進入緊急模式，嘗試以 root 進入終端模式，
但是因為當初安裝的時候並沒有開啟 root，
而是讓系統自動賦予第一個使用者 sudo 的權限，
雖然知道將有問題的那一行程式碼刪除就可以恢復正常，
但是無法開啟終端模式的情況下根本沒辦法修改檔案，
在 grub 指令下也沒辦法修改檔案，
後來的解決的方式是以 Debian Live CD/DVD 開機，
剛好又沒有對硬碟做加密，
所以可以進入系統將有問題的那一段程式碼，
系統就回到原本的狀態，彷彿什麼事情都沒有發生過一樣。

### 總結

1. 把 root 帳戶關閉可能不是好主意
2. 隨時準備個 Live CD/DVD 可以在系統崩潰時有個搶救模式
3. 對硬碟加密時應特別小心，要有預設出問題時的應變方式

參考 [how-to-edit-file-from-grub-prompt-in-rhel6](http://unix.stackexchange.com/questions/78433/how-to-edit-file-from-grub-prompt-in-rhel6),
[Debian Live CD/DVD](https://www.debian.org/CD/live/)
