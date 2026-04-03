# 与 `frontend-design`（Anthropic skills）对齐的要点

本 skill **不把**上游当作运行时依赖；生成 HTML 时遵守其**审美纪律**即可。完整原文：[anthropics/skills `frontend-design`](https://github.com/anthropics/skills/tree/main/skills/frontend-design)。

## 生成前

- **目的**：读者是谁、要解决什么理解问题。
- **Tone**：默认 Lab·Canonical；用户要写冷色 / 工程感时再切变体。
- **差异化**：journey 让人记住调用顺序，而不是又一页白板。

## 生成时

- **字体**：display + body 有对比；禁用 Inter / Roboto 做主标题。
- **色彩**：主色 + accent 浅底；禁大紫渐变铺满。
- **版面**：`.shell` 取中间留白（见 `ui-tokens.md`）。

## 许可证

再分发时请保留对 Anthropic 上游 `LICENSE` 的说明。
