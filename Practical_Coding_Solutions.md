# Practical Solutions for Research Coding

## 代码结构及风格

通常来说文章的代码可以分为Simulation和Empirical……
（待填坑）

## 极大似然估计+优化目标函数

- 通常我们面对的是一个非标准的极大似然估计问题（其中非标准代表无法直接用现成的模型，例如python中的logistic regression模型，来直接调用解决，而是需要根据你的目标函数写对应的优化代码，python代码可以参考 https://rlhick.people.wm.edu/posts/estimating-custom-mle.html


## Python 建模


- 代码加速通常来说有两种加速方式：
  - 对于普通的numpy计算，使用`multiprocessing`这类的多线程并行计算来将for循环divide and conquer掉
  - 如果矩阵非常大，而对矩阵的操作较为简单，比如简单的加加减减、卷积等，可以使用GPU加速运算


- tmux 使用：
  - 鼠标滚动：https://blog.csdn.net/liumiaocn/article/details/104100000

## R 画图

- 写的不错的教程，(四川师范大学研究生公选课《数据科学中的R语言》的课程)[https://bookdown.org/wangminjie/R4DS/]

- [ ] 如何读入一个文件夹下的所有csv文件
- [ ] 正则表达式 [stringr](https://bookdown.org/wangminjie/R4DS/tidyverse-stringr.html)