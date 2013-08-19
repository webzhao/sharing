<section data-state="bg-cover">
    <style>
        .bg-cover body {background-image: url(//farm4.staticflickr.com/3254/3120186015_b5e4feaa19_b.jpg)}
    </style>
    <h1 style="bottom:15%;top:auto;">High performance web</h1>
</section>

<style>
.reveal li {
    margin: 1em 0;
}
</style>

--------------------

# Why performance matters?

-------------------------

>Speed is the most important feature...  If something is slow, they're just gone. 

&nbsp;

>Yahoo! – A 400 milliseconds slowdown resulted in a 5-9% drop in full-page traffic.

&nbsp;

>Netflix – Adopting a single optimization, gzip compression, resulted in a 13-25% speedup and cut their outbound network traffic by 50%.

-------------------------

##What performance means?

* In this talk, we focus on __Response Time__ of __Websites__
* Reduce the __Time To Interactivity (TTI)__

-----------------------

##In this talk

* Some facts about how browser load web page
* Best practices of high performance web
* Explain reasons behind these rules
* Methods and tools used to improve performance

-----------------------

##Browser rendering Process

![waterfall](http://p6.qhimg.com/t01eb6ab40d0b4fc6d4.png)

-------------------

##Notes about rendering

* Browser [start rending](http://www.yahoo.com/) as soon as it receives HTML
* Browser downloads components(js/css/image) parallel in a queue
* Connections per host are [limited](http://www.stevesouders.com/blog/2008/03/20/roundup-on-parallel-connections/)

-------------------

## #0 Minimize HTTP Requests 

* HTTP request is expensive
  * DNS Lookup + Connecting + Blocking + Sending + Waiting + Receiving
* Ways to reduce requests number
  * Combine JS/CSS files
  * [CSS Sprites](http://css-tricks.com/examples/CSS-Sprites/Example1After/)
  * [Keep-Alive](http://en.wikipedia.org/wiki/HTTP_persistent_connection) in HTTP Headers
  * Minimize [redirects](http://developer.yahoo.com/blogs/ydn/posts/2007/07/high_performanc_9/)
  * [Lazy](http://search.yahoo.com/mobile/s?p=obama) load [components](http://v.qq.com/)

------------------

## #1 Make components cacheable 

* Add [Expires](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.21) or [Cache-Control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) Header
* Make JavaScript and CSS External
* Configure [ETags](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.19)
* Make Ajax [Cacheable](http://developer.yahoo.com/blogs/ydn/posts/2007/09/high_performanc_12/)

------------------

## #2 Reduce DNS Lookups

* Reducing the number of unique hostnames
  * will reduce the amount of parallel downloading
  * balance them

<style>
.process-table {position:absolute;bottom: -2em;left:1em; border:none;border-collapse: collapse;}
.process-table td {padding: 0.3em;background:orange;border-left:1px solid #FFF}
.process-table td:first-child {border-left:none}
.process-table td.current {background:green}
</style>

<table class="process-table">
<tr>
<td class="current">DNS lookup</td>
<td>Connecting</td>
<td>Blocking</td>
<td>Sending</td>
<td>Waiting</td>
<td>Receiving</td>
</tr>
</table>

------------------

## #3 Parallelize downloads 

* Split Components [Across Domains](http://yuiblog.com/blog/2007/04/11/performance-research-part-4/)
* Avoid CSS [@import](http://www.stevesouders.com/blog/2009/04/09/dont-use-import/)

<table class="process-table">
<tr>
<td>DNS lookup</td>
<td>Connecting</td>
<td class="current">Blocking</td>
<td>Sending</td>
<td>Waiting</td>
<td>Receiving</td>
</tr>
</table>

------------------

## #4 Use Non-Blocking JS

* Fact: Javascript [blocks](http://dl.dropbox.com/u/6929017/slides/performance/blocking_js.html) rendering and parallel downloads
* How to make js non-blocking
  * put js at bottom or lazy load js
  * create script tag [dynamically](http://dl.dropbox.com/u/6929017/slides/performance/non_blocking_d.html)
  * use _defer_ or [_async_](http://dl.dropbox.com/u/6929017/slides/performance/non_blocking_a.html) attribute


<table class="process-table">
<tr>
<td>DNS lookup</td>
<td>Connecting</td>
<td class="current">Blocking</td>
<td>Sending</td>
<td>Waiting</td>
<td>Receiving</td>
</tr>
</table>

------------------

## #5 Minimize request size

* Reduce Cookie Size
  * Use [localstorage](http://diveintohtml5.info/storage.html) over cookie
* Use [Cookie-free](http://search.yahoo.com/mobile) Domains for Components
* Use [GET](http://developer.yahoo.com/performance/rules.html#ajax_get) for AJAX request if possible

<table class="process-table">
<tr>
<td>DNS lookup</td>
<td>Connecting</td>
<td>Blocking</td>
<td class="current">Sending</td>
<td>Waiting</td>
<td>Receiving</td>
</tr>
</table>

------------------

## #6 Responsive server-side

* Flush the buffer early
  * [Example without flush](http://dev.search.yahoo.com/test/no_flush.php)
  * [Example with flush](http://dev.search.yahoo.com/test/flush.php)
* Parallelize workflow on server
  * [Facebook BigPipe](http://www.facebook.com/note.php?note_id=389414033919)

<table class="process-table">
<tr>
<td>DNS lookup</td>
<td>Connecting</td>
<td>Blocking</td>
<td>Sending</td>
<td class="current">Waiting</td>
<td>Receiving</td>
</tr>
</table>

------------------

## #7 Minimize component transfer size

* [Minimize](http://yuilibrary.com/projects/yuicompressor/) Javascript and CSS file
* [Optimize](http://www.smushit.com/ysmush.it/) images and CSS sprites
* [Gzip](http://en.wikipedia.org/wiki/Gzip) components
* Serve scaled images

<table class="process-table">
<tr>
<td>DNS lookup</td>
<td>Connecting</td>
<td>Blocking</td>
<td>Sending</td>
<td>Waiting</td>
<td class="current">Receiving</td>
</tr>
</table>

------------------

## #8 Optimize browser rendering

* Avoid Repaint and [Reflow](http://www.youtube.com/watch?v=ZTnIxIA5KGw)
  * Put CSS at top
  * Specify image dimensions
* Avoid CSS [expressions](https://developers.google.com/speed/docs/best-practices/rendering#AvoidCSSExpressions)
* Avoid [Filters](http://developer.yahoo.com/blogs/ydn/posts/2007/07/high_performanc_6/)

------------------

<section data-state="singleui">
    <style>.singleui body {background-image:url(//farm7.staticflickr.com/6031/6328994265_daca6ca212_b.jpg)}</style>
    <h2 style="text-align:left;" class="fragment">UI Thread = <br/>update UI + execute Javascript</h2>
</section>

------------------

## #9 Minimize UI update in JS

* Cache references to accessed elements
* Update nodes "[offline](http://ejohn.org/blog/dom-documentfragments/)" and then add them to the tree
* Change [className](http://www.quirksmode.org/dom/classchange.html) over change style
* Use CSS3 transition over JS animation

------------------

## #10 Take UX into account

* Make [onload](http://dl.dropbox.com/u/6929017/slides/performance/loading.pdf) faster
* Add [loading indicator or progress bar](http://www.usabilitypost.com/2009/01/23/making-wait-times-feel-shorter/) for long time operation

------------------

## Tools (1/2)

* Rule checking
  * Yahoo! [YSlow](http://yslow.org/)
  * Google [PageSpeed](https://developers.google.com/speed/)

* Timeline
  * [Firebug](http://getfirebug.com/)
  * [HTTPWatch](http://www.httpwatch.com/)
  * [Webkit](https://developers.google.com/chrome-developer-tools/)/[IE](http://en.wikipedia.org/wiki/Internet_Explorer_Developer_Tools) developer tools

-------------------------

## Tools (2/2)

* Image optimization
  * Yahoo! [Smush.it](http://www.smushit.com/ysmush.it/)
  * [Pngcrush](http://pmt.sourceforge.net/pngcrush/) and [ImageMagic](http://www.imagemagick.org/script/index.php)
  * [SpriteMe](http://spriteme.org/)

* JS/CSS compression
  * [YUI compressor](http://yuilibrary.com/projects/yuicompressor/)
  * [Google Closure](https://developers.google.com/closure/)

------------------

## Books

<a href="http://search.safaribooksonline.com/book/web-development/9780596529307"><img src="http://akamaicovers.oreilly.com/images/9780596529307/lrg.jpg" style="max-width: 40%;display:inline-block;" /></a> &nbsp; &nbsp;
<a href="http://search.safaribooksonline.com/book/web-design-and-development/9780596803773"><img src="http://akamaicovers.oreilly.com/images/9780596522315/lrg.jpg" style="max-width:40%; display:inline-block" /></a>


------------------

## Online Resources

* [Best Practices for Speeding Up Your Web Site](http://developer.yahoo.com/performance/rules.html) from Yahoo! 
* [Web Performance Best Practices](https://developers.google.com/speed/docs/best-practices/rules_intro) from Google
* [Steve Souders](http://www.stevesouders.com/blog/)'s Blog

------------------

## &nbsp;
## 

##Keywords of web performance optimization

------------------

<div class="bg" style="background-image:url(http://farm1.staticflickr.com/22/88003222_c875cfda73_b.jpg)">
<h1 style="top:auto;bottom:10%;left:6%;">Bottleneck</h1>
</div>

------------------

<div class="bg" style="background-image:url(http://farm5.staticflickr.com/4040/4195859328_6ff0f4cce7_b.jpg)">
<h1 style="top:auto;left:auto;right:6%;bottom:10%">Non-blocking</h1>
</div>

------------------

<div class="bg" style="background-image:url(http://farm4.staticflickr.com/3595/3410239848_a84804547e_b.jpg)">
<h1 style="">Parallel</h1>
</div>

------------------

<div class="bg" style="background-image:url(http://farm6.staticflickr.com/5175/5550384603_c21d01d774_b.jpg)">
<h1 style="top:auto;bottom:10%;left:6%">Lightweight</h1>
</div>

------------------

<div class="bg" style="background-image:url(http://farm6.staticflickr.com/5166/5234047189_aca32601f6_b.jpg)">
<h1 style="top:auto;left:auto;right:8%;bottom:10%">Balance</h1>
</div>

------------------

<div class="bg" style="background-image:url(http://farm4.staticflickr.com/3155/4557184853_bd070613bb_b.jpg)">
<h1 style="top:auto;bottom:10%">Perception</h1>
</div>

------------------

# &nbsp;

#Q & A

------------------

##CC images used


* http://www.flickr.com/photos/lrargerich/3120186015/
* http://www.flickr.com/photos/atwatervillage/6328994265/
* http://www.flickr.com/photos/jakescreations/88003222/
* http://www.flickr.com/photos/rene1956/3410239848/
* http://www.flickr.com/photos/jeffmollman/5550384603/
* http://www.flickr.com/photos/benheine/4557184853/
* http://www.flickr.com/photos/2c2believe/5234047189/

