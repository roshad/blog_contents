---
tags:
  - AI
title: Untitled
date created: 260223
date modified: 260223
---
### 1. 核心架构：什么是 CLI + Skill？

这是微软提出的另一种“让 AI 操控浏览器”的思路，与 MCP 的标准化 Server 不同，它由两部分组成：

- **CLI (`playwright-cli`)**：一个高性能、无状态（通过 Session 持久化）的命令行工具。它将复杂的浏览器操作（点击、输入、滚动、快照）封装成了简单的 Bash 命令。
- **Skill (`SKILL.md`)**：一个专门给 AI 看的“说明书”。它不是代码定义，而是一份结构化的文档，定义了 AI 应该如何使用该 CLI、操作的优先级（例如：先 snapshot 再行动）以及如何解析精简后的页面状态。
### 2. 比 MCP  
- pros
- **极致的 Token 效率 (Token Efficiency)**：
- **“脱机”上下文管理**：
    - 它将浏览器的视觉状态（截图、完整 DOM）保存在本地磁盘。AI 只有在需要“看图”时才显式调用相关命令。这种“按需读取”的机制让 AI 能够处理极长路径的 web 任务而不会因为 Context 溢出而“失忆”。
- **部署极度简单**：
    - 不需要配置复杂的 MCP Server 链条。只要环境里有 `npx`，AI 就能直接通过终端命令调用。它非常适合像 **Claude Code** 或 **Github Copilot CLI** 这种原生就拥有强大终端能力的 AI Agent。
- **Session 级持久化**：
    - 它原生支持将 Cookie 和 Storage 状态存入文件或通过 Socket 复用。这意味着 AI 可以在不同的 CLI 调用之间完美保持登录状态，而不需要像某些 MCP 实现那样每次重新配置。
### 3. 比 MCP 少了啥？（劣势）
- **生态标准化**：
    - **CLI+Skill**  需要CLI环境。
    - **MCP** 是一个通用的跨工具标准（数据库、文件、API 都能用同一个协议）。
- **工具发现机制 (Discovery)**：
    - 在 MCP 中，客户端可以自动枚举 Server 提供的所有 Tool。
    - 在 CLI+Skill 中，AI 必须预配置（或通过检索读取）`SKILL.md` 才能知道有哪些命令可用。
- **结构化交互**：
    - MCP 基于 JSON-RPC，返回的是强类型的结构化数据。
    - CLI 模式主要依赖文本输出。虽然 `playwright-cli` 的输出也非常规范，但不如 MCP 协议那样方便后续的其他编程逻辑直接解析。
### 4. 总结与建议：该选哪一个？

|维度|Playwright-cli (CLI + Skill)|Playwright MCP Server|
|---|---|---|
|**核心受众**|**Coding Agents** (如 Claude Code, Cursor)|通用 AI 助手 / 自研 Agent 框架|
|**Token 消耗**|**极低** (针对长对话优化)|较高 (通常传输大量元数据)|
|**响应速度**|极快 (直接进程调用)|中等 (需要协议握手/转换)|
|**易用性**|只要会写 Bash 就能集成|需要支持 MCP 协议的客户端|

**结论：**
- 如果你正在开发一个**高频操作、需要长程推理、且对 Token 成本敏感**的 Coding Agent，`playwright-cli` 的这种 **CLI + Skill** 架构目前看是**超越 MCP** 的最佳实践。
- 如果你需要一个**标准统一、多工具协作、对协议规范要求严苛**的系统，**MCP** 仍然是生态兼容性最好的选择。