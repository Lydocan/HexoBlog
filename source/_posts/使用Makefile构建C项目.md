---
title: 使用Makefile构建C项目
date: 2018-03-18 21:20:35
tags: Makefile C项目
---
最近接触多是一些C语言的项目，而说到C语言，个人感觉大部分都是使用makefile来构建项目的。

作为一个新手，这里就简单说说makefile构建项目的一些方法，给同样刚入门的人一些启发就是。


## 基本语法

### 变量
```(make)
CC = gcc
XX = g++

# 编译链接选项
CFLAGS = -Wall -O3 -g -c
```

### 通配符

`$@` 表示所有目标文件 <br>
`$^` 表示所有的依赖文件<br>
`$<` 表示第一个依赖文件

### 变量替换引用

```
OBJECTS = $(SOURCES:.c=.o)
```

### 使用内置函数

```
wildcard 扩展通配符
notdir 去除路径
patsubst 替换通配符
```