## File API

---

### File API是什么

* 允许开发者访问用户选中的文件
    * 文件选择框
    * 文件拖放

---

### 通过文件选择框获取文件对象

* 监听`<input type="file">`的`change`事件
* 通过 input.files 属性获取文件对象列表

---

### [Demo](http://jsbin.com/jarice/edit?js,output)

---

### 通过拖拽获取文件对象

* 选定一个可拖放的区域
* 给这个元素绑定dragenter、dragover事件并组织默认行为
* 绑定drop事件，通过 e.dataTransfer.files 获取文件对象

---

### [Demo](http://jsbin.com/yogamu/4/edit?html,js,output)

---

### 读取文件内容

* fileReader.readAsBinaryString(Blob|File)
* fileReader.readAsText(Blob|File, opt_encoding)
* fileReader.readAsDataURL(Blob|File)
* fileReader.readAsArrayBuffer(Blob|File)

---

### Blob

* Binary large object
* 二进制文件容器
* 可以修改

---

### [Data URL Demo](http://jsbin.com/zosine/edit?html,js,console,output)

---

### [Read Text Demo](http://jsbin.com/zecabi/2/edit?html,js,output)

---

### 文件上传

* 使用FormData和XMLHttpRequest
* 不使用FormData（上传前进行图片压缩）
    * fileReader.readAsBinaryString()
    * xmlHttpRequest.sendAsBinary()

---

### [示例：图片处理](http://makeitsolutions.com/labs/jic/)

---


@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>
