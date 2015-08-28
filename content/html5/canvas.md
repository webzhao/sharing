## Canvas

---

### Canvas是什么？

* HTML5绘图元素
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

* 笛卡尔坐标
* 左上角为原点 (0,0)
* x轴向右，y轴向下

---

### 矩形

```javascript
var canvas = document.getElementById('canvas');
if (canvas.getContext) {
  var ctx = canvas.getContext('2d');

  ctx.fillRect(25,25,100,100);
  ctx.clearRect(45,45,60,60);
  ctx.strokeRect(50,50,50,50);
}
```

---

### 路径

* beginPath() 开始路径绘制
* moveTo() 移动到指定位置
* lineTo() 从当前位置绘制直线到指定位置
* closePath() 结束路径
* stroke() 描边
* fill() 填充

---

### 画个三角形

```javascript
var canvas = document.getElementById('canvas');
if (canvas.getContext){
  var ctx = canvas.getContext('2d');

  ctx.beginPath();
  ctx.moveTo(75,50);
  ctx.lineTo(100,75);
  ctx.lineTo(100,25);
  ctx.fill();
}
```

---

### 曲线

* arc(x, y, radius, startAngle, endAngle, anticlockwise) 圆弧
* quadraticCurveTo(cp1x, cp1y, x, y) 二次贝塞尔曲线
* bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y) 三次贝塞尔曲线

---

### 绘制心形

```javascript
var canvas = document.getElementById('canvas');
if (canvas.getContext){
  var ctx = canvas.getContext('2d');
  ctx.beginPath();
  ctx.moveTo(75,40);
  ctx.bezierCurveTo(75,37,70,25,50,25);
  ctx.bezierCurveTo(20,25,20,62.5,20,62.5);
  ctx.bezierCurveTo(20,80,40,102,75,120);
  ctx.bezierCurveTo(110,102,130,80,130,62.5);
  ctx.bezierCurveTo(130,62.5,130,25,100,25);
  ctx.bezierCurveTo(85,25,75,37,75,40);
  ctx.fill();
}
```
