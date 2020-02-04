---
layout:     post                    # 使用的布局（不需要改）
title:      NLP week4               # 标题 
subtitle:   Regular Expression #副标题
date:       2020-02-4              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - study
---

# **IST664-NLP**
>Week 4 Regular Expression!

## **Resources**
[Python Regex Cheatsheet](https://www.debuggex.com/cheatsheet/regex/python)

[测试regex网站](https://regex101.com/)

[regex cheatsheet](http://web.mit.edu/hackl/www/lab/turkshop/slides/regex-cheatsheet.pdf)

## **Lecture Content**

### **Regular Expression**
Regular Expression: a tiny, highly specialized programming language
- embadded inside Python, Perl, Java, php and other languages
- match or replace patterns

>本文用Perl习惯即//来表示正则表达式

#### 普通匹配

| Pattern       | Matches       |Example                        |
| ------------- |:-------------:| -----------------------------:|
| woodchuck     | woodchuck     | The *woodchuck* eats lettuce  |

#### 可替代的匹配
用方括号包住的表示alternative（可替代）

| Pattern       | Matches             |Example     |
| ------------- |:-------------------:| ----------:|
| [wW]oodchuck  | Woodchuck, woodchuck| *Woodchuck*|

#### 范围匹配
[a-z], [A-Z], [0-9]

#### ^在[]内表示否定
[^a-z], [^s^](not s or ^)
>如果不在中括号[]内而是在字符中间，^表示^字符,e.g. a^b

#### |表示或
woodchuck|groudhog 表示同时匹配两个单词 
e.g. A *woodchuck* is the same as a *groundhog*!

#### 重复匹配符号
- ? : 0 or 1
- * : 0:n
- + : 1:n
- . : 表示任意字符
- {m}: 把之前的字符重复m次
- {m,n}: 把之前的字符重复m-n次
e.g. Xyz{3}: abx*Xyzzz*
     abc{1,5}: xycabcc tfeabcccc

#### 开头和结尾(Anchor tags): ^ 和 $
- ^\[A-Z]  : 开头任意大写字母
- ^\[^A-Za-z] : 开头非字母
- .$: 结尾为任意字符
- /**\b**our**\b**/ : word boundary
- /**\B**our**\B**/ : non-word boundary
简单来说两头\b则匹配的
