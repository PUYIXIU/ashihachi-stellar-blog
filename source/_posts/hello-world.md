---
#menu_id: post
title: Stellar使用指南
date: 2025-02-21 13:02:49
tags: [hexo]
categories: []
description: 
  
# 参考资料
references:
  - '[Stellar官方文档](https://xaoxuu.com/wiki/stellar/pages/)'


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
leftbar:
rightbar:
h1: # 设置为 '' 隐藏标题
type: # tech | story
---

随便写点什么吧

<!-- more -->

# 1️⃣基本使用

## 💭表达类标签

### emoji表情包


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


- <a href="https://gcore.jsdelivr.net/gh/norevi/waline-blobcatemojis@1.0/blobs/">blobcat表情库</a>

### icon 图标标签

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

### mark 标记

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

### hashtag 标签

{% hashtag Stellar https://xaoxuu.com/wiki/stellar/ %}
{% hashtag Hexo https://hexo.io/ color:blue %}
{% hashtag GitHub https://github.com/xaoxuu/ color:dark %}

```markdown
{% hashtag Stellar https://xaoxuu.com/wiki/stellar/ %}
{% hashtag Hexo https://hexo.io/ color:blue %}
{% hashtag GitHub https://github.com/xaoxuu/ color:dark %}
```

### image 图片标签

```markdown
{% image src [description] [download:bool/string] [width:px] [padding:px] [bg:hex] [fancybox:bool/string] %}
```

```yml 参数说明
src: 图片地址
description: 图片描述
download: href # 下载地址，设置此值后鼠标放在图片上会显示下载地址，如果下载地址为图片地址，可以设置为 true
width: 200px # 图片宽度
padding: 16px # 图片四周填充宽度
bg: '#ffffff' # 图片区域背景颜色，16进制
fancybox: href # fancybox 放大地址，设置此值后会调用该链接放大，如果放大地址为图片地址，可以设置为 true
```

#### 横向铺满图片

{% image /images/base/test.jpg 猫猫镇楼 download:true fancybox:true %}

```markdown
{% image /images/base/test.jpg 猫猫镇楼 download:true fancybox:true %}
```

#### 竖图（小图）优化

{% image /images/base/test2.jpg 猫猫镇楼 width:300px padding:10px bg:var(--card) download:true fancybox:true %}

```markdown
{% image /images/base/test2.jpg 猫猫镇楼 width:300px padding:10px bg:var(--card) download:true fancybox:true %}
```

### quote 引用

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

### poetry 诗词

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

### paper 纸张标签

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

### reel 卷轴标签

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

### note 备注块

{% note 备注标题 备注内容 %}

```markdown
- color: red、orange、amber、yellow、green、cyan、blue、purple、light、dark、warning、error
{% note 备注标题 备注内容 [color:color] %}
```

### link 链接卡片

{% link https://xaoxuu.com/blog/20221029/ icon:https://xaoxuu.com/assets/xaoxuu/avatar/rect-256@2x.png Stellar-每个人的独立博客 %}

```markdown
{% link href [title] [icon:src] [desc:true/false] %}
```

### button 按钮

{% button 文档 /wiki  icon:solar:notebook-bookmark-bold-duotone %}
{% button 探索 /explore color:yellow icon:solar:planet-bold-duotone size:xs %}

```markdown
- size: 默认 | xs（最小号）
{% button text url [icon:key/src] [color:color] [size:xs] %}
{% button 文档 /wiki  icon:solar:notebook-bookmark-bold-duotone %}
{% button 探索 /explore  icon:solar:planet-bold-duotone size:xs %}
```

### okr 目标管理

- okr：Objectives and Key Results

{% okr o1 %}

2025年小目标：全球旅行✈️
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
您可以在 _config.yml 文件中修改标签的颜色和文案
<!-- tab 小提示2 -->
您可以在 _config.yml 文件中增加任意的标签配置
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

### copy 复制行

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

### radio 单选

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

### checkbox 复选

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

### audio 音频标签

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
  - 2表示歌曲
  - 0表示歌单
- netease: 歌曲/歌单id，在网易云分享链接中能找到
- autoplay
  - 1 表示自动播放
  - 0 表示手动播放

### video 视频标签

{% video bilibili:BV1x44y1K7ho %}
{% video youtube:FDUk0Kcte9A %}

```markdown
{% video bilibili:BV1x44y1K7ho %}
{% video youtube:FDUk0Kcte9A %}

- width: 500px # 单位 80% 20em 100mm
- autoplay: 1/0 # 1：自动播放 0：手动播放
```

### navbar 导航栏

{% navbar active:/wiki/ [文章](/) [项目](/wiki/) [留言](#comments) [GitHub](https://github.com/xaoxuu/) %}

```markdown
- 由链接组成的导航栏
{% navbar active:/wiki/ [文章](/) [项目](/wiki/) [留言](#comments) [GitHub](https://github.com/xaoxuu/) %}
```

### frame 设备框架

{% frame iphone11 img:/images/base/phone.jpg focus:top %}

```markdown
{% frame iphone11 img:/assets/wiki/prohud/toast/demo-loading.png video:/assets/wiki/prohud/toast/demo-loading.mp4 focus:top %}
```

### 文本修饰标签集

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

## 🔢数据类标签

### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#timeline-%E6%97%B6%E9%97%B4%E7%BA%BF">timeline 时间线</a>

{% timeline %}
<!-- node 2025 年 2 月 25 日 -->
今天科三考试最后熄火，还好我平时练车熄火太多所以很熟，回空挡打火换一档完成靠边停车，贴着及格线过了，激动的心颤抖的手
{% image /images/meme/idrive.jpg width:300px %}
<!-- node 2025 年 2 月 24 日 -->
下午科目三模拟3把连挂，教练差点气撅过去
{% image /images/meme/acat.jpg width:200px %}
{% endtimeline %}

```markdown
{% timeline %}
<!-- node 2025 年 2 月 25 日 -->
今天科三考试最后熄火，还好我平时练车熄火太多所以很熟，回空挡打火换一档完成靠边停车，贴着及格线过了，激动的心颤抖的手
{% image /images/meme/idrive.jpg width:300px %}
<!-- node 2025 年 2 月 24 日 -->
下午科目三模拟3把连挂，教练差点气撅过去
{% image /images/meme/acat.jpg width:200px %}
{% endtimeline %}
```

> <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#%E5%8A%A8%E6%80%81%E6%97%B6%E9%97%B4%E7%BA%BF">动态时间线参考</a>

### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#friends-%E5%8F%8B%E9%93%BE">friends 友链</a>

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

### <a href="https://xaoxuu.com/wiki/stellar/tag-plugins/data/#sites-%E7%BD%91%E7%AB%99%E5%8D%A1%E7%89%87">sites 网站卡片</a>

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

### ghcard 卡片

{% ghcard puyixiu %}
{% ghcard xaoxuu/hexo-theme-stellar theme:dark %}
