## 移动Web调试

---

### 使用Chrome模拟

* User-Agent
* 屏幕
    - 分辨率
    - Device Pixel Ratio
    - 缩放
* 传感器
    - touch事件
    - 地理位置

---

## 在设备上访问网页

---

### 设置hosts

---

### Android

* 已经取得root权限
    * Root Explorer等文件编辑工具修改/etc/hosts
    * 专门的hosts管理工具
* 没有root权限
    * adb

---

### iOS

* 越狱
    * 使用文件编辑工具或管理工具
* 未越狱
    * 其它办法

---

### 代理服务器方法

* 启动一台机器作为代理服务器（Fiddler、Charles即可）
* 在手机上设置代理服务器
* 手机将会使用代理服务器上的设置

---

## 远程调试

---

### 调试iOS设备

---

### 调试Android设备

---

### 限制

* <i class="fa-apple"></i> iOS 6+
* <i class="fa-android"></i> Android 4.0+

### 低版本Android：Weinre

<span style="color:#f44">We</span>b <span style="color:#f44">in</span>spector <span style="color:#f44">re</span>mote

---

### Weinre工作原理

* 开启一个web socket服务器
* 注入脚本到调试页面，页面状态以JSON格式发送到服务器；接收服务器调试命令。
* 以webkit的调试工具为基础

---

谢谢！
