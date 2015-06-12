## Touch事件

---

### 鼠标事件 vs. touch事件

* 鼠标事件
	- mousedown
	- mousemove
	- mouseup
	- click

* touch事件
	- touchstart
	- touchmove
	- touchend
	- touchcancel

---

### 兼容鼠标事件

![touch](img/mobile/touch.png)

---

### 事件触发顺序

[代码](http://jsbin.com/qewiya/1/edit?html,js,output)

---

![http://output.jsbin.com/qewiya](http://qr.liantu.com/api.php?w=500&text=http://output.jsbin.com/qewiya)

---

### 为什么click会有延迟？

* 移动浏览器双击缩放页面
* 触摸一下之后要判断是否有第二下

---

### 使用tap事件

* zepto
* fastclick
* hammer

---

### 事件穿透

[代码](http://jsbin.com/nidate/4/edit)

---

![http://output.jsbin.com/nidate/4](http://qr.liantu.com/api.php?w=500&text=http://output.jsbin.com/nidate/4)

---

### TouchEvent对象

* touches
* targetTouches
* changedTouches

---

### Touch对象

* clientX
* clientY
* pageX
* pageY

---

### 练习

全屏网页拖动 

---

### touchcancel事件

* 被系统通知、应用切换等中断
* 超出边界


