## 地理位置

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
