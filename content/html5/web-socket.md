## Web Socket

---

### 什么是WebSocket

* 可在网络浏览器和服务器之间建立Socket连接。

---

### 浏览器端创建连接

```javascript
var connection = new WebSocket('ws://example.com/echo');
```

---

### 与服务器通信

```javascript
connection.onopen = function () {
  connection.send('Ping');
};
connection.onerror = function (error) {
  console.log('WebSocket Error ' + error);
};
connection.onmessage = function (e) {
  console.log('Server: ' + e.data);
};
```

---

### 服务端接处理

* socket.io

---

```javascript
var io = require('socket.io')(http);
io.on('connection', function(socket){
  console.log('a user connected');
});
//发送
io.emit('some event', { for: 'everyone' });
//接收
socket.on('chat message', function(msg){
    $('#messages').append($('<li>').text(msg));
  });
```

---

### 实例：聊天程序
