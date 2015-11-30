## Web fonts

---

### Web Fonts

* 在页面上使用服务器字体
* 满足设计师对特殊字体使用的需求
* 与使用图片展示特殊字体的方案对比
    * 文件更小
    * 易于维护

---

<link href='https://fonts.googleapis.com/css?family=Black+Ops+One|Frijole|Rock+Salt' rel='stylesheet' type='text/css'>

<p style="font-family:'Black Ops One';font-size: 2em">Grumpy wizards make toxic brew for the evil Queen and Jack.</p>

---

<p style="font-family:Frijole;font-size: 2em">Grumpy wizards make toxic brew for the evil Queen and Jack.</p>

---

<p style="font-family:'Rock Salt';font-size: 2em">Grumpy wizards make toxic brew for the evil Queen and Jack.</p>

---

### 引入Web Font

```css
@font-face {
  font-family: 'fancyFont';
  src: url('http://www.example.com/fancyFont.eot');
  src: url('http://www.example.com/fancyFont.eot?#iefix') format('embedded-opentype'),
       url('http://www.example.com/fancyFont.woff') format('woff'), /* 所有现代浏览器 */
       url('http://www.example.com/fancyFont.ttf')  format('truetype'), /* Safari, Android, iOS */
       url('http://www.example.com/fancyFont.svg#svgFontName') format('svg'); /* Legacy iOS */
}
.title {
    font-family: 'fancyFont';
}
```

---

### 中文字体

* 中文字体太大，十几到几十兆

---

### 字体裁切工具

* [fontmin](http://ecomfe.github.io/fontmin/)
* [fontspider](http://font-spider.org/)

---

### Demo

---

### UTF-8 字符

<p style="font-size:2em">&#9829; &#10026; &#8734; &#9993; &#9888; &#9992; &#10047;  &#9775;</p>

---

### 图标字体

* 将图标做成字体在页面上使用
* 优点
    * 随意调整大小、颜色、阴影、透明度等
    * 尺寸小

---

### 使用图标库

* [Fontawesome](http://fortawesome.github.io/Font-Awesome/icons/)
* [iconmoon](https://icomoon.io/app)
* [阿里图标库](http://www.iconfont.cn/)

---

### 自己动手制作Font icons

* 导出SVG文件
* 使用工具生成
    * [fontello](http://fontello.com/)
    * [customfont](http://fontcustom.com/)

---

### 浏览器支持

* IE 4+
* Firefox
* Chrome
* Android
* Safari

---

### 注意事项

* 渲染问题
    * Chrome 阻塞渲染 + 超时
    * 其它浏览器：页面闪动
    * 解决办法：base64后inline
* 锯齿（Windows Chrome下）
* 版权

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>
