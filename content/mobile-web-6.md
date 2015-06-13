## 设备API

---

### Geolocation

* 使用HTML5的geolocation API可以获取地理位置
* 浏览器会采用GPS、WIFI、基站等多种方式定位
* 注意：使用地理位置信息需要得到用户授权

---

### get current position

```javascript
navigator.getCurrentPosition(function(pos){
    console.log(pos);
}, function(err){
    console.log(err);
}, {
    enableHighAccuracy: true,
    timeout: 5000,
    maximumAge: 5000
});
```

---

###demo

[代码](http://output.jsbin.com/kuwuzi)

---

### watch position

* 持续跟踪设备位置的改变
* navigator.geolocation.watchPosition
* navigator.geolocation.clearWatch

---

## 图片上传

* input type="file"

---

### 浏览器支持

* iOS 6+
* 安卓内置浏览器：2.3+
* WebView：
    * 4.4以下：客户端实现设置WebChromeClient，并实现其中的openFileChooser方法
    * 4.4及以上：需要客户端实现，并提供接口给页面

---

### Demo

[File upload](http://codepen.io/webzhao/embed/gpRNBQ/?height=480&theme-id=0&default-tab=result)

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

[摇一摇](http://codepen.io/webzhao/embed/pJwMvy/?height=480&theme-id=0&default-tab=result)


