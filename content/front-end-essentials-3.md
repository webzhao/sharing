### 前端开发基础课之
# CSS进阶

赵文博@奇舞团

---

### whoami

* **赵文博**
* 奇舞团前端工程师
* 负责360商业产品前端
<p style="font-size:120%;margin-top:0.5em">
    <a href="https://github.com/webzhao" target="_blank" title="Github"><i class="fa fa-github"></i></a>&nbsp;
    <a href="http://www.flickr.com/photos/53827079@N06/" target="_blank" title="Flickr"><i class="fa-flickr"></i></a>&nbsp;
    <a href="https://twitter.com/webzhao" target="_blank" title="Twitter"><i class="fa-twitter"></i></a>&nbsp;
    <a href="http://cn.linkedin.com/pub/wenbo-zhao/29/7b1/514" target="_blank" title="Linkedin"><i class="fa-linkedin"></i></a>&nbsp;
</p>

---

### 这节课讲什么？

* 盒模型
* 视觉格式化模型

---

## 盒模型基础

---

### box model

![box model](img/essentials/box-model.png)

---

### width

* 指定*content box*宽度
* 百分数相对于父容器（包含块）的content box宽度

---

### height

* 指定*content box*高度
* 百分数相对于父容器（包含块）的content box高度
* 只有当包含块的高度不依赖该元素时，百分比高度才生效

---

### padding

* 内边距
* padding-top、padding-right、padding-bottom、padding-left
* 缩写：padding

---

### margin

* 外边距
* margin-top、margin-right、margin-bottom、margin-left
* 缩写：margin

---

### margin折叠

<iframe height='388' scrolling='no' src='http://codepen.io/webzhao/embed/EjZWqV/?height=388&theme-id=0&default-tab=html' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/EjZWqV/'>EjZWqV</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### margin可以为负值吗？

---

### border

* 边框
* border-width: 1px
* border-style: solid | dashed | dotted
* border-color: #f00
* border: 1px solid #ccc
* border-left-width: 4px

---

### 练习

<iframe height='337' scrolling='no' src='http://codepen.io/webzhao/embed/YXNVra/?height=337&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/YXNVra/'>YXNVra</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### 当四条边框颜色不同时

<iframe height='372' scrolling='no' src='http://codepen.io/webzhao/embed/XbpRzj/?height=372&theme-id=0&default-tab=css' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/XbpRzj/'>Triangles with CSS explanation</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### 练习

使用CSS制作一个<em style="font-size:2em">▼</em>

---

### 改变盒模型计算方式

<iframe height='338' scrolling='no' src='http://codepen.io/webzhao/embed/XbpRqN/?height=338&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/XbpRqN/'>XbpRqN</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

## 浏览器如何排版的

视觉格式化模型

---

### 先来了解几个概念

---

### 视口（Viewport）

* 浏览器的可视区域
* 用户通过视口查看网页内容（透过窗户看风景）

---

### 块级*元素*(Block-level Elements)

* 会被格式化成块状的元素
* 例如p、div、section等
* 将display设置为block、list-item、table使元素变为块级

---

### 行级元素

* 不会为其内容生成块级框
* 让其内容分布在多行中
* display设置为inline, inline-block, inline-table使元素变为行级

---

### 行级 vs. 块级

<iframe src="http://jsbin.com/joramogage/1/embed?html,css,output" width="660" height="480"></iframe>

---

### display属性

* block 块级
* inline 行级
* inline-block 元素本身是行级，为其内容生成块级框
* none 在排版时将元素忽略

---

## 休息

---

### Generated Content

* ::before和::after
* content
* 伪类 vs. 伪元素

---


### 定位方案

* 正常流
* 浮动
* 绝对定位

---

### 排版流（文档流）

* 除根元素、浮动元素和绝对定位元素外， 其它元素都在排版流之内
* 而根元素、 浮动和绝对定位的元素会脱离文档流
* 在排版流中块级元素独占一行；行级元素可以水平并排摆放

---

### 浮动（float）

* 浮动可以实现将多个块级框并排显示
* 浮动元素从排版流中脱离，被漂浮在容器左边或右边
* 浮动元素不会影响其后面的块级框
* 但是浮动元素后面的行级元素会避开浮动元素

---

### 浮动

<iframe height='360' scrolling='no' src='http://codepen.io/webzhao/embed/pJRPBy/?height=360&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/pJRPBy/'>pJRPBy</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### clear

* 指定元素哪一边不能与之前的浮动框相邻
* clear: left | right | both

---

### 清除浮动的方法

* clear (Generated content)
* Block Formatting Contexts（BFC）

---

### 块级格式化上下文

* 在BFC中，框会从包含块的顶部开始，从上到下摆放
* BFC内的浮动不会影响到BFC外部的元素
* BFC的高度会包含其内的浮动元素
* BFC不会和浮动元素重叠

---

### BFC的创建

* 浮动框
* 绝对定位框
* 非块级的块容器(inline-block)
* overflow属性非visible的块框

---

### BFC的作用

* 清除浮动
* 防止margin折叠
* 双栏布局

---

### 练习

<iframe height='441' scrolling='no' src='http://codepen.io/webzhao/embed/rVjwLG/?height=441&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/rVjwLG/'>rVjwLG</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### position

* static，非定位，默认值
* relative，相对定位（相对自己）
* absolute，绝对定位，相对非static父级元素定位

---

### 练习

<iframe height='446' scrolling='no' src='http://codepen.io/webzhao/embed/LVxLxg/?height=446&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/LVxLxg/'>LVxLxg</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### 自动计算

* 这些值都可以不指定
    * top
    * left
    * right
    * bottom
    * width
    * height
* 如果冲突了怎么办?
* [示例](http://codepen.io/webzhao/pen/EjZwEW?editors=110)

---

### position:fixed

* 相对于Viewport定位
* 不会随页面滚动发生位置变化

---

### 练习

做一个图标 <span class="fa fa-home"></span>

---

### 堆叠层次

* z-index，整数
* z-index大的一定在上面吗？

---

### z-index的大小与层次

<iframe height='504' scrolling='no' src='http://codepen.io/webzhao/embed/eNgGyZ/?height=504&theme-id=0&default-tab=html' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/eNgGyZ/'>eNgGyZ</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### 堆叠层次

* z-index指定元素在所属堆叠上下文中的层次
* 堆叠上下文的形成
    * z-index值为非auto的定位元素

---

### 绘制顺序

* 每个堆叠上下文中， 从下到上的顺序显示：
    * background, boder
    * z-index为负值的定位元素
    * 正常块级元素
    * 浮动
    * 行级元素
    * z-index为0
    * z-index为正数

---

### 练习

<iframe height='392' scrolling='no' src='http://codepen.io/webzhao/embed/EjZwRW/?height=392&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/EjZwRW/'>EjZwRW</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---


谢谢
