# Codebase to Web

**Agent skill**（**Cursor**、**Claude Code**、**Windsurf**、**OpenClaw** 等宿主）：把 GitHub 上的 **Agent Skill 仓库** 变成**单文件、可本地打开的「Skill 实验室」HTML**。

指向 skill 仓，得到可双击浏览的页面——**区块阅读**、**可步进组件路径 journey**、**大白话**、**目录树**、**README 简析**——避免典型大紫渐变「AI 皮肤」。

**仓库：** [github.com/YeJe-cpu/codebase-to-web](https://github.com/YeJe-cpu/codebase-to-web) · [English](README.md)

---

## Skill 在仓库里长什么样？（GitHub 上能看到吗？）

**能。** Skill **就是本仓库**，不是别的目录。克隆后你会看到：

| 路径 | 作用 |
|------|------|
| **[`SKILL.md`](SKILL.md)** | 主技能说明（多数宿主默认读这个文件）。 |
| **[`SKILL.zh-CN.md`](SKILL.zh-CN.md)** | 中文规则的完整副本；可选，也可合并进一份 `SKILL.md`。 |
| **`references/`** | 生成 HTML **实验室页**时模型要参考的补充说明：配色字体、版式检查、别做成大紫渐变那张图——**不是**另一个独立产品。通俗说明见 **[`references/README.md`](references/README.md)**。 |
| **`web/`** | **生成结果**默认落盘处；仓库里只保留占位（`.gitkeep`），真实 `.html` 一般不入库（见 `.gitignore`）。 |

以前口头叫 **Skill Lab** / **`oss-skill-lab-html`**，指的是**这类单页 HTML 的产出**；**源代码形态的 skill** 就在本仓库根目录的 **`SKILL.md`**（以及 `references/`），没有名为 `skill-lab` 的子文件夹专门存 skill。

---

## GitHub 上到底是什么

只有上述 skill 包 + 双 README + `LICENSE`。**没有**上传你整个 `emo专用` 工作区。

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
| **Claude Code** | 如 `~/.claude/skills/codebase-to-web/`（口语音常被听写成 **Cloud Code**，指同一产品） |
| **Windsurf** | 以当前官方文档中的项目级 skills 为准 |
| **OpenClaw** | 如 `~/.openclaw/skills/`、`~/.agents/skills/` 或工作区 `skills/`，见 [OpenClaw · Skills](https://docs.openclaw.ai/skills/)（中文社群口语「**龙虾**」多指 **OpenClaw**，文档与 journey 里请写规范名） |

保留 **`SKILL.md` + `SKILL.zh-CN.md` + `references/`**（含 `*.zh-CN.md` 镜像）。多数宿主默认只读 `SKILL.md`；中文说明可合并进一份或按团队约定 symlink。  
**产出语言：** 见 `SKILL.md` / `SKILL.zh-CN.md` —— 英文对话 → 整页英文，中文对话 → 整页中文。

然后对模型说：**「把 `owner/repo` 做成 Skill 实验室单页。」**

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
├── SKILL.zh-CN.md
├── references/
├── web/
├── README.md
└── README.zh-CN.md
```

## 许可证

MIT — 见 [LICENSE](LICENSE)。
