### 前端开发基础课之
# CSS基础

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

* CSS基本语法
* 初级CSS选择器
* 继承和优先级
* 控制文本样式
* 简单盒模型

---

### CSS的组成

```css
h1 {
    color: red;
    font-size: 16px;
}

/* 选择器：h1 */
/* 声明：color: red */
/* 属性：color */
/* 属性值：red */
/* 规则 */

```

---

### 代码风格

```css
h1 { color: red; font-size: 14px; }

h1 {
    color: red;
    font-size: 14px;
}
```

---

### 使用CSS

```markup
<!-- 外链 -->
<link rel="stylesheet" href="/path/to/style.css">

<!-- 嵌入 -->
<style type="text/css">
    li { margin: 0; list-style: none; }
    p { margin: 1em 0; }
</style>

<!-- 内联 -->
<p style="margin:1em 0">Example Content</p>
```

---

### 选择器

选择器用来从页面中选择元素，以给它们定义样式。

---

### 通配选择器

```css
/* 匹配所有元素 */
* {
    box-sizing: border-box;
}
```

---

### 标签选择器

```css
/* 匹配所有p元素 */
p {
    margin: 1em 0;
}
```

---

### ID选择器

```markup
<div id="example">Example Content</div>

<style type="text/css">
    /* 匹配id为example的元素
     * 注意：id的值在一个HTML中必须是唯一的
     */
    #example {
        font-size: 14px;
        line-height: 1.6;
    }
</style>
```

---

### 类选择器

```markup
<p class="warning">这是一条警告信息</p>
<!-- 可以给一个元素指定多个class，用空格隔开 -->
<div class="warning icon">这是另外一条警告信息</div>

<style type="text/css">
    .warning {color: orange;}
    .icon {background: url(warn.png) no-repeat 0 0;}
</style>
```

---

### 简单选择器

* 通配选择器
* 标签选择器
* ID选择器
* 类选择器

---

### 属性选择器

```markup
<label><i class="icon-user"></i>用户名：</label>
<input type="text" name="username" disabled>

<label><i class="icon-key"></i>密码：</label>
<input type="password" name="password" required>
```
```css
input[disabled] { background: #eee; color: #999; }
input[type="password"] { border-color: #999 }
[class^=icon-] { display: inline-block; vertical-align: middle; }
```

---

### 简单选择器的直接组合

```markup
<p class="warning">这是一条警告信息</p>
<div class="warning icon">这是另外一条警告信息</div>
```

```css
p.warning { color: orange; }
```

---

### 后代选择器

```markup
<ul class="menu">
    <li>item 1</li>
    <li>
        item 2
        <ul>
            <li>subitem 1</li>
            <li>subitem 1</li>
        </ul>
    </li>
    <li>item 3</li>
</ul>
```
```css
.menu li {  } /* 后代选择器 */
.menu>li {  } /* 亲子选择器 */
```

---

### 同时为一组选择器定义样式

```css
h1 { margin: 1em 0; color: #333; font-size: 16px; }
.richtext p { margin: 1em 0; color: #333; }
ul li { margin: 1em 0; color: #333; }
```
↓
```css
h1, .richitext p, ul li { margin: 1em 0; color: #333; }
h1 { font-size: 16px; }
```

---

### 伪类

```css
a:link { ... }      /* 未访问过的链接 */
a:visited { ... }   /* 已访问过的链接 */
a:hover { ... }     /* 鼠标移到链接上的样式 */
a:active { ... }    /* 鼠标在连接上按下时的样式 */
input:focus { ... } /* 获得焦点时的样式 */
```

---

## 优先级

---

### 哪条规则生效？

```markup
<h1 id="title" class="text">段落文字</h1>
```

```css
#title { font-size: 18px; }
h1.text { font-size: 14px; }
```

---

### 选择器的特异度(Specificity)

|       选择器            | 内联? | id个数 | (伪)类个数 | 标签个数 | 特异度 |
|-------------------------|----------|--------|--------------|----------|--------|
| #nav .list li a:link    | 0        | 1      | 2            | 2        | 0122   |
| .hd ul.links a          | 0        | 0      | 2            | 2        | 0022   |

<style>
.reveal table th { text-shadow:none; }
.reveal table th,
.reveal table td {
    font-size: 0.8em;
    padding: 0.5em 1em;
    white-space: nowrap
}
</style>

---

## 继承

---

### 继承

某些属性会自动继承其父元素的值，除非显式指定一个值

```markup
<p>
    This is a <em>test</em> of <strong>inherit</strong>.
</p>
<style type="text/css">
    p { color: #666; }
    em { color: red; }
</style>
```

---

## 文本样式

---

### font-family

* 使用逗号分隔的字体或字体系列名称
* 初始值由浏览器设置决定，可继承

---

```css
body {
    font-family: Arial, sans-serif;
}
h1 {
    font-family: "Microsoft Yahei", Arial, sans-serif;
}
```

---

### 字体系列

<ul>
    <li style="font-family:serif">
        Serif 衬线体
        <ul>
            <li>Georgia、宋体</li>
        </ul>
    </li>
    <li style="font-family:Helvetica,sans-serif">
        Sans-Serif 无衬线体
        <ul>
            <li>Arial、Helvetica、黑体、微软雅黑</li>
        </ul>
    </li>
    <li style="font-family:monospace">
        Monospace等宽字体
        <ul>
            <li>Consolas、Courier、宋体</li>
        </ul>
    </li>
</ul>

---

### font-size

* 定义文字的大小，可使用px、百分比、em等做单位
* 初始值为medium（由浏览器设置决定，一般16px），可继承

---

```css
.slide-page li {
    font-size:36px;
}
.richtext h4 {
    font-size: 125%;
}
.continue {
    font-size: 0.85em;
}
```

---

### 长度单位em

* 一般是相对于font-size的计算值的
* 用在font-size属性上时，是相对于父元素的font-size计算值

---

## line-height

* 每行文字所占用的高度
* 初始值为normal（具体值由浏览器决定），可继承
* 取值：<长度> | <数字> | <百分比>
* 段落文字一般取值1.4～1.8

---

```css
#header { line-height: 48px; }
#content .wrap { line-height: 1.6; }
```

---

```markup
<section>
    <h1>这是一个很长的标题啊</h1>
    <p>这是正文</p>
</section>
<style type="text/css">
    section {
        font-size: 12px;
        line-height: 1.5em;
    }
    h1 {
        font-size: 30px;
    }
</style>
```

---

<iframe src="http://jsbin.com/bodayisali/1/embed?html,output" width="100%" height="400"></iframe>

---

### font-style

* 定义文字以斜体还是正常方式显示
* normal为正常方式，italic为斜体
* 初始值为normal，可继承

---

### font-weight

* 定义文字的粗细程度
* 初始值为normal，可继承
* normal为正常粗细，bold为粗体

---

### font

```css
/* 斜体 粗细 大小/行高 字体*/
font: bold 14px/24px arial, sans-serif;
font: 12px/1.5 arial;
font: 14px serif;
```

---

### color

* 指定文字的颜色
* 初始值由浏览器决定（一般为黑色），可继承

---

### 颜色的表示：关键字

![color](img/essentials/named-color.png)

---

### RGB 和 RGBA

<iframe src="http://hex.colorrrs.com/" width="600" height="400"></iframe>

---

<iframe src="http://jsbin.com/bavokedohe/1/embed?output" width="660" height="480"></iframe>

---

### HSL 和 HSLA

* Hue: 色相(H)是色彩的基本属性,就是平常所说的颜色名称,如红色、黄色等。取值范围是0-360。
* Saturation: 饱和度(S)是指色彩的纯度,越高色彩越纯,低则逐渐变灰。取值范围0-100%。
* Lightness: 越高颜色越亮。取值范围是0-100%。
* 例如：hsl(0, 50%, 50%)、hsla(120, 50%, 30%, 0.5)

---

<iframe src="http://color.aurlien.net/" width="1000" height="600"></iframe>

---

### text-align

* 定义文本在容器内的对齐方式
* 初始值由HTML的dir属性决定，可继承
* 其它值：left | right | center | justify

---

<iframe src="http://jsbin.com/forabanena/1/embed?output" width="660" height="480"></iframe>

---

### text-decoration

* 定义了文本的一些装饰效果，比如下划线、删除线等
* 初始值为none，可继承
* 其它值：<span style="text-decoration:underline">underline</span> | <del>line-through</del> | <span style="text-decoration:overline">overline</span>

---

## 盒模型基础

---

### box model

![box model](img/essentials/box-model.png)

---

### width

* 指定content box宽度
* 百分数相对于父容器（包含块）的content box宽度

---

### height

* 指定content box高度
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

### border

* 边框
* border-width: 1px
* border-style: solid | dashed | dotted
* border-color: #f00
* border: 1px solid #ccc
* border-left-width: 4px

---

### 当四条边框颜色不同时

<iframe height='500' scrolling='no' src='//codepen.io/Tresva/embed/dxHsb/?height=500&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/Tresva/pen/dxHsb/'>Triangles with CSS explanation</a> by Henry Delro (<a href='http://codepen.io/Tresva'>@Tresva</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

@state: blue

<p style="font-size:6em"><i class="fa-comments"></i></p>

---

谢谢！

---



