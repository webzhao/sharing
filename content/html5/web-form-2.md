## Web Form 2.0

---

### placeholder

<input name="username" placeholder="请输入用户名" style="font-size: 1.6em">

```markup
<input name="username" placeholder="请输入用户名">
```

---

### email

<form action="">
    <input type="email" style="font-size: 1.5em">
</form>

```markup
<input type="email">
```

---

### url


<form action="">
    <input type="url" style="font-size: 1.5em">
</form>

```markup
<input type="url">
```

---

### number

<form action="">
    <input type="number" min="0" max="10" step="2" style="font-size: 1.5em">
</form>

```markup
<input type="number" min="0" max="10" step="2">
```

---

### range

<form action="">
    <input type="range" min="0" max="10" step="2" style="font-size: 1.5em">
</form>

```markup
<input type="range" min="0" max="10" step="2">
```

---

### 日期时间

<form action="">
    <p>date: <input type="date" style="font-size: 1.5em"></p>
    <p>datetime: <input type="datetime" style="font-size: 1.5em"></p>
    <p>datetime-local: <input type="datetime-local" style="font-size: 1.5em"></p>
    <p>month: <input type="month" style="font-size: 1.5em"></p>
    <p>week: <input type="week" style="font-size: 1.5em"></p>
    <p>time: <input type="time" style="font-size: 1.5em"></p>
</form>

---

### search

<form action="">
    <input type="search" style="padding:0.5em">
</form>

```markup
<input type="search">
```

---

### color

<form action="">
    <input type="color" style="font-size: 1.5em">
</form>

```markup
<input type="color">
```

---

### 选择多个文件

<form action="">
    <input type="file" multiple accept="image/*, .pptx, .docx">
</form>

```markup
<input type="file" multiple accept="image/*, .pptx, .docx">
```


---

### 必填验证

<form action="">
    <input type="text" required style="font-size: 1.5em">
</form>

```markup
<input type="text" required>
```

---

### 正则验证

<form action="">
    <input type="text" required pattern="1[358]\d{9}" placeholder="请输入手机号" style="font-size: 1.5em">
</form>

```markup
<input
    type="text"
    required
    pattern="1[358]\d{9}"
    placeholder="请输入手机号"
>
```

---

### 表单验证JavaScript接口

* 方法
    * checkValidity()
    * setCustomValidity()

---

### 发送表单数据

```javascript
var formElement = document.querySelector("form");
var formData = new FormData(formElement);
var request = new XMLHttpRequest();
request.open("POST", "submitform.php");
request.send(formData);
```

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>

