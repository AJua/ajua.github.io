---
title: mac 環境設定
tags: [mac]
---

## 套件管理程式

[安裝 homebrew](https://brew.sh/)

[安裝 homebrew cask](https://caskroom.github.io/)

## neovim with python on mac

```sh
brew install python
brew install python3
pip2 install neovim --upgrade
pip3 install neovim --upgrade
```

mac 上面系統會預先安裝 python 於 `/usr/bin/python`
在執行 `brew install python` 完之後，shell 上面的 python 依然指向 



add this to ~/.config/nvim/init.vim

```vimrc
let g:python2_host_prog = '/usr/local/bin/python'
let g:python3_host_prog = '/usr/local/bin/python3'
```

## 參考資料

[Neovim with Python on OSX](https://ricostacruz.com/til/neovim-with-python-on-osx)
