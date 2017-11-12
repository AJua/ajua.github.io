---
title: Running shotwell on Bash on Ubuntu on Windows
tags: [Linux, Windows]
---
自從被某網友推坑使用 Debian 之後,
我就很喜歡使用 shotwell 來管理我拍的相片,
我最喜歡的一點是 shotwell 會自動根據 EXIF 的拍攝日期來顯示照片,
而不是跟實際的資料夾結構綁定,
這讓照片的管理變得十分容易,
唯一的缺點是只能在 Gnome 的桌面環境下使用,
為了在 Windows 上面執行 shotell,
一個方式是用 virtual box,
但是實際跑起來不是很方便,
而這裡要介紹的是另一個方式, 
原理也有點複雜, 不過有一個好處是可以寫成 script,
也就是可以自動化在新的電腦安裝,
以下是安裝步驟: 
<!--more-->

1. 首先在 Windows 安裝 Xming, 個人推薦使用 scoop 來安裝, 如果還沒有 scoop
   的話, 可以按照這兩行指令安裝
``` powershell
Set-ExecutionPolicy RemoteSigned -scope CurrentUser
iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
```
更多關於 scoop 可以看 [Scoop A command-line installer for Windows](http://scoop.sh/)

2. 有了 scoop 之後, 安裝套件都非常容易
``` powershell
scoop install Xming
```

3. 開始執行 Xming 
``` powershell
xlaunch.exe
```

4. 接下來打開 Bash on Ubuntu on Windows, 將圖形介面輸出至Xming,
   第三段是為了[ 讓 D-Bus 使用 tcp 取代 socket ](https://www.reddit.com/r/Windows10/comments/4rsmzp/bash_on_windows_getting_dbus_and_x_server_working/)
``` bash
export DISPLAY=:0.0 
echo "export DISPLAY=:0.0" >> ~/.bashrc
sed -i 's/<listen>.*<\/listen>/<listen>tcp:host=localhost,port=0<\/listen>/' /etc/dbus-1/session.conf
```

5. 開始安裝 shotwell 跟中文字型
``` bash
apt-get update && apt-get upgrade -y
apt-get install -y shotwell fonts-arphic-uming
```

6. 開始執行 shotwell
``` bash
shotwell
ln -s /mnt/d/Syncthing/Pictures/shotwell ~/.local/share/shotwell
```

參考資料

[How to run the native Ubuntu desktop on Windows 10](http://www.zdnet.com/article/how-to-run-run-the-native-ubuntu-desktop-on-windows-10/)
