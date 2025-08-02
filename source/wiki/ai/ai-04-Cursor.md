---
wiki: ai # 项目id
title: Cursor
---

https://docs.cursor.com/zh/welcome

快捷键：
- Ctrl+Shift+J 打开Cursor设置

# 概念

- tab代码补全
  - 自动补全多行和代码块（使用频率很高）
  - 在文件内和跨文件跳转到下一个自动补全建议（没怎么试过，不喜欢）
- 内联编辑选中内容
  - 选中代码块
  - 快捷键：Ctrl+K
- 与Agent聊天
  - 跨文件读取和修改代码，用自然语言描述更改
  - 快捷键：Ctrl+I
- 其它
  - 工作交给后台代理（没用过，Ctrl+E无法打开后台代理控制面板）
    - 快捷键： Ctrl+E
  - 编写规则
    - New Cursor Rule，打开命令面板
    - 创建一个新的mdc文件
    - 定义一些样式规则

核心概念（https://docs.cursor.com/zh/get-started/concepts）
- Tab
  - 代码补全（根据当前代码和最近更改的建议）
- Agent
  - 跨文件读取和修改代码
- Background Agent（？？？）
  - 一边工作一边异步运行任务
  - 可以通过编辑器或外部集成（如Slack）访问
- Inline Edit
  - Ctrl+K根据描述更改（和Agent差不多）
- Chat
  - 不用改代码的Agent
- Rules
  - 定义AI行为的自定义指令。
  - 设置编码标准、框架偏好
- Memory
  - 需要持久存储的上下文和对话
  - 是另一种形式的rules
- Indexing 索引
  - 当打开一个项目时，Cursor开始学习该项目的代码，即“索引”
  - 打开项目时，索引自动开始
  - 对代码库进行语义分析，支持代码搜索、引用查找和上下文感知建议
- MCP
  - 集成外部工具的模型上下文协议
  - 连接数据库、API和文档源
- 模型
  - 用于代码生成不同的AI模型
  - 每个模型具有不同的速度和能力特性


## 核心：Tab
https://docs.cursor.com/zh/tab/overview#tab
- 接受：Tab
- 拒绝：Esc
- 逐词接受：Ctrl+Arrow-Right

- 如何生成的？
  - 上下文窗口中的代码被加密发送到后端
  - 后端解密后读取上下文
  - Cursor Tab模型预测代码建议，并返回给客户端在编辑器中显示
# 相关术语

- AI Agent 人工智能代理
  - AI Agent相当于一个虚拟助理，能够根据目标、规则和环境做出决策和行动
  - 根据收集到的信息自主做出决策、与环境交互
  - 传统AI类似于相机的手动聚焦模式，需要人去选中画面主体，AI Agent就可以对画面自识别，智能聚焦
