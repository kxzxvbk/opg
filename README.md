# Operator-Precedence-Parse
北京航空航天大学软件学院

编译原理课程

算符优先分析作业

### 编译原理作业总目录

https://github.com/ZhuChenyuCZ/CompilerHomeWorkList

### 如果我的作业对你有帮助的话，麻烦给个star吧：D



# 算符优先分析作业

## 评测网址

https://oj.karenia.cc/suite/1ft03dkbb240y

### 快速开始

#### 本地方法

在同文件夹下创建一个名为in.txt的文件。在in.txt中填写输入数据。

```
gcc -Wall OPG.c
./a.out in.txt
```

#### OJ测试方法

在评测机中输入仓库地址以及分支名称，点击提交。

## 题目

编程实现以下文法 `G[E]` 的算符优先分析法：

```none
E -> E '+' T | T
T -> T '*' F | F
F -> '(' E ')' | 'i'
```

## 输入输出要求

对于每一个测试点，你需要读入**一个符合或不符合文法的句子**，占据 1 行。你需要在读取这个句子之后输出使用算符优先级矩阵分析这个句子的步骤。

输入不会超过 1000 字节，且只含非空白 ASCII 字符，以 `\r\n` 结束。

输出要求如下：

- 对于每一次压栈，输出一行 `I{压入的符号}`（不含大括号），如 `Ii` 是压入 `i`；
- 对于每一次成功的、含有终结符的规约，输出一行 `R` *(1)* ；
- 对于失败的规约，输出一行 `RE` *(2)* ；
- 对于不能识别或无法比较符号优先关系的栈顶和读入符号，输出一行 `E` *(2)* 。

*(1)* ：因为符号优先文法不区分非终结符，如 `T -> F` 等的仅含非终结符的规约实际上是不存在的。

遇到 *(2)* 的情况，输出相应内容后不继续向下分析，直接退出。不管分析结果如何，程序返回值都应为 `0`。

## 提交参数

本次实验的标识符是 `opg`，你的 `judge.toml` 应以 `[jobs.opg]` 开头。

评测机提供的输入是一个文件路径 `$input`，你的程序可以选择将文件作为命令行参数传入后读取文件，也可以选择使用 `cat $input | <你的程序>` 从标准输入读入。

## 示例输入输出

由于符号优先文法不区分非终结符，下面使用 `N` 代表任意非终结符。

### A

输入：`i`

输出：

```none
Ii
R
```

解释：

1. 读入 `i`
2. 规约 `N <- i`

### B

输入：`i+i`

输出：

```none
Ii
R
I+
Ii
R
R
```

解释：

1. 读入 `i`
2. 规约 `N <- 'i'`
3. 读入 `+`
4. 读入 `i`
5. 规约 `N <- 'i'`
6. 规约 `N <- N '+' N`

### C

输入：`i+`

输出：

```none
Ii
R
I+
RE
```

### D

输入：`ii`

输出：

```none
Ii
E
```

### 其他相关地址

测试OJ Rurikawa

[https://oj.karenia.cc](https://oj.karenia.cc/)

SystemProgramming 论坛

[http://forum.loheagn.com](http://forum.loheagn.com/)

评测机开源仓库

https://github.com/BUAA-SE-Compiling/rurikawa

评测机使用说明

https://github.com/BUAA-SE-Compiling/rurikawa/blob/master/docs/manual/submit.md

## 评测记录

2020-11-05 21:12

14/14

1ft7yhdcr9eqg

master

2020-11-05 21:05

Dispatched

1ft7y48d53by1

master

2020-11-05 21:03

Dispatched

1ft7y19cs8btj

master

2020-11-05 20:55

5/14

1ft7xjgcs95vm

master

2020-11-05 20:46

12/14

1ft7x1ycvjf7b

master

2020-11-05 20:23

0/14

1ft7vpcd53tm2

master

2020-11-05 20:19

0/14

1ft7vead3g7s6

master

2020-11-05 20:14

4/14

1ft7v58cy9f80

master

2020-11-05 20:11

0/14

1ft7tz5czj577

master

没了