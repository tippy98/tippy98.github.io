---
title: 【CSS】CSS 总结记记录——布局实现篇
date: 2020-09-12 23:23:19
tags: 
  - CSS
categories: 
  - CSS
  - CSS 总结
---

> CSS 总结记录的第一弹——布局实现篇
> 开坑待填，Notion 写了一部分了...
> CSS 可以说一直是我的大弱项了，自从工作中认知到了这点后，也一直在补，所以博客的第一弹是关于 CSS 的，希望能给大家一点启发......

<!-- more -->

## Layout——超经典的两列布局

> 两列布局可以说超经典了，以前我的错误学习方法就是靠背，因为其实在百度上一搜《两列布局》/ 《布局大全》就是一大堆的代码，以前想着能用就行，就Ctrl + C/V 大法了，但是你会发现你用了就忘记了。但是在新一轮补知识的时候，我发现这东西是有根据的，必须根据各种模型的表现形式，让布局在脑海里可控。

### div 布局实现两列布局

#### 正常实现

​	说到 div，它就是一块级元素，使用它进行布局主要是利用了它[文档流](https://juejin.im/post/6844903854304133127)的特性，**块级元素独占一行，从上往下流动**，但是 div 只有一列，要实现两列布局需要用一个[脱离文档流](https://juejin.im/post/6844903854304133127)的元素，盖在 div 的上面，这时候就很容易想到了position和float脱离文档流方案：

![](https://photoeditor.oss-cn-chengdu.aliyuncs.com/%E5%9B%BE%E7%89%871.png)

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="css,result" data-user="kiznaiver1998-the-sans" data-slug-hash="dyMKbxa" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="dyMKbxa">
  <span>See the Pen <a href="https://codepen.io/kiznaiver1998-the-sans/pen/dyMKbxa">
  dyMKbxa</a> by Kiznaiver1998 (<a href="https://codepen.io/kiznaiver1998-the-sans">@kiznaiver1998-the-sans</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

最后，只需要在下面的块级元素利用[盒模型](https://juejin.im/post/6844904151411900430#heading-0)的 `margin` 进行占位，就实现了两列布局。

***

#### 思考1——inline-block

​	对于文档流，我们很自然会思考另外一个更符合需求的特性——内联元素从左到右流动，到达最右边才会进行换行，而inline-block又为内联元素提供了盒模型的表现形式

***

#### 思考2——BFC自适应



### Flex 实现两列布局



### table & grid 实现两列布局



## Layout——超经典的三列布局



## 尾声&安利

#### Flex 教程安利

[flex 学习游戏——送青蛙回家](http://flexboxfroggy.com/#zh-cn)：这个网址侧重教你如何使用。

[flex 学习教程——阮一峰博客](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)：这个网址侧重原理，理解原理后就能在脑海里模拟出布局的行为了。

[flex 教程实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)：这个很适合在看完前两个后当做作业，自己实现一遍。

#### 布局教程安利

[nec，更好的 CSS 方案](http://nec.netease.com/)

To be continued......