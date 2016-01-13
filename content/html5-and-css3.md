## Doing it the HTML 5 way!

<style>
.reveal .run-btn {display:none}
.box-model {width: 10em;height: 6em;background:#09c;box-shadow:#f80 0 0 0px 2em, #690 0 0 0 4em, #999 0 0 0 6em; margin: 6em auto 7.5em auto!important}
.box-model p {line-height: 2em; position: relative; top: -6em}
</style>

### 赵文博

---

## whoami

* **赵文博**
* 奇舞团前端工程师
* 负责 360 商业产品前端
<p style="font-size:120%;margin-top:0.5em">
    <a href="https://github.com/webzhao" target="_blank" title="Github"><i class="fa fa-github"></i></a>&nbsp;
    <a href="http://www.flickr.com/photos/53827079@N06/" target="_blank" title="Flickr"><i class="fa-flickr"></i></a>&nbsp;
    <a href="https://twitter.com/webzhao" target="_blank" title="Twitter"><i class="fa-twitter"></i></a>&nbsp;
    <a href="http://cn.linkedin.com/pub/wenbo-zhao/29/7b1/514" target="_blank" title="Linkedin"><i class="fa-linkedin"></i></a>&nbsp;
</p>

---

### Why HTML 5 ?

---

### HTML 5 设计思想

* 兼容已有内容
* 避免不必要的复杂性
* 解决现实的问题
* 优雅降级
* 尊重事实标准
* 用户 》开发者 》浏览器厂商 》标准制定者 》理论完美

---

## HTML 5 有什么

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

## Writing markups, the HTML 5 way

---

### Old days

* `<div class="header"></div>`
* `<span class="date">2016-01-12</span>`
* `<input type="text" class="date-input">`

---

### 语义标签

* 结构
    * section、article、nav、header、footer、aside、main
* 媒体
    * video、audio
* 表单
    * [新增表单验证和表单类型](http://html5doctor.com/demos/forms/forms-example.html)
* 其它
    * figure、figcaption、data、time、progress

---

### MathML

<link href="https://developer.cdn.mozilla.net/static/styles/libs/mathml.css" rel="stylesheet" type="text/css">

<math>
    <mtable>
    <mtr>
    <mrow>
        <msup>
            <mi> a </mi>
            <mn>2</mn>
        </msup>
        <mo> + </mo>
        <msup>
            <mi> b </mi>
            <mn>2</mn>
        </msup>
        <mo> = </mo>
        <msup>
            <mi> c </mi>
            <mn>2</mn>
        </msup>
    </mrow>
</mtr>
    <mtr>
      <mrow>
        <mo>(</mo>
        <mfrac>
          <msup>
            <mo>∂</mo>
            <mn>2</mn>
          </msup>
          <mrow>
            <mo>∂</mo>
            <msup>
              <mi>x</mi>
              <mn>2</mn>
            </msup>
          </mrow>
        </mfrac>
        <mo>+</mo>
        <mfrac>
          <msup>
            <mo>∂</mo>
            <mn>2</mn>
          </msup>
          <mrow>
            <mo>∂</mo>
            <msup>
              <mi>y</mi>
              <mn>2</mn>
            </msup>
          </mrow>
        </mfrac>
        <mo>)</mo>
      </mrow>
      <msup>
        <mrow>
          <mo minsize="150%">|</mo>
          <mi>φ <!-- \varphi --></mi>
          <mo stretchy="false">(</mo>
          <mi>x</mi>
          <mo>+</mo>
          <mi mathvariant="normal">i</mi>
          <mi>y</mi>
          <mo stretchy="false">)</mo>
          <mo minsize="150%">|</mo>
        </mrow>
        <mn>2</mn>
      </msup>
      <mo>=</mo>
      <mn>0</mn>
    </mtr>
    </mtable>
</math>

---

## Inline frames, the HTML 5 way

---

### Old days

* iframe 的安全性无法保证
* iframe 内无法使用父页面样式

---

### [iframe](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)

* sandbox: 限制 iframe 页面的行为
* seamless: 让 iframe 使用父页面样式

---

## Communication, the HTML 5 way

---

### Old days

* 页面跨域通信
    * `window.name`
* 及时获取服务端信息
    * Ajax 轮询
    * 长连接

---

### 跨页面通信

```javascript
var popup = window.open('some url');
popup.onload = function() {
    popup.postMessage('hello', 'http://example.com');
}

// in the popup page
window.on('message', function(e) {
    console.log(e.data);
});

```

---

### Server Sent Events

```javascript
// 建立连接
var evtSource = new EventSource("ssedemo.php");

// 监听服务器事件
evtSource.onmessage = function(e) {
    console.log(e.data);
}
```

---


### Web Socket

* 在网络浏览器和服务器之间建立Socket连接
* 可以建立浏览器和服务器间的全双工连接

---

### 浏览器端

```javascript
// 创建连接
var connection = new WebSocket('ws://example.com/echo');

// 发送消息
connection.send('消息内容');

// 接收消息
connection.onmessage = function (e) {
  console.log('Server: ' + e.data);
};
```

---

### Web Socket 服务端

* [socket.io](http://socket.io/)
* [Websocket-Node](https://github.com/theturtle32/WebSocket-Node)

---

### Server Sent Events vs. Web Socket

    +-------------+-------------+--------------+
    |     XHR     |     SSE     |      WS      |
    +-------------+-------------+------+       +
    |               HTTP               |       |
    +----------------------------------+-------+
    |                    TLS *                 |
    +------------------------------------------+
    |                    TCP                   |
    +------------------------------------------+
    |                    IP                    |
    +------------------------------------------+

---

### WebRTC

* Web Real-time Communications
* 点对点分享音视频流或数据
* 三部分 API
    * Network Stream API
    * PeerConnection API
    * DataChannel API

---

### [Network Stream API](https://idevelop.ro/ascii-camera/)

```javascript
var p = navigator.mediaDevices.getUserMedia();
p.then(function(mediaStream) {
    var video = document.querySelector('video');
    video.src = window.URL.createObjectURL(mediaStream);
    video.onloadedmetadata = function(e) {
        // Do something with the video here.
    };
}).catch(function(err) {
    console.log(err.name);
});
```

---

### PeerConnection API

```javascript
var pc = new RTCPeerConnection();
RTCPeerConnection.createOffer().then(function(description){
    pc.setRemoteDescription(new RTCSessionDescription({
        type: 'offer',
        sdp: 'some sdp value'
    }));
});
```

---

### DataChannel API

```javascript
// 创建connection
var pc = new RTCPeerConnection();

// 创建数据通道
var dc = pc.createDataChannel("my channel");
dc.onmessage = function (event) {
    console.log("received: " + event.data);
};
dc.send('some message');
```

---

## Client-side storage, the HTML 5 way

---

### Old days

* Cookie
* Flash UserData

---

### DOM Storage

```javascript
localStorage.setItem('some-key', 'some-value');
localStorage.getItem('some-key');
localStorage.removeItem('some-key');
localStorage.clear();

//storage events
window.addEventListener('storage', function(e){
    // e.key, e.oldValue, e.newValue
}, false);

//session storage
sessionStorage.setItem('some-key', 'some-value');
```

---

### indexedDB

* 存储对象
* Object Store，存储一类数据，类比关系数据库中的表
* Key：组织Object Store中的对象
* Value：存储的内容，可以是JavaScript中的基本数据类型或Object、Array、Date等
* Cursor：游标，遍历结果集的机制

---

### 打开数据库

```javascript
var db;
var request = indexedDB.open("todoDB");
request.onsuccess = function(event) {
    db = request.result;
}
```

---

### 存储对象

```javascript
var transaction = db.transaction(["todo"], "readwrite");
var todoStore = transaction.objectStore("todo");
var request = todoStore.add({
    title: 'do something',
    done: false
});
request.onsuccess = function(event) {
    // event.target.result, 被添加的对象key
}
```

---

### App Cache

* 通过清单指定哪些资源需要被缓存
* 被缓存资源无网络时也可使用
* 被缓存资源，有网络时也直接使用缓存，加载更快
* 清单被更新时，资源会重新下载

---

### manifest 离线清单

```markup
<html manifest="test.appcache">
</html>
```

```markup
# test.appcache

CACHE MANIFEST
/theme.css
/logo.gif
/main.js

NETWORK:
login.asp

FALLBACK:
/html5/ /404.htm
```

---

### `online` / `offline` 事件

```javascript
window.addEventListener('online', function(e){
    // connected to internet
});

window.addEventListener('offline', function(e) {
    // disconnected to internet
});
```

---

## High Performance HTML 5

---

### Old days

* 单线程：JavaScript 和 UI 渲染不能同时进行
* setTimeout

---

### [Web Workers](http://html5demos.com/worker)

* 真正的多线程
* 只能进行纯计算，无法操作 DOM

---

```javascript
// in web page
var myWorker = new Worker("worker.js");
myWorker.postMessage(someData);
myWorker.addEventListener('message', function(e){
    //e.data
});

//in worker.js
onmessage = function(e) {
    //do some computation width e.data
    var result = someOperation(e.data);
    postMessage(result);
}
```

---

### requestAnimationFrame

```javascript
var start = null;
var element = document.getElementById("SomeElementYouWantToAnimate");

function step(timestamp) {
    if (!start) start = timestamp;
    var progress = timestamp - start;
    element.style.left = Math.min(progress/10, 200) + "px";
    if (progress < 2000) {
        window.requestAnimationFrame(step);
    }
}

window.requestAnimationFrame(step);
```

---

### requestIdleCallback

```javascript
btn.addEventListener('click', function(){
    //start UI animation
    updateUI();
    requestIdleCallback(function(){
        var encryptedData = encrypt(params);
        //track log
        log(encryptedData);
    });
});
```

---

### Navigation Timing API

```javascript
//页面加载各个阶段时间记录
performance.timing

//手动计时
performance.mark('ajax_1');
performance.measure('ajax_1');
```

---

## Multimedia, the HTML 5 way

---

### Old days

* Flash

---

### Video

```markup
<video width="320" height="240" controls>
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.mp4" type="video/mp4">
</video>
<script>
    var v = document.getElementById('video');
    v.play();
    v.pause();
    v.load();
</script>
```

---

### Audio

![audio api](https://mdn.mozillademos.org/files/7893/web-audio-api-flowchart.png)

---

## Online games, the HTML 5 way

---

### Old days

* Flash
* DOM

---

### Canvas

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

### SVG

* [Demos](http://www1.plurib.us/svg_gallery/)

---

### Canvas vs. SVG

* Canvas
    * 性能好

* SVG
    * 缩放
    * 描述
    * CSS
    * 事件

---

### WebGL

* 3D Context for Canvas
* [Demos](http://threejs.org/examples/)

---

### Full Screen API

```javascript
var elem = document.getElementById("myvideo");
elem.requestFullscreen();

//exit
elem.exitFullScreen();
```

---

### Pointer Lock API

```javascript
var elem = document.getElementById("myvideo");
elem.requestPointerLock();

//exit
document.exitPointerLock();
```


---

## Accessing devices with HTML 5

---

### Geolocation


```javascript
navigator.geolocation.getCurrentPosition(function(pos){
    console.log(pos);
}, function(err){
    console.log(err);
}, {
    enableHighAccuracy: true,
    timeout: 5000,
    maximumAge: 5000
});

//navigator.geolocation.watchPosition
//navigator.geolocation.clearWatch
```



---

### Device Orientation

```javascript
window.addEventListener("deviceorientation", function(e) {
    console.log(e.alpha, e.beta, e.gamma)
}, false);

window.addEventListener("orientationchange", function() {
    console.log(screen.orientation);
});

```

---

## Web apps, the HTML 5 way

---

### History API

```javascript
//产生历史记录以并保存状态
history.pushState({page: 1}, '第1页', '/page/1');

//监听前进后退，做出响应
window.addEventListener('popstate', function(e){
    console.log(e.state);
});
```

---

### Service Wroker

* 一个在浏览器后台运行的 Web Worker
* 即使页面关闭后，Service Worker 仍可运行

---

```javascript
navigator.serviceWorker.register('/sw.js').then(function(registration) {
    // Registration was successful
    console.log('ServiceWorker registration successful with scope: ',    registration.scope);
}).catch(function(err) {
    // registration failed :(
    console.log('ServiceWorker registration failed: ', err);
});

//in the worker
var CACHE_NAME = 'my-site-cache-v1';
var urlsToCache = [
  '/',
  '/styles/main.css',
  '/script/main.js'
];

self.addEventListener('install', function(event) {
  // Perform install steps
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then(function(cache) {
        console.log('Opened cache');
        return cache.addAll(urlsToCache);
      })
  );
});
```

---

### protocol handlers

```javascript
navigator.registerProtocolHandler("search", "http://www.haosou.com/s?q=%s", "search handler");
```

---

## CSS layout, the HTML 5 way

---

### Old days

* float / position / display
* 一层套一层
* JavaScript 计算

---

<div class="box-model"><p>margin box<br>border box<br>padding box<br>content box</p></div>

box-sizing: content-box | padding-box | border-box

---

```css
.content {
    box-sizing: border-box;
    width: 100%;
    padding: 1em;
}
```

---

### vh and vw

* vh: Viewport 高度的 1%
* vw: Viewport 宽度的 1%

```css
.page {
    height: 100vh;
}
```

---

### calc

```css
.content {
    height: calc(100vh - 100px)
}

```

---

### flex box


Flexbox可控制容器内的子元素：

* 水平或垂直排成一行
* 控制子元素对齐方式
* 控制子元素的宽度/高度
* 控制子元素显示顺序
* 控制子元素是否折行

---

[Flexbox Demo](http://dabblet.com/gist/95e5b65622aeae4d031d)

---

## Animation, the HTML 5 way

---

### Old days

* $('.element').animate()

---

### [transition](http://jsbin.com/zivoji)

* 从一个状态到另一个状态的过渡
* 动画的意义：告诉用户发生了什么

```css
transition: all 1s linear 0.5s;
transition: width 1s linear, height 1s linear 1s;
```

---

### animation

* 定义关键帧
* 指定动画行为
* [代码](http://jsbin.com/yazaqe/edit?html,output)

---

### web animation API

```javascript
var player = document.getElementById('toAnimate').animate([
    { transform: 'scale(1)', opacity: 1, offset: 0 },
    { transform: 'scale(.5)', opacity: .5, offset: .3 },
    { transform: 'scale(.667)', opacity: .667, offset: .7875 },
    { transform: 'scale(.6)', opacity: .6, offset: 1 }
], {
    duration: 700, //milliseconds
    easing: 'ease-in-out', //'linear', a bezier curve, etc.
    delay: 10, //milliseconds
    iterations: Infinity, //or a number
    direction: 'alternate', //'normal', 'reverse', etc.
    fill: 'forwards' //'backwards', 'both', 'none', 'auto'
});
```

---

## 开始使用 HTML 5 和 CSS 3

---

### 兼容性

* [Can I Use](http://caniuse.com/)
* [MDN](https://developer.mozilla.org/en-US/)

---

### 优雅降级

* 圆角 --> 直角
* 阴影 --> 无阴影
* requestAnimationFrame --> setTimeout
* Web Socket --> 长连接

---

### polyfill

* canvas --> exCanvas
* SVG --> Raphaël
* MathML --> MathJax

---

## 总结

* 在考虑实现方案时，尽量选择 HTML 5 或 CSS 3 标准技术
* 不要怕浏览器不支持，大多数技术都有降级方案

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>

---

## Thanks

