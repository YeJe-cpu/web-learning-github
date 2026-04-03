# repo-to-skill-lab

A **Claude Code / Cursor / Windsurf–friendly skill** that turns any **public GitHub Agent Skill repo** into a **beautiful, self-contained, single-file HTML “lab page”**—so you can **see the journey** (who loads whom) instead of drowning in Markdown folders.

> **Naming:** Pronounced like *[codebase-to-course](https://github.com/zarazhangrui/codebase-to-course)* but for **repos full of `SKILL.md`**: *repo → skill lab*. Easier to remember than `oss-skill-lab-html`.

[中文说明](README.zh-CN.md)

---

## Who is this for?

- You **starred a skills repo** (or cloned `anthropics/skills`, community packs, etc.) and want a **one-glance map**: install path → trigger → which file fires → what the README hype is about.
- You **write or maintain** Agent Skills and want a **shareable HTML artifact** for teammates who won’t read fifteen nested Markdown files first.
- You’re fine with **Chinese-first** narrative copy in the output (the skill is optimized for 中文实验室页); swap language in your prompt if you want EN-only.

---

## What the output looks like

One **`.html`** you can double-click offline (Google Fonts still need network once):

| Block | Why it exists |
|--------|----------------|
| **GitHub meta bar** | Stars / forks / created—snapshot time in footer |
| **Plain-language blurb** | “What is this in one breath?” |
| **Interactive journey chat** | Step-through bubbles: user → host → skill → … |
| **User vs behind-the-scenes steps** | What you see vs what files/hooks run |
| **Repo tree** | Monospace skeleton aligned with README |
| **README heat bullets** | Demand / distribution / moat / compliance |

**Visual default (“Lab·Canonical”):** warm editorial UI—**Fraunces + Source Sans 3**, terracotta accent, balanced column width—aligned with discipline from [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design) (ideas, not a runtime dependency). Optional **cool** or **teal technical** variants when you ask for a different vibe.

---

## How to install

### Cursor / Claude Code / generic agents

1. Copy this folder into your skills directory, e.g.  
   `.agents/skills/repo-to-skill-lab/` or `~/.claude/skills/repo-to-skill-lab/`
2. Keep structure:

```
repo-to-skill-lab/
├── SKILL.md
├── references/
│   ├── workflow.md
│   ├── ui-tokens.md
│   └── frontend-design-notes.md
└── README.md
```

3. In chat, point at a repo and ask to generate the lab page.

### Output location

By default, generated files go to **`skill-lab/<owner>-<repo>.html`** next to your project. Change the folder in your prompt if you prefer another path.

---

## Trigger phrases

- “Generate a Skill Lab HTML for `owner/repo`”
- “把这个仓库做成 Skill 实验室单页”
- “OSS journey 单页 + 组件路径在前”
- Drop a GitHub URL and ask for **实验室页 / skill_lab**

---

## How this relates to **codebase-to-course**

| | [codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) | **repo-to-skill-lab** |
|--|--|--|
| **Input** | Any application codebase | Repos dominated by **Agent Skills** |
| **Output** | Interactive **course** (modules, quizzes, diagrams) | Single **lab handout** (meta + journey + tree + README takeaways) |
| **Goal** | Teach *how the code runs* | Teach *how the skill **installs & chains*** |

They pair nicely: use **course** for runtime code literacy; use **lab** for *agent packaging* literacy.

---

## Launch & positioning tips (optional)

If you’re shipping your **own** fork or announcing the repo, methodology from **[jonathimer/devmarketing-skills](https://github.com/jonathimer/devmarketing-skills)** is a good fit: developer-audience honesty, concrete examples, “Show HN–style” substance over hype. Install that pack separately if you want slash-commands for launch copy.

**Topic tags that ride current interest:** `agent-skills`, `claude-code`, `cursor`, `windsurf`, `static-html`, `developer-education`, `llm`.

---

## License

MIT—see [LICENSE](LICENSE).

Anthropic’s `frontend-design` text remains under its own license if you copy quotes; link to their [repo](https://github.com/anthropics/skills/tree/main/skills/frontend-design).

---

## Contributing

PRs welcome: clearer journey templates, EN-first variant, or tighter defaults for your host. Open an issue with a sample repo if the HTML misses the real call path.
