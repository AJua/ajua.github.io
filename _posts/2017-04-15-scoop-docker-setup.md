---
title: Setup docker with scoop on windows
tags: [docker]
---

```sh
# install docker and docker machine by scoop
scoop install docker docker-machine

docker-machine create default
docker-machine env default | Invoke-Expression

# 測試安裝是否正確
docker run hello-world
```
