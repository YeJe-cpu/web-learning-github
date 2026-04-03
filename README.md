# Codebase to Web

An **agent skill** (Cursor, Claude Code, Windsurf, **OpenClaw**, …) that turns **Agent Skill repositories** on GitHub into a **beautiful, self-contained, single-page HTML lab**.

Point it at a skills repo. Get back a **lab you can double-click**—**scroll-friendly sections**, **step-through journey** (who loads whom), **plain-language blurbs**, **repo tree**, and **README context**—without the typical purple-gradient AI look.

**Repo:** [github.com/YeJe-cpu/codebase-to-web](https://github.com/YeJe-cpu/codebase-to-web) · [中文说明](README.zh-CN.md)

---

## Where is the skill on GitHub?

The skill **is** this repo. After `git clone`, you get:

| File / folder | Role |
|---------------|------|
| **[`SKILL.md`](SKILL.md)** | Main skill instructions (what hosts usually load). |
| **[`SKILL.zh-CN.md`](SKILL.zh-CN.md)** | Same rules in Chinese; optional if you merge into one file. |
| **`references/`** | Extra rules the agent reads when **generating** the HTML lab—fonts/colors, layout checklist, design guardrails. Not a second product; see [`references/README.md`](references/README.md). |
| **`web/`** | Default **output** folder for generated `.html` (repo keeps only `.gitkeep`; real pages are local / gitignored). |

There is **no** separate “Skill Lab” source folder name on disk—the old working title was `oss-skill-lab-html`; the publishable bundle lives **here** under **`codebase-to-web`**.

---

## What’s on GitHub

Only the files above plus READMEs, `LICENSE`, and a tiny [`docs/`](docs/README.md) helper (GitHub “About” copy). Not your whole `emo专用` workspace.

---

## Who is this for?

**“Skill hoarders who still have a job to do”—** you already use **Cursor**, **Claude Code**, **Windsurf**, **OpenClaw**, or similar. You **star skill repos** (or vendor `anthropics/skills`, community packs, in-house `SKILL.md` trees). They work. But you don’t yet have a **single map** of **install → trigger → which file fires → what the README implies**.

**Practical goals:**

* Steer agents (commands, skill folders)  
* Spot README oversimplifications (hooks live elsewhere)  
* Onboard teammates without fifteen Markdown tabs  
* Share one artifact with maintainers  

---

## What the lab looks like

One **`.html`** — no bundler, no `npm install`; works offline after first font load (Google Fonts):

* **GitHub meta bar** — stars, forks, created-at (+ **snapshot** in footer)  
* **Plain-language blurb**  
* **Interactive journey** — user → host → skill / ref → … (length follows the real path)  
* **User vs behind-the-scenes steps**  
* **Repository tree**  
* **README heat bullets** — demand / distribution / moat / compliance  
* **Lab·Canonical** design (Fraunces + Source Sans 3 + terracotta); ideas from [Anthropic `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design); optional cool/teal variants on request  

---

## How to install

Copy the **`codebase-to-web`** folder (this repo) into the skill location your **host** expects:

| Host | Typical location |
|------|------------------|
| **Cursor** | e.g. `.agents/skills/codebase-to-web/` in your project (or your team convention) |
| **Claude Code** | e.g. `~/.claude/skills/codebase-to-web/` |
| **Windsurf** | per current Windsurf / Cascade docs (project-level skills path) |
| **OpenClaw** | e.g. `~/.openclaw/skills/`, `~/.agents/skills/`, or workspace `skills/` — see [OpenClaw · Skills](https://docs.openclaw.ai/skills/) for load order |

Keep this layout (English references are default; Chinese mirrors end with `.zh-CN.md`):

```
codebase-to-web/
├── SKILL.md                 # canonical for most hosts
├── SKILL.zh-CN.md           # Chinese skill copy (optional; merge if your host reads one file)
├── references/
│   ├── workflow.md
│   ├── workflow.zh-CN.md
│   ├── ui-tokens.md
│   ├── ui-tokens.zh-CN.md
│   ├── frontend-design-notes.md
│   └── frontend-design-notes.zh-CN.md
├── web/                     # default HTML output (ignored by git)
├── README.md
└── README.zh-CN.md
```

**Page language:** English prompt → English lab page; 中文 → 中文页面 (see `SKILL.md`).

Then in chat: *“Turn `owner/repo` into a Skill Lab HTML page.”*

### Output path

Default: **`web/<owner>-<repo>.html`**. Override in your prompt if needed.

---

## Trigger phrases

* “Turn this skills repo into a Skill Lab HTML”  
* “Generate a lab page for this Agent Skill repo”  
* “Journey first, then steps — 实验室页”  
* “把这个仓库做成 Skill 实验室单页”  

---

## Design philosophy

### Install first, journey second

Force the **journey block before** long-form steps so the call path sticks.

### Show the call path

Prefer **step-through chat** or **tree** over long prose; ~2–3 sentences per blurb.

### One artifact

Filename **`owner-repo.html`**; **no build** = reproducible output.

### Pair with *Codebase to Course*

[zarazhangrui/codebase-to-course](https://github.com/zarazhangrui/codebase-to-course) for **application code** depth; **Codebase to Web** for **`SKILL.md` ecosystems** (packaging, triggers, references).

---

## Skill structure

```
codebase-to-web/
├── SKILL.md
├── SKILL.zh-CN.md
├── references/
├── docs/              # optional: GitHub About copy — see docs/README.md
├── web/
├── README.md
└── README.zh-CN.md
```

---

## License

MIT — [LICENSE](LICENSE).

## Contributing

[CONTRIBUTING.md](CONTRIBUTING.md).
