## 设备API

---

### Geolocation

navigator

---

### get current position

---

demo:http://output.jsbin.com/kuwuzi

---

### watch position

---

## 图片上传

* input type=file

---

### 浏览器支持

* iOS 6+
* 安卓内置浏览器：2.3+
* WebView：
    * 4.4以下：客户端实现设置WebChromeClient，并实现其中的openFileChooser方法
    * 4.4及以上：需要客户端实现，并提供接口给页面

---

### Demo

File upload

---

### 注意

* 图片一般1-5M左右，上传前一般需要压缩
* 图片包含转向信息，需要处理

---

### 设备运动API（devicemotion）

* devicemotion事件
* DeviceMotionEvent对象
    * acceleration
    * accelerationIncludingGravity
* 浏览器
    * iOS 4.3+
    * Android 3.0+

---

### 练习

摇一摇

---


