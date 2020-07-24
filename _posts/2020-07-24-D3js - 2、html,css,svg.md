---
layout:     post                    # 使用的布局（不需要改）
title:      D3js - 2、html,css,svg    # 标题 
subtitle:    可视化       				#副标题
date:       2020-07-24            # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - D3js
---
<font size="4"></font><br />

## D3js - 2、html,css,svg

> 课程code：[https://vizhub.com/curran/366c38ba5ebc4631b4bd936f3b709744](https://vizhub.com/curran/366c38ba5ebc4631b4bd936f3b709744)

## 1、html,css
略，见w3school

## 2、svg
矢量图，放大不影响

`<svg> </svg>`

简单操作见⬇️

[https://www.w3schools.com/graphics/svg_circle.asp](https://www.w3schools.com/graphics/svg_circle.asp)

### circle、rect

> 选颜色可以，google **color picker**

### g
**g** tag 可以group对象, **transform**可以带着组内元素移动，**fill**可以覆盖原先的颜色, **stroke**: outline 

```
<g transform="translate(0, 200)" fill="#adf6ff" stroke="black">
          <circle cx="50" cy="50" r="40" stroke-width="5"></circle>
          <rect x="150" y="25" width="50" height="50"></rect>
	</g>
```

### line(直线）, path(多段线)

x1, x2, y1, y2, stroke, stroke-width

```
<path fill="none" d="M300 280 L350 200 L400 250 L450 230"></path>
```




