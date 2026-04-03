---
name: web-learning-github
description: "Agent skill (Web Learning GitHub): Skill repo → single-file HTML walkthrough (fd-pass layout: two-column steps, Next/Play all/Reset chat). Default web/<owner>-<repo>.html. Language: follow user unless README demo needs EN+中文 toggle. Palette may vary (Lab·Canonical + optional blind-box variants). Hosts: Cursor, Claude Code, Windsurf, OpenClaw."
---

# Agent Skill repo → single-file visual HTML (Web Learning GitHub)

## Goal

Deliver a **double-clickable** single HTML file that explains **who talks to whom after install/trigger**, with Star/Fork and repo layout context—**learning / orientation**, not a shipping scaffold generator.

## Output language (required)

- **Default:** if the user wants a normal walkthrough (no README demo mention), generate **one language only**—match **English** or **中文** from the user’s prompt (dominant language; if unclear, default **English** for this OSS bundle unless they prefer 中文).
- **README / demo screenshot:** when the goal is a **bilingual** page for **GitHub README** (or they say “demo 截图要中英文”), build **one HTML** with an **EN | 中文** UI toggle and paired blocks—same as below.

### One file, EN / 中文 toggle (when needed)

When bilingual is required: duplicate each user-visible block (e.g. `block-i18n en` / `zh` or equivalent), add **EN | 中文** controls + small JS on `html.is-en` / `html.is-zh`. **Default** toggle to the user’s first message language or **English**. Keep **one** GitHub meta bar and **one** tree; translate labels only.

## File output rules

- **Published OSS skill bundle (this repo):** one repo → one file → **`web/<owner>-<repo>.html`** (or a directory the user specifies).
- **Author local lab (multi-project workspace):** when the user asks to keep generated walkthroughs **out of the skill repo** or under their **OSS lab folder**, also write (or only write) **`30_resources/oss-skill-lab/<owner>-<repo>.html`** relative to the parent workspace that holds `web-learning-github/` and `30_resources/` — adjust the path if their tree differs; **do not** imply that path exists for every downloader of the skill.
- **Multiple repos** in one request, or explicit “single tabbed page”: you may emit one combined HTML; if no preference, **prefer separate files**.
- Agree the output directory in chat if **both** `web/` and lab paths apply; **default for strangers cloning the skill remains `web/`**.

## Hosts (for journey/install copy)

When naming the host in journey bubbles or install steps, follow the user’s real environment. Examples (always verify against vendor docs):

| Host | Typical skill path (examples) |
|------|-------------------------------|
| **Cursor** | Project `.agents/skills/<skill-folder>/` (or team convention) |
| **Claude Code** | `~/.claude/skills/<skill-folder>/` |
| **Windsurf** | Per current Windsurf / Cascade docs (often project-level skills) |
| **OpenClaw** | e.g. `~/.openclaw/skills/`, `~/.agents/skills/`, or workspace `skills/` — load order: [OpenClaw · Skills](https://docs.openclaw.ai/skills/) |

If unknown, say **“host / agent IDE”** instead of a single brand.

## Section order

1. **GitHub meta bar** — link, `stargazers_count`, `forks_count`, `created_at` (UTC).
2. **Plain blurb** — jargon-free scenario sentence.
3. **Deliverable blurb** — Markdown vs hooks vs scripts, etc.
4. **Component path / journey (before long steps)** — playable chat; `data-sender` roles. **Do not hard-code a fixed number of messages.** Use as many (or as few) bubbles as the real repo needs—simple skills might be **3–5** beats, tangled repos **10+**. Never pad to a magic number.
5. **Step journey** — per step “on the surface” / “behind the scenes”.
6. **Repo tree** — `pre.tree` monospace.
7. **README bullets** — demand / distribution / moat / compliance, one each.

## Interaction & layout (non‑negotiable: fd‑pass contract)

Unless the user explicitly opts out, generated pages must **behave and lay out** like the fd-pass reference:

- **Page structure:** `.shell`, `.hint`, `.meta-bar`, `.plain`, `.blurb`, `.section-title`, `.readme-box`, `footer.note` (see `web/YeJe-cpu-web-learning-github.html` or `*.fd-pass.html`).
- **Component path:** `.path-wrap` → `.chat-window` → `.chat-messages` (avatar bubbles), `.chat-typing` with **`#<chatWindowId>-typing-avatar`**, `.chat-controls` with **Next**, **Play all**, **Reset**, and **`.chat-progress`** derived from **actual** `.chat-message` count.
- **Steps:** `.step` + **`.grid2`** (≥720px **two columns**): `.card.user` (surface) and `.card.back` (backstage).

## Color & surface (flexible — “盲盒 OK”)

Within **`frontend-design` discipline** (no Inter-for-headlines, no tacky purple-gradient heroes), you may **vary** accents, gradients, borders, and decorative blocks between runs—**Lab·Canonical** as the default **starting point**, plus **Variant A/B** or a light “wildcard” when it improves clarity or fits the repo vibe. **Do not** treat exact hex values as immutable; **do** keep contrast readable and the **interaction contract** above intact.

Read `references/ui-tokens.md` and `references/frontend-design-notes.md`.

## Chat widget

Per `.chat-window`: `typing-avatar` id = `{chatWindowId}-typing-avatar`; `.chat-message` elements start `display:none`; **`initChat`-style** controls: step forward, play all, reset; progress from `.chat-message` count.

## More

Start here if the folder names look cryptic: **`references/README.md`** (plain-language map).

- `references/workflow.md`
- `references/ui-tokens.md`
- `references/frontend-design-notes.md`

**Chinese:** `SKILL.zh-CN.md`, `references/*.zh-CN.md`.
