@state: green

<p style="opacity:0.5"><img src="img/debug/carnaval.png" style="width:20em"></p>

### &nbsp;
# 移动网站调试
### &nbsp;
### 赵文博

---

## whoami

@state: blue, @fragment

* **赵文博**
* 奇舞团前端工程师
* 在做联盟和CRM
<p style="font-size:120%;margin-top:0.5em">
	<a href="https://github.com/webzhao" target="_blank" title="Github"><i class="fa fa-github"></i></a>&nbsp;
	<a href="http://www.flickr.com/photos/53827079@N06/" target="_blank" title="Flickr"><i class="fa-flickr"></i></a>&nbsp;
	<a href="https://twitter.com/webzhao" target="_blank" title="Twitter"><i class="fa-twitter"></i></a>&nbsp;
	<a href="http://cn.linkedin.com/pub/wenbo-zhao/29/7b1/514" target="_blank" title="Linkedin"><i class="fa-linkedin"></i></a>&nbsp;
</p>

---

@state: light

![dev](img/debug/dev.png)

[www.75team.com/archives/388](http://www.75team.com/archives/388)

---

@state: light

<div style="font-size:250%;margin:0.5em">
    <i class="fa-apple fragment"></i> &nbsp;
    <i class="fa-android fragment"></i>
</div>
<style type="text/css">
.reveal .version {display:inline-block;line-height:1.5;padding: 0 0.5em 0.1em 0.5em; background:#444;color:#fff;margin:0 0.1em;font-style:normal;border-radius:2em}
</style>
<div style="margin:3em 0" class="fragment">
    iOS:
    <i class="version">5</i>
    <i class="version">6</i>
    <i class="version">7</i><br><br>
    Android:
    <i class="version">2.2</i>
    <i class="version">2.3</i>
    <i class="version">3.0</i>
    <i class="version">4.0</i>
    <i class="version">4.1</i>
    <i class="version">4.2</i>
</div>
<div style="font-size:250%;margin:0.5em;" class="fragment">
    <p style="opacity:0.8">
        <img src="img/debug/android_browser.svg" style="width:1em">
        <img src="img/debug/safari.svg" style="width:1em">
        <img src="img/debug/chrome.svg" style="width:1em">
        <img src="img/debug/opera.svg" style="width:1em">
    </p>
</div>

---

@state: light

<div style="position:relative;font-size:8em">
    <i class="fa-bug"></i>
    <i class="fa-ban fragment" style="position:absolute;top:0;right:0;bottom:0;left:0;color:#f44;font-size:1.8em"></i>
</div>

---

@state: light

## #1. 尝试使用桌面浏览器调试

---

@state: light

## 使用Chrome的模拟功能

* User-Agent
* 屏幕

    - 分辨率
    - Device Pixel Ratio

* 传感器

    - touch事件(包括多点)
    - 地理位置

---

@state: light

## #2. 使用设备调试

---

@state: light

## 如何在手机上访问开发中的网页？

---

@state: light

## 代理服务器

<p class="fragment">可以使用Fiddler</p>

---

@state: light

## Chrome浏览器的端口转发

* 访问PC上正在开发的网页
* 手机上可以使用Chrome或其它浏览器

---

@state: light

## 如何在手机上设置hosts？

---

@state: light, @fragment

* [安装App修改hosts](http://www.leidian.com/s?q=hosts)
* 设置代理为PC，使用PC上的hosts
* 使用xip.io服务

    - 10.18.60.64.xip.io => 10.18.60.64
    - docs.10.18.60.64.xip.io => 10.18.60.64

---

@state: light

## #3. 远程调试

---

@state: light

## 在iOS上远程调试

---

@state: light

![mobile setting](img/debug/mobile_setting.jpg)

---

@state: light

![safari setting](img/debug/safari_setting.png)

---

@state: light

![safari_menu](img/debug/safari_menu.png)

---

@state: light

![ios debug](img/debug/ios_debug.jpg)

---

@state: light

## 在Android上远程调试

---

@state: blue

## 演示

---

@state: blue

## 很酷对不对？

---

@state: light

## 限制

* <i class="fa-apple"></i> iOS 6+
* <i class="fa-android"></i> Android 4.0+

---

@state: light

## Weinre

<span style="color:#f44">We</span>b <span style="color:#f44">in</span>spector <span style="color:#f44">re</span>mote

---

@state: light

## Weinre工作原理

* 开启一个web socket服务器
* 注入脚本到调试页面，页面状态以JSON格式发送到服务器；接收服务器调试命令。
* 以webkit的调试工具为基础

---

@state: light

## 浏览器通过JSON交换调试数据

* [WebKit Remote Debugging Protocol](http://code.google.com/p/chromedevtools/wiki/WIP)
* [Firebug Crossfire Protocol](http://getfirebug.com/wiki/index.php/Crossfire)
* [Opera Scope Transport Protocol](http://scope.bitbucket.org/)

---

@state: light

## Novakit：让调试更简单

[novakit.qiwoo.org](http://novakit.qiwoo.org/)

---

@state: green

<p style="font-size:6em"><i class="fa-comments"></i></p>

---

@state: blue

## 谢谢大家！

<p style="font-size:6em"><i class="icon-smile"></i></p>

---

## 参考文档

* [Chrome DevTools for Mobile: Screencast and Emulation](http://www.html5rocks.com/en/tutorials/developertools/mobile/)
* [The Remote Debugging Landscape](http://thecssninja.com/talks/remote_debugging/)
* [Hacking Chrome DevTools](https://medium.com/p/8c8896f5cef3)



<style type="text/css">
.reveal h1 {font-size:2.4em;}
.reveal h2 {font-size:1.6em;}
.reveal img {max-width:100%;}
.reveal a:not(.image) { color: #ccc; color: rgba(255,255,255,0.8); }
.reveal a:not(.image):hover { color: #fff; }
.reveal .overlay {display:inline-block;width:auto;background:rgba(0,0,0,0.5);padding:0.5em 1em;margin:0;line-height:1.6;font-size:1.5em}
</style>
