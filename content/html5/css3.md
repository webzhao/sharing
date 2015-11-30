## CSS3新特性

---

* 高级选择器
* 圆角
* 阴影
* 背景缩放
* Flexbox布局
* 媒体查询和响应式设计

---

### 兄弟选择器

* E ~ F 一般兄弟选择器
* E + F 相邻兄弟选择器

---

### 兄弟选择器

<iframe height='325' scrolling='no' src='http://codepen.io/webzhao/embed/pJRaEM/?height=325&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/pJRaEM/'>pJRaEM</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### :checked与兄弟选择器结合

<iframe height='286' scrolling='no' src='http://codepen.io/webzhao/embed/mJRXWL/?height=286&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/mJRXWL/'>Sibling Selectors</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

### 结构伪类

* :first-child
* :last-child
* :nth-child()

---

<iframe src="http://nthmaster.com/" width="100%" height="2000" frameborder="no"></iframe>

### :not() 否定伪类

<iframe height='322' scrolling='no' src='http://codepen.io/webzhao/embed/OVWQgB/?height=322&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/OVWQgB/'>OVWQgB</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### border-radius 圆角

* border-radius: 5px
* 可以指定四个方向
* 可以使用百分数

---

<iframe height='371' scrolling='no' src='http://codepen.io/webzhao/embed/qdRxVj/?height=371&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/webzhao/pen/qdRxVj/'>qdRxVj</a> by webzhao (<a href='http://codepen.io/webzhao'>@webzhao</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### 阴影

<iframe src="http://silviarebelo.com/demos/boxgenerator/" width="100%" height="1000" frameborder="no"></iframe>

---

### background-size 背景缩放

<iframe height='836' scrolling='no' src='http://codepen.io/herihehe/embed/aLwGt/?height=836&theme-id=0&default-tab=result' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/herihehe/pen/aLwGt/'>CSS Background Size</a> by Heri Setiawan (<a href='http://codepen.io/herihehe'>@herihehe</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

---

### Flexbox可控制容器内的子元素：

* 水平或垂直排成一行
* 控制子元素对齐方式
* 控制子元素的宽度/高度
* 控制子元素显示顺序
* 控制子元素是否折行

---

Flexbox是W3C布局方面标准中的*终极武器*

---

![axis](img/css3/axis.png)

---

[Flexbox Demo](http://dabblet.com/gist/95e5b65622aeae4d031d)

---

### 响应式设计是什么？

一种能在不同屏幕大小的设备上都能提供优秀的浏览体验的网页设计方案

---


### media query

针对不同的屏幕，应用不同的样式

```markup
<link rel="stylesheet" href="m.css"
	media="screen and (max-width: 480px)">
```

```css
@media screen and (min-width: 480px) {
	.selector {  … }
}
```

---

### 可以查询的media

* width
* height
* device-width
* device-height
* device-pixel-ratio
* orientation

---


@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>
