## Video 和 Audio

---

### Video

* HTML5 标签
* 不使用任何插件直接播放视频
* 提供JavaScript API控制视频播放暂停等

---

### 引入

```markup
<video width="320" height="240" src="movie.ogg">
</video>

<video width="320" height="240" controls>
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

<table style="margin: 0 auto" width="900">
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

<video src="http://www.runoob.com/try/demo_source/movie.ogg" controls preload width="600"></video>

---

### [JavaScript控制](/demos/html5/video.html)

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
* waiting
* seeking
* timeupdate

---

### Video与Canvas结合

* drawImage(video, 0, 0, w, h)
* [demo](http://html5doctor.com/demos/video-canvas-magic/demo1.html)

---

### Audio

```markup
<audio src="music.ogg">
</audio>

<audio controls>
  <source src="music.ogg" type="audio/ogg">
  <source src="music.mp3" type="audio/mp3">
</audio>
```

---

### Web Audio API

* [API](https://webaudio.github.io/web-audio-api/)
* [Demo](http://mdn.github.io/violent-theremin/)

---


@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>

