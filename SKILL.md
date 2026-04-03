---
name: codebase-to-web
description: "Agent skill: GitHub OSS Agent Skill repo → self-contained single-file Chinese Skill Lab HTML (meta, journey chat, user vs behind-the-scenes, tree, README bullets). Default output web/<owner>-<repo>.html. Host-agnostic: Cursor, Claude Code, Windsurf, OpenClaw. Lab·Canonical visuals + frontend-design discipline; optional cool/teal variants. Triggers: repo URL, 生成 Skill 实验室页, skill lab HTML."
---

# OSS Agent Skill → 单页「实验室」HTML（Codebase to Web）

## 目标

交付**本地可双击打开**的单文件 HTML，帮助读者理解「装完 / 触发之后谁在对谁做什么」，并对照 Star/Fork 与目录结构。

## 落盘规则（重要）

- **默认**：一个仓库 → **一个独立 HTML** → **`web/<owner>-<repo>.html`**（或用户在对话里指定的目录）。保持一仓一文件。
- **多仓库**：用户在同一条需求里给出 2+ 个仓库，或要求「整合成 Tab 页」时，可输出单一整合 HTML；无偏好时 **优先多个单文件**。
- 不要把实验室页散落在与项目无关的路径根目录；与用户约定统一输出目录（本 skill 默认识别 **`web/`**）。

## 宿主与安装路径（生成说明文 / journey 时可引用）

撰写「如何安装本 skill」或对话 journey 里点名宿主时，按用户真实环境选用；常见对应关系（随各产品更新以官方文档为准）：

| 宿主 | 典型 skill 目录（示例） |
|------|-------------------------|
| **Cursor** | 项目内 `.agents/skills/<skill-folder>/`（或团队约定路径） |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | 以 Windsurf / Cascade 当前文档为准（常为项目级 skills 配置） |
| **OpenClaw** | 如 `~/.openclaw/skills/`、用户级 `~/.agents/skills/`、或工作区 `skills/` 等；**优先级与加载规则**见官方文档：[OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

若用户未指定宿主，正文可用泛称 **「宿主 / Agent IDE」**，避免写死单一品牌。

## 固定版式顺序

1. **GitHub 元数据条**：链接、`stargazers_count`、`forks_count`、`created_at`（UTC）。
2. **大白话**（`plain`）：零术语场景句。
3. **交付物 blurb**：Markdown / Hook / 脚本等形态。
4. **组件路径（必须在分步旅程之前）**：可播放的对话 journey；`data-sender` 区分角色；条数按真实路径展开（复杂项目 6–15 条 journey map）。**可**在气泡中体现「用户在 Cursor / Claude Code / OpenClaw 中触发技能」等路径，与上表一致。
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
