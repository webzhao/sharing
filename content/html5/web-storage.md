## 离线应用

---

### HTML5 支持的存储类型

* localStorage
* indexedDB
* App Cache

---

### localStorage

* 一种在本地存储数据的技术
* 存储 key / value 字符串

---

### 存储数据

```javascript
localStorage.somekey = someStr;
// 或者
localStorage.setItem('some-key', someStr);
// 存储复杂数据
localStorage.key2 = JSON.stringify(someObject);
```

---

### 获取数据

```javascript
var value = localStorage.somekey;
// 或者
var value = localStorage.getItem('some-key');
```
---

### 清除数据

```javascript
localStorage.removeItem('some-key');
// 或者
localStorage.clear();
```
---

### [Demo](/demos/html5/localstorage.html)

---

### 域名限制

* 数据按域名进行存储
    * www.example.com 和 abc.example.com不能共用
* 和 `同源策略`不同
    * 协议
    * 端口号

---

### 时间限制

* localStorage 无限制
    * 网站开发者负责清除写入的本地存储
* sessionStorage 关闭浏览器后失效

---

### 容量限制

* 不同浏览器的策略不同
    * Safari 5M
    * 其它浏览器 10M
* QUOTA_EXCEEDED_ERR异常

---

### 浏览器支持

* Chrome
* Firefox
* IE 8+

---

### localStorage vs. Cookie

<style>
.reveal table {
    margin: 0 auto;
}
.reveal table td, .reveal table th {
    padding: 0.5em 1em;
}
</style>

|  | localStorage     | Cookie |
| ------------- | ------------- | -------------|
| 发送服务器？ | 否 | 是 |
| 容量 | 5M / 10M  | <4K |
| 有效期 | 永久，需要开发者清理 | 可设置有效期 |

---

### localStorage应用场景

* 存储不需要每次发送到服务器的用户数据
* 当作缓存使用（移动端）

---

### Web SQL

* 基于SQLite的关系型数据库存储
* 适用于存储比较复杂的结构化数据

---

### 操作数据

```javascript
var db = openDatabase(
    'dbname',
    '1',
    'todo list example db',
    2 * 1024 * 1024
);
database.transaction(function(tx) {
    tx.executeSql(
        "CREATE TABLE tasks (id REAL UNIQUE, text TEXT)",
        []
    );
});
```

---

### Web SQL 状态

* 标准废弃
* 推荐使用indexedDB代替

---

### indexedDB

* NoSQL数据库，key-value键值对储存数据
* 异步接口
* 对JavaScript对象友好
* 同源策略

---

### 基本概念

* 数据库
* Object Store，存储一类数据，类比关系数据库中的表
* Key：组织Object Store中的对象
* Value：存储的内容，可以是JavaScript中的基本数据类型或Object、Array、Date等
* Cursor：游标，遍历结果集的机制

---

### 连接数据库

```javascript
indexedDB = window.indexedDB
         || window.webkitIndexedDB
         || window.mozIndexedDB
         || window.msIndexedDB;
var db;
var request = indexedDB.open("todoDB");
request.onerror = function(event) {
    //处理错误
}
request.onsuccess = function(event) {
    db = request.result;
}
```

---

### 创建 Object Store

```javascript
/* 假设要存储的对象格式为： 
{
    id: 1,
    title: 'clean room',
    done: false
}
*/
var store = db.createObjectStore(
    "todo",
    { keyPath: "id", autoIncrement: true }
);
store.createIndex("id", "id", { unique: true });
```

---

### 存储对象

```javascript
var transaction = db.transaction(["todo"], "readwrite");
var todoStore = transaction.objectStore("todo");
var request = todoStore.add({
    title: 'do something',
    done: false
});
request.onsuccess = function(event) {
    // event.target.result, 被添加的对象key
}
```

---

### 删除对象

```javascript
var transaction = db.transaction(["todo"], "readwrite");
var todoStore = transaction.objectStore("todo");
var request = todoStore.delete('12'); // object key
request.onsuccess = function(event) {
    // event.target.result
}
```

---

### 查询对象

```javascript
var transaction = db.transaction(["todo"], "read");
var todoStore = transaction.objectStore("todo");
var request = todoStore.get('12'); // object key
request.onsuccess = function(event) {
    // event.target.result
}
```

---

### 使用游标遍历对象

```javascript
var transaction = db.transaction(["todo"], "read");
var todoStore = transaction.objectStore("todo");
var todoList = [];
todoStore.openCursor().onsuccess = function(event) {
    var cursor = event.target.result;
    if (cursor) {
        todoList.push(cursor.value);
        cursor.continue();
    } else {
        // complete
    }
};

```

---

### 更新对象

```javascript
var transaction = db.transaction(["todo"], "readwrite");
var todoStore = transaction.objectStore("todo");
var request = todoStore.put({
    id: 12
    title: 'do something',
    done: false
});
request.onsuccess = function(event) {
    // event.target.result, 被添加的对象key
}
```

---

### 浏览器支持

* IE 10+
* Firefox 10+
* Chrome 23+
* Android 4.4+
* iOS 7.1+

---

### [Demo](https://matthew-andrews.github.io/offline-todo/)

---

> localStorage 和 indexedDB 解决了在本地存储应用数据的问题，要实现无网络时也能使用，还需要靠 *App Cache*

---

### App Cache

* 通过清单指定哪些资源需要被缓存
* 被缓存资源无网络时也可使用
* 被缓存资源，有网络时也直接使用缓存，加载更快
* 清单被更新时，资源会重新下载

---

### manifest 离线清单

```markup
<!DOCTYPE HTML>
<html manifest="test.appcache">

<body>
    content
</body>

</html>
```

---

### manifest

```
CACHE MANIFEST
# updated: 20150901
/theme.css
/logo.gif
/main.js

NETWORK:
login.asp

FALLBACK:
/html5/ /404.htm
```

---

### 资源类型

* CACHE MANIFEST
    * 离线可用
* NETWORK
    * 必须联网使用
* FALLBACK
    * 无法联网时的替代

---

### 更新机制

* 用户清空浏览器缓存
* manifest 文件被修改
* 由程序来更新应用缓存

---

### AppCahe事件

* cached
* checking
* downloading
* error
* progress
* updateready

---

### 使用事件

```javascript
applicationCache.addEventListener('updateready', function() {
    alert('发现新版本！');
}, false);
```

---

### 注意事项

* 避免URL中使用参数 index.html?a=1&b=2
* 检测到新版本后，需要刷新页面
* manifest文件本身不能被缓存

---

### 浏览器支持

* IE 10+
* Firefox
* Chrome
* Android
* iOS

---

### 切换网络状态

* navigator.onLine
* online / offline 事件

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>

