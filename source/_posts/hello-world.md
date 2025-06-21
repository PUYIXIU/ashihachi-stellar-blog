---
menu_id: post
title: Stellar使用指南
date: 2025-02-21 13:02:49
tags: [hexo]
categories: []
description:
password:
# 参考资料
references:
  - "[Stellar官方文档](https://xaoxuu.com/wiki/stellar/pages/)"
  - "[hexo博客](https://xaoxuu.com/wiki/stellar/pages/)"
# 封面
cover: /images/covers/java1.jpg # 动态拉取：workout,strava
# 横幅
banner: /images/covers/java1.jpg # 动态拉取：workout,strava
# 海报（可选，全图封面卡片）
#poster:
#    headline: 大标题 # 必填
#    topic: 标题上方的小字 #可选
#    caption: 标题下方小字 # 可选
#    color: red #可选

# 插件
sticky: # 数字越大越靠前
mermaid:
katex:
mathjax:
# 可选
topic: # 专栏 id
author:
comments: # 设置 false 禁止评论
indexing: # 设置 false 避免被搜索
breadcrumb: # 设置 false 隐藏面包屑导航
leftbar: # []
rightbar:
h1: # 设置为 '' 隐藏标题
type: # tech | story
repo: xaoxuu/hexo-theme-stellar
---

随便写点什么吧

<!-- more -->

{% link https://xaoxuu.com/blog/20221029/ icon:https://xaoxuu.com/assets/xaoxuu/avatar/rect-256@2x.png Stellar-每个人的独立博客 %}

{% link https://hexo.io/zh-cn/docs/ icon:https://hexo.io/logo.svg 文档 | Hexo %}

## 1️⃣ 基本使用

### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/express/">💭 表达类标签</a>

#### emoji 表情包

{% emoji 蛋糕 %}
{% emoji twemoji 1f634 %}
{% emoji qq 咖啡 %}
{% emoji tieba 礼物 height:2em %}
{% emoji blobcat blobcatheartpride height:3em %}

```markdown
{% emoji 蛋糕 %}
{% emoji twemoji 1f634 %}
{% emoji qq 咖啡 %}
{% emoji tieba 礼物 height:2em %}
{% emoji blobcat blobcatheartpride height:3em %}
```

- <a href="https://gcore.jsdelivr.net/gh/norevi/waline-blobcatemojis@1.0/blobs/">blobcat 表情库</a>

#### icon 图标标签

可以在任意位置插入图标：{% icon octopus:32 %}

{% icon octopus:32 color:red %}
{% icon octopus:32 color:orange %}
{% icon octopus:32 color:yellow %}
{% icon octopus:32 color:green %}
{% icon octopus:32 color:cyan %}
{% icon octopus:32 color:blue %}
{% icon octopus:32 color:purple %}

```markdown
可以在任意位置插入图标：{% icon octopus:32 %}

{% icon octopus:32 color:red %}
{% icon octopus:32 color:orange %}
{% icon octopus:32 color:yellow %}
{% icon octopus:32 color:green %}
{% icon octopus:32 color:cyan %}
{% icon octopus:32 color:blue %}
{% icon octopus:32 color:purple %}
```

#### mark 标记

{% mark 默认 %}
{% mark 红 color:red %}
{% mark 橙 color:orange %}
{% mark 黄 color:yellow %}
{% mark 绿 color:green %}
{% mark 青 color:cyan %}
{% mark 蓝 color:blue %}
{% mark 紫 color:purple %}
{% mark 亮 color:light %}
{% mark 暗 color:dark %}
{% mark 警告 color:warning %}
{% mark 错误 color:error %}

```markdown
{% mark 默认 %}
{% mark 红 color:red %}
{% mark 橙 color:orange %}
{% mark 黄 color:yellow %}
{% mark 绿 color:green %}
{% mark 青 color:cyan %}
{% mark 蓝 color:blue %}
{% mark 紫 color:purple %}
{% mark 亮 color:light %}
{% mark 暗 color:dark %}
{% mark 警告 color:warning %}
{% mark 错误 color:error %}
```

#### hashtag 标签

{% hashtag Stellar https://xaoxuu.com/wiki/stellar/ %}
{% hashtag Hexo https://hexo.io/ color:blue %}
{% hashtag GitHub https://github.com/xaoxuu/ color:dark %}

```markdown
{% hashtag Stellar https://xaoxuu.com/wiki/stellar/ %}
{% hashtag Hexo https://hexo.io/ color:blue %}
{% hashtag GitHub https://github.com/xaoxuu/ color:dark %}
```

#### image 图片标签

```markdown
{% image src [description] [download:bool/string] [width:px] [padding:px] [bg:hex] [fancybox:bool/string] %}
```

```yml 参数说明
src: 图片地址
description: 图片描述
download: href # 下载地址，设置此值后鼠标放在图片上会显示下载地址，如果下载地址为图片地址，可以设置为 true
width: 200px # 图片宽度
padding: 16px # 图片四周填充宽度
bg: "#ffffff" # 图片区域背景颜色，16进制
fancybox: href # fancybox 放大地址，设置此值后会调用该链接放大，如果放大地址为图片地址，可以设置为 true
```

##### 横向铺满图片

{% image /images/base/test.jpg 猫猫镇楼 download:true fancybox:true %}

```markdown
{% image /images/base/test.jpg 猫猫镇楼 download:true fancybox:true %}
```

##### 竖图（小图）优化

{% image /images/base/test2.jpg 猫猫镇楼 width:300px padding:10px bg:var(--card) download:true fancybox:true %}

```markdown
{% image /images/base/test2.jpg 猫猫镇楼 width:300px padding:10px bg:var(--card) download:true fancybox:true %}
```

#### quote 引用

{% quot 居中引用 %}

```markdown
{% quot 居中引用 %}
```

{% quot 自定义配置 icon:coffee %}

```markdown
{% quot 自定义配置 icon:coffee %}
```

{% quot 也可以指定任意图标 prefix:cat-head:64 suffix:dog-head:64 %}

```markdown
{% quot 也可以指定任意图标 prefix:cat-head:64 suffix:dog-head:64 %}
```

{% quot 特别引用 el:h4 icon:talk %}

```markdown
{% quot 特别引用 el:h4 icon:talk %}
```

#### poetry 诗词

{% poetry 黑客也是创造者，与画家、建筑师、作家一样 author:保罗·格雷厄姆 footer:《黑客与画家》节选 %}
黑客搞懂 **“计算理论”**（theory of computation）的必要性，
与画家搞懂颜料化学成分的必要性差不多大。
{% endpoetry %}

```markdown
{% poetry 黑客也是创造者，与画家、建筑师、作家一样 author:保罗·格雷厄姆 footer:《黑客与画家》节选 %}
黑客搞懂 **“计算理论”**（theory of computation）的必要性，
与画家搞懂颜料化学成分的必要性差不多大。
{% endpoetry %}
```

#### paper 纸张标签

{% paper style:underline title:《忏悔录》节选 author:卢梭 date:《忏悔录》 footer:第二、三章节选 %}

<!-- line left -->

第二章

<!-- paragraph -->

这话不是根据我自己的经验，而是根据我的观察，因为我知道自己的经验是完全不适于别人的。

<!-- line right -->

第三章

<!-- paragraph -->

可是我无论怎样用功，进步还是很小。说起来真是奇怪，我虽然也有相当的理解能力，我却从来不能从老师那里——父亲和朗拜尔西埃先生是例外——学到什么东西。
我另外的一些知识，都是我自学来的，这个以后就会清楚的。我那不能忍受任何束缚的思想不肯服从时间的限制；担心学不会的心情妨碍着我专心听讲：
生怕由于自己不懂而让教我的人着急的心情促使我装懂，教的人一直往下教，我却什么也不懂。**我想按自己的步调行动，不愿顺从别人的步调。**
{% endpaper %}

```markdown
{% paper style:underline title:《忏悔录》节选 author:卢梭 date:《忏悔录》 footer:第二、三章节选 %}

<!-- line left -->

第二章

<!-- paragraph -->

这话不是根据我自己的经验，而是根据我的观察，因为我知道自己的经验是完全不适于别人的。

<!-- line right -->

第三章

<!-- paragraph -->

可是我无论怎样用功，进步还是很小。说起来真是奇怪，我虽然也有相当的理解能力，我却从来不能从老师那里——父亲和朗拜尔西埃先生是例外——学到什么东西。
我另外的一些知识，都是我自学来的，这个以后就会清楚的。我那不能忍受任何束缚的思想不肯服从时间的限制；担心学不会的心情妨碍着我专心听讲：
生怕由于自己不懂而让教我的人着急的心情促使我装懂，教的人一直往下教，我却什么也不懂。**我想按自己的步调行动，不愿顺从别人的步调。**
{% endpaper %}
```

- style：underline | 无，是否带下划线
- title：标题
- author：作者
- date：日期
- footer：页脚

```markdown 正文可设置段落格式
<!-- section 小节标题 -->

小节标题，居中显示

<!-- paragraph -->

段落，首行缩进两个字符

<!-- line left -->

段落左对齐

<!-- line right -->

段落右对齐
```

#### reel 卷轴标签

{% reel 南陵别儿童入京 author:李白 date:全唐诗 footer:节选 %}
白酒新熟山中归，黄鸡啄黍秋正肥。
呼童烹鸡酌白酒，儿女嬉笑牵人衣。
高歌取醉欲自慰，起舞落日争光辉。
游说万乘苦不早，著鞭跨马涉远道。
会稽愚妇轻买臣，余亦辞家西入秦。
仰天大笑出门去，我辈岂是蓬蒿人。
{% endreel %}

```markdown
{% reel 南陵别儿童入京 author:李白 date:全唐诗 footer:节选 %}
白酒新熟山中归，黄鸡啄黍秋正肥。
呼童烹鸡酌白酒，儿女嬉笑牵人衣。
高歌取醉欲自慰，起舞落日争光辉。
游说万乘苦不早，著鞭跨马涉远道。
会稽愚妇轻买臣，余亦辞家西入秦。
仰天大笑出门去，我辈岂是蓬蒿人。
{% endreel %}
```

#### note 备注块

{% note 备注标题 备注内容 %}

```markdown
- color: red、orange、amber、yellow、green、cyan、blue、purple、light、dark、warning、error
  {% note 备注标题 备注内容 [color:color] %}
```

#### link 链接卡片

{% link https://xaoxuu.com/blog/20221029/ icon:https://xaoxuu.com/assets/xaoxuu/avatar/rect-256@2x.png Stellar-每个人的独立博客 %}

```markdown
{% link href [title] [icon:src] [desc:true/false] %}
```

#### button 按钮

{% button 文档 /wiki  icon:solar:notebook-bookmark-bold-duotone %}
{% button 探索 /explore color:yellow icon:solar:planet-bold-duotone size:xs %}

```markdown
- size: 默认 | xs（最小号）
  {% button text url [icon:key/src] [color:color] [size:xs] %}
  {% button 文档 /wiki  icon:solar:notebook-bookmark-bold-duotone %}
  {% button 探索 /explore  icon:solar:planet-bold-duotone size:xs %}
```

#### okr 目标管理

- okr：Objectives and Key Results

{% okr o1 %}

2025 年小目标：全球旅行 ✈️
从家门口的小公园开始吧

<!-- okr kr1 percent:1 -->

重构 tag-plugins 和 wiki 系统

- 当 {% mark KR %} 进度为 100% 时，标签默认显示为 {% mark color:green 已完成 %}
- 当 {% mark KR %} 未设置进度时，默认为 {% mark 0% %}
- 当 {% mark O %} 未设置进度时，则显示所有 {% mark KR %} 进度平均值

<!-- okr kr2 percent:0.9 status:off_track -->

完成主要页面设计稿
{% tabs align:left %}

<!-- tab 小提示1 -->

您可以在 \_config.yml 文件中修改标签的颜色和文案

<!-- tab 小提示2 -->

您可以在 \_config.yml 文件中增加任意的标签配置
{% endtabs %}

<!-- okr kr3 percent:-0.12 status:unfinished -->

完成前置准备工作
{% checkbox 在咸水和海滩之间找一亩地 %}
{% checkbox 求出圆周率后15位 %}
{% checkbox 找出宇宙的终极逻辑 %}
{% checkbox 去地狱里走两步 %}

<!-- okr kr-4 status:at_risk -->

开发、测试和发布

{% endokr %}

#### copy 复制行

{% copy curl -s https://sh.xaox.cc/install | sh %}
{% copy curl -s https://sh.xaox.cc/install | sh prefix:$ %}
{% copy git:https xaoxuu.com/hexo-theme-stellar %}
{% copy git:ssh xaoxuu.com/hexo-theme-stellar %}
{% copy git:gh xaoxuu.com/hexo-theme-stellar %}

```markdown
{% copy curl -s https://sh.xaox.cc/install | sh prefix:$ %}
{% copy git:https xaoxuu.com/hexo-theme-stellar %}
{% copy git:ssh xaoxuu.com/hexo-theme-stellar %}
{% copy git:gh xaoxuu.com/hexo-theme-stellar %}
```

#### radio 单选

{% radio 没有勾选的单选框 %}
{% radio checked:true 已勾选的单选框 %}

{% radio 没有勾选的单选框 color:green %}
{% radio checked:true 已勾选的单选框 color:green %}

```markdown
{% radio 没有勾选的单选框 %}
{% radio checked:true 已勾选的单选框 %}
```

- checked：true | false
- color：颜色

#### checkbox 复选

{% checkbox 普通的没有勾选的复选框 %}
{% checkbox checked:true 普通的已勾选的复选框 %}
{% checkbox symbol:plus color:green checked:true 显示为加号的绿色的已勾选的复选框 %}
{% checkbox symbol:minus color:yellow checked:true 显示为减号的黄色的已勾选的复选框 %}
{% checkbox symbol:times color:red checked:true 显示为乘号的红色的已勾选的复选框 %}

```markdown
{% checkbox 普通的没有勾选的复选框 %}
{% checkbox checked:true 普通的已勾选的复选框 %}
{% checkbox symbol:plus color:green checked:true 显示为加号的绿色的已勾选的复选框 %}
{% checkbox symbol:minus color:yellow checked:true 显示为减号的黄色的已勾选的复选框 %}
{% checkbox symbol:times color:red checked:true 显示为乘号的红色的已勾选的复选框 %}
```

- checked：true | false
- symbol： plus | minus | times
- color：颜色

#### audio 音频标签

- 支持音乐外链和网易云音乐

{% audio https://github.com/volantis-x/volantis-docs/releases/download/assets/Lumia1020.mp3 %}
{% audio netease:4919517 %}
{% audio type:2 netease:4919517 autoplay:0 %}

```markdown
{% audio https://github.com/volantis-x/volantis-docs/releases/download/assets/Lumia1020.mp3 %}
{% audio netease:4919517 %}
{% audio type:2 netease:4919517 autoplay:0 %}
```

- type
  - 2 表示歌曲
  - 0 表示歌单
- netease: 歌曲/歌单 id，在网易云分享链接中能找到
- autoplay
  - 1 表示自动播放
  - 0 表示手动播放

#### video 视频标签

{% video bilibili:BV1x44y1K7ho %}
{% video youtube:FDUk0Kcte9A %}

```markdown
{% video bilibili:BV1x44y1K7ho %}
{% video youtube:FDUk0Kcte9A %}

- width: 500px # 单位 80% 20em 100mm
- autoplay: 1/0 # 1：自动播放 0：手动播放
```

#### navbar 导航栏

{% navbar active:/wiki/ [文章](/) [项目](/wiki/) [留言](#comments) [GitHub](https://github.com/xaoxuu/) %}

```markdown
- 由链接组成的导航栏
  {% navbar active:/wiki/ [文章](/) [项目](/wiki/) [留言](#comments) [GitHub](https://github.com/xaoxuu/) %}
```

#### frame 设备框架

{% frame iphone11 img:/images/base/phone.jpg focus:top %}

```markdown
{% frame iphone11 img:/assets/wiki/prohud/toast/demo-loading.png video:/assets/wiki/prohud/toast/demo-loading.mp4 focus:top %}
```

#### 文本修饰标签集

- 这是 {% psw 密码 %} 标签
- 这是 {% u 下划线 %} 标签
- 这是 {% emp 着重号 %} 标签
- 这是 {% wavy 波浪线 %} 标签
- 这是 {% del 删除线 %} 标签
- 这是 {% sup 上角标 color:red %} 标签
- 这是 {% sub 下角标 %} 标签
- 这是 {% kbd 键盘样式 %} 标签，试一试：{% kbd ⌘ %} + {% kbd D %}

```markdown
- 这是 {% psw 密码 %} 标签
- 这是 {% u 下划线 %} 标签
- 这是 {% emp 着重号 %} 标签
- 这是 {% wavy 波浪线 %} 标签
- 这是 {% del 删除线 %} 标签
- 这是 {% sup 上角标 color:red %} 标签
- 这是 {% sub 下角标 %} 标签
- 这是 {% kbd 键盘样式 %} 标签，试一试：{% kbd ⌘ %} + {% kbd D %}
```

### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data">🔢 数据类标签</a>

#### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#timeline-%E6%97%B6%E9%97%B4%E7%BA%BF">timeline 时间线</a>

{% timeline %}

<!-- node 2025 年 2 月 25 日 -->

今天科三考试最后熄火，还好我平时练车熄火太多所以很熟，回空挡打火换一档完成靠边停车，贴着及格线过了，激动的心颤抖的手
{% image /images/meme/idrive.jpg width:300px %}

<!-- node 2025 年 2 月 24 日 -->

下午科目三模拟 3 把连挂，教练差点气撅过去
{% image /images/meme/acat.jpg width:200px %}
{% endtimeline %}

```markdown
{% timeline %}

<!-- node 2025 年 2 月 25 日 -->

今天科三考试最后熄火，还好我平时练车熄火太多所以很熟，回空挡打火换一档完成靠边停车，贴着及格线过了，激动的心颤抖的手
{% image /images/meme/idrive.jpg width:300px %}

<!-- node 2025 年 2 月 24 日 -->

下午科目三模拟 3 把连挂，教练差点气撅过去
{% image /images/meme/acat.jpg width:200px %}
{% endtimeline %}
```

> <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#%E5%8A%A8%E6%80%81%E6%97%B6%E9%97%B4%E7%BA%BF">动态时间线参考</a>

#### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#friends-%E5%8F%8B%E9%93%BE">friends 友链</a>

{% friends exm_blogs %}

```yaml /source/_data/links/exm_blogs.yml
- title: 明眸如初
  url: https://www.zywvvd.com/
  cover:
  icon: https://www.zywvvd.com/image/avatar.png
  description: Hexo-Butterfly搭建，访问统计的3d模型非常炫酷
```

```markdown
{% friends exm_blogs %}
```

#### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#sites-%E7%BD%91%E7%AB%99%E5%8D%A1%E7%89%87">sites 网站卡片</a>

{% sites sites_design %}

```yml /source/_data/links/sites_design.yml
- title: unsplash
  url: https://unsplash.com/
  cover: /images/site/unsplash.png
  icon: https://unsplash.com/favicon.ico
  description: 高质量图片分享平台
```

```markdown
{% sites sites_design %}
```

#### ghcard 卡片

{% link https://github.com/anuraghazra/github-readme-stats icon:/images/icons/github.png GitHub Card API %}

{% ghcard puyixiu theme:dark %}
{% ghcard PUYIXIU/ashihachi-stellar-blog theme:dark %}

```markdown
{% ghcard puyixiu theme:dark %}
{% ghcard PUYIXIU/ashihachi-stellar-blog theme:dark %}
```

### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/container/">📦 容器类标签</a>

#### box 盒子容器

```markdown
{% box [title] [color:color] [child:codeblock/tabs] %}
{% endbox %}
```

```yaml 参数说明
title: 标题
color: red/orange/yellow/green/cyan/blue/purple/light/dark
child: codeblock | tabs
```

#### folding 折叠容器

{% folding 展开详情 %}

```markdown
{% folding title [codeblock:bool] [open:bool] [color:color] %}
content
{% endfolding %}
```

```yaml 参数说明
codeblock: true | false
open: true | false
color: red/orange/yellow/green/cyan/blue/purple/light/dark
```

{% endfolding %}

#### folders 聚合折叠容器

{% folders %}

<!-- folder 抽屉A -->

这个抽屉是空的

<!-- folder 抽屉B -->

这个抽屉是空的

<!-- folder 抽屉C -->

找到了一把手电筒
{% endfolders %}

```markdown
{% folders %}

<!-- folder 抽屉A -->

这个抽屉是空的

<!-- folder 抽屉B -->

这个抽屉是空的

<!-- folder 抽屉C -->

找到了一把手电筒
{% endfolders %}
```

#### tabs 分栏容器

{% tabs active:2 align:center %}

<!-- tab 图片 -->

{% image /images/base/test.jpg width:300px %}

<!-- tab 代码块 -->

```javascript
let x = 123;
console.log("Hello World");
```

<!-- tab 表格 -->

| a   | b   | c   |
| --- | --- | --- |
| a1  | b1  | c1  |
| a2  | b2  | c2  |

{% endtabs %}

```markdown
{% tabs active:2 align:center %}

<!-- tab 图片 -->

{% image /images/base/test.jpg width:300px %}

<!-- tab 代码块 -->

content

<!-- tab 表格 -->

| a   | b   | c   |
| --- | --- | --- |
| a1  | b1  | c1  |
| a2  | b2  | c2  |

{% endtabs %}
```

```yaml 参数配置
align: center
active: 激活标签
```

#### grid 网格分区

{% quot el:h4 动态列数 %}

```yaml 默认布局
1列: 240px - 480px
2列: 480px - 720px
3列: >720px
```

{% grid %}

<!-- cell -->

{% image /images/photos/gui_shan_han_mu.jpg fancybox:true %}

<!-- cell -->

<a href="http://kaogu.cssn.cn/zwb/kgyd/kgbk/200808/t20080822_3912527.shtml">龟山汉墓</a>

崖洞墓是在石山中开凿墓室的一种墓葬形制，地下空间的布置虽然比较自由，但都最大限度象征和模仿了地上生活的内容。目前所知的汉代诸侯王崖洞墓分布在江苏徐州、河北满城等地，共有三十多座。

主要集中于黄淮之间的东部地区。徐州北洞山汉墓和狮子山汉墓就是西汉前期的两座大型楚王崖洞墓。

> 刘注墓原棺室的室顶正好对着山的最高处，真不知道在山里作业的工匠是怎么确定的位置。不过后来因为顶上裂开了，才把棺椁移到现在的墓室里。

{% endgrid %}

```markdown
{% grid %}

<!-- cell -->

content left

<!-- cell -->

content right
{% endgrid %}
```

```yaml 参数配置
w: 一列的宽度
c: 固定列数
bg: box | card
gap: 每列之间的间距，默认16px
br: 圆角半径
```

{% quot el:h4 固定列数 %}

```markdown
{% grid c:2 %}
...
{% endgrid %}
```

{% quot el:h4 背景样式 %}

{% grid bg:box w:150px %}

<!-- cell -->

cell 1

<!-- cell -->

cell 2

<!-- cell -->

cell 3

<!-- cell -->

cell 4
{% endgrid %}

{% grid bg:card w:150px %}

<!-- cell -->

cell 1

<!-- cell -->

cell 2

<!-- cell -->

cell 3

<!-- cell -->

cell 4
{% endgrid %}

#### gallery 图库

{% box 类似效果 %}

- <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/container/#albums-%E4%B8%93%E8%BE%91%E5%AE%B9%E5%99%A8">albums 专辑容器</a>
- <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/container/#posters-%E6%B5%B7%E6%8A%A5%E5%AE%B9%E5%99%A8">posters 海报容器</a>

{% endbox %}

{% gallery %}
![@tianhao_wang](https://images.unsplash.com/photo-1688142202243-e218ad203952?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDYzfEZ6bzN6dU9ITjZ3fHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1700994630045-f7a20df6d92e?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwcm9maWxlLXBhZ2V8MjN8fHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1533274221104-015a584a1005?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDE4fGJvOGpRS1RhRTBZfHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1539604214100-ab860d9082e0?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDIxfGJvOGpRS1RhRTBZfHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1698843848092-588f9c1bb0bd?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwcm9maWxlLXBhZ2V8Mzh8fHxlbnwwfHx8fHw%3D)
![@vklemen](https://images.unsplash.com/photo-1516571748831-5d81767b788d?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
{% endgallery %}

```markdown
{% gallery %}
![@tianhao_wang](https://images.unsplash.com/photo-1688142202243-e218ad203952?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDYzfEZ6bzN6dU9ITjZ3fHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1700994630045-f7a20df6d92e?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwcm9maWxlLXBhZ2V8MjN8fHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1533274221104-015a584a1005?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDE4fGJvOGpRS1RhRTBZfHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1539604214100-ab860d9082e0?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHx0b3BpYy1mZWVkfDIxfGJvOGpRS1RhRTBZfHxlbnwwfHx8fHw%3D)
![@eberhard](https://images.unsplash.com/photo-1698843848092-588f9c1bb0bd?w=800&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwcm9maWxlLXBhZ2V8Mzh8fHxlbnwwfHx8fHw%3D)
![@vklemen](https://images.unsplash.com/photo-1516571748831-5d81767b788d?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D)
{% endgallery %}
```

#### banner 横幅容器

```yaml 参数配置
bg: 背景
avatar: 头像
link: 跳转链接
```

{% quot el:h4 独立页面 %}

{% banner 随记 bg:/images/covers/coffee1.jpg %}
{% navbar active:/notes/ [随记](/notes/) [收藏](/bookmark/) %}
{% endbanner %}

```markdown
{% banner 随记 bg:/images/covers/coffee1.jpg %}
{% navbar active:/notes/ [随记](/notes/) [收藏](/bookmark/) %}
{% endbanner %}
```

{% quot el:h4 用户资料页 %}

{% banner 足八桑 八条腿各有想法 bg:/images/covers/pixel_universe.png avatar:/images/base/avatar.png %}
{% endbanner %}

```markdown
{% banner 足八桑 八条腿各有想法 bg:/images/covers/pixel_universe.png avatar:/images/base/avatar.png %}
{% endbanner %}
```

#### swiper 轮播容器

{% swiper effect:cards %}
![](https://images.unsplash.com/photo-1625171515821-1870deb2743b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
![](https://images.unsplash.com/photo-1528283648649-33347faa5d9e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
![](https://images.unsplash.com/photo-1542272201-b1ca555f8505?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
![](https://images.unsplash.com/photo-1524797905120-92940d3a18d6?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
{% endswiper %}

```markdown
{% swiper effect:cards %}
![](https://images.unsplash.com/photo-1625171515821-1870deb2743b?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
![](https://images.unsplash.com/photo-1528283648649-33347faa5d9e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
![](https://images.unsplash.com/photo-1542272201-b1ca555f8505?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
![](https://images.unsplash.com/photo-1524797905120-92940d3a18d6?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80)
{% endswiper %}
```

```yaml 参数配置
effect: cards | coverflow
width: min | max
```

## 2️⃣ 进阶用法

### <a href="http://xaoxuu.com/wiki/stellar/widgets">自定义小组件</a>

组件库在 {% mark _data/widgets.yml %} 中创建

#### 组件库

##### toc 目录树

效果可以参考当前页面右侧的 {% mark 本文目录 %}

```markdown _data/widgets.yml
toc:
layout: toc
list_number: false # 是否显示序号
min_depth: 2 # 建议不要低于 2 即从 H2 标签开始解析（H1 标签用于文章大标题）
max_depth: 5 # 5 代表最多解析到 H5 标签
fallback: recent # Use a backup widget when toc does not exist.
collapse: false # true / false / auto (始终折叠/不折叠/自动折叠)
```

##### recent 近期文章

```markdown _data/widgets.yml
recent:
layout: recent
rss: # /atom.xml # npm i hexo-generator-feed
limit: 5 # Count of posts
```

##### related 相关文章

展示有相同 {% mark tag %} 的其它项目

```markdown _data/widgets.yml
related:
layout: related
```

##### linkList 链接列表

展示一组链接列表

```markdown _data/widgets.yml
linklist:
layout: linklist

# columns:1 列表显示

# columns:2 每 2 个按钮放一行

columns: 1
items:
#- icon: '<svg...></svg>' # 或者 icons.yml 中设置的 icon 名称

- icon: github:logo # 或者 icons.yml 中设置的 icon 名称
  title: 关于
  url: /about/
```

##### markdown 文本内容

```markdown _data/widgets.yml
welcome:
layout: markdown
title: 欢迎欢迎
#linklist: # 与 linklist 组件写法相同 # columns: 1 # items: # - icon: # title: # url:
content: |
欢迎来到 **赛博珊瑚礁 🪸**
我是这间陋室的守门人 **Ashly**
家里那位八腕目正在 **赛博云游中**
请问要来杯 **海盐风味的咖啡 ☕** 吗？

<div style="display:flex;justify-content:center"><img src="/images/base/TaiFi.gif" /></div>
src: # 可以设置外部 md 文件链接
```

##### tagcloud 标签云

```markdown _data/widgets.yml
tagcloud:
layout: tagcloud
title: 标签云

# 标签云配置

min_font: 12
max_font: 24
amount: 100
orderby: name
order: 1 # 1, sac 升序；-1, desc 降序
color: false # 使用颜色
start_color: # 开始的颜色。您可使用十六进位值（'#b700ff'），rgba（rgba(183, 0, 255, 1)），hsla（hsla(283, 100%, 50%, 1)）或 颜色关键字。此变量仅在 color 参数开启时才有用。
end_color: # 结束的颜色。您可使用十六进位值（'#b700ff'），rgba（rgba(183, 0, 255, 1)），hsla（hsla(283, 100%, 50%, 1)）或 颜色关键字。此变量仅在 color 参数开启时才有用。
show_count: false # 显示每个标签的文章总数
```

##### ghuser github 用户面板

```markdown _data/widgets.yml
ghuser:
layout: ghuser
username: github # your github login username
avatar: true # show avatar or not
menu: true # show menu or not
```

##### ghrepo github 项目面板

```markdown _data/widgets.yml
ghrepo:
layout: ghrepo
```

```markdown _posts/xxx.md
repo: xaoxuu/hexo-theme-stellar
```

```markdown _data/wiki/projects.yml
name: Stellar
title: Stellar
subtitle: '每个人的独立博客 | Designed by xaoxuu'
repo: xaoxuu/hexo-theme-stellar
```

##### <a href="https://xaoxuu.com/wiki/stellar/widgets/#timeline">timeline 时间线</a>

```markdown _data/widgets.yml
timeline:
layout: timeline
title: 近期动态
api: https://api.github.com/repos/xaoxuu/hexo-theme-stellar/issues # 若你想限制数量，在 api 链接后面加上?per_page=1 指限制为 1 条
user: # 是否过滤只显示某个人发布的内容，如果要筛选多人，用英文逗号隔开
hide: # title,footer # 隐藏标题或底部 # 此功能需要 Stellar v1.13.0
```

#### <a href="https://xaoxuu.com/wiki/stellar/widgets/#%E7%81%B5%E6%B4%BB%E7%94%A8%E6%B3%95">灵活用法</a>

指定的页面如果希望对组件的某个属性进行覆写时：

```markdown _post/xxx.md
---
title: 某一篇文章
leftbar:
  - welcome # 只写一个字符串代表引用对应的通用组件
  - override: my_timeline_lite
    api: https://xxx
---
```
