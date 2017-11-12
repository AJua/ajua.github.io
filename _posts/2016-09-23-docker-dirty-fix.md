---
title: docker dns lookup fail
tags: [Debian]
---

<!--more-->
應該是應該dns設定上的錯誤導致執行 <code>docker run</code> 的時候，docker
沒辦法正確找到伺服器的位置，下面的解法是先手動找出伺服器的位置，然後寫到自己的 host，
下次執行 <code>docker run</code> 會跳過dns直接連到伺服器。

```sh
$ dig docker.io +noall +answer +nocomments

; <<>> DiG 9.10.3-P4-Debian <<>> docker.io +noall +answer +nocomments
;; global options: +cmd
docker.io.Docker  0        INA     52.207.178.113

echo '52.207.178.113 index.docker.io' >> /etc/hosts
```

參考 [Docker - dial tcp: lookup index.docker.io: no such host - Solution](https://linuxconfig.org/docker-dial-tcp-lookup-index-docker-io-no-such-host-fix)
