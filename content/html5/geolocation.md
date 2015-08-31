## 地理位置

---

### Geolocation

* 使用HTML5的geolocation API可以获取地理位置
* 浏览器会采用GPS、WIFI、基站等多种方式定位
* 注意：使用地理位置信息需要得到用户授权

---

### get current position

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

### 经纬度 --> 地址

* 逆向地理编码API

---

### Geolocation使用注意事项

* 用户授权过程必不可少
* 定位速度比较慢
* Google服务不稳定

---

### 兼容性

* IE9+
* Firefox
* Chrome
* iOS
* Android

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>


