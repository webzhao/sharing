# 移动Web开发
### 赵文博
#### webzhao@gmail.com

---

### 课程内容

* 移动Web的世界
* Viewport与屏幕分辨率
* 响应式设计
* Touch事件
* 高性能动画
* 使用移动设备API
* 移动Web调试


---

## 进入移动Web的世界

---

### 什么是移动Web

* 使用Web标准技术
    * HTML(5)
    * CSS
    * JavaScript
    * SVG
* 在智能移动设备上使用
    * 手机（iPhone、Android）
    * 平板电脑

---

### 手机 - 屏幕

![screen](http://p8.qhimg.com/d/inn/9d6d2597/stat.png)

---

### 手机 - 分辨率

![resolution](img/mobile/resolution-chart.png)

---

### 手机 - GPS

* 绝大多数手机具备GPS
* 可以获取精确地理位置

---

### 陀螺仪

* 获取手机在三维空间的运动加速度
* 可以实现摇一摇等功能

---

### 相机

* 用户可以上传照片文件
* 500 ～ 1300万像素
* 一般照片尺寸为1 ～ 5M

---

## 移动网络

---

### 移动网络

<table width="700" style="margin:auto;line-height:2">
    <thead>
        <tr>
            <th>网络类型</th>
            <th>所占比例</th>
            <th>平均速度</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>WiFi</td>
            <td>69.1%</td>
            <td>1M/S</td>
        </tr>
        <tr>
            <td>4G</td>
            <td>7.5%</td>
            <td>0.8M/S</td>
        </tr>
        <tr>
            <td>3G</td>
            <td>10.9%</td>
            <td>120K/S</td>
        </tr>
        <tr>
            <td>2G</td>
            <td>12.4%</td>
            <td>20K/S</td>
        </tr>
    </tbody>
</table>

---

## 移动操作系统

---

### 两大平台

* iOS 32%
* Android 68%
* <del>Windows Phone</del>


---

### iOS

<img alt="iOS Version" src="img/mobile/ios-version.png" class="dark">

---

### Android

<img alt="Android Version" src="img/mobile/android-version.png" class="dark">

---

## 移动端浏览器

---

### 浏览器

* 都是基于Webkit内核
* 类型
    - 内置浏览器
    - 第三方浏览器
    - WebView

---

### 内置浏览器

* iOS
    - Safari
* Android 4.3及以下
    - Android内置浏览器
* Android 4.4及以上
    - Google停止开发Android内置浏览器
    - 系统内置浏览器由手机厂商自己决定（自己开发、Chrome等）

---

### 第三方浏览器

* 用户自行下载安装的浏览器
* 用户量最多
    * UC
    * QQ
    * Opera

---

### 国内浏览器

* 附加“功能”
    * 省流量
    * 夜间模式
    * 滑动前进后退
* 开发者文档
    * [UC](http://www.uc.cn/business/developer/)
    * [QQ](http://open.mb.qq.com/doc?id=1201)

---

### WebView

* 一种在应用中嵌入页面的技术
* 在Android和iOS中都可以实现
* 最常用的WebView
    - 微信
    - 微博

---

### iOS上的WebView

* 苹果安全限制比较严格
* 只能使用iOS提供的UIWebView控件
* 比Safari性能稍微差一些

---

### Android

* 默认的WebView
    - 4.4以下 基于Android内置浏览器
    - 4.4及以上 基于Chromium
* 自定义WebView
    - 腾讯X5
    - 安卓的开放造成的兼容性问题

---

### 兼容性

* 特性支持
    * 降级方案
    * 兼容性速查 [Can I Use.com](http://caniuse.com/)
* bug
    * [StackOverflow](http://stackoverflow.com/)
    * [Android Bug List](https://code.google.com/p/android/issues/list)


---

### 开发工具

* Chrome浏览器
* 脚本库
    * 原生JS
    * Zepto

