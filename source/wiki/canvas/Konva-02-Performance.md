---
wiki: canvas # 项目id
title: 性能控制
---

http://konvajs-doc.bluehymn.com/docs/performance/All_Performance_Tips.html

# Shape Caching

http://konvajs-doc.bluehymn.com/docs/performance/Shape_Caching.html
https://konvajs.org/api/Konva.Node.html#cache
- 通过cache，可以将node转变成图片，再渲染到场景中
  - 适用于需要大量绘制重复元素的场景
- 实现原理：
  - 将目标节点（Shape/Group）绘制到一个离屏的canvas上，生成一个静态图像快照（静态位图）以提高性能
  - 之后渲染时直接复用这张位图，避免重复计算和绘制，从而提高性能
  - 类似于蛋糕模具的功能
- 跨域问题：
  - 如果目标节点上使用了图片，那这张图片不允许跨域获取
  - Canvas污染
    - https://developer.mozilla.org/zh-CN/docs/Web/HTML/How_to/CORS_enabled_image
    - 当canvas绘制使用到跨域图片时，浏览器会标记该Canvas为“污染”状态
    - 受污染的Canvas无法读取像素数据
- cache无法自动检测到节点的尺寸，因此需要指定x/y/width/height等变量

{% image ./imgs/konva/shapeCache.png 使用cache绘制大量重复图形  width:300px fancybox:true %}


# Layer Management 层级管理
http://konvajs-doc.bluehymn.com/docs/performance/Layer_Management.html

- konva中每个layer对应独立的canvas元素
- 在更新、移动、动态变化指定layer的元素时，不会重绘其它图层的元素
- 在konva中，stage对应一个DOM容器，layer则对应一个canvas元素
- 建议：一般不会创建过多元素，最多3-5个

使用layer区分动态画布和静态画布：
{% image ./imgs/konva/layer.gif layer分层  width:300px fancybox:true %}

# Optimize Animation Performance 优化动画性能

使用animation函数控制动画帧的时候，
如果在某一帧没有需要更新的内容，可以通过返回false的方式禁止画布刷新
- 优化点：减少帧刷新次数
```javascript
// 振幅
const amplitude = 100
// 周期
const period = 2000
const centerX = stage.width() / 2
const anim = new Konva.Animation(function (frame) {
  if (frame.time % (period * 2) < period) {
    // 第一个period周期内更新
    hexagon.x(
      amplitude * Math.cos((frame.time * 2 * Math.PI) / period) + centerX
    )
  } else {
    // 第二个周期停止刷新
    return false
  }
}, layer)
anim.start()
```
{% image ./imgs/konva/OptimizeAnimation.gif 通过减少动画帧实现优化  width:300px fancybox:true %}

# Batch Draw 批量绘制

http://konvajs-doc.bluehymn.com/docs/performance/Batch_Draw.html

- 典型场景
  - 监听鼠标位置更新单个元素时，会引起整张画布频繁地更新
- 这种情况可能会导致极度密集的重绘
- 可以通过batchDraw，将重绘系统挂载到动画引擎上

```javascript
// 整体重绘
layer.draw()
// 批量重绘
layer.batchDraw()
```

# Shape Redraw 图形重绘

```javascript
// 画布重绘
layer.draw()
// 节点重绘
shape.draw()
```

Konva支持单独重新绘制某个图形，并且不会刷新整张画布，
但重绘节点必须满足如下条件：
- 节点不能是半透明的
- 节点不需要与其他节点重叠
  - 重绘的节点会覆盖在其他节点的上层
- 节点绘制结果不需要依赖下层内容（比如没有混合模式）


{% image ./imgs/konva/ShapeRedraw.gif 重绘单个节点  width:300px fancybox:true %}
