## 动画效果


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

```css
transition: all 1s linear 0.5s;
transition: width 1s linear, height 1s linear 1s;
```

[代码](http://jsbin.com/zivoji)

---

### transition-property

* 指定哪些属性是需要过渡的
* 可以指定多个用逗号隔开

---

### transition-duration

* 指定过渡时间
* 可以指定多个，和属性对应

---

### transition-timing-function

* 指定过渡的过程中，属性值变化的快慢
* [常见时间函数](http://cubic-bezier.com)

---

### transition-delay

* 指定过渡要延迟多久才开始
* 可以指定过个，和属性对应

---

### transitionend 事件

* 在JavaScript中，可以监听transitionend事件来得知过渡完成
* 注意：避免使用setTimeout来做动画完成后的事

---

### 练习：翻页应用

页面切换放手后的动画

---

### animation

* 动画可以实现更复杂的样式变化效果

---

### 使用CSS animation

* 定义关键帧
* 指定动画行为

---

### demo

[代码](http://jsbin.com/yazaqe/edit?html,output)

---

### transform 变形

* 对元素进行变形
    - 平移
    - 旋转
    - 缩放
    - 扭曲
* 例如
    - transform: translate(10px, 20px) scale(0.5);

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
