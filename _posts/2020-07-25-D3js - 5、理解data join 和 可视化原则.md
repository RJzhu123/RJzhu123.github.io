---
layout:     post                    # 使用的布局（不需要改）
title:      D3js - 5、理解data join 和 可视化原则   # 标题 
subtitle:    可视化       				#副标题
date:       2020-07-25            # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - D3js
---
<font size="4"></font><br />

## D3js - 5、理解data join 和 可视化原则

## Data Join

一图流

<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh481jq64sj31kl0u01bi.jpg" width = 70%>

* Enter 选中data 匹配 dom元素
* update 选中匹配元素进行操作
* exit 选中未匹配 数据的元素
* merge 同时进行enter 和 update


## 可视化原则
### 1、 marks
<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh484griw7j31o60u0drz.jpg" width = 80%>

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gh4858bdg6j31hp0u01cb.jpg)

### gis map绘制
<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh485pempwj310q0u01kx.jpg" width = 70%>


### 如何选择mark和channel
<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh486rydwdj31740tu4qp.jpg" width = 70%>
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gh4870drglj30z10u0k76.jpg)

**bar chart 最精确**

<img src = "https://tva1.sinaimg.cn/large/007S8ZIlgy1gh487yuiozj30u00wcaob.jpg" width =40%>

**长度最可靠**

### 2、 channel

![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gh489cgwchj31gv0u01gk.jpg)
**运用之妙，存乎一心**