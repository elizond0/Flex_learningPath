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
2. wrap：向下换行,第一行在上方
3. wrap-reverse：向上换行,第一行在下方

* 3.flex-flow属性是flex-direction属性和flex-wrap属性的简写形式,默认值为row nowrap

* 4.justify-content属性定义了项目在主轴上的对齐方式
1. flex-start（默认值）：左对齐
2. flex-end：右对齐
3. center： 居中
4. space-between：两端对齐,项目之间的间隔都相等
5. space-around：每个项目两侧的间隔相等.所以,项目之间的间隔比项目与边框的间隔大一倍

* 5.align-items属性定义项目在交叉轴上如何对齐
1. flex-start：交叉轴的起点对齐
2. flex-end：交叉轴的终点对齐
3. center：交叉轴的中点对齐
4. baseline: 项目的第一行文字的基线对齐
5. stretch（默认值）：如果项目未设置高度或设为auto,将占满整个容器的高度

* 6.align-content属性定义了多根轴线(多行)的对齐方式.如果项目只有一根轴线,该属性不起作用
1. flex-start：与交叉轴的起点对齐
2. flex-end：与交叉轴的终点对齐
3. center：与交叉轴的中点对齐
4. space-between：与交叉轴两端对齐,轴线之间的间隔平均分布
5. space-around：每根轴线两侧的间隔都相等.所以,轴线之间的间隔比轴线与边框的间隔大一倍
6. stretch（默认值）：轴线占满整个交叉轴

## 4.项目的属性

* 1.order属性定义项目的排列顺序.数值越小,排列越靠前,可以负数,默认为0

* 2.flex-grow属性定义项目的放大比例,默认为0,即如果存在剩余空间,也不放大
1. 如果所有项目的flex-grow属性都为1,则它们将等分剩余空间（如果有的话）
2. 如果一个项目的flex-grow属性为2,其他项目都为1,则前者占据的剩余空间将比其他项多一倍

* 3.flex-shrink属性定义了项目的缩小比例,默认为1,即如果空间不足,该项目将缩小
1. 如果所有项目的flex-shrink属性都为1,当空间不足时,都将等比例缩小
2. 如果一个项目的flex-shrink属性为0,其他项目都为1,则空间不足时,前者不缩小

* 4.flex-basis属性定义了在分配多余空间之前,项目占据的主轴空间（main size）
1. 浏览器根据这个属性,计算主轴是否有多余空间.它的默认值为auto,即项目的本来大小
2. 它可以设为跟width或height属性一样的值（比如350px）,则项目将占据固定空间

* 5.flex属性是flex-grow, flex-shrink 和 flex-basis的简写,默认值为0 1 auto.后两个属性可选
1. 该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto).
2. 建议优先使用这个属性,而不是单独写三个分离的属性,因为浏览器会推算相关值.

* 6.align-self属性允许单个项目有与其他项目不一样的对齐方式,可覆盖align-items属性(容器的属性,用于定义项目在交叉轴上如何对齐).
1. 默认值为auto,表示继承父元素的align-items属性,如果没有父元素,则等同于stretch(垂直拉伸)
2. 该属性可能取6个值,除了auto,其他都与align-items属性完全一致,(align-self: auto | flex-start | flex-end | center | baseline | stretch)

## 5.demo-骰子布局

* 详细代码见./05.html

## 6.demo-网格布局

1. 基本网格布局:最简单的网格布局，就是平均分布。在容器里面平均分配空间，跟上面的骰子布局很像，但是需要设置项目的自动缩放。
2. 百分比布局:某个网格的宽度为固定的百分比，其余网格平均分配剩余的空间。

* 详细代码见./06.html

## 7.demo-圣杯布局

* 圣杯布局（Holy Grail Layout）指的是一种最常见的网站布局。页面从上到下，分成三个部分：头部（header），躯干（body），尾部（footer）。其中躯干又水平分成三栏，从左到右为：导航、主栏、副栏。

## 8.输入框的布局

* 在输入框的前方添加提示，后方添加按钮,flex布局可以轻松解决

## 9.悬挂式布局

* 主栏的左侧或右侧，需要添加一个图片栏