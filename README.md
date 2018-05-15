# Flex_learningPath

## 0.参考资料

1. [阮一峰 Flex布局教程](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

## 1.Flex简介

* 兼容性:Chrome 21+ , Opera 12.1+ , Firefox 22+ , Safari 6.1+ , IE 10+
* Flex 是 Flexible Box 的缩写,意为"弹性布局",用来为盒状模型提供最大的灵活性
* 任何一个容器都可以指定为 Flex 布局 , 行内元素也可以使用 Flex 布局 , Webkit 内核的浏览器,必须加上-webkit前缀
* 注意,设为 Flex 布局以后,子元素的float、clear和vertical-align属性将失效

## 2.基本概念

* 采用 Flex 布局的元素,称为 Flex 容器（flex container）,简称"容器".它的所有子元素自动成为容器成员,称为 Flex 项目（flex item）
* 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）
* 主轴的开始位置（与边框的交叉点）叫做main start,结束位置叫做main end；交叉轴的开始位置叫做cross start,结束位置叫做cross end
* 项目默认沿主轴排列.单个项目占据的主轴空间叫做main size,占据的交叉轴空间叫做cross size.

## 3.容器的属性

* 1.flex-direction属性决定主轴的方向（即项目的排列方向）
1. row（默认值）：主轴为水平方向,起点在左端
2. row-reverse：主轴为水平方向,起点在右端
3. column：主轴为垂直方向,起点在上沿
4. column-reverse：主轴为垂直方向,起点在下沿

* 2.flex-wrap属性定义,如果一条轴线排不下,如何换行.默认情况下,项目都排在一条线（又称"轴线"）上
1. nowrap（默认）：不换行
2. wrap：向下换行，第一行在上方
3. wrap-reverse：向上换行，第一行在下方

* 3.flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap

* 4.justify-content属性定义了项目在主轴上的对齐方式
1. flex-start（默认值）：左对齐
2. flex-end：右对齐
3. center： 居中
4. space-between：两端对齐，项目之间的间隔都相等
5. space-around：每个项目两侧的间隔相等.所以，项目之间的间隔比项目与边框的间隔大一倍

* 5.align-items属性定义项目在交叉轴上如何对齐
1. flex-start：交叉轴的起点对齐
2. flex-end：交叉轴的终点对齐
3. center：交叉轴的中点对齐
4. baseline: 项目的第一行文字的基线对齐
5. stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度

* 6.align-content属性定义了多根轴线(多行)的对齐方式.如果项目只有一根轴线，该属性不起作用
1. flex-start：与交叉轴的起点对齐
2. flex-end：与交叉轴的终点对齐
3. center：与交叉轴的中点对齐
4. space-between：与交叉轴两端对齐，轴线之间的间隔平均分布
5. space-around：每根轴线两侧的间隔都相等.所以，轴线之间的间隔比轴线与边框的间隔大一倍
6. stretch（默认值）：轴线占满整个交叉轴