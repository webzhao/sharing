<link rel="stylesheet" type="text/css" href="css/360safe/font.css" />
<style type="text/css">
    .strong {
        color: #f44;
        color: #9c0;
    }

    .green {
        color: #9c0;
    }

    .reveal .table td{
        text-align: center;
        color: #666;
        vertical-align: middle;
    }


</style>

<h1>Case study of <br /><a href="http://www.360safe.com/tmp201308" target="blank">360国际版官网 </a></h1>
### 瓜瓜@奇舞团
### huangwei@360.cn

----------


## 面向的用户？

<p class="fragment">国外用户，高级浏览器比例达到<span class="green">80%</span>，IE6用户比例<span  class="green">0.2%</span></p>
<p class="fragment">高级浏览器下<span class="strong">体验</span>，IE6-8浏览器下达到<span class="strong">可用</span></p>
<p class="fragment"><span class="strong">"平稳退化"</span>的开发方法</p>

----------

## IE6下的差别
<img src="" alt="" class="fragment">


----------

<section data-state="blue">
    <h2>Parallax Scrolling</h2>
    <p class="fragment">
        多层背景以不同的速度移动，形成立体的运动效果。
    </p>
</section>

----------

##你会如何实现以下效果呢？
<iframe width="100%" height="3000" src="http://jsfiddle.net/superhunks/9rrfP/5/embedded/result/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
  
----------

## 实现方法：
<p><span class="fragment">Dom 元素</span><span class="fragment"> -> position:absolute</span><span class="fragment"> -> 监听window.onscroll, 改变top/margin-top/background-position</span></p>
<iframe class="fragment" width="100%" height="1000" src="http://jsfiddle.net/superhunks/9rrfP/5/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

----------

<section>
    <h2>如何优化？</h2>
</section>

----------

<section>
    <h2>节流</h2>
    <pre class="fragment">
        <code style="font-size: 0.5em;">
function throttle(fn, threshhold) {
    var last = new Date(); 
    return function() {
        var context = this, 
            args = arguments;
        var now = new Date();
        if(now - last >= threshhold) {
            last  = now;
            fn.apply(context, args);
        }
    };
}

$window.scroll(
    throttle(function() {
    // 滚动事件响应函数
    }, 30）
);
        </code>
    </pre>
</section>

----------

<section>
    <h2>只改变视窗内的层</h2>
    <pre class="fragment">
        <code style="font-size:0.5em;">
    var $parallax = $('.parallax-container'), 
        $window = $(window), 
        ratio = $parallax.data('ratio'),            // 滚动速率
        refreshInterval = 30,                       // 页面刷新间隔
        startOffsetTop = window.innerHeight,        // 开始滚动的位置
        offsetTop = $parallax.offset().top;

    $window.scroll(throttle(function(e) {
        var scrollTop = $window.scrollTop();
        // 到达开始滚动的位置
        if(offsetTop - scrollTop <= startOffsetTop) {
            var parallaxScrollTop = offsetTop > startOffsetTop ? (scrollTop - (offsetTop - startOffsetTop)) * ratio : scrollTop * ratio;    
            $parallax.css('background-position', 'center -' + parallaxScrollTop + 'px');
            // $parallax.css('-webkit-transform', 'translateY(' + -scrollTop + 'px)');
            // $parallax.css('transform', 'translateY(' + -scrollTop + 'px)');
        }
    }, refreshInterval));
    </code>
    </pre>
</section>

----------

<section>
    <h2>硬件加速</h2>
</section>

----------

<section>
    <h2>什么是硬件加速</h2>
    <ul>
    <li class="fragment">把一些计算量大得图像处理工作交给专门的硬件(GPU)来处理以减轻CPU工作量的技术</li>
    <li class="fragment">网页在渲染时分成若干个层(把一些计算量较大的图像处理工作交给专门的硬件layer)，这些layer由GPU组合(composite)</li>
    </ul>
</section>

----------

<section>
    <h2>启用硬件加速</h2>
    <ul>
        <li class="frament">给需要做动画的元素添加样式<p class="green">-webkit-transform:tranlated3d(0,0,0)</p></li>
        <li class="fragment">该元素在渲染时会放在一个单独的layer中</li>
        <li class="fragment">在该元素上使用css动画会很流畅</li>
    </ul>
</section>

----------

<section>
    <h2>例子</h2>
    <img src="img/360safe/example.png" />
</section>

----------

<section>
    <h2>传统方法</h2>
    <p class="fragment">用javascript设置一个timer，逐帧改变.popup的top和left值</p>
</section>

----------

<section>
    <h2>硬件加速的CSS3动画</h2>
    <pre>
        <code style="font-size:0.8em;">
.popup {
    -webkit-transition: -webkit-transform 1s ease-in;
    -webkit-transform: translate3d(0,0,0);
}
.popup.moved {
    -webkit-transform: translate3d(100px, 100px, 0);
}
        </code>
    </pre>
</section>

----------

<h2>对比</h2>
<img src="img/360safe/compare.png" alt="">

----------

<section>
    <h2>优化的实现：</h2>
    <iframe width="100%" height="1000" src="http://jsfiddle.net/superhunks/9rrfP/6/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
</section>

----------

<section data-state="green">
    <h2 style="line-height: 1.3em">Chrome Developer tools<br />调试渲染性能</h2>
    <p class="fragment">Timeline</p>
    <p class="fragment">Show paint rectangles</p>
    <p class="fragment">Show composited layer borders</p>
</section>

----------

<section data-state="blue"><h2>CSS3 Icon Font</h2></section>

----------

<section>
    <h2>为什么要将icon做成字体？</h2>
<!--    <p class="fragment">字体文件小，一般20-50kb</p>
    <p class="fragment">尺寸和颜色可以用css来控制</p>
    <p class="fragment">透明完全兼容IE6</p> -->
</section>

----------

<section>
    <h2>字体文件小</h2>
    <p class="fragment" style="float: left;width:50%;"><img src="img/360safe/sprite.png"><span>PNG24 Css Sprite. <span class="green">25kB</span></span></p>
    <p class="fragment" style="float: right;width:50%;"><img src="img/360safe/woff.png"></p>
</section>

----------

<section>
    <h2>颜色和尺寸可由css控制</h2>
    <div class="icon fragment" data-icon="o" style="font-size:10em;color:#fff"></div>
</section>

----------

<section>
    <h2>良好的跨浏览器支持</h2>
    <div class="icon fragment">IE4+<span class="green">&radic;</span></div>
</section>

----------

<section>
    <h2>字体格式的浏览器支持</h2>
    <table cellpadding="0" cellspacing="0" style="background-color: #ffffff;" class="table">
        <tbody>
        <tr style="background-color: gray; color: #ffffff; text-align: center;">
        <th align="center" width="140" height="30">Browser</th><th align="center" width="200">@font-face</th><th align="center" width="120">TrueType</th><th align="center" width="120">WOFF</th><th align="center" width="120">EOT</th><th align="center" width="120">SVG</th><th align="center" width="120">SVGZ</th>
        </tr>
        <tr>
        <td align="center"><img src="http://pic002.cnblogs.com/images/2011/36987/2011020918254839.png"></td>
        <td align="center">4+</td>
        <td align="center">9+</td>
        <td align="center">9+</td>
        <td align="center">4+</td>
        <td align="center">&nbsp;</td>
        <td align="center">&nbsp;</td>
        </tr>
        <tr bgcolor="#f0f7ff">
        <td align="center"><img src="http://pic002.cnblogs.com/images/2011/36987/2011020918264049.png"></td>
        <td align="center">3.5+</td>
        <td align="center">3.5+</td>
        <td align="center">3.6+</td>
        <td align="center">&nbsp;</td>
        <td align="center">&nbsp;</td>
        <td align="center">&nbsp;</td>
        </tr>
        <tr>
        <td align="center"><img src="http://pic002.cnblogs.com/images/2011/36987/2011020918271360.png"></td>
        <td align="center">4+</td>
        <td align="center">4+</td>
        <td align="center">6+</td>
        <td align="center">&nbsp;</td>
        <td align="center">4+</td>
        <td align="center">6+</td>
        </tr>
        <tr bgcolor="#f0f7ff">
        <td align="center"><img src="http://pic002.cnblogs.com/images/2011/36987/2011020918265934.png"></td>
        <td align="center">3.1+</td>
        <td align="center">3.1+</td>
        <td align="center">6+</td>
        <td align="center">&nbsp;</td>
        <td align="center">3.1+</td>
        <td align="center">3.1+</td>
        </tr>
        <tr>
        <td align="center"><img src="http://pic002.cnblogs.com/images/2011/36987/2011020918262177.png"></td>
        <td align="center">10+</td>
        <td align="center">10+</td>
        <td align="center">11.1+</td>
        <td align="center">&nbsp;</td>
        <td align="center">10+</td>
        <td align="center">10+</td>
        </tr>
        </tbody>
    </table>
    <!-- <ul>
        <li>webkit/safari：支持TrueType/OpenType(.ttf)，OpenType PS(.otf)，iOS4.2+支持.ttf，iOS 4.2以下只支持SVG字体；</li>
        <li>Chrome：除webkit支持的以外，从Chrome 6开始，开始支持woff格式I；</li>
        <li>Firefox：支持.ttf和.otf，从Firefox 3.6开始支持woff格式；Opera 11开始支持WOFF</li>
        <li>Opera：支持.ttf、.otf、.svg</li>
        <li>IE：只支持eot格式，IE9开始支持woff。</li>
    </ul> -->
    <p class="fragment" style="margin-top:30px"><span class="strong">注: </span>woff是最新的w3c推荐的web开放字体格式(web open font format)，字体文件压缩得更小</p>
</section>

----------

<section>
    <h2>如何将icon变成字体？</h2>
    <ol>
        <li class="fragment">使用Adobe Photoshop和Adobe Illustrator生成图标的svg文件</li>
        <li class="fragment">
            通过第三方工具生成字体文件
            <ul>
                <li><a href="http://www.fontsquirrel.com/tools/webfont-generator" target="black">fontsquirrel</a></li>
                <li><a href="http://fontastic.me" target="blank">fontastic</a></li>
            </ul>
        </li>
    </ol>
</section>

----------

<section>
    <h2>在CSS中使用Icon字体</h2>
    <pre style="font-size:0.5em;">
        <code class="fragment">
@font-face {
  font-family: "safe360";
  src:url("http://www.360safe.com/static/fonts/safe360.eot");
  src: url("http://www.360safe.com/static/fonts/safe360.eot?#iefix") format("eot");
  src: local("☺"), url("http://www.360safe.com/static/fonts/safe360.woff") format("woff"), url("http://www.360safe.com/static/fonts/safe360.ttf") format("truetype"), url("http://www.360safe.com/static/fonts/safe360.svg#safe360") format("svg");
  font-weight: normal;
  font-style: normal;
}
.icon { font-family: "safe360"}

<span class="icon">i</span>
    </code>
    <code class="fragment">
[data-icon]:before {
  font-family: "safe360";
  content: attr(data-icon);
}
    </code>
    </pre>
</section>


----------

<section>
    <h2>美中不足</h2>
    <ul>
        <li class="fragment">Chrome等浏览器对icon font解析得不够平滑，边缘有小锯齿<span class="icon" data-icon="e" style="font-size: 2em;margin-left: 20px;vertical-align:middle"></span></li>
        <li class="fragment">只支持纯色icon</li>
        <li class="fragment">制作麻烦，在自定义字体库中添加字体时需重新制作字体文件</li>
        <li class="fragment">为防止盗用字体，IE和FF浏览器有垮与策略。跨域请求字体文件需在http header中设置Access-Control-Allow-Orig</li>
    </ul>
</section>

----------

<section data-state="blue">
    <h2>Polyfills</h2>
    <p class="fragment">Polyfills是一段代码，提供了开发者们希望浏览器原生支持的功能</p>
    <pre class="fragment" style="box-shadow:none">
        <code style="font-size:0.5em;">
if (!Function.prototype.bind) { Function.prototype.bind = ...; }
        </code>
    </pre>
</section>

----------

<section>
    <h2>常用的Polyfills</h2>
    <ul>
        <li class="fragment"><a target="blank" href="https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills">HTML5shiv</a></li>
        <li class="fragment"><a href="http://leaverou.github.com/prefixfree/">-prefix-free</a></li>
        <li class="fragment"><a href="http://selectivizr.com/">selectivizr</a></li>
        <li class="fragment"><a href="https://github.com/plus2/DD_belatedPNG">DD-belatedPNG</a></li>
        <li class="fragment">......</li>
    </ul>
</section>

----------

<section data-state="green">
    <h2>Q&A</h2>
</section>

----------

<section data-state="red">
    <h2>Thanks!</h2>
</section>

----------

<section>
    <h2>参考资料</h2>
    <ul>
        <li><a href="http://www.html5rocks.com/en/tutorials/speed/parallax/?redirect_from_locale=zh"></a>http://www.html5rocks.com/en/tutorials/speed/parallax</li>
        <li><a href="http://code.flickr.net/2013/06/04/adventures-in-jank-busting-parallax-performance-and-the-new-flickr-home-page/">http://code.flickr.net/2013/06/04/parallax_adventures</a></li>
        <li><a href="http://www.qianduan.net/css3-icon-font-guide.html"></a>http://www.qianduan.net/css3-icon-font-guide.html</li>
        <li><a href="http://remysharp.com/2010/10/08/what-is-a-polyfill/"></a>http://remysharp.com/2010/10/08/what-is-a-polyfill/</li>
        <li><a href="http://www.netmagazine.com/features/10-best-polyfills">http://www.netmagazine.com/features/10-best-polyfills/a></li>
    </ul>
</section>





