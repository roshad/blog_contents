---
title: AI UI
date created: 260210
date modified: 260223
tags:
  - AI
---
- [Design Prompts](https://www.designprompts.dev/)  风格网站示例
- [Godly ](https://godly.website/) 顶级设计示例
- [frontend-design](https://github.com/anthropics/claude-code/blob/main/plugins/frontend-design/skills/frontend-design/SKILL.md) 基本的设计规范，避免ai味为主。

| 维度           | [ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/main/.claude/skills/ui-ux-pro-max/SKILL.md) | **magic-mcp**                        |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------ |
| **定位**       | **设计百科全书与规则集**                                                                                                                 | **动态组件搬运工**                          |
| **核心卖点**     | 整合了 67 种风格和 99 条 UX 准则，非常系统地提供“行业标准”。                                                                                          | 直接从 21st.dev 库中抓取现成的、带动画的 React 代码块。 |
| **对既有网站的作用** | **规范化**：适合把一个乱糟糟的网站变整齐、变专业、变合规。                                                                                                | +几个特效组件                              |
| **生成质量**     | 依赖 Prompt 描述，质量取决于模型对规则的理解。                                                                                                    | **最高**（因为它搬运的是人类设计师预定义好的顶级代码）。       |
| **避坑属性**     | 避免常见的 UX 错误（如对比度不足）。                                                                                                           | 避免自己手写复杂动画写出 Bug。                    |
- `用 ui-ux-pro-max 为 [产品类型] 设计 [页面]，风格 [关键词]，技术栈 [栈]。先给 design system（颜色/字体/间距/组件规范），再给可落地代码。`
### 3. 在“优化既有网站”背景下的最终建议

根据你的具体痛苦点来选：

#### 情况 A：我的网站功能全，但看着很乱，逻辑不通。

- **选 `ui-ux-pro-max-skill`**。
- **原因**：它能从 UX 维度帮你梳理交互逻辑，确定一套统一的设计系统（Design System），把业余水平拉升到专业水平。

#### 情况 B：我想让我的网站快速变得“高级、炫酷”，有很多动画。

- **选 `magic-mcp`**。
- **原因**：直接“拿来主义”。它生成的代码是目前开源社区最顶尖的组件（来自 21st.dev），视觉冲击力极强，且不需要你写复杂的 Framer Motion 逻辑。

#### 情况 C：我想让我的网站有“灵魂”，看起来像设计公司定制过，且不想有 AI 味。

- **选 `frontend-design` (Anthropic)**。
- **原因**：它会帮你选择大胆的字体搭配（如 Serif 标题配独特 Sans 字体）、非对称排版。如果你用的是 Claude Code，这个 Skill 是官方调优过的，对设计质感的把控力最强。

---

### 4. 终极组合建议 (Pro Tips)

如果你想通过 AI 实现顶级优化，我建议将它们这样组合：

1. **大脑 (Thinking)**：将 `frontend-design` 的 **"Design Thinking"** 部分作为你的核心指令（System Prompt），告诉 AI 拒绝平庸。
2. **骨架 (Structure)**：利用 `ui-ux-pro-max-skill` 里的 **Layout 建议** 和 **UX Guidelines** 来确保网站好用。
3. **血肉 (Components)**：在关键位置（如 Header, Hero Section）调用 `magic-mcp` 插入 **Magic UI** 级别的组件。

**如果你不想折腾三个，最推荐哪一个？**

- 如果你追求**速度和视觉冲击力**：**`magic-mcp`**。因为它是“结果导向”的，直接给代码，效果立竿见影。
- 如果你追求**代码原创度和品牌质感**：**`frontend-design`**。它能让 AI 像个真正的设计师一样思考，而不是仅仅在拼凑组件。