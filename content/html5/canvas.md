## Canvas

---

### Canvas是什么？

* HTML5新增的一个绘图元素
* 使用JavaScript控制图形绘制
* 可绘制路径、矩形、圆形、字符以及添加图像等

---

### 获取Canvas对象

```markup
<canvas id="test" width="200" height="100"></canvas>
<script>
    var c = document.getElementById("test");
    var cxt = c.getContext("2d");
    cxt.fillStyle = "#FF0000";
    cxt.fillRect(0, 0, 150, 75);
</script>
```

---

### 坐标系

<img src="img/html5/axis.jpg">

---

### 矩形

* cxt.fillRect(x, y, w, h);
* cxt.clearRect(x, y, w, h);
* cxt.strokeRect(x, y, w, h);

---

<iframe src="http://jsbin.com/vamewa/1/embed?js,output" frameborder="0" width="800" height="600"></iframe>

---

### 路径

* beginPath() 开始路径绘制
* moveTo(x, y) 移动到指定位置
* lineTo(x, y) 从当前位置绘制直线到指定位置
* closePath() 结束路径
* stroke() 描边
* fill() 填充

---

### 画个三角形

<iframe src="http://jsbin.com/tozire/1/embed?js,output" frameborder="0" width="800" height="600"></iframe>

---

### 曲线

```javascript
// 圆弧
arc(x, y, radius, startAngle, endAngle, anticlockwise)
// 二次贝塞尔曲线
quadraticCurveTo(cp1x, cp1y, x, y)
// 三次贝塞尔曲线
bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
```

---

### 贝塞尔曲线

<img src="https://upload.wikimedia.org/wikipedia/commons/3/3d/B%C3%A9zier_2_big.gif" width="800">

---

### 二阶贝塞尔曲线

<img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/B%C3%A9zier_2_big.svg" style="background:#fff" width="800">

---

### 三阶贝塞尔曲线

<img src="https://upload.wikimedia.org/wikipedia/commons/d/db/B%C3%A9zier_3_big.gif" width="800">


---

### 绘制心形

<iframe src="http://jsbin.com/guwitu/1/embed?js,output" frameborder="0" width="800" height="600"></iframe>

---

### 显示文字

* fillText(text, x, y, maxWidth)
* strokeText(text, x, y, maxWidth)
* 文本样式控制
    * font = "48px Arial"
    * textAlign = "left"
* measureText(text)

---

### Demo

<iframe src="http://jsbin.com/keguqu/2/embed?js,output" frameborder="0" width="800" height="600"></iframe>

---

### 使用图片

```javascript
drawImage(
    image,
    sx, sy, sWidth, sHeight, // 原图
    dx, dy, dWidth, dHeight  // 绘制到Canvas
)
```

---

### Demo

<iframe src="http://jsbin.com/kadami/8/embed?js,output" frameborder="0" width="800" height="600"></iframe>

---

### 变换

* 对画布进行变换
    * translate(x, y)
    * scale(x, y)
    * rotate(angle)
* save()
* restore()

---

<iframe src="http://jsbin.com/hiqoto/3/embed?js,output" frameborder="0" width="800" height="600"></iframe>

---

### 动画

<iframe src="http://jsbin.com/tilawuv/2/embed?js,output" frameborder="0" width="800" height="600"></iframe>

---

### 事件绑定

* 只能绑定在canvas元素上
* 通过事件发生的坐标，判断发生在哪个图形上

---

### Canvas 使用场景

* 对性能要求
* 图形交互较少

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>



