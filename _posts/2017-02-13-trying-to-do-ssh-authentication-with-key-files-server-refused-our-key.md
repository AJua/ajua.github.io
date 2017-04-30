---
title: ssh 權限設定
tags: [Debian]
---

檔案的權限設定錯誤會導致 ssh 認證失敗

```sh
# enter the public key in ~/.ssh/authorized_keys in one line (needs to start with ssh-rsa)
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
chown $USER:$USER ~/.ssh -R

# change /etc/ssh/sshd_config so it contains AuthorizedKeysFile %h/.ssh/authorized_keys
sudo service ssh restart

# for debug
tail -f /var/log/auth.log.
```
參考連結:

[ trying-to-do-ssh-authentication-with-key-files-server-refused-our-key ]( http://askubuntu.com/questions/306798/trying-to-do-ssh-authentication-with-key-files-server-refused-our-key )
