# Codebase to Web

**Agent skill**（**Cursor**、**Claude Code**、**Windsurf**、**OpenClaw** 等宿主）：把 GitHub 上的 **Agent Skill 仓库** 变成**单文件、可本地打开的「Skill 实验室」HTML**。

指向 skill 仓，得到可双击浏览的页面——**区块阅读**、**可步进组件路径 journey**、**大白话**、**目录树**、**README 简析**——避免典型大紫渐变「AI 皮肤」。

**仓库：** [github.com/YeJe-cpu/codebase-to-web](https://github.com/YeJe-cpu/codebase-to-web) · [English](README.md)

> 可选另一套叙事（开发者营销取向）：[Track A 中文](docs/README-track-a.zh-CN.md) · [EN](docs/README-track-a.md)

---

## 适合谁？

**「收了 skill 还要交付的人」** —— 你已在使用 **Cursor / Claude Code / Windsurf / OpenClaw** 等。你会 **star 或内置** 各类 `SKILL.md` 仓库，但缺一张 **安装 → 触发 → 读哪些文件 → README 意味着什么** 的总图。

**目标：** 指挥 agent · 验 README 是否藏 Hook · onboarding · Maintainer 对齐。

---

## 实验室页长什么样？

单个 **`.html`**，无需打包；字体首次需联网（Google Fonts）。含：GitHub 元数据、大白话、可步进 journey、分步（表面/背后）、目录树、README 简析、**Lab·Canonical** 视觉（可要求变体）。理念参考 [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design)。

---

## 安装（按宿主选路径）

将本仓库中的 **`codebase-to-web`** 文件夹拷入对应 skill 目录：

| 宿主 | 常见路径（示例） |
|------|------------------|
| **Cursor** | 如项目内 `.agents/skills/codebase-to-web/` |
| **Claude Code** | 如 `~/.claude/skills/codebase-to-web/`（其他 CLI 式宿主以官方为准） |
| **Windsurf** | 以当前官方文档中的项目级 skills 为准 |
| **OpenClaw** | 如 `~/.openclaw/skills/`、`~/.agents/skills/` 或工作区 `skills/`，加载优先级见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

保留 `SKILL.md` 与 `references/` 结构。然后对模型说：**「把 `owner/repo` 做成 Skill 实验室单页。」**

### 产出路径

默认 **`web/<owner>-<repo>.html`**；可在对话里改目录。

---

## 触发示例

* 「把这个 skill 仓生成实验室 HTML」  
* 「组件路径 journey 在前，再分步」  
* “Turn this skills repo into a Skill Lab HTML”  

---

## 设计理念

**先 journey 再长文**；**能对话/树就不堆段**；**单文件可分享**。  
应用代码深读用 [zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)；**Skill 包与调用链**用 **Codebase to Web**。

---

## 目录结构

```
codebase-to-web/
├── SKILL.md
├── references/
├── docs/
├── web/
├── README.md
└── README.zh-CN.md
```

## 许可证

MIT — 见 [LICENSE](LICENSE)。
