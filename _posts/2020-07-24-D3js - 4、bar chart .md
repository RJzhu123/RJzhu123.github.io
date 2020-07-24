---
layout:     post                    # 使用的布局（不需要改）
title:      D3js - 4、bar chart    # 标题 
subtitle:    可视化       				#副标题
date:       2020-07-24            # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - D3js
---
<font size="4"></font><br />

## D3js - 4、bar chart

CSV : comma seperate value

## 1、导入 csv 数据

逻辑：

<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh2qfeq4rmj311a0tkakv.jpg" width = 50%></img>

### Linear Scale

<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh2qjr4mp1j31la0n4n90.jpg" width = 60%></img>

### Band Scale

<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh2qo4ieawj315s0oy46u.jpg" width = 70%></img>

### Margin Convention

<img src ="https://tva1.sinaimg.cn/large/007S8ZIlgy1gh2qwjdcyxj31gq0rwjw9.jpg" width = 70%></img>

### Axe

**axisLeft, axisBottom**

### Format Number

**format**

参考网页：[http://bl.ocks.org/zanarmstrong/05c1e95bf7aa16c4768e](http://bl.ocks.org/zanarmstrong/05c1e95bf7aa16c4768e)

```
  const xAxisTickFormat = number =>
    format('.3s')(number)
      .replace('G', 'B');
```

### Remove Unnecessary Lines
```
  g.append('g')
    .call(axisLeft(yScale))
    .selectAll('.domain, .tick line')
      .remove();
```

### Add Title
```
  g.append('text')
      .attr('class', 'title')
      .attr('y', -10)
      .text(titleText);
```

### Add Axis Labels
```
  xAxisG.append('text')
      .attr('class', 'axis-label')
      .attr('y', 65)
      .attr('x', innerWidth / 2)
      .attr('fill', 'black')
      .text(xAxisLabelText);
```

### 可视化style参考

[https://github.com/amycesal/dataviz-style-guide/blob/master/Sunlight-StyleGuide-DataViz.pdf](https://github.com/amycesal/dataviz-style-guide/blob/master/Sunlight-StyleGuide-DataViz.pdf)

### 效果
![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gh2sc99gksj31la0u013q.jpg)

### code: index.js
```
import {
  select,
  csv,
  scaleLinear,
  max,
  scaleBand,
  axisLeft,
  axisBottom,
  format
} from 'd3';

const titleText = 'Top 10 Most Populous Countries';
const xAxisLabelText = 'Population';

const svg = select('svg');

const width = +svg.attr('width');
const height = +svg.attr('height');

const render = data => {
  const xValue = d => d['population'];
  const yValue = d => d.country;
  const margin = { top: 50, right: 40, bottom: 77, left: 180 };
  const innerWidth = width - margin.left - margin.right;
  const innerHeight = height - margin.top - margin.bottom;
  
  const xScale = scaleLinear()
    .domain([0, max(data, xValue)])
    .range([0, innerWidth]);
  
  const yScale = scaleBand()
    .domain(data.map(yValue))
    .range([0, innerHeight])
    .padding(0.1);
  
  const g = svg.append('g')
    .attr('transform', `translate(${margin.left},${margin.top})`);
  
  const xAxisTickFormat = number =>
    format('.3s')(number)
      .replace('G', 'B');
  
  const xAxis = axisBottom(xScale)
    .tickFormat(xAxisTickFormat)
    .tickSize(-innerHeight);
  
  g.append('g')
    .call(axisLeft(yScale))
    .selectAll('.domain, .tick line')
      .remove();
  
  const xAxisG = g.append('g').call(xAxis)
    .attr('transform', `translate(0,${innerHeight})`);
  
  xAxisG.select('.domain').remove();
  
  xAxisG.append('text')
      .attr('class', 'axis-label')
      .attr('y', 65)
      .attr('x', innerWidth / 2)
      .attr('fill', 'black')
      .text(xAxisLabelText);
  
  g.selectAll('rect').data(data)
    .enter().append('rect')
      .attr('y', d => yScale(yValue(d)))
      .attr('width', d => xScale(xValue(d)))
      .attr('height', yScale.bandwidth());
  
  g.append('text')
      .attr('class', 'title')
      .attr('y', -10)
      .text(titleText);
};

csv('data.csv').then(data => {
  data.forEach(d => {
    d.population = +d.population * 1000;
  });
  render(data);
});
```
