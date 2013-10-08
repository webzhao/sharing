
# 探 索<br>![Node.js](img/node/nodejs.png "Node.js")</h1>
### 赵文博@奇舞团

----------

<section data-state="blue">
    <h2>我们出发吧</h2>
</section>

----------

## Node.js是...
<p class="fragment">服务器端JS运行环境</p>
<p class="fragment">基于Google V8引擎</p>
<p class="fragment"><strong>不是</strong>一个Web开发框架</p>

----------

## 终于可以写后端代码了...

<p style="font-size: 5em" class="fragment"><span class="icon-thumbs-up"></span></p>

----------

## 安装
<div class="fragment">
    <iframe src="http://nodejs.org/" frameborder="0" scrolling="auto" width="960" height="480"></iframe>
</div>

----------

## Hello World

<pre><code data-trim="1">
// hello.js
console.log('Hello World!');
</code></pre>
<pre class="fragment"><code data-trim="1" class="no-highlight">
[~/explore-Node.js]$ node hello.js
Hello World
</code></pre>

----------

## 读写文件

<pre><code data-trim="1" class="line">
var fs = require('fs');
fs.readFile('test.txt', function(err, data){
    console.log(data);
});
console.log('开始读文件了...');
</code></pre>

----------

## HTTP服务器

<pre><code data-trim="1" class="line">
var http = require('http');
http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type':'text/html'});
    res.write('Hello World\n');
    res.end();
}).listen(1337);
console.log('服务器运行中...');
</code></pre>

----------

<section data-state="blue">
    <h2>Node.js的模块机制</h2>
</section>

----------

## 原生模块
<p class="fragment">编译进Node.js</p>
<p class="tmp">
    <style scoped>.tmp em {margin-right:0.5em}</style>
    <em class="fragment">http</em>
    <em class="fragment">fs</em>
    <em class="fragment">net</em>
    <em class="fragment">process</em>
    <em class="fragment">path</em>
    <em class="fragment"><a href="http://Node.js.org/api/" target="_blank">等</a></em>
</p>

----------

## 文件模块
<p class="fragment">原生模块之外的模块</p>
<p class="fragment">和<em>文件(夹)</em>一一对应</p>


----------

## 定义模块

<pre><code data-trim="1" class="line">
// circle.js
var pi = Math.PI;
exports.area = function (r) {
    return pi * r * r;
};
exports.circumference = function (r) {
    return 2 * pi * r;
};
</code></pre>

----------

## 使用模块

<pre><code data-trim="1">
// myapp.js
var circle = require('./circle.js');
console.log('半径为4的圆面积是：' + circle.area(4));
</code></pre>

----------

## 模块加载策略
<pre><code data-trim="1">
// 使用绝对路径
require('/usr/share/foo/circle.js');
</code></pre>
<pre class="fragment"><code data-trim="1">
// 使用相对路径
require('./foo/circle.js');
</code></pre>
<pre class="fragment"><code data-trim="1">
// 使用模块名
// 若不是原生模块，自动添加.js、.json、.node后缀查找
// [$NODE_PATH, ~/.node_modules, 
//  ./node_modules, ../node_modules, ...]
require('circle');
</code></pre>

----------

## 文件夹模块(Package)

<pre><code data-trim="1">
require('./mypackage');
</code></pre>

<pre class="fragment"><code data-trim="1">
// 文件夹下“package.json”的main属性指定实际载入的JS代码
{
    "name": "name of the package",
    "main": "libs/main.js",
    ...
}
</code></pre>

<pre class="fragment"><code data-trim="1">
// 如无package.json，则载入文件夹下的index.js文件
</code></pre>

----------

## <em>npm</em>
<iframe src="https://npmjs.org/" frameborder="0" scrolling="auto" width="960" height="480"></iframe>

----------

<section data-state="green">
    <h3>终于完成了...</h3>
    <h3 class="fragment">第一部分</h3>
</section>

----------

<section data-state="blue">
    <h2>深入Node.js</h2>
</section>

----------

## Node.js起源

----------

## C10K 问题

<p class="fragment"><em>Concurrent 10,000 Connections</em></p>
<p class="fragment">让服务器支持<em>一万</em>并发请求！</p>

----------

## 传统Web服务器(Apache)

<p class="fragment">
    <img src="img/node/block_server.svg" width="800">
</p>

----------

## 使用多线程处理并发

<div style="position:relative">
<p class="fragment">
    <img src="img/node/threads.svg" width="800">
</p>
<div class="fragment" style="position:absolute;width:300px;height:200px;border:2px dashed #fff;top:10px;left:320px;"></div>
<p class="fragment">资源浪费！</p>
</div>

----------

<div style="position:relative;margin:0 auto;width:720px;">
    <style>.thread{width:350px;height:20px;background:url(img/node/th.svg) no-repeat;background-size:100%;margin-bottom:20px!important;}</style>
    <div class="thread fragment"></div>
    <div class="thread fragment" style="margin-left:30px;"></div>
    <div class="thread fragment" style="margin-left:60px;"></div>
    <div class="thread fragment" style="margin-left:90px;"></div>
    <div class="thread fragment" style="margin-left:120px;"></div>
    <div class="fragment" style="width:350px;height:20px;background:#222;margin-left:150px;border:1px dashed #999"></div>
    <div class="thread fragment" style="position:absolute;top:0;left:360px;"></div>
    <div class="fragment" style="position:absolute;top:0;left:150px;padding-top:230px;width:206px;text-align:center;border-left:2px dashed #fff;border-right:2px dashed #fff;">阻塞...</div>
    <div class="fragment" style="position:absolute;font-size:5em;bottom:50px;right:20px"><span class="icon-thumbs-down"></span></div>
</div>

----------

## 单线程、事件驱动

<p class="fragment">
    <img src="img/node/event_loop.png">
</p>

----------

<img src="img/node/non-block.svg" width="960">

----------

## HTTP服务器

<pre><code data-trim="1" class="line">
var http = require('http');
http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type':'text/html'});
    res.write('Hello World\n');
    res.end();
}).listen(1337);
console.log('服务器运行中...');
</code></pre>

----------

## HTTP服务器(Revisited)

<pre><code data-trim="1" class="line">
var http = require('http');
var server = http.createServer();
server.on('request', function(req, res){
    res.writeHead(200, {'Content-Type':'text/html'});
    res.end('Hello World\n' + Math.random());
});
server.on('request', function(req, res){
    console.log(new Date().toLocaleString() + '\t' +
        req.url + '\t' +
        req.headers['user-agent']
    );
});
server.listen(1337);
console.log('服务器运行中...');
</code></pre>

----------

## Node.js的事件机制

<div style="width:580px;margin:0 auto;text-align:left">
<p>Node.js中大部分模块都继承自<em>EventEmitter</em></p>
<p>实现事件机制的方法：</p>
<ol>
    <li>on / addListener</li>
    <li>once</li>
    <li>removeListener</li>
    <li>removeAllListeners</li>
    <li>emit</li>
</ul>
</div>

----------

## 继承EventEmitter
<pre><code data-trim="1" class="line">
var util = require("util");
var events = require("events");

function MyStream() {
    events.EventEmitter.call(this);
}

util.inherits(MyStream, events.EventEmitter);

// 可以在MyStream的实例上使用on/emit了
</code></pre>

----------

<section data-state="blue">
    <h2>回到Node.js起源的问题...</h2>
</section>

----------

## 事件驱动的框架

<p class="fragment">C - libevent</p>
<p class="fragment">Python - Twisted</p>
<p class="fragment">Ruby - Event Machine</p>

----------

## 为什么使用JavaScript？

<p class="fragment">V8引擎使JavaScript运行更快</p>
<p class="fragment">JavaScript适合异步和事件驱动</p>
<p class="fragment">JavaScript已经被众多前端工程师熟悉</p>

----------

## 总结一下

----------

## Node.js是...

<p class="fragment"><em>基于V8引擎的</em></p>
<p class="fragment"><em>事件驱动的</em></p>
<p class="fragment"><em>非阻塞的</em></p>
<p class="fragment"><em>JavaScript平台</em></p>

----------

<section data-state="blue">
    <h2>探索更多...</h2>
</section>

----------

<section style="text-align:left">
    <h2>综合教程</h2>
    <p><a href="http://www.infoq.com/cn/master-Node.js" target="_blank">深入浅出Node.js - 田永强、崔康</a></p>
    <p><a href="http://ofps.oreilly.com/titles/9781449398583/" target="_blank">Up and Running with Node.js - Mike Wilson</a></p>
    <p><a href="http://www.nodebeginner.org/index-zh-cn.html" target="_blank">Node入门（适合JavaScript新手）- Manuel Kiessling</a></p>
    <p><a href="http://nodeguide.com/" target="_blank">Felix's Node.js Guide - Felix Geisendörfer</a></p>
    <p><a href="http://book.mixu.net/" target="_blank">Mixu's Node book - Mikito Takada</a></p>
    <p><a href="https://github.com/maxogden/art-of-node" target="_blank">The Art of Node</a></p>
    <p><a href="http://visionmedia.github.io/masteringnode/" target="_blank">Mastering Node</a></p>
</section>

----------

<section style="text-align:left">
    <h2>博客和社区</h2>
    <p><a href="http://howtonode.org/" target="_blank">How To Node</a></p>
    <p><a href="http://cNode.js.org/" target="_blank">CNode：Node.js专业中文社区</a></p>
</section>

----------

<section style="text-align:left">
    <h2>Web开发框架</h2>
    <p class="framework">
        <style>.framework a {margin:0 0.2em;font-size:80px;font-family:'Segoe UI Light','Segoe UI';color:#fff!important}</style>
        <a href="https://github.com/visionmedia/express" target="_blank">Express</a>
        <a href="http://developer.yahoo.com/cocktails/mojito/" target="_blank"><img src="http://l.yimg.com/os/290/2012/06/25/logo-mojito-png_062613.png" height="100"></a>
        <a href="http://meteor.com/" target="_blank">Meteor</a>
    </p>
</section>

----------

<section style="text-align:left">
    <h2>Web应用中间件</h2>
    <p><a href="http://socket.io/" target="_blank">Socket.IO: the cross-browser WebSocket for realtime apps</a></p>
    <p><a href="https://github.com/senchalabs/connect" target="_blank">connect: High performance middleware framework</a></p>
    <p><a href="https://github.com/mikeal/request" target="_blank">request: Simplified HTTP request client</a></p>
</section>

----------

<section style="text-align:left">
    <h2>JavaScript模板引擎</h2>
    <p><a href="https://github.com/visionmedia/jade" target="_blank">Jade: robust, elegant, feature rich template engine for Node.js</a></p>
    <p><a href="http://paularmstrong.github.io/swig/" target="_blank">swig: A fast django-like templating engine</a></p>
    <p><a href="http://handlebarsjs.com/" target="_blank">Handlebars : Minimal Templating on Steroids</a></p>
    <p><a href="http://akdubya.github.io/dustjs/" target="_blank">dust</a></p>
</section>

----------

<section style="text-align:left">
    <h2>异步编程</h2>
    <p><a href="https://github.com/caolan/async" target="_blank">Async.js: Async utilities for node and the browser</a></p>
    <p><a href="http://documentup.com/kriskowal/q/" target="_blank">q: A library for promises</a></p>
    <p><a href="https://github.com/cujojs/when" target="_blank">when.js: A lightweight Promises/A+ and when() implementation</a></p>
</section>

----------

<section style="text-align:left" data-state="blue">
    <h2>开发工具</h2>
    <p class="framework">
        <a href="http://yeoman.io/" target="_blank"><img src="https://raw.github.com/yeoman/yeoman.io/gh-pages/media/toolset.png" height="240"></a>&nbsp; 
        <a href="http://yeoman.io/" target="_blank" style="vertical-align:90px"><img src="http://nothing.to/img/jshint.png" height="120"></a>

    </p>
</section>

----------

<section data-state="green">
    <h2>Q &amp; A</h2>
    <p style="font-size:5em"><span class="icon-comments"></span></p>
</section>

----------

<section data-state="red">
    <h2>感谢大家的时间！</h2>
    <p style="font-size: 5em"><span class="icon-smile"></span></p>
</section>

----------

<section style="text-align:left">
<h2>参考资料</h2>
<p>http://Node.js.org/api/index.html</p>
<p>http://www.infoq.com/cn/master-Node.js</p>
<p>https://github.com/joyent/node/wiki/modules</p>
<p>http://stackoverflow.com/questions/2353818/</p>
<p>http://www.kegel.com/c10k.html</p>
<p>https://speakerdeck.com/jacksontian/nodejian-jie</p>
<p>
    <img src="http://creativecommons.org/wp-content/themes/creativecommons.org/images/chooser_cc.png">
    <img src="http://creativecommons.org/wp-content/themes/creativecommons.org/images/chooser_by.png" >
</p>
</section>

