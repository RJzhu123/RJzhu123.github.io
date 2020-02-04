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
<font size="4"></font><br />
# **IST664-NLP**
>Week 4 Regular Expression!

## **Resources**
[Python Regex Cheatsheet](https://www.debuggex.com/cheatsheet/regex/python)

[测试regex网站](https://regex101.com/)

[regex cheatsheet](http://web.mit.edu/hackl/www/lab/turkshop/slides/regex-cheatsheet.pdf)

## **Lecture Content**

## **Regular Expression**
Regular Expression: a tiny, highly specialized programming language

- embadded inside Python, Perl, Java, php and other languages
- match or replace patterns


***

### 普通匹配

| Pattern       | Matches       |Example                        |
| ------------- |:-------------:| -----------------------------:|
| woodchuck     | woodchuck     | The *woodchuck* eats lettuce  |

### 可替代的匹配
用方括号包住的表示alternative（可替代）

| Pattern       | Matches             |Example     |
| ------------- |:-------------------:| ----------:|
| [wW]oodchuck  | Woodchuck, woodchuck| *Woodchuck*|

### 范围匹配
	[a-z], [A-Z], [0-9]

### ^在[]内表示否定
	[^a-z], [^s^](not s or ^)
>如果不在中括号[]内而是在字符中间，^表示^字符,e.g. a^b

### |表示或
	woodchuck|groudhog 表示同时匹配两个单词 
	e.g. A *woodchuck* is the same as a *groundhog*!

### 重复匹配符号
- ? : 	0 or 1
- \* : 0:n
- \+ : 1:n
- . : 表示任意字符
- {m}: 把之前的字符重复m次
- {m,n}: 把之前的字符重复m-n次
<br/>`Xyz{3}: abx*Xyzzz*`</br>
<br/>`abc{1,5}: xycabcc tfeabcccc`</br>

### 开头和结尾(Anchor tags): ^ 和 $
- ^\[A-Z]  : 开头任意大写字母
- ^\[^A-Za-z] : 开头非字母
- .$: 结尾为任意字符
- /**\b**our **\b**/ : word boundary
- /**\B**our **\B**/ : non-word boundary

简单来说word boundary 则为匹配单词开头，而非boundary则匹配单词中间(即两边不是区分word的界限)

### 替换

s/<替代的pattern>/<被替代的单词>

`e.g. s/colour/color`
### capture group
空格可以保存一个pattern在memory里，然后可以通过 \1（register）来简单访问前面第一个捕捉到的group

`e.g. ([0-9]+)\1   --------  ada *233233* 145145 daww `

>  如果不想使用捕捉的特性，则在左括号后加一个问号?

### escapes '\'
-  “\[](){}\|^$.?+\*\”
-  "\n\r\t"
-  whitespace: \s = \[\t\r\n\f\v]
-  digit: \d = \[0-9]
-  word: \w = \[a-zA-Z0-9_]
-  non-whitespace: \S
-  non-digit: \D
-  non-word: \W
- Registers: \1, \2, etc

### 贪婪特性
如果不认为设置，默认的匹配原则是贪婪的，即选最多最长的
e.

* greedy:  
`/^.\*t/ *a076bt876xyt*dx`
* non-greedy:  
`/^.\*?t/ *a076bt*876xytdx`

***
### python简单实用正则表达式
1. 第一种用法  
	`pattern = re.compile(“<regular expr>”)`
	`m = pattern.search(string)`
	
2. 第二种用法  
	`'re.match(“<regular expr>”, string)' `
	
3. 其他常用函数
	<br/>`'pattern.match' #返回true如果字符串的开头匹配`<\br>
	<br/>`'pattern.search' #搜索字符串，任意位置找到或者没找到，返回 *MatchObject* or None`<\br>
	<br/>`'pattern.findall' #返回所有匹配项存在list中返回`<\br>

	- *MatchObject* 也有一些函数
		<br/>`match.group() 返回匹配的string`<\br>
		<br/>`match.start() 返回匹配项起始位置`<\br>
		<br/>`match.end() 返回匹配项的最后位置`<\br>
		<br/>`match.span() 返回start和end位置的tuple`<\br>
4. 替代  
	<br/>`'p=re.compile("pattern")' `<\br>
	<br/>`'string = p.sub("<替代值>",string)'`<\br>
	
***
以上就是nlp第四周有关正则表达式的内容，欢迎指正
