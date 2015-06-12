## Viewport与分辨率

---

### ViewPort（视口）

* 视觉视口（Visual Viewport）
* 布局视口（Layout Viewport）

---

![visual viewport](img/mobile/visual-viewport.png)

---

![layout viewport](img/mobile/layout-viewport.png)

---

### 理解视口

* 视觉视口
	- 窗户
	- 通过视口看页面
* 布局视口
	- 风景的大小
	- 决定页面布局的容器

---

### 默认布局视口

```markup
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>默认Viewport</title>
</head>
<body>
  <p>如果不设置Viewport，默认的布局视口和视觉视口是多少呢？</p>
   <dl>
     <dt>视觉视口：</dt>
     <dd id="visual_viewport"></dd>
     <dt>布局视口：</dt>
     <dd id="layout_viewport"></dd>
   </dl>
  <script>
    document.getElementById('visual_viewport').innerHTML = 
		window.innerWidth;
    document.getElementById('layout_viewport').innerHTML = 
		document.documentElement.clientWidth;
  </script>
</body>
</html>
```

---

![http://output.jsbin.com/rivubo](http://qr.liantu.com/api.php?w=500&text=http://output.jsbin.com/rivubo)

---

### 布局视口设置

```markup
<!-- 固定视口宽度 -->
<meta name="viewport" content="width=320">

<!-- 将视口宽度设置为设备宽度 -->
<meta name="viewport" content="width=device-width">
```

---

### 练习

设置viewport

---

### 缩放会改变布局视口或视觉视口吗？

<!--<iframe src="http://jsbin.com/zacaza/2/embed?html,js" width="800" height="500"></iframe>-->
[代码](http://jsbin.com/zacaza/2/embed?html,js)

---

![http://output.jsbin.com/zacaza/2](http://qr.liantu.com/api.php?w=500&text=http://output.jsbin.com/zacaza/2)

---

### 缩放

* 不改变布局视口
* 风景前后移动

---

![scale](img/mobile/scale.png)

---

### 设置缩放

```markup
<!-- 设置默认缩放为1 -->
<meta name="viewport" content="width=device-width;initial-scale=1;">

<!-- 设置最大缩放为2，最小为1 -->
<meta name="viewport" content="width=device-width;minimum-scale=1;maximum-scale=2">

<!-- 禁止用户缩放 -->
<meta name="viewport" content="width=device-width;initial-scale=1;user-scalable=no">
```

---

## 物理像素和CSS像素

---

### 物理像素

* 一个物理像素是显示屏能显示的最小物理单元
* 物理像素高，屏幕效果比较细腻

---

### 如果我们在CSS中指定的是物理像素

* 传统的PC网站显示文字太小
* 同样的字体，在不同物理分辨率的手机上显示差异很大

---

<img alt="css-pixel" src="img/mobile/css-pixel.png" class="dark">

---

### CSS像素

* 用4个点的物理像素抽象成一个CSS像素
* 几个物理长度等于一个CSS像素由手机厂商决定

---

### Device Pixel Ratio

* 设备像素比，简称DPR
* 1个CSS像素的长度 = 1个物理像素的长度 X DPR

---

### 常见手机分辨率

<table width="700" style="margin:auto;line-height:2">
    <thead>
        <tr>
            <th>机型</th>
            <th>物理分辨率</th>
            <th>CSS分辨率</th>
            <th>DPR</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>小米手机 3</td>
            <td>1080 X 1920</td>
            <td>360 X 640</td>
            <td>3</td>
        </tr>
        <tr>
            <td>三星Note II</td>
            <td>720 X 1280</td>
            <td>360 X 640</td>
            <td>2</td>
        </tr>
        <tr>
            <td>iPhone 5S</td>
            <td>640 X 1136</td>
            <td>320 X 568</td>
            <td>2</td>
        </tr>
    </tbody>
</table>

---

### 视网膜（Retina）屏

dpr >=2 高分辨率屏，retina屏幕

---

### Retina屏幕上的图片显示

[代码](http://jsbin.com/ruzaro/1/edit?html,output)

---

![http://output.jsbin.com/ruzaro](http://qr.liantu.com/api.php?w=500&text=http://output.jsbin.com/ruzaro)

---

### 兼容retina屏幕

将图片中每个像素和物理像素对应起来!

---

### 图片

* 使用@2x图片
* 设置img的CSS宽度和高度

---

### 背景图片

* 使用@2x图片
* 使用background-size设置图片大小

---

### 练习

让图片显示的更清楚！

---

### 其它选项

* 使用SVG图片
* 使用CSS模拟一些形状
  * 形状
  * 圆角
  * 阴影
* 使用字体图标（Web font）

