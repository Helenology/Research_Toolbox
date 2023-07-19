# **TIPS**

[TOC]

## 前言

Tips for LaTeX

## 1 Latex

### 1.1 Latex基本使用文档

- [一份短小有用的Latex文档](https://liam.page/2014/09/08/latex-introduction/)
- [该作者主页](https://liam.page/)，有很多其他有用资料

### 1.2 Latex与VScode

- 查看PDF： 'option+cmd+v'
- 正向触发：edit' > 'SyncTeX from cursor' in the side bar, or by the shortcut cmd+option+j
- 反向触发："cmd+click"
- 开启check模式："latex-workshop.chktex.enabled": true
- 识别与编译中文：
  
```latex
% 如果不成功，在文件的首行加上:"%!TEX program = xelatex"
\documentclass[UTF8]{ctexart} % 以该句开头
```

- 编译配置 ：
在VScode中点击 `View --> Command Palette` ，搜索 `settings.json` ，选择 `Open User settins (JSON)`，做如下配置，详见[在 VSCode 的 LaTeXworkshop 插件中使用 LaTeXmk](https://liam.page/2020/04/24/using-LaTeXmk-with-LaTeXworkshop-with-VSCode/)。

```json
  "latex-workshop.latex.tools": [
    {
      "name": "XeLaTeXmk",
      "command": "latexmk",
      "args": [
        "-xelatex",
        "-synctex=1",
        "-shell-escape",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "pdfLaTeXmk",
      "command": "latexmk",
      "args": [
        "-pdflatex",
        "-synctex=1",
        "-shell-escape",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "LuaLaTeXmk",
      "command": "latexmk",
      "args": [
        "-lualatex",
        "-synctex=1",
        "-shell-escape",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "LaTeXmk-DVIPDFMx",
      "command": "latexmk",
      "args": [
        "-e",
        "$dvipdf='dvipdfmx %O -o %D %S'",
        "-latex",
        "-pdfdvi",
        "-synctex=1",
        "-shell-escape",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "upLaTeXmk-DVIPDFMx",
      "command": "latexmk",
      "args": [
        "-e",
        "$dvipdf='dvipdfmx %O -o %D %S'",
        "-latex=uplatex",
        "-pdfdvi",
        "-synctex=1",
        "-shell-escape",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    }
  ],
  "latex-workshop.latex.recipes": [
    {
      "name": "XeLaTeXmk",
      "tools": [
        "XeLaTeXmk",
      ]
    },
    {
      "name": "pdfLaTeXmk",
      "tools": [
        "pdfLaTeXmk",
      ]
    },
    {
      "name": "LuaLaTeXmk",
      "tools": [
        "LuaLaTeXmk",
      ]
    },
    {
      "name": "LaTeXmk-DVIPDFMx",
      "tools": [
        "LaTeXmk-DVIPDFMx",
      ]
    },
    {
      "name": "upLaTeXmk-DVIPDFMx",
      "tools": [
        "upLaTeXmk-DVIPDFMx",
      ]
    }
  ]
```

### 1.3 Latex与Github

- 安装 git latexdiff
[git 网址](https://gitlab.com/git-latexdiff/git-latexdiff)
[操作指南](https://stackoverflow.com/questions/6188780/git-latex-workflow)

```sh
# 具体命令
git latexdiff HEAD -- # 当前未push的local版本与上一次commit之间的版本差异
git latexdiff HEAD^ # 最新一次commit与上一次commit之间的版本差异
git latexdiff HEAD~1
```

- 注意事项
  - 因为latexdiff本身用颜色来区分不同版本，因此原文件不能使用`\usepackage{ulem}`，也不要带颜色，否则容易产生冲突。


### 1.4 一些快捷LaTex参考

- latex表格生成器：https://www.tablesgenerator.com/
  > 复制数据到网站上，调整格式（边框、三线表），自动生成LaTex表格

