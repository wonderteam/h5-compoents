# Carousel 组件

## 轮播图模式
![alt](http://)![轮播图demo](https://s3.wandougongzhu.cn/s/51/home_609994.png)首页顶部的模样就是轮播图模式，该模式允许手指滑动来切换。

## 主要配置参数
>index: 0, // 起始下标
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
 
 