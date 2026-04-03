---
name: repo-to-skill-lab
description: "Generate a self-contained Chinese Skill Lab HTML page for GitHub OSS Agent Skill repos—meta, journey chat, step-by-step user vs behind-the-scenes, tree, README heat. Default one repo → one file in skill-lab/. Visual Lab·Canonical (Fraunces + terracotta) with frontend-design discipline; optional cool/teal variants. Triggers: repo URL, 生成 Skill 实验室页, agent skill journey."
---

# OSS Agent Skill → 单页「实验室」HTML

## 目标

交付**本地可双击打开**的单文件 HTML，帮助读者理解「装完 / 触发之后谁在对谁做什么」，并对照 Star/Fork 与目录结构。

## 落盘规则（重要）

- **默认**：一个仓库 → **一个独立 HTML** → **`skill-lab/<owner>-<repo>.html`**（或用户指定的同级目录）。保持一仓一文件。
- **多仓库**：用户在同一条需求里给出 2+ 个仓库，或要求「整合成 Tab 页」时，可输出单一整合 HTML；无偏好时 **优先多个单文件**。
- 不要把实验室页散落在与项目无关的路径根目录；与用户约定统一输出目录（本仓库默认识别 `skill-lab/`）。

## 固定版式顺序

1. **GitHub 元数据条**：链接、`stargazers_count`、`forks_count`、`created_at`（UTC）。
2. **大白话**（`plain`）：零术语场景句。
3. **交付物 blurb**：Markdown / Hook / 脚本等形态。
4. **组件路径（必须在分步旅程之前）**：可播放的对话 journey；`data-sender` 区分角色；条数按真实路径展开（复杂项目 6–15 条 journey map）。
5. **分步旅程**：每步「表面上」/「背后」。
6. **仓库骨架**：`pre.tree`。
7. **README 简析**：需求 / 传播 / 壁垒 / 合规，各 1 bullet。

## 视觉

读 `references/ui-tokens.md`（Lab·Canonical 默认）与 `references/frontend-design-notes.md`（与 Anthropic `frontend-design` 纪律对齐，非运行时依赖）。变体 A/B 仅用户明确要求或「盲盒」时使用。

## Chat 脚本

每个 `.chat-window`：`typing-avatar` 的 id 为 `{chatWindowId}-typing-avatar`；消息初始 `display:none`，进度按 `.chat-message` 数量自动计算。

## 扩展阅读

- `references/workflow.md`
- `references/ui-tokens.md`
- `references/frontend-design-notes.md`
