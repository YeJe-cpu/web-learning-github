---
name: web-learning-github
description: "Agent skill（Web Learning GitHub）：与 SKILL.md 一致。默认单语随用户；README 演示/截屏要双语时再做 EN|中文 切换。版式 fd-pass（双列分步、下一条/全部播放/重播）。默认 web/<owner>-<repo>.html。配色可在纪律内微调盲盒。宿主：Cursor 等。"
---

# Agent Skill 仓 → 单文件可视化 HTML（Web Learning GitHub）

## 产出语言（必遵守）

- **默认：**普通 walkthrough、未提 README 演示 → **整页单语**，随用户提示的**主导语言**（中文为主则全文中文，英文为主则全文英文；混杂时随主导；未声明时国际化场景可偏英文）。
- **README / demo 截屏：**用户明确要放进 **README 的演示图、要中英文**（或「demo 双语截屏」）→ **单文件** 加 **EN | 中文** 切换与成对文案块；元数据条与目录树仍可共用。

### 同一 HTML 内中英文切换（仅在需要时）

需要双语时：为可见块做 **英文 + 中文** 两套（如 `block-i18n en` / `zh`），加切换按钮与 `html.is-en` / `is-zh`；**默认**以用户先发语言或英文为主。

> 多数宿主只会自动读 **`SKILL.md`**。若环境只加载一份，可把本文件合并进 `SKILL.md` 或按团队约定 symlink。

## 目标

交付**本地可双击打开**的单文件 HTML，帮助读者理解「装完 / 触发之后谁在对谁做什么」，并对照 Star/Fork 与目录结构——偏**学习、扫盲与路径理解**，不是帮你生成上线代码脚手架。

## 落盘规则（重要）

- **对外开源的 skill 包（本仓库）**：一个仓库 → **一个 HTML** → **`web/<owner>-<repo>.html`**。
- **维护者本机实验室**（多项目工作区）：用户希望生成物**不进 skill 仓**或统一放在 **OSS 实验目录**时，可另写或只写 **`30_resources/oss-skill-lab/<owner>-<repo>.html`**（相对于同时包含 `web-learning-github/` 与 `30_resources/` 的父目录；他人克隆后若无此路径，以用户当场约定为准）。
- **多仓库**：同一需求多仓或要 Tab 合一页时，可输出整合 HTML；无偏好时 **优先多文件**。
- 若 **`web/`** 与 **实验室目录** 都要，在对话里**确认**；**陌生人只用本 skill 时默认仍写 `web/`**。

## 宿主与安装路径（生成说明文 / journey 时可引用）

| 宿主 | 典型 skill 目录（示例） |
|------|-------------------------|
| **Cursor** | 项目内 `.agents/skills/<skill-folder>/` |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | 以 Windsurf / Cascade 当前文档为准 |
| **OpenClaw** | 如 `~/.openclaw/skills/`、`~/.agents/skills/`、工作区 `skills/` 等，参见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

若用户未指定宿主，正文可用泛称 **「宿主 / Agent IDE」**。

## 固定版式顺序

1. **GitHub 元数据条**  
2. **大白话**  
3. **交付物 blurb**  
4. **组件路径（必须在分步旅程之前）** — 聊天条数**不写死**：按真实仓库需几条写几条；简单仓可很少，复杂仓可 **10+**，勿为凑数硬塞。  
5. **分步旅程**（表面上 / 背后）  
6. **仓库骨架** `pre.tree`  
7. **README 简析**  

## 交互与版式（fd‑pass 约定，应遵守）

除非用户明确不要，**行为和排版**应对齐 fd-pass：

- **页面结构**：`.shell`、`.hint`、`.meta-bar`、`.plain`、`.blurb`、`.section-title`、`.readme-box`、`footer`（见 `web/YeJe-cpu-web-learning-github.html` 或 `*.fd-pass.html`）。
- **组件路径**：`.path-wrap` → `.chat-window` → `.chat-messages`、`.chat-typing` + **`#<chatWindowId>-typing-avatar`**、控制条 **下一条 / 全部播放 / 重播**、**`.chat-progress`** 按**实际** `.chat-message` 条数计算。
- **分步**：`.step` + **`.grid2`**（宽屏 **两列**）`.card.user` / `.card.back`。
- **目录树**：`pre.tree`，可用 `.f` / `.n`。

## 配色与装饰（可灵活、「盲盒」友好）

在 **`frontend-design` 纪律**内（主标题别 Inter 糊脸、别大紫渐变铺底等），可在各次生成中**微调**强调色、渐变、描边、点缀色块；**Lab·Canonical** 为默认起点，**变体 A/B** 或轻量 wildcard 允许用于气质/区分度。**不要**把某个 hex 当铁律；**要**保证对比可读与上面**交互约定**不打折。

读 `references/ui-tokens.zh-CN.md`、`references/frontend-design-notes.zh-CN.md`。

## Chat 脚本

每个 `.chat-window`：`typing-avatar` id = `{chatWindowId}-typing-avatar`；`.chat-message` 初始 `display:none`；**fd-pass 同款** 逐步展示、**全部播放**、**重播**；进度为「已 reveal / 总数」。

## 扩展阅读（中文）

先看 **`references/README.md`**。

- `references/workflow.zh-CN.md`
- `references/ui-tokens.zh-CN.md`
- `references/frontend-design-notes.zh-CN.md`

**English:** `SKILL.md` + `references/*.md`。
