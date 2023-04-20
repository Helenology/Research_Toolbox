# **TIPS**

## Table of Contents

<!-- - [**TIPS**](#tips)
  - [Table of Contents](#table-of-contents)
  - [1. Python](#1-python)
    - [1.1 tensorflow指定版本的安装及升级到最新版](#11-tensorflow指定版本的安装及升级到最新版)
    - [1.2 添加Anaconda的TUNA镜像](#12-添加anaconda的tuna镜像)
    - [1.3 在jupyter上装kernel](#13-在jupyter上装kernel)
    - [1.4 VS code Python入门](#14-vs-code-python入门)
    - [1.5 jupyter Markdown 基本操作](#15-jupyter-markdown-基本操作)
    - [1.6 Jupyter Notebook的安装以及对R语言的支持](#16-jupyter-notebook的安装以及对r语言的支持)
    - [1.7 Jupyter Notebook转换成python](#17-jupyter-notebook转换成python)
  - [2 终端](#2-终端)
    - [2.1 Mac通过终端修改文件](#21-mac通过2终端修改文件)
    - [2.2 一些有用的链接](#22-一些有用的链接)
    - [2.3 Terminal 快捷键](#23-terminal-快捷键)
    - [2.4 Brew 管理mac包](#24-brew-管理mac包)
    - [2.5 Linux 命令](#25-linux-命令)
  - [3 Latex](#3-latex)
    - [3.1 快捷方式](#31-快捷方式)
    - [3.2 Latex的公式](#32-latex的公式) -->

[TOC]


## 1. Python

### 1.1 tensorflow指定版本的安装及升级到最新版

安装anaconda，然后用python的pip可以安装特定版本的tensorflow，如：
pip install tensorflow-gpu==1.4.0

卸载特定版本的tensorflow，如：
pip uninstall tensorflow-gpu==1.4.0

如何查看当前tensorflow版本：
python
import tensorflow as tf
tf.\_\_version\_\_

如何查看当前tensorflow的安装路径：
tf.\_\_path\_\_

补充一个： cpu(升级到指定版本eg:1.13.1) pip install --upgrade tensorflow==1.13.1

创建新环境
conda create -n horovod python==3.7

删除环境
conda remove -n horovod --all

安装horovod
pip install --no-cache-dir horovod

查看环境
conda info --env

激活虚拟环境
conda activate tensornew

激活conda 
source /Users/macbooke/opt/anaconda3/bin/activate

pip install —-upgrade tensorflow
pip install --upgrade --ignore-installed

pip uninstall horovod

conda install gcc_linux-64 gxx_linux-64

conda run pip install --no-cache-dir horovod

horovodrun -np 16 -H server1:4,server2:4,server3:4,server4:4 python train.py

### 1.2 添加Anaconda的TUNA镜像

conda config --add channels <https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/>
% TUNA的help中镜像地址加有引号，需要去掉

设置搜索时显示通道地址
conda config --set show_channel_urls yes

推荐使用ustc(中科大的)：<https://pypi.mirrors.ustc.edu.cn/simple>

豆瓣：<http://pypi.douban.com/simple>

阿里：<http://mirrors.aliyun.com/pypi/simple>

pip  install --index <https://pypi.mirrors.ustc.edu.cn/simple> matplotlib --default-timeout=1000

pip install tensorflow-probability -i https://pypi.tuna.tsinghua.edu.cn/simple/ --user




### 1.3 在jupyter上装kernel

conda activate 新环境

conda install ipykernel    #经测试每个新环境都要装一次，不然下一句无法运行，但是不用重装jupyter

python -m ipykernel install --user --name 环境名称 --display-name "Python (环境名称)"    #添加新环境到jupyter中

jupyter notebook    #在对应环境下打开jupyter



### 1.4 VS code Python入门

<https://code.visualstudio.com/docs/python/python-tutorial#_prerequisites>

- `快捷键`
  - 1.) “#%%”  可以包括代码Cell，一个cell运行，在interactive中交互展示

### 1.5 jupyter Markdown 基本操作

<https://www.jianshu.com/p/3115d2260ec2>

[jupyter 小技巧](https://blog.csdn.net/simple_the_best/article/details/52821136)

### 1.6 Jupyter Notebook的安装以及对R语言的支持

[Jupyter Notebook的安装以及对R语言的支持](https://www.jianshu.com/p/a66399b1c74d)

IRkernel::installspec()

### 1.7 Jupyter Notebook转换成python
jupyter nbconvert --to script XX.ipynb

### 1.8 Jupyter Notebook 画图清晰
%matplotlib inline
%config InlineBackend.figure_format = 'svg'


## 2 终端

### 2.1 Mac通过终端修改文件

- 1 进入指定修改的文件所在文件夹 cd 文件夹名称
- 2 进入编辑模式 vim +文件名
- 3 插入修改 shift + i
- 4 退出插入模式 esc
- 5 整页翻页 ctrl-f ctrl-b f就是forword b就是backward
- 6 翻半页 ctrl-d ctlr-u d=down u=up
- 7 滚一行 ctrl-e ctrl-y
- 8 保存退出 shift + : wq
- 9 强制退出(不保存) shift + : qa!

### 2.2 一些有用的链接

- [玩转 Terminal 终端：入门指南及进阶技巧](https://sspai.com/post/45534)
- [每天一个linux命令目录](https://www.cnblogs.com/peida/archive/2012/12/05/2803591.html)
- [macOS 终端(Terminal) 命令行 教程](https://www.jianshu.com/p/a9bf79b1b134)
- [最全面的终端初级教程！](https://blog.csdn.net/yechaodechuntian/article/details/45242747)


### 2.3 Terminal 快捷键

- 本机地址：ssh macbooke@222.29.64.202  密码：2823
- 本机jupyter密码：shuyuan
- 查看mac终端端口命令 netstat -AaLlnW
- 查看ip命令 ifconfig | grep "inet"
- 查看主机名 hostnamectl 或者echo $HOSTNAME
- 查看外网地址 curl cip.cc
- 新建文件夹 mkdir 

- 复述： echo "想说的话"
- 列举当前路径下的全部文件并展开所有子文件夹： ls -R
- 清屏：clear
- 把电脑上的 Windows 分区彻底删除：sudo diskutil eraseVolume free none diskx，[把电脑上的 Windows 分区彻底删除](https://sspai.com/post/43699)
- man 指令查看命令用法，比如可以使用 man diskutil来查看这个磁盘管理命令的具体用法说明，想要退出这个说明按下键盘 Q 即可
- 关闭崩溃报错：defaults write com.apple.CrashReporter DialogType none 命令关闭这个问题报告。若你希望恢复其显示，可以输入 defaults write com.apple.CrashReporter DialogType crashreport。
- 修改文件日期： 有时你可能需要修改文件创建或修改日期，这时可以使用 touch -t 199505090000 拖入文件命令。
- 不要进入休眠状态：可以使用 caffeinate 命令让电脑时刻清醒。当你需要其恢复正常时，按下 ⌃Control - C 即可停止该命令。
- 程序假死需要强退：使用 killall 命令。以微信为例，若想强退它，只需输入 killall WeChat
- 截图保存为 JPEG：defaults write com.apple.screencapture type jpg，如果你希望撤销这条指令，输入 defaults write com.apple.screencapture type png

- 关闭截图自动阴影： defaults write com.apple.screencapture disable-shadow -bool true; killall SystemUIServer
- 重新启动阴影时，可以输入：defaults write com.apple.screencapture disable-shadow -bool false; killall SystemUIServer
- 显示隐藏文件夹：defaults write com.apple.finder AppleShowAllFiles -bool true; killall Finder，当你不需要再显示时，输入：defaults write com.apple.finder AppleShowAllFiles -bool false; killall Finder
- 整理程序栏：可添加一个空白分界符，defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'; killall Dock
- 文件格式转换 textutil 若你手头有一篇 DOCX 文件需要被转换成 TXT，则可以输入 textutil -convert txt 文件路径，文件路径则可以采用拖拽文件到终端的方法自动填充
- 磁盘处理 diskutil，diskutil list 命令会将你的现有磁盘状况显示出来
- 从终端进入Finder：终端cd到文件件下，然后”open .” 打开文件夹路径对应的Finder
- 并行计算的东西
  - 到达路径： cd /Users/macbooke/Downloads/parallel_computation
  - 传输文件 scp -r CaJC wushuyuan@219.143.237.177:
  - 查看路径 ls
  - 登入ssh   ssh wushuyuan@219.143.237.177
  - more st1.txt
  - dos2unix st1.txt 改正换行的问题
  - qsub JC_ture_data_M.txt 提交任务
  - qstat #直接看
  -l 子目录
  -lt 按时间排
  - more JC_ture_data_M.Rout 正在运行的东西  回车退出
  - tail -f JC_ture_data_M.Rout  #-fresh随时刷新（监控代码）  （control c）跳出
  - dir 看有什么目录
  - cd 到那个目录
  - get 得到文件
  - get -r 得到文件夹
  - rm [-r] #删除文件【文件夹】
  - cd ..　　　　　　上级目录


- ssh
  - 在每台服务器或虚拟机上配置hosts，命令行输入 vim /etc/hosts
  - 

- 从ncov@39.98.189.107下载文件：
scp -r ncov@39.98.189.107:/data/ncov /Users/macbooke/Downloads/ $\quad$密码：wuhanjiayou

- 服务器的东西
  - 账号和密码，可能要登vpn $\quad$账号：wushuyuan@222.29.89.7  $\quad$密码：shuyuan1425
  - 往本地传东西：scp -r wushuyuan@222.29.89.7:~/DL/BASICS /Users/macbooke/Downloads/ $\quad$ scp DL.gz wushuyuan@222.29.89:/home/wushuyuan/MyDL
  - 查看内存：nvidia-smi
  - 监控内存：watch -n 0.01 nvidia-smi  或者 watch --color -n1 gpustat -cpu
  - ps -efl grep 对应的数$$
  - kill 杀死进程
  - 查看各种信息：  htop （GPU，内存等）h的意思是更人性化？
  - top -H -p 67981 (查看特定进程)
  - 自己登录，然后新建终端   ln -s /work/share/Hanson/DL/ ~/ 这句话是建立一个/work/share/Hanson/DL  到自己主目录的快捷方式的意思
  - cp -r 源路径 指定目录. 复制文件
  - mv file1.txt file2.txt 重命名，file1为旧文件名，file2为新文件名
  - 生成压缩包 tar -zcvf folder_name.tar.gz folder_name
  - 解压 tar -zxvf folder_name.tar.gz
  - unzip zipped_file.zip
  - 查看路径 pwd
  - 微软服务器账号密码 student@52.143.96.134 Microsoft@365
- sudo killall airportd
- find . -name '*.md'
- mdfind -name 文件名字
- 修改密码: passwd
- root权限: su
- sftp  wushuyuan@219.143.237.177  回车 密码
  - dir 看有什么目录
  - cd 到那个目录
  - get 得到文件
  - get -r 得到文件夹
- tensorflow限制内存
```python
 gpus = tf.config.experimental.list_physical_devices('GPU')
 if gpus:
   # Restrict TensorFlow to only allocate 1GB of memory on the first GPU
     try:
         tf.config.experimental.set_virtual_device_configuration(
             gpus[0],
             [tf.config.experimental.VirtualDeviceConfiguration(memory_limit=5000)])
     except RuntimeError as e:
     # Virtual devices must be set before GPUs have been initialized
         print(e)
```


### 2.4 Brew 管理mac包

- 搜索应用 brew search 应用名（一般需英文名）
- 只是单个应用名（如 squirrel），你可以用 brew install squirrel 直接安装[1]，一般这类能直接下载安装的都是命令行工具。你还可以看到一类名字前带着 cask 的应用，它们需要换个命令来安装：brew cask 应用名。就如其名字所代表的一样，brew cask（木桶）下载下来的是一个个打包好 .app 文件。
- brew cask 应用名: [攻略](https://sspai.com/post/40321>;<https://sspai.com/post/32857)
- 检查一下可更新的应用有哪些：brew outdated
- 更新一下可更新的应用：brew upgrade
- 加上需要更新的应用名，避开不需要更新的应用：brew upgrade 应用名
- 更新完后可以运行一下下面的命令，把应用的旧版本和缓存删除：brew cleanup
- 你只是想看看有哪些应用可以清理，但暂时不需要处理它们：brew cleanup -n
- 指定需要清理缓存的应用：brew cleanup 应用名
- 访问应用官网：新功能我是不是需要？它的新版本适不适配我的系统？brew home 应用名

### 2.5 Linux 命令

- 把输出写入log 文件:
```bash
python client_start.py 2>&1 | tee $(date "+%Y%m%d_%H%M%S").log
```

## 3 Latex

### 3.1 快捷方式

- 查看PDF： 'option+cmd+v'
- 正向触发：edit' > 'SyncTeX from cursor' in the side bar, or by the shortcut cmd+option+j
- 反向触发："cmd+click"
- 开启check模式："latex-workshop.chktex.enabled": true

### 3.2 Latex的公式

- [一份短小有用的Latex文档](https://liam.page/2014/09/08/Latex-introduction/)
