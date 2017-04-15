---
title: Setup docker with scoop on windows
tags: [docker]
---

檔案的權限設定錯誤會導致 ssh 認證失敗

```sh
# install docker and docker machine by scoop
scoop install docker docker-machine

docker-machine create default
docker-machine env default | Invoke-Expression

# 測試安裝是否正確
docker run hello-world
```

[ trying-to-do-ssh-authentication-with-key-files-server-refused-our-key ]( http://askubuntu.com/questions/306798/trying-to-do-ssh-authentication-with-key-files-server-refused-our-key )
