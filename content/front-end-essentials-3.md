### 前端开发基础课之
# CSS进阶

赵文博@奇舞团

---

## whoami

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

@fragment

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

<iframe src="http://jsbin.com/ciqunayifi/1/embed?html,css" width="660" height="480"></iframe>

---

### border

* 边框
* border-width: 1px
* border-style: solid | dashed | dotted
* border-color: #f00
* border: 1px solid #ccc
* border-left-width: 4px

---

### 当四条边框颜色不同时

<iframe height='500' scrolling='no' src='http://codepen.io/Tresva/embed/dxHsb/?height=500&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>

---

### 改变盒模型计算方式

* box-sizing
    * content-box 默认值
    * border-box 宽度值包含border

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

### 块级*框*(Block)

* 每个块级元素生成一个块级框来包含其子框
* 块级框参与*块级格式化上下文*

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

### 练习



---

### 块级格式化上下文

* Block Formatting Contexts（BFC）
* 在BFC中，框会从包含块的顶部开始，从上到下摆放
* BFC的创建
    * 浮动框
    * 绝对定位框
    * 非块级的块容器(inline-block)
    * overflow属性非visible的块框



---


---


---


---


---


---


---


---


---


---
