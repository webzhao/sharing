
@bg: img/devtools/chrome.svg

# Chrome开发者工具的秘密
### &nbsp;
### 赵文博

---

## whoami

@state: blue

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

## console

---

```javascript
console.log('当前时间：', new Date());
console.warn('这是一条警告消息');
console.error('这是一条错误消息');
```

---

## 格式化输出

```javascript
console.log('我是来自%s的%s', '奇舞团', '赵文博');
console.log('本次分享大约需要%i分钟', 60);
console.log('对象：%O', window.location);
console.log('DOM：%o', document.body);
```

---

## 来点颜色看看

```javascript
console.log(
    '%cConsole还挺有意思的~~',
    'color:#fff;background:#f44;font-size:18px'
);
```

---

## 用console来计时

```javascript
console.time('循环计时');
for (var i = 0; i < 100000; i++) {
    Math.random() * Math.random();
}
console.timeEnd('循环计时');

```
---

## 选择元素

```javascript
$('.past'); // querySelector
$$('.past'); // querySelectorAll
$x('/html/body/script') // xpath
```

---

```javascript
var obj = {x:1, y:2};
copy(obj);
```


---

## console就到这里吧

```javascript
console.clear();
```

---

@state: green

<p style="font-size:6em"><i class="fa-comments"></i></p>

---

@state: blue

## 谢谢大家！

<p style="font-size:6em"><i class="icon-smile"></i></p>

---

## 参考文档

* [Secrets of the Browser Developer Tools](http://devtoolsecrets.com/)
* [Chrome DevTools](https://developers.google.com/chrome-developer-tools/)
* [Hacking Chrome DevTools](https://medium.com/p/8c8896f5cef3)



<style type="text/css">
.reveal h1 {font-size:2.4em;}
.reveal h2 {font-size:1.6em;}
.reveal img {max-width:100%;}
.reveal a:not(.image) { color: #ccc; color: rgba(255,255,255,0.8); }
.reveal a:not(.image):hover { color: #fff; }
.reveal .overlay {display:inline-block;width:auto;background:rgba(0,0,0,0.5);padding:0.5em 1em;margin:0;line-height:1.6;font-size:1.5em}
</style>
