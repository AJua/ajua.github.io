---
title: Reset Photos for macOS
tags: [macOS]
---
在使用 Photos for macOS 的時候, 很容易將資料弄得很亂, 
所以如果想要將 Photos for macOS 回復到一開始的狀態的話, 
可以手動將設定檔與圖庫刪除, 之後重新開啟即可
<!--more-->

``` bash
rm -rf ~/Library/Preferences/com.apple.Photos.plist
rm -rf ~/Pictures/照片圖庫.photoslibrary
```

來源: [How Can I Totally Reset iPhoto?](https://discussions.apple.com/thread/1491679?tstart=0)

