---
layout:     post                    # 使用的布局（不需要改）
title:      Information Extraction           # 标题 
subtitle:   nlp664-week13 #副标题
date:       2020-04-04              # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - nlp
---
<font size="4"></font><br />

## Information Extraction
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdke5l3avlj316i0iiacy.jpg)

#### Typical Tasks
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdke6s2adtj31480potce.jpg)

#### Examples
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdke8225cij31f20syn6e.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkec3703xj31ac0q2jy0.jpg)
先识别，再分类

![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkee8v1yoj319u0u0dnc.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkef1ep4nj319o0tygsj.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkeueli1dj317h0u00zk.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkekgr5ztj31960u0dnf.jpg)

![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfi85z1bj31ck0tkjvh.jpg)

### NER (Named Entity Recognition)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkel2egw5j31080goact.jpg)

#### Typical Type
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkelcy0nfj31g80guqdt.jpg)

#### Ambiguity
同一个名词可能有很多种type
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkeryza67j31f40q4twa.jpg)

#### NER方法
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdketktdowj31c00r2jvc.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkevds4aqj31820u049a.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkevzljg0j314q0u0alr.jpg)

### Relations
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkewv305kj31700f4432.jpg)

#### Typical Type
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkex8od41j31ai0jg47o.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkf09rwjwj31fu0l0wmz.jpg)

#### 方法
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkf1mekutj31960qs0wk.jpg)
先判断是不是relations，再判断是什么relation

#### features　
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkf1mekutj31960qs0wk.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkf5kkialj316w0n8whs.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkf7o15cnj318n0u07gb.jpg)

#### bootstrapping
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfbkrh63j31760u0dlj.jpg)

### Template Filling
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfgj0zt0j31be0pe42n.jpg)
 ![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfhjvk95j31d60lw44k.jpg)


#### IE Example: Bioinformatic NLP

不同领域的names和relations很不一样，所以针对不同domain有不同方法.
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkflqyerbj316c0pajv6.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfmapnohj319r0u07j6.jpg)
![](https://tva1.sinaimg.cn/large/00831rSTgy1gdkfnorajxj31fc0muk0e.jpg)

针对生物领域，不需要很强泛化，只需要对specific的内容有效就可以


