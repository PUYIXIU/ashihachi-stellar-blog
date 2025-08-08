---
wiki: ai # 项目id
title: Cursor参考文档
# 横幅
banner: /images/covers/cursor_bg.jpg # 动态拉取：workout,strava
references:
  - "[Cursor官方文档](https://docs.cursor.com/zh/welcome)"
  - "[Cursor论坛](https://forum.cursor.com/)"
  - "[Cursor键盘快捷键](https://docs.cursor.com/zh/configuration/kbd)"
  - "[上下文工作原理](https://docs.cursor.com/zh/guides/working-with-context)"
---


## 核心 Core

{% box child:tabs %}
{% tabs active:1  %}
<!-- tab 快速开始 Quickstart -->

{% folders %}
<!-- folder Tab代码自动补全 / Autocomplete with Tab -->
{% box  %}

 | 操作     | 快捷键                     |
 | :------- | :------------------------- |
 | 接受建议 | {% kbd Tab %}              |
 | 拒绝     | {% kbd Esc %}              |
 | 逐词接受 | {% kbd Ctrl+Arrow-Right %} |

{% endbox %}

{% box 🔍工作原理 color:cyan %}
- 上下文窗口中的代码被加密发送到后端
- 后端解密后读取上下文
-  {% mark Cursor Tab模型 color:yellow %} 预测代码建议，并返回给客户端在编辑器中显示
{% endbox %}

<!-- folder 内联编辑选中内容 / Inline Edit a selection -->

{% box %}
| 操作         | 快捷键                         |
| :----------- | :----------------------------- |
| 打开内联浮窗 | {% kbd Ctrl+K               %} |
| 切换输入焦点 | {% kbd Ctrl+Shift+K         %} |
| 提交         | {% kbd Enter                %} |
| 取消         | {% kbd Ctrl+Shift+BackSpace %} |
| 快速提问     | {% kbd Alt+Enter            %} |
| 发送到聊天   | {% kbd Ctrl+L            %}    |
{% endbox %}

{% box 内联模式 %}

| 模式                        | 描述                              |
| :-------------------------- | :-------------------------------- |
| Edit Selection / 选区编辑   | 针对选中代码修改                  |
| Edit Full File / 全文件编辑 | 整个文件范围的更改                |
| Quick Question / 快速问答   | 针对选中代码提问                  |
| Send to Chat / 发送到聊天   | 发送到聊天，支持更高级的Agent功能 |

{% endbox %}

{% box 默认上下文 %}

内联模式也支持使用 {% mark @符号 color:yellow %} ，添加默认上下文。

上下文类型可以是：

- 相关文件 / @Files
- 最近查看的代码 / @Code
- 相关信息 / @Docs&Web
- 相关代码定义 / @Definitions

{% endbox %}

{% box 终端内联编辑 %}

- 在 {% mark 终端 color:green %} 中按快捷键 {% kbd Ctrl+K %}
- 描述希望执行的操作，可以生成相应的命令

{% endbox %}

<!-- folder 与Agent聊天 / Chat with Agent -->
{% box %}

> Cursor上限和下限跨度最大的功能

- 上到串通工作流
- 下到联网查问题
- 高到MCP上下文
- 低到CMD控制台

{% endbox %}
<!-- folder Agent后台处理 / Handoff word to Background Agent -->
{% box %}
- 用户和Cursor异步并行工作
- 可以通过编辑器或外部集成（如Slack）访问
- {% del 目前还没有用到 %}，有需要参考[文档](https://docs.cursor.com/zh/background-agent)
{% endbox %}
<!-- folder 编写规则 / Write a rule -->
{% box %}
- 创建  {% mark mdc文件 color:yellow %} 
- 定义一些规则，{% wavy 相当于通用持久记忆 %}
{% endbox %}
<!-- folder MCP服务器 / Set up an MCP server -->
{% box %}
- 集成外部工具的模型上下文协议
- 连接数据库、API和文档源
{% endbox %}
{% endfolders %}

<!-- tab 概念 Concepts -->
{% folders %}
<!-- folder Tab -->
{% box %}
- {% wavy 自动补全多行和代码块 %}
- 在文件内和跨文件跳转到下一个自动补全建议
{% endbox %}
<!-- folder Agent -->
{% box %}
- Agent相当于一个虚拟助理，{% wavy 能够根据目标、规则和环境做出决策和行动 %}
- 对于Cursor Agent，环境就是能够读取到的代码和文件内容
{% endbox %}
<!-- folder Background Agent -->
{% box %}
- 一边工作一边异步运行任务
- 可以通过编辑器或外部集成（如Slack）访问
{% endbox %}
<!-- folder Inline Edit -->
{% box %}
- 精简版Agent
- 针对选中代码块进行编辑
{% endbox %}
<!-- folder Chat -->
{% box %}
传统对话式智能体
{% endbox %}
<!-- folder Rules -->
{% box %}
- 定义AI行为的自定义指令。
- 设置编码标准、框架偏好
{% endbox %}
<!-- folder Memory -->
{% box %}
- {% wavy 需要持久存储的上下文和对话 %}
- 是另一种形式的rules
{% endbox %}

{% box 记忆如何创建 %}
{% grid c:2 bg:card %}
<!-- cell -->
**Sidecar观察**
- {% wavy 有一个独立的模型，观察对话并自动提取记忆 %}
- 在后台被动进行
- 后台生成的记忆需要用户批准才能保存，确保对内容的信任和控制
<!-- cell -->
**工具调用**
- 当用户明确要求Agent记住某些内容
- 或当它注意到应该为未来的会话保留重要信息时
- Agent可以直接使用工具调用创建记忆
{% endgrid %}
{% note 管理记忆 Cursor Setting > Rules 中管理记忆 %}

{% endbox %}

<!-- folder Indexing -->
{% box %}
- 当打开一个项目时，Cursor开始学习该项目的代码，即“索引”
- 打开项目时，索引自动开始
- 对代码库进行语义分析，支持代码搜索、引用查找和上下文感知建议
{% endbox %}
<!-- folder MCP -->
{% box %}
- 集成外部工具的模型上下文协议
- 连接数据库、API和文档源
{% endbox %}
<!-- folder 模型 -->
{% box %}
- 用于代码生成不同的AI模型
- 每个模型具有不同的速度和能力特性
{% endbox %}
{% endfolders %}

{% endtabs %}

{% endbox %}

### 核心：🤖智能体

{% box %}

{% folders %}
<!-- folder 模式 Modes -->
{% box %}
{% grid c:2  bg:card %}
<!-- cell -->
**Agent**
- 自主探索、多文件编辑
- 权限：{% wavy 所有工具 %}
<!-- cell -->
**Ask**
- 只读探索、无自动更改
- 权限：{% wavy 搜索工具 %}
<!-- cell -->
**Manual**
- 直接文件编辑、具有明确控制
- 权限：{% wavy 编辑工具 %}
- 只编辑明确选择的文件
- 在确切知道要编辑什么时效果最佳，选择正确的文件并给出清晰的指令
<!-- cell -->
**Custom**
- 用户定义的功能
- 对特定的工具组合和指令创建自定义模式

{% endgrid %}

{% endbox %}
<!-- folder 工具 Tools -->
{% box %}

在Custom模式下，智能体的这些工具可以被自由的启用/禁用

{% endbox %}

<!-- folder 应用更改 Apply Changes -->

{% box  %}

应用、接受或拒绝聊天中的代码建议

{% endbox %}

{% box 原理简述 %}

{% wavy Apply是一个专门的Cursor模型 %}

- 专门接收Agent生成的代码，并集成到文件中
- Apply不生成代码，只负责集成
- 可以处理多个文件和大型代码库的更改

{% endbox %}

<!-- folder 审查差异 Review Diffs -->

{% box %}

审查和管理由AI代理生成的代码更改
- 逐文件审查
- 选择性接受
- 审查更改（review changes）查看更改的完整差异

{% endbox %}

<!-- folder 聊天标签页 Chat Tabs -->

{% box %}

- 可以同时运行多个对话
- {% wavy 每个标签页都维护自己的上下文、历史记录和模型选择 %}

{% endbox %}

<!-- folder 检查点 Checkpoints -->
{% box %}

自动快照跟踪Agent更改，可以进行restore恢复

{% endbox %}
<!-- folder 终端集成 Terminal Integration -->
{% box %}

- 可以使用Agent执行终端命令、监控输出并处理多步骤流程
- 为可信工作流配置自动运行

{% endbox %}
<!-- folder 聊天历史 Chat History -->
{% box %}

回顾之前讨论、跟踪编码会话、参考早期聊天上下文

{% endbox %}
<!-- folder 导出聊天 Export Chats -->
{% box %}

- 导出为  {% mark markdown格式 color:yellow %} 
- 与团队成员分享解决方案、或从编码会话中创建知识库

{% endbox %}
<!-- folder 规则 Rules -->
{% box %}

- 可以使用rules，为Agent的行为定义自定义指令
- 有助于维护编码标准、强制执行模式、个性化Agent

{% endbox %}
{% endfolders %}


{% endbox %}


{% quot 智能体：💬聊天 prefix:hardware:64 el:h4 %}

{% folders %}
<!-- folder 标签页 Tabs -->
{% box %}
- **沙盒隔离：** 每个标签页的对话历史、上下文、模型选择独立
  
- **冲突：** 多个标签页编辑相同的文件时，系统会提示解决冲突（和git merge相似）
  
- **引用其他聊天记录：** 使用 {% mark Past Chats color:yellow %} 来包含其他标签页或者之前绘画的上下文
{% endbox %}

{% box 💡建议 color:yellow %}
- 每个标签页使用一个任务，提供清晰的初始描述
- 关闭已完成的标签页以保持工作区整洁
{% endbox %}

<!-- folder 检查点 Checkpoints -->
{% box %}
- **用途：** 在Agent更改后保存和恢复之前的状态
- **提示：** 检查点不是版本控制，还是需要使用git来保存永久历史记录
{% endbox %}

{% box 🔍工作原理 color:cyan %}
- 本地存储
- 仅跟踪Agent更改
- 自动清理（在当前会话和最近的历史记录中保存）
{% endbox %}

<!-- folder 导出 Export -->
{% box 导出内容（Markdown格式） %}
- 所有消息和响应
- 语法高亮代码块
- 文件引用和上下文
- 按时间顺序的对话流程
{% endbox %}
{% box 💡注意 color:yellow %}
导出时请检查敏感数据：**API密钥、内部URL、专有代码、个人信息等**
{% endbox %}

<!-- folder 复制 Duplicate -->
{% box %}
- 从对话中的任意点创建分支，选择  {% mark Duplicate Chat color:cyan %} 
- 到该时间点的上下文会被保留，原始对话保持不变
- 两个聊天都维护各自独立的历史记录
{% endbox %}
<!-- folder 历史记录 History -->
{% box %}
- 历史聊天记录可以打开、删除、重命名
- 记录会存储在本机器 {% mark SQLite数据库 color:yellow %} 中
- **后台代理：** 不在常规的历史记录中，而是存储在远程数据库中
- **引用过往聊天记录：** {% mark @Past Chats color:cyan %}
{% endbox %}
<!-- folder 摘要功能 Summarization -->
{% box %}
- 聊天中长对话的上下文管理
- {% wavy Cursor会自动摘要和管理上下文 %}，保持聊天的高效
{% endbox %}
{% box 🔍工作原理 color:cyan %}
- 当对话变得越来越长时，Cursor会对比较旧的消息进行摘要（压缩）
- 对文件和文件夹，Cursor使用另一种处理方式：{% wavy 智能压缩 %}
- Cursor会根据文件大小和可用上下文空间确定呈现它们的最佳方式

**文件压缩的几种情况：**
{% box %}
{% tabs %}
<!-- tab 已压缩 -->
- 压缩会向模型显示关键的结构元素，如函数签名、类、方法。
- 模型有需要时展开特定文件
- 最大化了对可用上下文窗口的有效利用
<!-- tab 显著压缩 -->
文件太大而无法完整包含，压缩也不行，模型只能获取到文件名
<!-- tab 未包含（警告） -->
项目太大无法包含在上下文窗口
{% endtabs %}
{% endbox %}

{% endbox %}
{% endfolders %}


{% quot 智能体：🧾规划 prefix:hardware:64 el:h4 %}

{% grid %}
<!-- cell -->

{% box Agent如何通过规划和管理复杂任务 %}
- 提前规划
- 结构化的待办事项列表、消息队列
{% endbox %}

<!-- cell -->
{% box 🗒️Agent待办事项 %}
- 将较长的任务分解为可管理的步骤
- 建立依赖关系？
- 结构化计划会随工作进展而更新
{% endbox %}
{% endgrid %}



{% box 🔍工作原理 color:cyan %}
- {% wavy  自动为复杂任务创建待办事项列表 %}
- 每个项目都可以依赖于其他任务
- 列表随工作进展实时更新
- 已完成的任务会自动标记为完成
{% endbox %}

{% box 可见性 %}
- 方式1：显示在聊天界面中
- 方式2：[Slack集成显示？](https://docs.cursor.com/zh/slack)

{% endbox %}
{% note 💡注意 最好清楚地描述最终目标，让Agent了解完整范围，才能创建更准确的任务分解 color:yellow %}
{% folding 使用队列 %}
- 当Agent正在工作时，输入下一个指令
- Enter将其添加到队列中
- 消息按顺序显示在活动任务下方
- 点击箭头可以重新排列队列消息
- Agent会在完成后按顺序处理它们
- 覆盖队列：强制推送消息，会绕过队列立即执行
{% endfolding %}



{% quot 智能体：🔧工具 prefix:hardware:64 el:h4 %}

{% folders %}
<!-- folder 搜索 Search （搜索代码库/网络以查找相关信息 ）-->
{% box %}

| 工具名                  | 描述                           |
| :---------------------- | :----------------------------- |
| 读取文件/Read files     | 最多250行，最大模式下为750行   |
| 列出目录/List directory | 只读取目录结构，不读取文件内容 |
| 代码库/Codebase         | 在已索引代码库中执行语义搜索   |
| Grep                    | 在文件中搜索确切的关键词或模式 |
| 搜索文件/Search files   | 使用模糊匹配按名称查找文件     |
| 网络/Web                | 生成搜索查询并执行网络搜索     |
| 获取规则/Fetch rules    | 根据类型和描述检索特定的规则   |


{% endbox %}
<!-- folder 编辑 Edit（对文件和代码库进行特定编辑） -->
{% box %}
| 工具名                        | 描述               |
| :---------------------------- | :----------------- |
| 编辑和重新应用/Edit & Reapply | 文件编辑并自动应用 |
| 删除文件/Delete file          | 删除文件           |
{% endbox %}

<!-- folder 运行 Run（与终端进行交互） -->
{% box %}
- {% wavy Cursor可以运行终端命令并监控输出 %}
- Cursor使用默认的终端配置文件
  - 修改中端配置文件：{% mark Terminal:Select Default Profile color:cyan %}
{% endbox %}
<!-- folder MCP -->
{% box %}
可以使用配置的MCP服务器与外部服务进行交互，例如数据库或第三方API
{% endbox %}
<!-- folder 高级选项 -->
{% box %}
| 工具名                        | 描述                                                    |
| :---------------------------- | :------------------------------------------------------ |
| 自动应用编辑/Auto-apply Edits | 自动应用编辑无需手动确认                                |
| 自动运行/Auto-run             | 自动执行终端命令并接受编辑,适用于运行测试套件和验证更改 |
| 安全防护/Guardrails           | 一大堆允许配置，来确保哪些工具可以自动执行              |
| 自动修复错误/Auto-fix Errors  | 当Agent遇到代码检查错误和警告时自动解决                 |
{% endbox %}

{% endfolders %}


### 核心：🚩规则

{% quot 规则介绍 el:h4 prefix:point-right:64 %}

{% box %}

- 通过可重用的作用域指令控制Agent模型的行为
- {% wavy 可以视为项目的持久上下文、偏好设置或工作流程 %}
- **规则适用范围：**为Agent和内联编辑提供系统级指令（tab不适用）

{% endbox %}

{% box 规则类型 child:tabs %}
{% tabs %}
<!-- tab 项目规则 -->
{% box %}
- 存储在 {% mark .cursor/rules color:blue %} 中
- 受版本控制作用于代码库
- 可以使用路径模式进行规则限定/手动调用/基于相关性包含
- 嵌套规则：
  - 子目录可以包含自己的 {% mark .cursor/rules color:blue %} 目录，范围限定在该文件夹内
  - 嵌套规则会根据项目层级自动附加

{% folding 💡可以使用Rules处理的场景 color:yellow %}
- 编码关于代码库的领域特定知识
- 自动化项目特定的工作流程或模版
- 标准化样式或架构决策
{% endfolding %}

{% endbox %}
<!-- tab 用户规则 -->
{% box %}
- 全局应用于Cursor环境
- 设置中定义并始终生效
- {% wavy 比较适合设置首选的沟通风格或编码约定 %}
{% endbox %}

{% endtabs %}
{% endbox %}

{% box 🔍作用原理 color:cyan %}
- 提供持久的、可重用的上下文
- 应用时，规则内容会包含在模型上下文的开始部分
{% endbox %}

{% quot 创建规则 el:h4 prefix:point-right:64 %}

{% box 规则结构 %}
{% mark MDC color:yellow %} 编写，支持元数据和内容格式

{% folding 属性 Property  %}
|    属性     |   描述   |
| :---------: | :------: |
| description | 规则描述 |
|    globs    |  作用域  |
| alwaysApply | 应用范围 |
{% endfolding %}
{% folding 规则作用类型 Rule Type  %}
|    属性     |   描述   |
| :---------: | :------: |
| Always | 始终包含在模型上下文中 |
|    Auto Attached    |  引用匹配glob模式的文件时包含  |
| Agent Requested | 由AI决定是否包含，因此必须提供描述 |
| Manual | 仅在使用@ruleName显式提及时包含 |
{% endfolding %}

{% endbox %}

{% box 创建规则 %}

{% timeline %}
<!-- node 创建方式1 -->
{% mark Cursor Settings > Rules color:cyan %} 可以看到并管理所有规则
<!-- node 创建方式2 -->
{% mark New Cursor Rule color:green %} 命令
<!-- node 创建方式3 -->
{% mark /Generate Cursor Rules color:green %} 命令，根据当前和智能体的对话，生成规则
{% endtimeline %}

{% endbox %}

{% folding 案例 open:false %}
这里Cursor文档里提供了几个[规则标准](https://docs.cursor.com/zh/context/rules#cursor)，还挺有意思的。
还有更多示例可以从提供商、框架、社区贡献的在线众包集合和储存库中找到。

```mdc 
---
alwaysApply: true
globs:
description: 自动化开发工作流程和文档生成
---
此规则自动化应用分析：
当被要求分析应用时：
1. 使用 npm run dev 运行开发服务器
2. 从控制台获取日志
3. 建议性能改进
此规则帮助生成文档：
通过以下方式帮助起草文档：
- 提取代码注释
- 分析README.md
- 生成markdown文档
```

{% endfolding %}


{% folding 💡建议 open:false color:yellow %}
-  {% wavy 规则应该是专注的、可操作的、有明确范围的 %} 
- 保持规则在500行以内
- 将大型规则拆分为多个可组合的规则
- 提供具体的实例或引用文件
- 避免模糊指导，编写规则时要像清晰的内部文档一样
- 在聊天中重复提示时重用规则
{% endfolding %}


## 上下文 Context

{% blockquote %}
上下文不足会导致幻觉或效率低下，而过多的上下文会稀释信号。找到合适的平衡点以获得最佳效果
{% endblockquote %}

{% folding ❔什么是上下文 %}

**答：上下文是指提供给模型的信息**

模型随后使用这些信息来预测后续信息

有两种类型的上下文：

{% grid c:2 bg:card %}
<!-- cell -->
**状态上下文 State Context**
- 对当下状态的描述
- 描述性
- _“这是一张新的设计图纸，对现有的颜色主题做了一些调整”_
<!-- cell -->
**意图上下文 Intent Context**
- 用户希望达到的目标
- 规定性
- _“我需要你按照这张图纸，修改界面的颜色样式”_
{% endgrid %}

缺少上下文时，Agent可能做出的反映：

{% box 反向对应：幻觉 Hallucination %}
模型在缺乏足够上下文情况下，生成看似合理但事实上虚构的内容
> User：秦始皇最近缺钱吗？
> AI：是的，他目前正在筹备修建新的长城项目，遇到资金短缺的情况非常正常...
{% endbox %}

{% box 正向对应：上下文感知 %}

Agent尝试通过搜索代码库、读取文件和调用工具自行收集上下文。

Cursor的核心构建理念即：**上下文感知**，旨在最大程度减少用户的干预

{% endbox %}

{% endfolding %}

{% folding 🕊️上下文使用建议 color:green %}
{% timeline %}
<!-- node 清晰表达 -->
清晰表达**状态 _（当下情况）_** 和 **意图 _（希望达成）_**
<!-- node 精确定位 -->
使用  {% mark @符号 color:yellow %}  进行精准上下文定位
<!-- node 总结经验 -->
重复使用的知识可以**总结为规则**，成为长期记忆
<!-- node 对外交流 -->
通过 {% mark MCP color:yellow %} 来连接外部系统
{% endtimeline %}
{% endfolding %}


### 上下文：代码库索引

{% box %}
- 通过为每个文件计算嵌入向量来索引代码库
- 如果已索引代码库  {% wavy 6周 %}  不活跃后会被删除
- 检查索引状态： {% mark Cursor Setting > Indexing & Docs color:cyan %} 
{% endbox %}


{% folding 配置项  %}
- 忽略文件（ {% mark .gitignore color:yellow %} 、 {% mark .cursorignore color:yellow %} ）
  - 提示： {% wavy 忽略大型内容文件可以提高答案准确性 %} 
- 查看已索引文件： {% mark View included files color:cyan %} 
{% endfolding %}


{% folding 多根工作区 %}
- 所有代码库都会自动建立索引
- AI可用每个代码库的上下文
-  {% mark .cursor/rules color:cyan %}  在所有文件夹中都有效
{% endfolding %}

{% folding PR搜索 %}

通过让历史变更可搜索和通过AI访问，帮助立即代码库的演进过程

{% box 🔍工作原理 color:cyan %}
 - 自动索引所有已合并的PR，来自仓库记录
 - 摘要会出现在语义搜索结果中
 - 通过智能过滤来优先显示最近的变更
 - Agent可以使用@获取PR、提交、问题或分支到上下文中
   - @[PR 编号]
   - @[commit hash]
   - @[branch name]
- 支持平台有限，目前主要是  {% mark github color:orange %}  和  {% mark bitbucket color:orange %} 
{% endbox %}
{% endfolding %}

### 上下文：忽略文件

{% box 配置文件 %}
-  {% mark .cursorignore color:cyan %} 
-  {% mark .cursirindexingignore color:cyan %} 
  - 仅从索引中排除文件，文件可以被AI访问，但不会出现在代码库搜索中

{% folding 配置方式 %}
{% timeline %}
<!-- node 全局忽略文件 -->
 {% mark Settings > Global Cursor Ignore List color:blue %} 
<!-- node 配置.cursorignore -->
在根目录中使用  {% mark .gitignore color:yellow %}  语法创建  {% mark .cursorignore color:blue %}  文件
<!-- node 默认忽略文件 -->
- {% mark .gitignore color:yellow %} 中的文件
- 一些默认忽略列表（文档里有）
- 在 {% mark .cursorignore color:cyan %} 中可以使用  {% mark !前缀 color:yellow %}  覆盖
<!-- node 否定模式限制 -->
- 以 {% mark ! color:yellow %} 为前缀
- 如果父目录通过 {% mark * color:yellow %} 被排除，则无法重新包含文件  {% del （好微妙...） %} 
- **建议：** 显式排除嵌套目录
{% endtimeline %}

{% endfolding %}

{% endbox %}

{% box 阻止范围 %}
-  {% mark index color:yellow %} 
-  {% mark tab color:yellow %} 、{% mark agent color:yellow %} 、{% mark inline edit color:yellow %} 
- {% mark @ color:yellow %}

{% note 💡注意 Agent发起的工具调用（终端/MCP）无法阻止 color:yellow %}
{% endbox %}

{% folding 为什么要忽略 %}
- **性能：**  {% wavy 排除无关部分可以实现更快的索引，和更准确的文件发现 %} 
- **安全性：**
  - 限制对API密钥、凭据、机密信息的访问
  - 虽然可以限制访问，但由于LLM的不可预测性，无法保证完全保护？？？
{% endfolding %}

### 上下文：MCP

{% box MCP（Model Context Protocol） %}
- MCP使Cursor能够连接到外部工具和数据源
- 无需重复解释项目结构，直接与工具集成
{% endbox %}

{% box 🔍工作原理 color:cyan %}
- MCP服务器通过协议公开功能，将Cursor连接到外部工具或数据源
- 支持三种传输方式：
  - stdio
    - Cursor管理/单用户/shell命令/手动
  - SSE
    - 部署为服务器/多用户/SSE端点URL/OAuth
  - Streamable HTTP
    - 部署为服务器/多用户/HTTP端点URL/OAuth
{% endbox %}


### 上下文：@符号

{% box %}
| @          | 描述                                            |
| :--------- | :---------------------------------------------- |
| @Files     | 引用特定文件                                    |
| @Folders   | 引用整个文件夹                                  |
| @Code      | 引用特定代码片段或符号                          |
| @Docs      | 访问文档和指南                                  |
| @Git       | 访问git历史记录和更改                           |
| @Past      | Chats 使用汇总的编辑器回话                      |
| @Rules     | 使用cursor规则                                  |
| @Terminals | 终端                                            |
| @Active    | Tabs 激活的智能体                               |
| @Linter    | Errors 引用lint错误                             |
| @Web       | 外部网络资源和文档                              |
| @Link      | 粘贴URL时，Cursor会将其自动标记为@Link，支持PDF |
| @Recent    | Changes 创建指向特定代码或文档的联机            |
| #Files     | 将文件添加到上下文中而不引用                    |
| /Commands  | 将打开和活动的文件添加到上下文中                |
{% endbox %}


