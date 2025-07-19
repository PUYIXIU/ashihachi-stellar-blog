---
wiki: canvas # 项目id
title: Polygon
---

- 官方文档：https://alexbol99.github.io/flatten-js/Polygon.html
- observable相关教程：https://observablehq.com/@alexbol99/flattenjs-tutorials-polygons

# Polygon 多边形模型

flatten的Polygon被由2个部分组成：
- edges：segment（线段）或者arc（弧线）
- faces：封闭的面
  - 面中的边形成的是环形的双向链表，因此可以向前和向后遍历这些边
 
## Polygon顶点的方向

可以通过addFace在一个Polygon中添加多个face，
- 如果每个face彼此间都没有交点，那么都算作独立的完整部分
- 如果face之间存在交叉区域，需要考虑到顺逆时针
  - 重叠路径的填充一般有2种规则（https://www.zhangxinxu.com/wordpress/2018/10/nonzero-evenodd-fill-mode-rule/）：
    - nonzero
      - 从任意点O射出一条射线，取射线和路径（AB）的交点P，如果OP和AP/BP组成顺时针方向+1，逆时针方向-1,
      - 最终得分不是0，点在内部，是0，点在外部
    - evenodd
      - 从任意点O射出一条射线，取射线和所有路径的交点
      - 交点数是单数，在内部，交点数是偶数，在外部
  - flatten中一律选用evenodd规则
    - 部分路径重叠的图形
      - 最终图形去除掉重叠区域
    - 对于包含关系的图形，分为island和hole区域
      - 包含图形为island，被包含图形为hole






## 构造函数

- 通过seg/arc组成的数组创建
- 通过点数组创建
- 通过box/circle实例创建
- 通过代表点的数字对数组创建

```js
new Polygon()
```

## 属性

- edges 边集合
    - PlanarSet类型
- faces 面集合
    - PlanarSet类型
- vertices 顶点集合

---

- edges
- faces
- box
- vertices
- addFace
- addVertex
- area
- cut
- contains
- cutWithLine
- deleteFace
- distanceTo
- dpath
- findEdgeByPoint
- intersect
- isEmpty
- isValid
- reacreateFaces
- removeChain
- removeEndVertex
- reverse
- rotate
- scale
- splitToIslands
- svg
- toArray
- toJSON
- transform
- translate

## 方法
