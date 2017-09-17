---
title: Latex xeCJK 樣板
tags: [Latex]
---

接續 [ Latex CJK 樣板 ]( /latex-CJK-template )， 在連結中所使用的中文是 `CJKutf8` 套件辦到，
而這裡所使用的是 `xeCJK` 搭配 `xelatex` 以及 `fontspec` 完成， 詳細作法如下。
``` tex
% contents of sample.tex
\documentclass{beamer}

\usepackage{xeCJK}
\usepackage{fontspec}

\setCJKmainfont{SimSun}

\title{Sample title}
\author{Anonymous}
\institute{Sample Institute}
\date{2017}
 
\begin{document}
 
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

\end{document}
```
``` sh
# continuously compile sample.tex
latexmk -xelatex -pvc -interaction=nonstopmode  -shell-escape sample.tex
```

參考連結:

 [ xeCJK中文環境 ]( https://www.ptt.cc/bbs/LaTeX/M.1366782607.A.202.html ), 
 [ 使用XeLaTeX處理中文 ]( https://www.ptt.cc/bbs/LaTeX/M.1261370608.A.7CC.html )
