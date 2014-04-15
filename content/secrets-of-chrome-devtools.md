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

@state: white

## 每天陪伴我们的调试工具，你真的了解它吗？

<img src="img/devtools/chrome_start.jpg">

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

## 分组

```javascript
console.group('分组1');
console.log('item 1');
console.log('item 2');
console.log('item 3');
console.groupEnd();
```

---

## 输出表格

```javascript
var list = [
    {
        title: '360导航',
        url: 'http://www.3600.com',
        color: '#44f'
    },
    {
        title: '360搜索',
        url: 'http://www.so.com'
    }
];
console.log(list);
console.table(list);
```

---

## 计数器

```javascript
function tossCoin() {
    console.count('抛硬币');
    if (Math.random() > 0.5) {
        console.count('正面');
    } else {
        console.count('反面');
    }
}
var i = 0;
while (i++ < 100) {
    tossCoin();
}
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

## 复制到剪贴板

```javascript
var obj = {x:1, y:2};
copy(obj);
```

---

## 快捷引用

```javascript
document.querySelector('a');
$_.href;
$0;  // 最后一次选中的DOM元素
$1;  // 倒数第二次选中的DOM元素
```

---
XHR
## console就到这里吧

```javascript
console.clear();
```

---

## Inspector

---

## 快速修改数字

| 数值改变      | 操作        |
| ------------- |:-------------:|
| ±1           | ↑/↓ |
| ±10          | Shift + ↑/↓ |
| ±0.1         | Alt + ↑/↓  |
| ±10          | Shift + ↑/↓ |
| ±100         | Shift + PgUp/PgDown |


---

### 拖拽修改DOM树

---

### 修改hover/focus/visited样式

<a href="#">这是一个链接</a>
<input type="text">

---

## debugging

---

## 在代码中设置断点

```javascript
function add(a, b) {
    debugger;
    return a + b;
}
add(Math.random(), 75);
```

---

## 设置中断条件

```javascript
var i = 0, value;
while (i++ < 100) {
    value = Math.random();
    console.log(value);
}
```
---

## XHR断点

<a href="demos/devtools/conditional.html" target="_blank">Demo</a>

---

## DOM断点

<a href="demos/devtools/dom_breakpoint.html" target="_blank">Demo</a>

---

## XHR断点

<a href="demos/devtools/xhr.html" target="_blank">Demo</a>

---

## 格式化代码

---

## Source Map

<a href="demos/devtools/source_map.html" target="_blank">Demo</a>

---

## LESS/SASS

<a href="demos/devtools/sass.html" target="_blank">Demo</a>

---

## Canvas调试

<a href="demos/devtools/canvas.html" target="_blank">Demo</a>

---

## workspace: Chrome as an IDE

<a href="http://localhost:8000" target="_blank">Demo</a>  <a href="https://developers.google.com/chrome-developer-tools/docs/authoring-development-workflow" target="_blank">文档</a>

---

@state: white

## Happy coding!

<img src="img/devtools/chrome_end.jpg">

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
* [JavaScript Source Map 详解](http://www.ruanyifeng.com/blog/2013/01/javascript_source_map.html)



<style type="text/css">
.reveal h1 {font-size:2.4em;}
.reveal h2 {font-size:1.6em;}
.reveal img {max-width:100%;}
.reveal a:not(.image) { color: #ccc; color: rgba(255,255,255,0.8); }
.reveal a:not(.image):hover { color: #fff; }
.reveal .overlay {display:inline-block;width:auto;background:rgba(0,0,0,0.5);padding:0.5em 1em;margin:0;line-height:1.6;font-size:1.5em}
.reveal table {margin: 0 auto}
.reveal table td, .reveal table th {padding: 0.3em 1em}
</style>
