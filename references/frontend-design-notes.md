# Alignment with Anthropic `frontend-design`

This skill does **not** bundle upstream as a runtime dependency; when generating HTML, follow its **design discipline**. Upstream: [anthropics/skills `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design).

## Before generating

- **Audience:** who reads this and what misunderstanding it fixes.
- **Tone:** default Lab·Canonical; switch variant only if the user wants cool / engineering vibes.
- **Differentiation:** journey encodes call order—avoid “another generic white page.”

## While generating

- **Type:** display + body contrast; no Inter / Roboto for the main headline.
- **Color:** primary + accent on a calm base; no full-bleed purple gradients.
- **Layout:** `.shell` medium margins (see `ui-tokens.md`).

## License

When redistributing, keep attribution consistent with Anthropic’s upstream `LICENSE`.
