## 响应式设计

---

### 响应式设计是什么？

一种能在不同屏幕大小的设备上都能提供优秀的浏览体验的网页设计方案

---

### 实际应用中的响应式设计

* [Microsoft](http://www.microsoft.com/)
* [Baidu](https://www.baidu.com/)

---

### 响应式设计中的图片

* 大图随容器自动缩放，保持高宽比
* max-width: 100%
* [Demo](http://output.jsbin.com/hifubu)

---

### 背景图片

* background-size: cover
* [Demo](http://www.h5shuo.com/pc)

---

### 练习：

一栏定宽，另一栏自适应

---

### 多种实现方式

* 绝对定位与margin
* float与BFC
* 模拟table
* flex布局

---

### flex box详解

http://flexboxin5.com/

---

### flex box新旧语法

http://pleeease.io/play/

---

### 练习

导航栏布局，多栏平均分配

---

### 多种实现方式

* float + 百分比宽度
* 模拟table
* flex布局

---

### 练习

网格布局，自动换行

---

### 实现方案

* float + 百分比宽度
* inline-block + justify
* flex

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

### 练习

使用media query实现菜单自动折行

---

### JS的自适应

* match media
* orientationChange事件

---

### 高度的响应（100%高）

* height: 100%生效条件
	* 父容器高度不依赖于它的高度
* html, body { height: 100% }

---

### 练习：几页全屏应用

[Demo](http://output.jsbin.com/dabuya)


