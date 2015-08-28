## File API

---

### File API是什么

* 允许开发者访问用户选中的文件
    * 文件选择框
    * 文件拖放

---

### 获取文件对象

```markup
<input type="file" id="files" name="files[]" multiple />
<output id="list"></output>
<script>
  function handleFileSelect(evt) {
    var files = evt.target.files;

    var output = [];
    for (var i = 0, f; f = files[i]; i++) {
      output.push('<li><strong>', escape(f.name), '</strong> (', f.type || 'n/a', ') - ',
                  f.size, ' bytes, last modified: ',
                  f.lastModifiedDate.toLocaleDateString(), '</li>');
    }
    document.getElementById('list').innerHTML = '<ul>' + output.join('') + '</ul>';
  }
  document.getElementById('files').addEventListener('change', handleFileSelect, false);
</script>
```

---

### 读取文件

* FileReader.readAsBinaryString(Blob|File)
* FileReader.readAsText(Blob|File, opt_encoding)
* FileReader.readAsDataURL(Blob|File)
* FileReader.readAsArrayBuffer(Blob|File)

---

### 示例：图片处理
