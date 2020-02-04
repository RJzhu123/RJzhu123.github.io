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
| Pattern       | Matches       |Example                      |
| ------------- |:-------------:| ---------------------------:|
| woodchuck     | woodchuck     | The *woodchuck* eats lettuce|

#### 可替代的匹配
用方括号包住的表示alternative（可替代）
| Pattern       | Matches             |Example     |
| ------------- |:-------------------:| ----------:|
| [wW]oodchuck  | Woodchuck, woodchuck| *Woodchuck*|
