---
layout:     post                    # 使用的布局（不需要改）
title:      Machine Translation and Summarization     # 标题 
subtitle:   nlp664-week13 #副标题
date:       2020-04-04              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - nlp
---
<font size="4"></font><br />

## Machine Translation

- Faithfulness – the meaning of the text has been preserved. 
-  Fluency – the translated text sounds natural to a native speaker, and also maintains the style of the original text
­

信达雅, 流畅且准确，这非常困难

#### Differences between languages
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfyq06ndj31fg0t8te5.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfzuffl1j31940r8n2h.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkg0hpighj31bs0qkgry.jpg)

语素不一样， 语法顺序不一样， 词汇意思没有一一对应的

### Task
(过时老方法）
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkg2j9s1lj317r0u04c3.jpg)

(新方法)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkg3bu8ndj31ay0l042e.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkg4yj5abj319o0mmtcf.jpg)
算概率，极大似然估计，得到结果.

language model保证fluency, translation model保证faithfulness
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgbacj0fj317e0u00xp.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgbnnos2j31a60rmjws.jpg)

### evaluation
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkge0ogwbj31a40mm42m.jpg)

***

## Summarization
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkggtvsgij31a40pc0xr.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgho5jjqj316y0k4diw.jpg)

### Example
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgieknm0j31910u0e81.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgjkvhjhj315d0u0tvz.jpg)

### Task
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgk4b01hj31d20u0466.jpg)

#### Content Selection
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgrzqsujj318l0u0wkz.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgs8zd7tj31a40l8wis.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgsho2h2j31ao0r8n1g.jpg)

#### Information Ordering
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgtolxj3j319u0ncgpg.jpg)

#### Simplifying Sentences
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgud49npj31ek0rogru.jpg)

### evaluation 
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkgux87h1j31960rcdl0.jpg)



