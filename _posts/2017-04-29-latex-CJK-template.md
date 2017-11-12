---
title: Latex CJK 樣板
tags: [Latex]
---

<!--more-->
使用 windows powershell
```sh
# Install scoop if it is not installed. Use scoop just like apt-get.
iex (new-object net.webclient).downloadstring('https://get.scoop.sh')

# install Latex
scoop install latex

# Recommand SumatraPDF as the default pdf viewer
scoop install SumatraPDF

# edit sample.tex with your favorite text editor 
vim sample.tex
```
``` tex
% contents of sample.tex
\documentclass{beamer}

\usepackage{listings}
\usepackage{CJKutf8}
 
\title{Sample title}
\author{Anonymous}
\institute{Sample Institute}
\date{2017}
 
\begin{document}
\begin{CJK}{UTF8}{min}
 
\frame{\titlepage}
 
\begin{frame}
\frametitle{Sample frame title}

蘇軾：和子由澠池懷舊
\begin{block}{}
人生到處知何似，恰似飛鴻踏雪泥；

泥上偶然留指爪，鴻飛那復計東西。

老僧已死成新塔，壞壁無由見舊題；

往日崎嶇還記否，路長人困蹇驢嘶。
\end{block}

\end{frame}

\end{CJK}
\end{document}
```
``` sh
# continuously compile sample.tex
latexmk -pvc -pdf -interaction=nonstopmode sample.tex
```

參考連結:

[ Scoop, A command-line installer for Windows ]( http://scoop.sh/ ),
[ cjk-support-in-latex ]( http://latex-my.blogspot.tw/2010/06/cjk-support-in-latex.html ),
[ make-latexmk-ignore-errors-and-finish-compiling ]( https://tex.stackexchange.com/questions/120019/make-latexmk-ignore-errors-and-finish-compiling )
