
### 前端开发基础课之
# HTML

赵文博@奇舞团

---

## whoami

* **赵文博**
* 奇舞团前端工程师
* 负责360商业产品前端
<p style="font-size:120%;margin-top:0.5em">
    <a href="https://github.com/webzhao" target="_blank" title="Github"><i class="fa fa-github"></i></a>&nbsp;
    <a href="http://www.flickr.com/photos/53827079@N06/" target="_blank" title="Flickr"><i class="fa-flickr"></i></a>&nbsp;
    <a href="https://twitter.com/webzhao" target="_blank" title="Twitter"><i class="fa-twitter"></i></a>&nbsp;
    <a href="http://cn.linkedin.com/pub/wenbo-zhao/29/7b1/514" target="_blank" title="Linkedin"><i class="fa-linkedin"></i></a>&nbsp;
</p>

---

@fragment

### 这节课讲什么？

* HTML中要掌握的关键点
* 图片与使用PhotoShop切图

---

```markup
<!DOCTYPE HTML>
<html>
<head>
    <meta charset="UTF-8">
    <title>HTML5页面</title>
</head>
<body>
    <h1>页面标题</h1>
    <p>页面正文</p>
</body>
</html>
```

<div style="position: absolute;border: 2px solid #F00;top: 2.7em;margin-top: 20px;width: 9.5em;left: 0.5em;" class="fragment"></div>

---

## doctype的作用

* Document Type，文档类型声明
* 指定HTML页面使用的标准和版本
* 浏览器根据doctype决定使用哪种*渲染模式*

---

## 渲染模式

* Quirks Mode 怪异模式
* Almost Standard Mode 准标准模式
* Standard Mode 标准模式

---

## 各种doctype

```plain
<!DOCTYPE HTML PUBLIC
    "-//W3C//DTD HTML 4.01//EN"
    "http://www.w3.org/TR/html4/strict.dtd">

<!DOCTYPE html PUBLIC
    "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<!DOCTYPE html>
```

---

## HTML4 vs. XHTML

```markup
<div CLASS=test>This is a <br> test.</div>
<script type="text/javascript">
    alert(1);
</script>
```
```markup
<div class="test">This is a <br/> test.</div>
<script type="text/javascript">
<![CDATA[
    alert(1);
]]>
</script>
```

---

## HTML 5 设计思想

* 兼容已有内容
* 避免不必要的复杂性
* 解决现实的问题
* 优雅降级
* 尊重事实标准
* 用户 》开发者 》浏览器厂商 》标准制定者 》理论完美

---

### HTML 5 标签
### &nbsp;

<object data="/img/essentials/content-model.svg" height="360" width="1000"></object>

---

### 语义化

* HTML中的元素、属性及属性值都拥有某些含义
* 开发者应该遵循*语义*来编写HTML

---

### 元数据元素

* base：指定基准URL及链接打开方式
* title：页面标题
* script：引入脚本
* style：嵌入页面样式表
* link：引入外部资源，比如外链样式表
* noscript：浏览器不支持脚本时才展示的内容
* meta：页面元数据

---

### meta标签

```markup
<meta charset="UTF-8">
<meta name="keywords" content="前端, HTML, CSS, JavaScript">
<meta name="description" content="前端基础教程">
<meta name="viewport" content="width=device-width; initial-scale=1; user-scalable=no">
<meta http-equiv="refresh" content="5; url=http://example.com/">
```

---

### 使用meta扩展HTML

```markup
<meta name="robots" content="noindex">
<meta name="format-detection" content="telphone=no, email=no">
<meta name="renderer" content="webkit">
```

---

### 标题

* `h1-h6`
* 展示文档结构

---

### 章节内容

* body：页面所有展示内容都放在body内
* article：文章
* aside：侧边栏
* nav：导航栏
* section：内容块
* header：页头
* footer：页尾

---

### 文本语义

* a：anchor，链接
* abbr： 缩写
* br：换行符
* del/ins： 删除/插入
* dfn：定义
* em：强调
* strong：重要的内容
* sub/sup：上标/下标

---

### a链接

* target属性
    * _self
    * _blank
    * _parent
    * _top
* href属性
    * [mailto:](mailto:zhaowenbo@360.cn)
    * [tel:](tel:15901511520)


---

### 引用

```markup
<blockquote>天才并不是自生自长在深林荒野里的怪物， 是由可以使
天才生长的民众产生、长育出来的，所以没有 这种民众，就没有天才。
</blockquote>
<p>--鲁迅</p>

<p>我最喜欢的一本书是<cite>小王子</cite>。</p>
```


---

### 列表标签

* 有序列表
* 无需列表
* 定义列表

---

### 有序列表(Ordered List)

```markup
<h1>世界电影票房排行榜</h1>
<ol>
    <li>阿凡达</li>
    <li>泰坦尼克号</li>
    <li>复仇者联盟</li>
</ol>
```

---

### 无序列表(Unordered List)

```markup
<h1>购物清单</h1>
<ul>
    <li>1个西瓜</li>
    <li>2瓶矿泉水</li>
    <li>1盒酸奶</li>
</ul>
```

---

### 定义列表(Definition List)

```markup
<h3>霸王别姬</h3>
<dl>
    <dt>导演：</dt>
    <dd>陈凯歌</dd>
    <dt>主演：</dt>
    <dd>张国荣</dd>
    <dd>张丰毅</dd>
    <dd>巩俐</dd>
    <dt>上映日期：</dt>
    <dd>1993-01-01</dd>
</dl>
```

---

### 嵌入内容

* img：图片
* svg：SVG矢量图
* audio：音频
* video：视频
* canvas：画布
* iframe：内联页面
* object：其它外部资源

---


### 使用图片

```markup
<img src="/path/to/img.jpg" alt="替代文字"
     width="300" height="200">

<figure>
    <img src="/path/to/img.png" alt="替代文字">
    <caption>图片标题</caption>
</figure>
```

---

### 图片的高宽指定

* 不指定高宽：原图大小显示
* 指定宽度：按比例缩放到指定宽度
* 指定高度：按比例缩放到指定高度
* 指定高宽：强制按指定宽高显示

---

### 常用图片格式

* jpg
    * 照片
* png
    * 色彩较少时使用
    * png24可以半透明
* gif
    * 无法半透明
    * 可以多帧做动画

---

### 使用PhotoShop进行简单的切图

---

@state: blue

<p style="font-size:6em"><i class="fa-comments"></i></p>

---

谢谢！

---

## 参考资料

* [HTML 5 Design Principles](http://www.w3.org/TR/html-design-principles/)
* [Wikipedia: Quirks Mode](http://en.wikipedia.org/wiki/Quirks_mode)
