## 离线存储

---

### HTML中支持的存储类型

* localStorage
* Web SQL
* indexedDB
* App Cache

---

### localStorage

* 存储机制，通过该机制，浏览器可以安全地存储键值对

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

### 域名限制

* 数据按域名进行存储
    * www.example.com 和 abc.example.com不能共用
* 和 `同源策略`不同
    * 协议
    * 端口号

---

### 时间限制

* localStorage 无限制
* sessionStorage 关闭浏览器后失效

---

### 容量限制

* 不同浏览器的策略不同

---

### 浏览器支持

* Chrome
* Firefox
* IE 8+

---

### localStorage vs. Cookie

* 是否发送服务器
* 容量

---

### localStorage应用

* 存储用户数据
* 当作缓存使用

---

### Web SQL

* 基于SQLite的关系型数据库存储
* 适用于存储比较复杂的

---

### 操作数据

```javascript
var db = openDatabase('dbname', '1', 'todo list example db', 2 * 1024 * 1024);
database.transaction(function(tx) {
    tx.executeSql("CREATE TABLE IF NOT EXISTS tasks (id REAL UNIQUE, text TEXT)", []);
});
```

---

### Web SQL 状态

* 标准暂停
* 推荐使用indexedDB

---

### indexedDB

* NoSQL数据
* 对JavaScript对象友好

---

### 创建数据库

```javascript
window.indexedDB = window.indexedDB || window.webkitIndexedDB || window.mozIndexedDB || window.msIndexedDB;

if ('webkitIndexedDB' in window) {
  window.IDBTransaction = window.webkitIDBTransaction;
  window.IDBKeyRange = window.webkitIDBKeyRange;
}

indexedDB.db = null;
indexedDB.onerror = function(e) {
  console.log(e);
};
```

---

### 存储对象

```javascript
indexedDB.open = function() {
  var v = "2.0 beta";
  var request = indexedDB.open("todos", v);

  request.onupgradeneeded = function(e) {
    var db = request.result;
    var store = db.createObjectStore("todo", {keyPath: "timeStamp"});  
  };

  request.onsuccess = function(e) {
    todoDB.indexedDB.db = e.target.result;
    todoDB.indexedDB.getAllTodoItems();
  };

  request.onfailure = todoDB.indexedDB.onerror;
};
```

---

### 离线应用App Cache

* 无网络时也可以使用
* 缓存资源，加载更快

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
