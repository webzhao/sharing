<style>
.reveal h1, .reveal h2, .reveal h3 {
    margin-bottom: 1em;
}
.reveal p {
    margin-bottom: 0.5em;
}
</style>

<h1 class="tag-microsharing">Android中的长度单位</h1>
### 赵文博@奇舞团
### zhaowenbo@360.cn

----------

## <strong style="color:#f44;font-family:Georgia">3</strong>种长度单位：
### 物理长度
### 屏幕像素
### 相对长度

----------

## 物理长度

----------

## mm
<p class="fragment">millimeter，毫米。</p>
<p class="fragment">成年人食指平均宽度为<em>16mm</em>。</p>

----------

## in
<p class="fragment">inch，英寸。</p>
<p class="fragment">iPhone 5屏幕对角线长度为<em>5in</em>。</p>

----------

## pt
<p class="fragment">point，点、磅。</p>
<p class="fragment"><em>1/72</em>英寸。一张A4纸宽度为<em>595pt</em>。</p>

----------

<section data-state="blue">
    <h2>什么情况下用物理单位？</h2>
</section>

----------

<section data-state="bg-ruler">
    <style type="text/css">
        .bg-ruler body {background-image: url(img/units/ruler.png)}
    </style>
</section>

----------

## 屏幕像素

----------

## px
<p class="fragment">对应显示屏的物理分辨率</p>
<p class="fragment"><em>4.4</em>英寸的HTC Magic分辨率为<em>320 X 480</em></p>
<p class="fragment"><em>4.7</em>英寸的HTC One分辨率为<em>1920 X 1080</em></p>

----------

<div style="position: relative;max-width:100%;max-height:100%">
    <img src="img/units/htcone.png" width="100%">
    <div style="position:absolute;width:22.2%;height:52%;top:23%;left:44.6%;background:#fff;"><p style="color:#000;font-size:12px;position:absolute;top:45%;width:100%;-webkit-transform:scale(0.5);transform:scale(0.5)">这是24px的文字</p></div>
</div>

----------

<section data-state="red">
    <h2>不要使用px做单位！</h2>
</section>

----------

## 相对单位

----------

## dp
<p class="fragment">Density-independent Pixels</p>
<p class="fragment">一个<em>抽象</em>的长度单位</p>
<p class="fragment">在<em>160dpi</em>的屏幕上，1dp等于1px</p>
<p class="fragment">dpi÷160 = 1dp÷1px</p>

----------

<section data-state="green">
    <h2>推荐使用dp做单位！</h2>
</section>

----------

## sp
<p class="fragment">Scale-independent Pixels</p>
<p class="fragment">和dp相同，除非...</p>

----------

<section data-state="dark">
    <img src="img/units/setting.png">
</section>

----------

<section data-state="green">
    <h2>设置字体大小时请使用sp做单位！</h2>
</section>

----------

## <del>QA</del>
#&nbsp;
<h4 class="fragment">因为每个人都听懂了</h4>

----------

<section data-state="orange">
    <h1 style="font-size: 5em;">:-)</h1>
</section>

----------

<section style="text-align:left">
<h2>参考资料</h2>
<p>http://developer.android.com/guide/topics/resources/more-resources.html#Dimension</p>
<p>http://en.wikipedia.org/wiki/List_of_displays_by_pixel_density</p>
<p>
    <img src="http://creativecommons.org/wp-content/themes/creativecommons.org/images/chooser_cc.png">
    <img src="http://creativecommons.org/wp-content/themes/creativecommons.org/images/chooser_by.png" >
</p>
</section>

