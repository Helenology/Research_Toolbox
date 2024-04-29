**<kbd>Research_Toolbox</kbd>** 

- [1. Academic PPT](#1-academic-ppt)
  - [1.1 Latex 数学公式](#11-latex-数学公式)
  - [1.2. 插图](#12-插图)
  - [1.3. 演讲技巧](#13-演讲技巧)
- [2. Academic Writing](#2-academic-writing)
  - [Academic Phrasing Recycling ✨](#academic-phrasing-recycling-)
  - [Abstract](#abstract)
  - [Introduction](#introduction)
  - [Literature](#literature)
    - [查找学术资料](#查找学术资料)
    - [文献管理软件+插件](#文献管理软件插件)
  - [Methodology](#methodology)
    - [Proof Theorem Citation](#proof-theorem-citation)
    - [Formula Requirements](#formula-requirements)
  - [Numerical Study](#numerical-study)
    - [Coding](#coding)
  - [Table and Figure](#table-and-figure)
    - [Table](#table)
    - [Sub-Figures](#sub-figures)
  - [Reference](#reference)
  - [LaTex Tips](#latex-tips)
- [3. Toward Acceptance](#3-toward-acceptance)
  - [3.1. Reply Letter](#31-reply-letter)
  - [3.2. 如何与editor沟通](#32-如何与editor沟通)
  - [3.x. 求神拜佛](#3x-求神拜佛)





# 1. Academic PPT

## 1.1 Latex 数学公式

- 非常推荐一个PPT的插件 [iguanatex](https://www.jonathanleroux.org/software/iguanatex/)，输入latex后生成就会以矢量图的方式插入latex代码（例如数学公式）


![Alt text](/pics/image.png)

## 1.2. 插图

- [阿里巴巴矢量图标库](https://www.iconfont.cn/)：矢量图
- `iSlide`：在mac上可以搜到的APP，矢量图，每天下载有最大数量限制
- [视觉中国网](https://www.vcg.com/creative-illustration/feibuxueguan/)：开始是免费试用，后来就要钱，图片质量很不错，氪金玩家可以考虑

## 1.3. 演讲技巧

- 重要性：开头>结尾>中间，开头需要在一上来就吸引大家的目光
- 如何短时间提高听众的兴趣：提一个问题；提到参加者的名字；讲一个笑话或者八卦（这个很难）
- 提高演讲的趣味性和故事性：
  - 整个结构按着一个自然的思考顺序串联整个演讲，从中不断发现问题*提出问题*，并尝试解决问题，解决得不好再分析为啥，再解决问题
  - 按照读者的思考逻辑顺序，*提出他们心里的疑问*
- 问什么答什么：
  - 最常见的问题是“是不是xxx”，只用回答“是”或“否”，不要过多纠缠，不要恋战
  - **尊重提问者**，他们第一次读你的PPT，很多地方没看清是很正常的，所以哪怕他们问了一个简单的问题，也可以自谦说自己讲漏了，是一个很好的问题
  - 请勿为自己辩解，坦诚地承认不足，反而可以用真诚打动别人，而不是一味强行解释，这样观感很不好，甚至会激怒提问者。如果提问者非常刁难，你又无法很好地回答对方的问题，就顺着对方的意思说，多夸夸对方是专家，说说自己还不足，一定不要反驳，否则后果可能很严重


# 2. Academic Writing

##  Academic Phrasing Recycling ✨

- 按照文章的结构，将**可重复利用的学术论文遣词造句**更新在
[Academic_Phrasing.md](./Academic_Phrasing.md) ✨
   -  [x] 最新更新 240428

- 同义词替换（from `good` to `terrific`)：[freethesaurus](https://www.freethesaurus.com/) 和 [thesaurus](https://www.thesaurus.com/) 
- chatGPT 永远的神
- overleaf + grammarly 插件，可以自动识别你的 typo、同义词替换、paraphrase等



## Abstract

- keywords 通常是5-10个，按照字母顺序排列


## Introduction



## Literature 

### 查找学术资料

- 如果 [google scholar](https://scholar.google.com/) 上无法轻松获得论文，可以去 [sci-hub](https://sci-hub.hkvisa.net/) 碰碰运气
- 教材可以去 [libgen](http://libgen.rs/) 或者 [zlibrary](https://cn1lib.is)，非常好用

### 文献管理软件+插件

- 文献管理软件，推荐 [zotero](https://github.com/zotero/zotero) 及相关的灰常好用的插件：
  1. [zotero-style](https://github.com/MuiseDestiny/zotero-style)：标签、#标签、进度 这三个功能还不错


## Methodology

### Proof Theorem Citation
- If you want to find some important theorems as references, start with consulting this document [Useful theorem sources](./Useful_theorem_sources.md).

### Formula Requirements

- Stylistic Requirements（如何让文章看上去更规范和美观）需要参照期刊的要求，例如 [biostatistics的要求](https://static.primary.prod.gcms.the-infra.com/static/site/biostatistics/document/maths-style-ref.pdf?node=572c095a7860500162e9&version=439324:09b02a27db4dca3881c8) ：
  - 行内公式不要写 $e^{\frac{1}{2\pi}}$，要写 $\exp\{1/(2\pi)\}$ 或者 $\exp\{(2\pi)^{-1}\}$
  - 积分不要写 $dx$，要写 $\mathrm{d} x$
  - 不要用 footnote


## Numerical Study

### Coding
  - 代码结构可以参考别人的repo，例如 [negative-label-smoothing](https://github.com/UCSC-REAL/negative-label-smoothing) 和 [CCD](https://github.com/tianyu0207/CCD)
  - argparse（或者类似的功能）：https://tendcode.com/article/python-shell/
    > 用于命令行传参
  - 实际编程中遇到的常见问题以及解决办法将持续更新在 [Practical_Coding_Solutions.md](./Practical_Coding_Solutions.md)

## Table and Figure

### Table

- latex表格生成器：https://www.tablesgenerator.com/
  > 复制数据到网站上，调整格式（边框、三线表），自动生成LaTex表格

### Sub-Figures

- 使用latex来调整子图很麻烦，因为万一图片的scale不一样还得调整半天，这里推荐使用PPT来排版：
  - 图片大小使用PPT对图片的横、宽进行设置可以达到一模一样
  - 图片的标题使用 [iguanatex](https://www.jonathanleroux.org/software/iguanatex/) 生成，再排版
  - 整个PPT包含所有子图和对应的标题，生成一个大图的pdf，再上传到文章中

## Reference



## LaTex Tips

- 推荐的 LaTex 教程，参见 [LaTex Tips](LaTeX_Tips.md)




# 3. Toward Acceptance


## 3.1. Reply Letter

- reply 遣词造句见 [Academic_Phrasing.md](Academic_Phrasing.md)

- reply 中才有的图表的序号最好与正文中图表的需要区分，例如正文采用 Figure 1，reply 里就可以采用 Figure I.



## 3.2. 如何与editor沟通

> 比如你的文章还没发表，但是你又发现了一大堆typo😳

- 如何卑微地给editor写邮件：https://www.howsci.com/the-letters-communicate-with-editor.html
  

## 3.x. 求神拜佛

- 雍和宫，对面还有吴裕泰冰淇淋