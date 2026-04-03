# Contributing

1. **Skill behavior** → `SKILL.md` (English) and/or `SKILL.zh-CN.md` (中文说明，需与英文版语义对齐) + `references/`.
2. **Visual tokens** → `references/ui-tokens.md` + `references/ui-tokens.zh-CN.md` (Lab·Canonical default).
3. **User-facing docs** → `README.md` / `README.zh-CN.md`. Maintainer-only drafts should **not** land in `docs/` unless they help fork owners (see `docs/README.md`).

Keep generated `web/*.html` out of PRs unless **sanitized examples**; `.gitignore` ignores them by default.

## Publish / GitHub About

When cutting a release, update GitHub **About** using [docs/GITHUB-ABOUT.md](docs/GITHUB-ABOUT.md).
