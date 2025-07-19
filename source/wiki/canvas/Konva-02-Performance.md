---
wiki: canvas # 项目id
title: 性能控制
---

http://konvajs-doc.bluehymn.com/docs/performance/All_Performance_Tips.html

# Shape Caching

http://konvajs-doc.bluehymn.com/docs/performance/Shape_Caching.html

- 通过cache，可以将node转变成图片，再渲染到场景中
- 实现原理：
  - 将目标节点（Shape/Group）绘制到一个离屏的canvas上，生成一个静态图像快照（静态位图）以提高性能
  - 之后渲染时直接复用这张位图，避免重复计算和绘制，从而提高性能
- 跨域问题：
  - 如果目标节点上使用了图片，那这张图片不允许跨域获取
  - Canvas污染
    - 当canvas绘制使用到跨域图片时，浏览器会

# Layer Management 层级管理
http://konvajs-doc.bluehymn.com/docs/performance/Layer_Management.html

- konva中每个layer对应独立的canvas元素
- 在更新、移动、动态变化指定layer的元素时，不会重绘其它图层的元素
- 在konva中，stage对应一个DOM容器，layer则对应一个canvas元素
- 建议：一般不会创建过多元素，最多3-5个

使用layer区分动态画布和静态画布：
{% image ./imgs/konva/layer.gif layer分层  width:300px fancybox:true %}

