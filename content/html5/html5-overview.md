## HTML5 概览

---

### HTML5的兴起

* XHTML2 vs. HTML5
* 移动Web

---

### HTML 5 设计思想

* 兼容已有内容
* 避免不必要的复杂性
* 解决现实的问题
* 优雅降级
* 尊重事实标准
* 用户 》开发者 》浏览器厂商 》标准制定者 》理论完美

---

### HTML5 有哪些东西？

<style>
.reveal table.html5 {
    margin: 0 auto;
}
.html5 img {
    width: 3em;
}
table.html5 td {
    text-align: center;
    padding: 1em;
}
</style>
<table class="html5">
    <tr>
        <td><img src="img/html5/semantics.svg?1"><br>语义化标签</td>
        <td><img src="img/html5/integration.svg?1"><br>性能和集成</td>
        <td><img src="img/html5/connectivity.svg?1"><br>连通性</td>
        <td><img src="img/html5/offline.svg?1"><br>离线与存储</td>
    </tr>
    <tr>
        <td><img src="img/html5/device.svg?1"><br>设备访问</td>
        <td><img src="img/html5/multimedia.svg?1"><br>多媒体</td>
        <td><img src="img/html5/css3.svg?1"><br>CSS3样式</td>
        <td><img src="img/html5/3d.svg?1"><br>图形与3D效果</td>
    </tr>
</table>

---

### [语义化](/demos/html5/semantics.html)

* 结构
    * section、article、nav、header、footer、aside、main
* 媒体
    * video、audio
* 表单
    * 新增表单验证和表单类型
* 其它
    * figure、data、time、progress

---

### 性能 & 集成

* [Web Workers](http://html5demos.com/worker)
* [拖放](http://html5demos.com/dnd-upload)
* XMLHttpRequest Level 2
* [History API](http://html5demos.com/history/second)
* requestAnimationFrame
* [全屏 API](http://davidwalsh.name/demo/fullscreen.php)

---

### 连通性

* Web Sockets
* [WebRTC](http://www.clicktorelease.com/code/optical-flow-webrtc/)

---

### 设备访问

* 使用地理位置定位
* 检测设备方向

---

### 离线 & 存储

* 离线资源：应用程序缓存
* 在线和离线事件
* localStorage
* IndexedDB
* 文件API

---

### CSS3样式

* 更灵活的布局方式
* 动画效果
* 阴影、圆角、边框等

---

### 多媒体

* 视频
* 音频

---

### 图形与3D效果

* Canvas绘图
* SVG矢量图
* WebGL

---
### 兼容性

* 特性支持
    * 降级方案
    * 兼容性速查 [Can I Use.com](http://caniuse.com/)
* bug
    * [StackOverflow](http://stackoverflow.com/)
    * [Android Bug List](https://code.google.com/p/android/issues/list)

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>
