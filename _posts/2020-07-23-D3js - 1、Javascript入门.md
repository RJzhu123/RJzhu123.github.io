---
layout:     post                    # 使用的布局（不需要改）
title:      D3js - 1、Javascript入门    # 标题 
subtitle:    可视化       				#副标题
date:       2020-07-23            # 时间
author:     renjie                      # 作者
header-img: img/aurora.jpeg    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - D3js
---
<font size="4"></font><br />

## D3js - 1、Javascript入门

## 1、Javascript入门
Javascript教程：
[https://eloquentjavascript.net/](https://eloquentjavascript.net/)

简单记录
### chapter 1 ： 数据类型
* 换行字符串：**`**
* **"Hello" +  5**  等于 `Hello${5}`
* 看类型：**typeof** 5
* **&&** 是and， **||**是or
* **1 == “1”** 会显示**true**， 更细的比较可以用三个等号**===**
* ternary操作: **true ? 1 : 2**
* **null** 和 **undefined**

### chapter 2 ： 程序结构

* 分号表示结尾；
* 声明变量：`var x = 5;` 等于 `let x = 5;`
* 如果用`const x = 5;`声明常量，常量不可以改变
* 条件判断:
```js
 if(isItTrue){
 	console.log("Yes")
 } else{
 	console.log("No"
 }
```
* 单行注释 `//` 多行注释`/* */`
* while loops： `while(判断条件){} `
* for loops: `for(let i = 0; i < 10; i++){}`

### chapter 3 : funciton

* 定义function `function square(x){ retrun x * x; }`
* 另一种方式 `let sq = function(x){ return x * x; }`
* 第三种方式： `sq = (x,y,z) => {}` 
* 递归recursion: 

<img src = "https://tva1.sinaimg.cn/large/007S8ZIlgy1gh1j0otkjjj30lq066406.jpg" width=40%>

### chapter 4: objects and arrays （重要）
* 定义object  `car = {year: 1997, make: 'Honda', model:'Accord', price: 2800};`
* `car.year`用点取object里的值   或 ` car['year']`
* 定义array：`let cars = [];`
* array里可以是数字、字符串、对象等
* 添加元素： `cars.push()`
* `cars.length;` 显示有多少元素
* `cars[0];`
* `for(car of cars) {};` 遍历， 或者for循环遍历, 或者 `cars.forEach(function);`
* `cars.map(car => car.price) ;` map返回新array
* `prices.sort()` 排序
* `cars.filter(car => car.price < 2000 );` 过滤
* object destructure

<img src = "https://tva1.sinaimg.cn/large/007S8ZIlgy1gh1jm357bvj30ys0e8tdi.jpg" width=50%>

* `JSON.stringify(cars, null , 2)`
*  `JSON.parse()` 把上面生成的字符串处理成原来的js对象

> 搜索js函数 ： mdn xxxx


### chapter 10: modules

* 用一个文件 例如 **cars.js** ，然后`export const cars = JSON.parse(JSONcars);`
* 然后导入用`import { cars } from 'cars'`



### chapter 11: 异步编程
<img src = "https://tva1.sinaimg.cn/large/007S8ZIlgy1gh1k6dnjd3j30s00cs753.jpg" width=50%>


* Promise

<img src = "https://tva1.sinaimg.cn/large/007S8ZIlgy1gh1kemuhzmj30yq0fkgxm.jpg" width=70%>

> [es6features](https://github.com/lukehoban/es6features)



