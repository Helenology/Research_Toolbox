# **TIPS**

[TOC]

## 前言

- 各类Tips，包括Tensorflow, Jupyter Notebook, Mac终端命令, Linux终端命令, 以及Latex。
- 命令部分比较杂乱，善用搜索功能查找。

## 1 Python的终端命令

### 1.1 Tensorflow的安装

```bash
pip install tensorflow-gpu==1.4.0 # 安装anaconda，然后用python的pip可以安装特定版本的tensorflow
pip uninstall tensorflow-gpu==1.4.0 # 卸载特定版本的tensorflow
tf.__path__ # 查看当前tensorflow的安装路径
pip install --upgrade tensorflow==1.13.1 # cpu(升级到指定版本eg:1.13.1) 
pip install --upgrade --ignore-installed

conda create -n horovod python==3.7 # 创建新环境
conda remove -n horovod --all # 删除环境
conda info --env # 查看环境
conda activate tensorflow # 激活虚拟环境
source /Users/macbooke/opt/anaconda3/bin/activate # 激活conda
```

### 1.2 添加镜像

```bash
conda config --add channels <https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/>
# TUNA的help中镜像地址加有引号，需要去掉
conda config --set show_channel_urls yes # 设置搜索时显示通道地址
pip install --index <https://pypi.mirrors.ustc.edu.cn/simple> matplotlib --default-timeout=1000
pip install tensorflow-probability -i https://pypi.tuna.tsinghua.edu.cn/simple/ --user
```

推荐使用ustc(中科大的)：<https://pypi.mirrors.ustc.edu.cn/simple>
豆瓣：<http://pypi.douban.com/simple>
阿里：<http://mirrors.aliyun.com/pypi/simple>

### 1.3 在Jupyter Notebook上装kernel

```bash
conda activate 新环境
# 经测试每个新环境都要装一次，否则下一句无法运行，但是不用重装jupyter
conda install ipykernel    
# 添加新环境到jupyter中
python -m ipykernel install --user --name 环境名称 
--display-name "Python (环境名称)"    
# 在对应环境下打开jupyter
jupyter notebook   
```

### 1.4 Jupyter Markdown基本操作

[Jupyter 小技巧1](https://www.jianshu.com/p/3115d2260ec2)

[Jupyter 小技巧2](https://blog.csdn.net/simple_the_best/article/details/52821136)

### 1.5 Jupyter Notebook的安装以及对R语言的支持

[Jupyter Notebook的安装以及对R语言的支持](https://www.jianshu.com/p/a66399b1c74d)
```py
IRkernel::installspec()
```

### 1.6 Jupyter Notebook转换成py类型文件

```sh
jupyter nbconvert --to script XX.ipynb
```

### 1.7 Jupyter Notebook让图像更清晰

```py
%matplotlib inline
%config InlineBackend.figure_format='svg'
```

## 2 一般的终端命令

### 2.1 Mac通过终端修改文件

```bash
- 1 进入指定修改的文件所在文件夹 cd 文件夹名称
- 2 进入编辑模式 vim + 文件名
- 3 插入修改 shift + i
- 4 退出插入模式 esc
- 5 整页翻页 ctrl-f ctrl-b f:forward b:backward
- 6 翻半页 ctrl-d ctrl-u d=down u=up
- 7 滚一行 ctrl-e ctrl-y
- 8 保存退出 shift + : wq
- 9 强制退出(不保存) shift + : qa!
```

### 2.2 一些有用的链接

- [玩转 Terminal 终端：入门指南及进阶技巧](https://sspai.com/post/45534)
- [每天一个linux命令目录](https://www.cnblogs.com/peida/archive/2012/12/05/2803591.html)
- [macOS 终端(Terminal) 命令行 教程](https://www.jianshu.com/p/a9bf79b1b134)
- [最全面的终端初级教程！](https://blog.csdn.net/yechaodechuntian/article/details/45242747)

### 2.3 Terminal 快捷键

- 把输出写入log 文件

```bash
python client_start.py 2>&1 | tee $(date "+%Y%m%d_%H%M%S").log
```

```sh
# 监控内存
watch -n 0.01 nvidia-smi # or 
watch --color -n1 gpustat -cpu
ps -efl grep 进程id 
kill # 杀死进程
htop #查看各种信息 , (GPU，内存等), h的意思是更人性化?
top -H -p 67981 # 查看特定进程
# 生成压缩包 
tar -zcvf folder_name.tar.gz folder_name
# 解压 
tar -zxvf folder_name.tar.gz
unzip zipped_file.zip
pwd # 查看路径
sudo killall airportd
find . -name '*.md'
mdfind -name 文件名字
passwd # 修改密码
su # root权限
```

```sh
# 查看mac终端端口命令 
netstat -AaLlnW
# 查看ip命令 
ifconfig | grep "inet"
# 查看主机名 
hostnamectl # or
echo $HOSTNAME
# 查看外网地址 
curl cip.cc
# 新建文件夹 
mkdir
# 复述
echo "words"
# 列举当前路径下的全部文件并展开所有子文件夹
ls -R
# 清屏
clear
```
  
- 把电脑上的 Windows 分区彻底删除：[把电脑上的 Windows 分区彻底删除](https://sspai.com/post/43699)

```sh
sudo diskutil eraseVolume free none diskx
```

- **man 指令**
查看命令用法。
比如可以使用 **man diskutil** 来查看这个磁盘管理命令的具体用法说明，想要退出这个说明按下键盘 Q 即可

- 不要进入休眠状态：可以使用 caffeinate 命令让电脑时刻清醒。当你需要其恢复正常时，按下 ⌃Control - C 即可停止该命令。
- 程序假死需要强退：使用 killall 命令。以微信为例，若想强退它，只需输入 killall WeChat
- 截图保存为 JPEG：defaults write com.apple.screencapture type jpg，如果你希望撤销这条指令，输入 defaults write com.apple.screencapture type png
- 显示隐藏文件夹：defaults write com.apple.finder AppleShowAllFiles -bool true; killall Finder，当你不需要再显示时，输入：defaults write com.apple.finder AppleShowAllFiles -bool false; killall Finder
- 文件格式转换 textutil 若你手头有一篇 DOCX 文件需要被转换成 TXT，则可以输入 textutil -convert txt 文件路径，文件路径则可以采用拖拽文件到终端的方法自动填充
- 磁盘处理 diskutil，diskutil list 命令会将你的现有磁盘状况显示出来
- 从终端进入Finder：终端cd到文件件下，然后”open .” 打开文件夹路径对应的Finder

### 2.4 并行计算与远程ssh

```sh
# 登入ssh   
ssh name@ip
# 在每台服务器或虚拟机上配置hosts，
vim /etc/hosts
# 从remote下载文件：
scp -r name@ip:/data/Downloads/
# 往本地传东西
scp -r name@ip:~/DL/BASICS /Users/Downloads/   
scp DL.gz name@ip:/home/
# 查看内存
nvidia-smi
# 自己登录，然后新建终端   
ln -s /work/share/Hanson/DL/ ~/ # 这句话是建立一个/work/share/Hanson/DL  到自己主目录的快捷方式的意思
```

```sh
more file_name.txt
dos2unix file_name.txt # 改正换行的问题
qsub file_name.txt # 提交任务
qstat # 直接看
-l # 子目录
-lt # 按时间排
more file_name.Rout # 正在运行的东西  回车退出
tail -f file_name.Rout  # -fresh随时刷新（监控代码）  （control c）跳出
dir # 看有什么目录
cd # 到那个目录
get # 得到文件
get -r # 得到文件夹
rm [-r] # 删除文件【文件夹】
cd ..　# 上级目录
sftp  name@ip  # 回车 密码
  - dir # 看有什么目录
  - cd # 到那个目录
  - get # 得到文件
  - get -r # 得到文件夹
```

### 2.5 Brew 管理mac包

- 搜索应用 brew search 应用名（一般需英文名）
- 只是单个应用名（如 squirrel），你可以用 brew install squirrel 直接安装[1]，一般这类能直接下载安装的都是命令行工具。你还可以看到一类名字前带着 cask 的应用，它们需要换个命令来安装：brew cask 应用名。就如其名字所代表的一样，brew cask（木桶）下载下来的是一个个打包好 .app 文件。
- 检查一下可更新的应用有哪些：brew outdated
- 更新一下可更新的应用：brew upgrade
- 加上需要更新的应用名，避开不需要更新的应用：brew upgrade 应用名
- 更新完后可以运行一下下面的命令，把应用的旧版本和缓存删除：brew cleanup
- 你只是想看看有哪些应用可以清理，但暂时不需要处理它们：brew cleanup -n
- 指定需要清理缓存的应用：brew cleanup 应用名
- 访问应用官网：新功能我是不是需要？它的新版本适不适配我的系统？brew home 应用名

## 3 Latex

### 3.1 Latex基本使用文档

- [一份短小有用的Latex文档](https://liam.page/2014/09/08/latex-introduction/)
- [该作者主页](https://liam.page/)，有很多其他有用资料

### 3.2 Latex与VScode

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

### 3.3 Latex与Github

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
