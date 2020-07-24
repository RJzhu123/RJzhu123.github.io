---
layout:     post                    # 使用的布局（不需要改）
title:      D3js - 3、introduction to D3js    # 标题 
subtitle:    可视化       				#副标题
date:       2020-07-24            # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - D3js
---
<font size="4"></font><br />

## D3js - 3、introduction to D3js

### D3js : Data-Driven Documents

[https://d3js.org/](https://d3js.org/)

> code: [https://vizhub.com/68416/be771477cb974c938cd8603dd8b59d32](https://vizhub.com/68416/be771477cb974c938cd8603dd8b59d32)

## 1、 loading D3js

```
 <script src="https://unpkg.com/d3@5.9.2/dist/d3.min.js"></script>

```

## 2、 importing d3 function

index.js

bundle.js


``` import { select } from 'd3' ```

## 3、 making a face

```
(function (d3) {
  'use strict';

  const svg = d3.select('svg');

  const width = +svg.attr('width');
  const height = +svg.attr('height');

  const g = svg.append('g')
    .attr('transform', `translate(${width / 2}, ${height / 2})`);

  const circle = g.append('circle');

  circle.attr('r', height / 2);
  circle.attr('fill', 'yellow');
  circle.attr('stroke', 'black');

  const eyeSpacing = 101;
  const eyeYOffset = -89;
  const eyeRadius = 40;
  const eyebrowWidth = 70;
  const eyebrowHeight = 20;
  const eyebrowYOffset = -70;

  const eyesG = g
    .append('g')
      .attr('transform', `translate(0, ${eyeYOffset})`);

  const leftEye = eyesG
    .append('circle')
      .attr('r', eyeRadius)
      .attr('cx', -eyeSpacing);

  const rightEye = eyesG
    .append('circle')
      .attr('r', eyeRadius)
      .attr('cx', eyeSpacing);

  const eyebrowsG = eyesG
    .append('g')
      .attr('transform', `translate(0, ${eyebrowYOffset})`);

  eyebrowsG
    .transition().duration(2000)
      .attr('transform', `translate(0, ${eyebrowYOffset - 50})`)
    .transition().duration(2000)
      .attr('transform', `translate(0, ${eyebrowYOffset})`);

  const leftEyebrow = eyebrowsG
    .append('rect')
      .attr('x', -eyeSpacing - eyebrowWidth / 2)
      .attr('width', eyebrowWidth)
      .attr('height', eyebrowHeight);

  const rightEyebrow = eyebrowsG
    .append('rect')
      .attr('x', eyeSpacing - eyebrowWidth / 2)
      .attr('width', eyebrowWidth)
      .attr('height', eyebrowHeight); 

  const mouth = g
    .append('path')
      .attr('d', d3.arc()({
        innerRadius: 150,
        outerRadius: 170,
        startAngle: Math.PI / 2,
        endAngle: Math.PI * 3 / 2
      }));

}(d3));
```

### Method Chain
.attr.attr.attr

### D3 documentation 
[https://github.com/d3/d3/wiki](https://github.com/d3/d3/wiki)

## animation

```.
transistion().ducration(1000)
	.attr('y, 100)
```

