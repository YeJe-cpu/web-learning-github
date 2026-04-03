# repo-to-skill-lab

把 **GitHub 上的 Agent Skill 开源仓** 生成 **单文件、可本地打开的「Skill 实验室」HTML**：先看 **组件路径**（谁加载谁），再读分步旅程、目录树和 README 热度简析。默认中文叙事；可在提示里改成全英文。

仓库名对齐 [codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) 的 **「X → Y」** 记法：**repo → skill lab**，比 `oss-skill-lab-html` 好记。

## 适用对象

- 收藏了一堆 `SKILL.md` 仓库却懒得逐层点开的人  
- 维护 Skill 包、需要给同事 **一页纸讲清安装与调用链**  
- 希望成品 **无构建步骤**、双击即看（字体首次需联网）

## 安装

将本目录拷到：

- `.agents/skills/repo-to-skill-lab/`（Cursor 等）
- 或 `~/.claude/skills/repo-to-skill-lab/`（Claude Code）

保持 `SKILL.md` 与 `references/` 结构不变。

## 产出路径

默认 **`skill-lab/<owner>-<repo>.html`**；可在对话里改输出目录。

## 触发示例

- 「给 `owner/repo` 做 Skill 实验室单页」  
- 「组件路径 journey 在前，再分步旅程」  

## 和 codebase-to-course 的关系

| | [codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) | **本 skill** |
|--|--|--|
| 输入 | 应用代码仓 | **Skill / Agent 技能包** 仓 |
| 输出 | 互动课程 | **单页实验室**（元数据 + journey + 树 + README 简析）|
| 目的 | 搞懂代码怎么跑 | 搞懂 **skill 怎么装、谁调谁** |

可并行使用：课程搞代码，实验室搞技能包。

## 发布与叙事（可选）

开源官宣可配合 [jonathimer/devmarketing-skills](https://github.com/jonathimer/devmarketing-skills) 里那套 **开发者受众** 写法：具体案例、少形容词、多可验证截图路径。

热门标签示例：`agent-skills`、`claude-code`、`cursor`、`静态页面`。

## 许可证

MIT。借用 Anthropic `frontend-design` 理念时请保留 [上游链接与许可](https://github.com/anthropics/skills/tree/main/skills/frontend-design)。
