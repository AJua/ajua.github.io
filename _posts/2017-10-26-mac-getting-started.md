---
title: mac 環境設定
tags: [macOS]
---
最近買了 mabook pro 13吋來當作是開發機, 
而我最喜歡用的程式碼編輯器是 vim, 
不過因為 vim 的同步執行在某些情境下並不是很方便, 
所以這次改用 neovim 來開發

<!--more-->


1. 安裝套件管理程式 [homebrew](https://brew.sh/) 跟 [homebrew cask](https://caskroom.github.io/)
``` bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew tap caskroom/cask
```

2. 安裝 neovim
``` bash
brew install neovim
brew install python
brew install python3
pip2 install neovim --upgrade
pip3 install neovim --upgrade
```

mac 上面系統會預先安裝 python 於 `/usr/bin/python`
在執行 `brew install python` 完之後, shell 上面的 python 依然指向 


add this to ~/.config/nvim/init.vim

```vimrc
let g:python2_host_prog = '/usr/local/bin/python'
let g:python3_host_prog = '/usr/local/bin/python3'
```

## 參考資料

[Neovim with Python on OSX](https://ricostacruz.com/til/neovim-with-python-on-osx)
