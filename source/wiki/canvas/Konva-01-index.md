---
wiki: canvas # 项目id
title: Knova介绍
---

- <a href="http://konvajs-doc.bluehymn.com/docs/overview.html">Konva文档</a>

# Konva

特点：
- 高性能动画、补间、节点嵌套（甚至包含数千个图形）
- 布局、滤镜、缓存、事件绑定

结构：
- 树结构
  - Stage舞台 → Layer图层 → Group组 → Shape图形
  - 根节点为Stage
  - 叶子节点为Shape
- 所有结构都是虚拟节点，类似于Html的DOM节点
- 每个layer有2个canvas渲染器（QA）
  - 场景渲染器：输出所看内容（类似GPU）
  - 图形命中检测渲染器：在隐藏的canvas里用于高性能检测事件

概念：
- 基本图形：
  - 支持Rect矩形、Circle圆形、Ellipse椭圆、Star星形、Polygon多边形、Regular Polygon等边多边形
  - Line直线、Spline样条曲线、Blob团型
  - Image图片
  - Text文字、TextPath路径文字、Label标签
  - SVG Path矢量路径、custom Shape自定义图形
- 样式
  - fill填充（solid color实色、gradients渐变、images图片）
  - stroke线条（color线条颜色、width线宽）
  - shadow阴影（color颜色、offset偏移、opacity透明度、blur模糊）
  - opacity透明度
- 事件
  - 输入事件
    - click、dblclick、mouseover、tap、dbltap、touchstart
  - attributes变化事件
    - scaleXChange、fillChange
  - 拖放事件
    - dragStart、dragmove
- 滤镜
- 动画
- 选择器
  - 可以根据type、id、name进行选择
- 序列化/反序列化
  - 将对象保存为Json格式
  - 通过json创建对象
- 性能
  - 缓存Caching，允许在buffer canvas里绘制元素，然后将buffer canvas中的元素绘制到场景（QA）
  - 图层控制