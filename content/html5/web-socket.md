## WebSocket

---

### 什么是WebSocket

* 在网络浏览器和服务器之间建立Socket连接
* 可以建立浏览器和服务器间的全双工连接

---

### WebSocket 协议

    +---------------------------+--------------+
    |       XMLHttpRequest      |   WebSocket  |
    +---------------------------+------+       +
    |               HTTP               |       |
    +----------------------------------+-------+
    |                    TCP                   |
    +------------------------------------------+
    |                    IP                    |
    +------------------------------------------+

---

### 连接过程

客户端发起 WebSocket 握手请求，基于HTTP

```
GET /chat HTTP/1.1
Host: example.com:8000
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: dGhlIHNhbXBsZSBub25jZQ==
Sec-WebSocket-Version: 13
```

---

服务器回应握手请求

```
HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: s3pPLMBiTxaQ9kYGzzhZRbK+xOo=
```

---

交换数据帧

<pre style="font-size:0.8em">
0                   1                   2                   3
0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
+-+-+-+-+-------+-+-------------+-------------------------------+
|F|R|R|R| opcode|M| Payload len |    Extended payload length    |
|I|S|S|S|  (4)  |A|     (7)     |            (16/64)            |
|N|V|V|V|       |S|             |   (if payload len==126/127)   |
| |1|2|3|       |K|             |                               |
+-+-+-+-+-------+-+-------------+ - - - - - - - - - - - - - - - +
|    Extended payload length continued, if payload len == 127   |
+ - - - - - - - - - - - - - - - +-------------------------------+
|                               | Masking-key, if MASK set to 1 |
+-------------------------------+-------------------------------+
|    Masking-key (continued)    |          Payload Data         |
+-------------------------------- - - - - - - - - - - - - - - - +
:                   Payload Data continued ...                  :
+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - +
|                   Payload Data continued ...                  |
+---------------------------------------------------------------+
</pre>

---

### 心跳检测

* Ping
* Pong

---

### 关闭连接

* 发送特殊帧数据
* 0x08

---

### 浏览器端创建连接

```javascript
var connection = new WebSocket('ws://example.com/echo');
```

---

### 在浏览器端与服务器通信

```javascript
connection.onopen = function () {
  console.log('连接到服务器啦！');
};

connection.send('消息内容');

connection.onerror = function (error) {
  console.log('WebSocket Error ' + error);
};

connection.onmessage = function (e) {
  console.log('Server: ' + e.data);
};
```

---

### 服务端接处理

* [socket.io](http://socket.io/)
* [Websocket-Node](https://github.com/theturtle32/WebSocket-Node)

---

```javascript
//node
var WebSocketServer = require('websocket').server;
var http = require('http');

var server = http.createServer(function(request, response) {
    console.log((new Date()) + ' Received request for ' + request.url);
    response.writeHead(404);
    response.end();
});
server.listen(8080, function() {
    console.log((new Date()) + ' Server is listening on port 8080');
});

wsServer = new WebSocketServer({
    httpServer: server,
    autoAcceptConnections: false
});

wsServer.on('request', function(request) {
    var connection = request.accept('echo-protocol', request.origin);
    console.log((new Date()) + ' Connection accepted.');
    connection.on('message', function(message) {
        connection.send('some message');
    });
    connection.on('close', function(reasonCode, description) {
        console.log((new Date()) + ' Peer ' + connection.remoteAddress + ' disconnected.');
    });
});
```

---

### [实例：聊天程序](http://localhost:3000/)

---

@state: green

<p style="font-size:6em"><i class="fa fa-comments"></i></p>
