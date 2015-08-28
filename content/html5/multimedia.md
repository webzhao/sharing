## Video 和 audio

---

### Video

* HTML5 标签
* 不使用任何插件直接播放视频
* 提供JavaScript API控制视频播放暂停等

---

### 引入

```markup
<video width="320" height="240" controls="controls">
  <source src="movie.ogg" type="video/ogg">
  <source src="movie.mp4" type="video/mp4">
</video>
```

---

### 标签的属性

* controls 是否显示控制元素
* src 视频源
* autoplay 自动播放
* preload 预先加载

---

### 视频格式

<table class="dataintable">
<tbody><tr>
<th>格式</th>
<th style="width:16%">IE</th>
<th style="width:16%">Firefox</th>
<th style="width:16%">Opera</th>
<th style="width:16%">Chrome</th>
<th style="width:16%">Safari</th>
</tr>

<tr>
<td>Ogg</td>
<td>No</td>
<td>3.5+</td>
<td>10.5+</td>
<td>5.0+</td>
<td>No</td>
</tr>

<tr>
<td>MPEG 4</td>
<td>9.0+</td>
<td>No</td>
<td>No</td>
<td>5.0+</td>
<td>3.0+</td>
</tr>

<tr>
<td>WebM</td>
<td>No</td>
<td>4.0+</td>
<td>10.6+</td>
<td>6.0+</td>
<td>No</td>
</tr>
</tbody></table>

---


### JavaScript控制

```javascript
var v = document.getElementById('video');
v.play();
v.pause();
v.load();
```

---

### 事件

* play
* pause
* playing
* waiting
* seeking
* timeupdate

---

### Audio

* 和video类似
