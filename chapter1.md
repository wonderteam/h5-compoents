# Carousel 组件

## 轮播图模式
![alt](http://)![轮播图demo](https://s3.wandougongzhu.cn/s/51/home_609994.png)首页顶部的模样就是轮播图模式，该模式允许手指滑动来切换。

#### 默认配置参数
```javascript
  index: 0, // 起始下标
  loop: true, // 是否循环
  durationMs: 2000, // 动画时间
  autoplay: true, // 是否自动播放
  autoplayIntervalMs: 1000, // 自动播放间隔时间
  swipable: true, // 是否允许手指滑动
  direction: 'horizontal', // 动画方向 垂直方向请写上 vertical
  currentClassName: 'current',
  activeClassName: 'active',
  el: null, // 绑定的包裹元素
  childItem: '.cont-item', // 子元素
  controlItem: '.carousel-control span', // 轮播图控制器元素
  swipeSen: 0.1 // 滑动切换的敏感度(这个参数会跟容器宽度相乘)
 ```
 
 #### 怎么使用
 >插件依赖于 zepto.js 插件，因此在使用时需要提前引入 zepto.js

使用只需两步：

 #####  1. HTML 片段
 
 ```HTML
 <div class="slider nova-carousel" style="height:2.8957528957529rem">
    <ul class="carousel-cont">
        <li class="cont-item">
            <a href="https://m.wandougongzhu.cn/activity/favor?loc=card%3A1%3A875%3A0%3Aa2179">
                <img src="https://ossimg.wandougongzhu.cn/ec97e92417ae60cf262c962b855c1ced.jpg@750w_290h_1l.jpg">
            </a>
        </li>
        <li class="cont-item">
            <a href="/index/?page_id=52">
                <img src="https://ossimg.wandougongzhu.cn/237090c97ff2153b435b3e60cb19f71b.png@750w_290h_1l.jpg">
            </a>
        </li>
    </ul>
    <div class="carousel-control">
        <span class="control-item"></span>
        <span class="control-item"></span>
    </div>
</div>
 ```
> 这段 HTML 代码里面包含了默认的 css 样式，如果就是这样的结构，后面的实例化就非常的方便，如果需要私人定制，就得仔细看下前面的默认配置项，对应修改即可。
 
##### 2. 写点儿 JS 代码

基于 Babel 编译的 js 写法：

```babel
require('coms/carousel/carousel.css'); // 引入基础的 css 样式文件

var Carousel = require('coms/carousel/carousel');
var slider = $('.slider');

new Carousel({
    el: slider,
    autoplayIntervalMs: 3000,
    durationMs: 1000
});
```
然后就好了，如果没好 多半是我没讲清楚，再看一遍🔫

还没好 就 @我 

## SWIPE （手滑）模式
![310品牌馆](https://s1.wandougongzhu.cn/s/67/swip_ba1d0f.png)
当需要显示的内容比容器大的时候，这种模式就很方便了。比如上图中，商品的数目比较多，在一行只能看到2个半，需要看到后面的就需要水平滑动。

#### 默认配置参数

```javascript
    speed: 0.5, // 惯性滑动速度
    timeConstant: 300, // 惯性滑动时间
    dir: 'horizontal' // 滑动的方向 (垂直方向 vertical )
```
 #### 怎么使用
 >插件依赖于 zepto.js 插件，因此在使用时需要提前引入 zepto.js

使用只需两步：

 #####  1. HTML 片段
 
 ```HTML
 <div class="container swiper">
    <ul>
        <li>
            <a href="/product/4363.html">
                <div class="img-box">
                    <img src="https://ossimg.wandougongzhu.cn/9289ab53877eaeb87227e544906296db.png@500w_4000h_1l.jpg">
                </div>
                <h3>ZERO PL essence化妝水 120ML</h3>
                <p class="price">¥424.03</p>
            </a>
        </li>
        <li>
            <a href="/product/4364.html">
                <div class="img-box">
                    <img src="https://ossimg.wandougongzhu.cn/d5bf801ef88cfaceccddf6e88807a3c8.png@500w_4000h_1l.jpg">
                </div>
                <h3>ZERO PL essence精华液 30ML</h3>
                <p class="price">¥567.04</p>
            </a>
        </li>
        <li>
            <a href="/product/4366.html">
                <div class="img-box">
                    <img src="https://ossimg.wandougongzhu.cn/31336285f790730e57cc63f75be940f7.png@500w_4000h_1l.jpg">
                </div>
                <h3>ZERO PL essence洗发乳 300ML</h3>
                <p class="price">¥216.82</p>
            </a>
        </li>
    </ul>
</div>
 ```
> 在 Swipe 模式，不需要引入额外的 css 样式文件，因此需要 自己实现容器里面的元素是在水平方向摆放的，比如 上面代码中的 li 元素，让他们在水平方向上布局，自动撑开 ul 元素的宽度， ul 的父容器 .swiper 一定要记得设置 overflow: hidden。
 
##### 2. 写点儿 JS 代码

基于 Babel 编译的 JS 写法：


```babel
var Carousel = require('coms/carousel/carousel');
var item = $('.swiper');

Carousel({
    mode: 'swipe', // 必须写成酱紫
    el: item,
    dir: 'horizontal',
    speed: 0.5
});
 ```