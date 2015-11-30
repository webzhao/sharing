## HTML5 vs Native

---

<style>
.reveal table {font-size: 0.8em}
.reveal table td,.reveal table th {padding: 0.5em}
.reveal table td:first-child {white-space:nowrap}
</style>

|  | HTML5 | 原生应用 |
|--------------|----------------------|----------------------|
| 更新 | 只需要服务器部署新版本，比较方便 | 需要发布新版客户端，需要商店审核，新版覆盖需要较长时间 |
| 动画 | 可以实现基本的动画效果，在低配置机器上不流畅 | 动画效果可以很炫，很流畅 |
| 加载速度 | 较慢。尤其是首次，可以充分利用缓存机制做优化 | 较快 |
| 开发成本 | 低。Web标准技术已经非常适合开发应用 | 高，人员、时间 |
| 访问硬件能力 | 仅限部分API | 所有设备权限 |
| 适用场景 | 内容内应用 | 重交互类应用 |

---

### Hybrid 应用

* 在原生应用中嵌入 HTML5 页面
* WebView

---

### 已有框架

* PhoneGap
* Apache Cordova
* Appcelerator Titanium
* AppCan

---

### 客户端和 HTML5 通信

* 客户端调用HTML5接口
    * javascript: 伪协议
* HTML5中调用客户端功能
    * Android: 截获页面上的prompt, console等调用
    * Android: addJavascriptInterface
    * iOS: 自定义协议拦截
