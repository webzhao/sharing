## Web font

---

### Web Font

* CSS中引入自定义字体

---

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
* 版权意识

---

### 字体裁切工具

* fontmin
* fontspider

---

### 图标字体

* 将页面上的图标做成字体
* 优点
    * 随意调整大小、颜色、阴影、透明度等
    * 尺寸小

---

### 使用图标库

* fontawesome
* iconmoon
* 阿里图标库

---

### 自定义图标字体

* 导出SVG文件
* 使用工具生成
    * fontello
    * customfont
