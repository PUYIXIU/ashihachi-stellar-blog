---
wiki: ai # 项目id
title: Cursor文档部分
references:
  - "[Cursor官方文档](https://docs.cursor.com/zh/welcome)"
---

{% box 其它内容参考  %}

- <a href="https://docs.cursor.com/zh/configuration/kbd">键盘快捷键</a>

{% endbox %}



# 核心

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

{% box Tab提示生成原理 %}
- 上下文窗口中的代码被加密发送到后端
- 后端解密后读取上下文
-  {% u Cursor Tab模型 %} 预测代码建议，并返回给客户端在编辑器中显示
{% endbox %}

<!-- folder 内联编辑选中内容 / Inline Edit a selection -->

{% box %}
| 操作         | 快捷键               |
| :----------- | :------------------- |
| 打开内联浮窗 | {% kbd Ctrl+K               %} |
| 切换输入焦点 | {% kbd Ctrl+Shift+K         %} |
| 提交         | {% kbd Enter                %} |
| 取消         | {% kbd Ctrl+Shift+BackSpace %} |
| 快速提问     | {% kbd Alt+Enter            %} |
| 发送到聊天     | {% kbd Ctrl+L            %} |
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

内联模式也支持使用@符号，添加默认上下文。
上下文类型可以是：
- 相关文件 / @Files
- 最近查看的代码 / @Code
- 相关信息 / @Docs&Web
- 相关代码定义 / @Definitions

{% endbox %}

{% box 终端内联编辑 %}

- 在 {% u 终端 %} 中按快捷键 {% kbd Ctrl+K %}
- 描述希望执行的操作，可以生成相应的命令

{% endbox %}

<!-- folder 与Agent聊天 / Chat with Agent -->
- Cursor上限和下限跨度最大的功能
- 下到联网问个小问题，上到串通整个工作流
- 高到MCP外接上下文，低到控制台运行终端命令
<!-- folder Agent后台处理 / Handoff word to Background Agent -->
- 用户和Cursor异步并行工作
- 可以通过编辑器或外部集成（如Slack）访问
- 目前还没有用到，有需要参考[文档](https://docs.cursor.com/zh/background-agent)
<!-- folder 编写规则 / Write a rule -->
- 创建mdc文件
- 定义一些规则，相当于通用持久记忆
<!-- folder MCP服务器 / Set up an MCP server -->
- 集成外部工具的模型上下文协议
- 连接数据库、API和文档源
{% endfolders %}

<!-- tab 概念 Concepts -->
{% folders %}
<!-- folder Tab -->
- 自动补全多行和代码块（使用频率较高）
- 在文件内和跨文件跳转到下一个自动补全建议（预判这一块）
<!-- folder Agent -->
- Agent相当于一个虚拟助理，能够根据目标、规则和环境做出决策和行动
- Agent根据收集到的信息自主做出决策、与环境交互
- 对于Cursor Agent，环境就是能够读取到的代码和文件内容
<!-- folder Background Agent -->
- 一边工作一边异步运行任务
- 可以通过编辑器或外部集成（如Slack）访问
<!-- folder Inline Edit -->
- 精简版Agent
- 针对选中代码块进行编辑
<!-- folder Chat -->
- 传统对话式智能体
<!-- folder Rules -->
- 定义AI行为的自定义指令。
- 设置编码标准、框架偏好
<!-- folder Memory -->
- 需要持久存储的上下文和对话
- 是另一种形式的rules
<!-- folder Indexing -->
- 当打开一个项目时，Cursor开始学习该项目的代码，即“索引”
- 打开项目时，索引自动开始
- 对代码库进行语义分析，支持代码搜索、引用查找和上下文感知建议
<!-- folder MCP -->
- 集成外部工具的模型上下文协议
- 连接数据库、API和文档源
<!-- folder 模型 -->
- 用于代码生成不同的AI模型
- 每个模型具有不同的速度和能力特性
{% endfolders %}

{% endtabs %}

{% endbox %}

## 核心：智能体

{% box 概览 Overview %}

{% folders %}
<!-- folder 模式 Modes -->
{% box %}
{% grid c:2  bg:card %}
<!-- cell -->
**Agent**
- 自主探索、多文件编辑
- 权限：所有工具
<!-- cell -->
**Ask**
- 只读探索、无自动更改
- 权限：搜索工具
<!-- cell -->
**Manual**
- 直接文件编辑、具有明确控制
- 权限：编辑工具
- 只编辑明确选择的文件
- 在确切知道要编辑什么时效果最佳，选择正确的文件并给出清晰的指令
<!-- cell -->
**Custom**
- 用户定义的功能
- 对特定的工具组合和指令创建自定义模式

{% endgrid %}

{% endbox %}
<!-- folder 工具 Tools -->
这个抽屉是空的
<!-- folder 应用更改 Apply Changes -->
找到了一把手电筒
<!-- folder 审查差异 Review Diffs -->
找到了一把手电筒
<!-- folder 聊天标签页 Chat Tabs -->
找到了一把手电筒
<!-- folder 检查点 Checkpoints -->
找到了一把手电筒
<!-- folder 终端集成 Terminal Integration -->
找到了一把手电筒
<!-- folder 聊天历史 Chat History -->
找到了一把手电筒
<!-- folder 导出聊天 Export Chats -->
找到了一把手电筒
<!-- folder 规则 Rules -->
找到了一把手电筒
{% endfolders %}


{% endbox %}


{% quot 智能体：聊天 prefix:hardware:64 el:h3 %}

{% quot 智能体：规划 prefix:hardware:64 el:h3 %}

{% quot 智能体：模式 prefix:hardware:64 el:h3 %}
{% quot 智能体：工具 prefix:hardware:64 el:h3 %}
{% quot 智能体：Apply prefix:hardware:64 el:h3 %}
{% quot 智能体：差异对比与审查 prefix:hardware:64 el:h3 %}



## 核心：后台代理 Background Agent

## 核心：Web & Mobile

## 核心：内联编辑

## 核心：规则

## 核心：记忆

# 上下文

## 上下文：代码库索引

## 上下文：忽略文件

## 上下文：MCP

## 上下文：@符号

# 集成

# 模型

# 配置

# 账户