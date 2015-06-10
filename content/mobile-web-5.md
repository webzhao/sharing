## 高性能动画

---

### transition（过渡）

* 从一个状态到另一个状态的过渡
* 动画的意义：告诉用户发生了什么

---

### 指定transition

* 什么属性发生变化时需要过渡
* 过渡持续多长时间
* 速度变化是什么样
* 是否有延迟

---

### transition

transition: all 1s linear 0.5s;
transition: width 1s linear, height 1s linear 1s;

http://jsbin.com/zivoji

---

transition-property

---

transition-duration: 

---

transition-timing-function:

http://cubic-bezier.com/

---

transition-delay

---

### transitionend 事件

---

### 练习：翻页应用

页面切换放手后的动画

---

### animation

动画可以实现更复杂的样式变化效果

---

### 使用CSS animation

* 定义关键帧
* 指定动画行为

---

### demo

http://output.jsbin.com/yazaqe

---

## transform 变形

对元素进行平移、旋转、缩放和扭曲
transform: translate(10px, 20px) scale(0.5);

---

### translate 平移

* translate(10px, 10px)
* translate3d(10px, 10px, 100px)
* translateX(10px)
* translateY(500px)

---

### rotate

* rotate(30deg)
* transform-origin

---

### 3D

* translate3d(10px, 0, 0)
* rotateX() 或 rotateY();

---

## 高性能动画

---

### 浏览器渲染过程

---

```markup
<html>
    <body>
        <h1 style="display:none">Article</h1>
        <p>Hi, I'm Banana</p>
        <div>
            <img src="example.png" alt="" />
        </div>
    </body>
</html>
```

---

### DOM

---

### DOM + CSS = Render Tree

---

### layout 布局

---

### 绘制

---

### GPU合成

上传到GPU，显示到屏幕

---

### 浏览器渲染

* 三个阶段：Layout、Paint、Composite
* 修改不同的CSS属性会从不同阶段开始重新渲染
* 重新开始得越靠前，花费时间越多

---

### 硬件加速

* 尽可能将渲染任务交给最后一个阶段，即GPU合成时去完成。避免layout和paint
* Layer生成
    * 3D的transform
    * animation

---

### 硬件加速的动画为什么快？

* Layer会被GPU缓存
* 对于不需要重绘的动画，CPU只需告诉GPU位置、缩放、透明度等信息即可

---

### 练习：使用硬件加速重写翻页

---

### 滚动

* 减少在每一帧的操作，尤其是引发重排、重绘的操作及复杂计算
* 适当降低touchmove等事件的调用频率

---

### demo

滚动时，显示当前区块的标题(对比demo)

---

### 休息

