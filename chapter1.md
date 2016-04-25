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
  direction: 'horizontal', // 动画方向
  currentClassName: 'current',
  activeClassName: 'active',
  el: null, // 绑定的包裹元素
  childItem: '.cont-item', // 子元素
  controlItem: '.carousel-control span', // 轮播图控制器元素
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

