# CSS3布局：新的可能性

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

## 布局？

---

* box model
* float
* position

---

# No

---

@fragment

##使用CSS3可以

* 简化布局实现方式
* 实现以前不能实现的布局方式

---

跳出兼容的惯性思维，在合适的场景使用更高级的布局方式。

---

@state: green

## box-sizing

---

@fragment

<style type="text/css">
.box-model {width: 10em;height: 6em;background:#09c;box-shadow:#f80 0 0 0px 2em, #690 0 0 0 4em, #999 0 0 0 6em; margin: 6em auto 7.5em auto!important}
.box-model p {line-height: 2em; position: relative; top: -6em}
</style>

<div class="box-model"><p>margin box<br>border box<br>padding box<br>content box</p></div>

box-sizing: content-box | padding-box | border-box

---

## [Demo](http://dabblet.com/gist/de697755292033c055e8)

---

## box-sizing 浏览器支持

<ul class="browser-support">
    <li><img src="img/css3/ie.png" alt="IE">8+</li>
    <li><img src="img/css3/firefox.png" alt="Firefox"></li>
    <li><img src="img/css3/chrome.png" alt="Chrome"></li>
    <li><img src="img/css3/opera.png" alt="Opera">7.0+</li>
    <li><img src="img/css3/safari.png" alt="Safari">3.0+</li>
    <li><img src="img/css3/ios.png" alt="iOS"></li>
    <li><img src="img/css3/android.png" alt="Android">2.1+</li>
<ul>

---

## display: table

---

## flex-box

---

## multicolumn

---

## gird layout

---

## css shape


<style type="text/css">
.reveal h1 {font-size:2.4em;}
.reveal h2 {font-size:1.6em;}
.reveal img {max-width:100%;}
.reveal a:not(.image) { color: #ccc; color: rgba(255,255,255,0.8); }
.reveal a:not(.image):hover { color: #fff; }
.reveal .overlay {display:inline-block;width:auto;background:rgba(0,0,0,0.5);padding:0.5em 1em;margin:0;line-height:1.6;font-size:1.5em}

.browser-support {display: table; margin-top:2em!important;}
.browser-support img {display: block; margin: 0 auto}
.browser-support li {display: table-cell; vertical-align:top; text-align: center;font-size:1.5em; box-sizing:border-box;padding:0 0.2em;}
</style>
