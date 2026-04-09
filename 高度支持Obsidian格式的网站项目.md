---
title: Untitled
date created: 260221
date modified: 260221
---
### 1. Astro + Obsidian 开源模板 (追求绝对自由与极致特效的首选)

**Astro** 是目前前端圈非常火的静态生成框架。它的特性使其成为做高度定制化“数字花园”的最完美基底。

- **为什么推荐它**：
    - **极致自由，框架无关**：Astro 允许你在同一个项目里混用 React、Vue、Svelte、Tailwind CSS。你想借用哪个生态的特效组件，直接装 npm 包就能用（比如 Framer Motion 的炫酷动画，或者 GSAP 特效）。
    - **加自定义页面极简**：基于文件路由，你只需要在 `src/pages` 下新建一个 `about.astro` 或 `portfolio.vue`，一个完全自定义排版的页面就出来了，和 Obsidian 笔记互不干扰。
    - **原生支持 View Transitions**：Astro 原生支持极其平滑的页面跳转动画（类似原生 App 的体验），只需加一行代码，这是目前网页特效的显学。
- **好用的开源模板推荐**：
    - **Astro Spaceship**：专门为渲染 Obsidian 设计的 Astro 主题，完美支持双向链接 `[[ ]]` 和 Obsidian 特色的语法，自带星空主题，但你可以完全把前端重写掉。
    - **Astro Modular**：另一个高度兼容 Obsidian 语法的 Astro 主题包。

### 2. Quartz v4 (专为 Obsidian 打造，且适合 TypeScript 开发者深度魔改)

之前稍微提到了 **Quartz**，但作为一个开发者，你需要知道它在 v4 版本进行了巨大的重构，完全抛弃了以前臃肿的 Hugo，完全使用 **Node.js + TypeScript** 从零重写了。

- **为什么推荐它**：
    - **插件化架构**：Quartz 现在像积木一样，它利用 Remark/Rehype 解析 Markdown。如果你想自己写一个解析某种特殊语法的特效，只需写一个 TypeScript 插件。
    - **React 组件库**：它的 UI 完全是基于 Preact (React 的轻量版) 写的。如果你懂 React，你可以直接在 `components` 文件夹里重写任何一块 UI，比如自己写一个带 3D 悬浮特效的组件替换掉默认的侧边栏。
    - **无需配置 Obsidian 语法**：Astro 项目通常需要你自己找插件去解析 Obsidian 的 Callouts (引用块)、嵌套本地图片和 Graph 图谱，而 Quartz 原生就把这些粗活干完了，你只管在其之上做美化和二开。
### 3. Docusaurus/Nextra (适合重度 React/Next.js 开发者)

如果你日常是写 React/Next.js 的，想用你最熟悉的栈：

- **Docusaurus** 是 Meta (Facebook) 开源的文档站生成器。你可以完全把你自己的 React 组件插入到 Markdown 中（通过 MDX），做自定义单页（Swizzle 机制）也很成熟。
- 缺点是：你需要自己找一些社区的 remark 插件（比如 `remark-obsidian`）来把 Obsidian 特有的双向链接转化为普通路由，否则点击会失效。