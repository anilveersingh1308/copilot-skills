# Copilot Workspace Instructions

When solving tasks in this repository:

## Core rules

1. Prefer workspace skills under `.github/skills/` only when the request clearly matches the skill's triggers.
2. Match user wording against each skill's `description` trigger phrases.
3. If two skills could apply, follow the priority order below — the FIRST matching rule wins.
4. A slash command (e.g. `/impeccable`, `/taste`, `/frontend-design`) ALWAYS wins over auto-routing.
5. Keep normal response style for safety-critical, destructive, or ambiguous instructions — do not invoke a skill if intent is unclear.
6. Never invoke two design-family skills for the same request — pick exactly one per the priority order.

## Routing priority — frontend / UI / design family

When the request is UI/design-related, evaluate in this exact order and pick the FIRST that matches:

1. **Slash command override** — user typed a skill's slash command → use that skill.
2. **`image-to-code`** — user provided a reference image/screenshot and wants frontend code from it.
3. **`huashu-design`** — HTML hi-fi prototype, interactive demo, slide deck, animation, design-variant exploration, narrated MP4/GIF export. Chinese triggers: 做原型, 设计Demo, 交互原型, 动画Demo.
4. **`app-store-screenshots`** — user wants App Store / Google Play listing screenshots, feature graphics, exportable mobile marketing screenshots, or a dedicated screenshot generator/editor for store assets.
5. **`canvas-design`** — deliverable is explicitly a static `.png` or `.pdf` (poster, print, single image). NOT for any web/interactive UI.
6. **`algorithmic-art`** — generative/algorithmic/p5.js art, flow fields, particle systems.
7. **`web-artifacts-builder`** — user explicitly asks for a multi-component claude.ai-style HTML artifact (React + Tailwind + shadcn/ui with state/routing).
8. **`minimalist-ui`** — user explicitly asks for editorial / minimalist / Notion / Linear style.
9. **`industrial-brutalist-ui`** — user explicitly asks for brutalist / hard Swiss-type style.
10. **`ui-ux-pro-max`** — user wants a deep cross-stack UI/UX *plan* (palettes, font pairings, UX rules across React/Next/Vue/Svelte/SwiftUI/RN/Flutter/Tailwind/shadcn/HTML), not just code.
11. **`theme-factory`** — apply or generate a reusable color+font theme across artifacts.
12. **`brand-guidelines`** — user mentions Anthropic brand colors, typography, or company design standards.
13. **`impeccable`** — DEFAULT for any other frontend work: design, redesign, audit, critique, polish, animate, optimize, harden a real production interface (websites, dashboards, components, forms, onboarding).
14. **`frontend-design`**, **`design-taste-frontend`**, **`redesign-existing-projects`**, **`emil-design-eng`** — slash-command ONLY (rule 1). Do NOT auto-trigger; `impeccable` supersedes them in this workspace.

## Routing — documents

15. Use `docx` for any Word `.docx` work: create, read, edit, tracked changes, letterheads, reports.
16. Use `pdf` for any PDF task: read, extract, merge, split, rotate, watermark, fill forms, OCR.
17. Use `pptx` for any PowerPoint `.pptx` work: decks, slides, templates, speaker notes.
18. Use `xlsx` when the primary input or output is a spreadsheet (`.xlsx`, `.xlsm`, `.csv`, `.tsv`).

## Routing — writing

19. Use `doc-coauthoring` for structured documentation, proposals, technical specs, decision docs.
20. Use `internal-comms` for status reports, leadership updates, FAQs, incident reports, newsletters, project updates.
21. Use `slack-gif-creator` only when the user asks for an animated GIF specifically for Slack.

## Routing — engineering

22. Use `claude-api` when code imports `anthropic` / `@anthropic-ai/sdk` or user asks about Claude API, prompt caching, model migration, tool use, batch, citations, memory.
23. Use `mcp-builder` when the user asks to build, design, or scaffold an MCP server (FastMCP Python or TS SDK).
24. Use `skill-creator` when the user asks to create, edit, evaluate, or optimize a Copilot/Claude skill.
25. Use `webapp-testing` when the user wants to test a local web app with Playwright (UI checks, screenshots, console logs).

## Routing — workflow

26. Use `caveman` only when the user asks for brevity, compression, or fewer tokens.
27. Use `caveman-help` for the caveman command card.
28. Use `review-delta` when the user asks to review changes, the last commit, or quick impact review.
29. Use `review-pr` when the user asks to review a PR, pull request, branch diff, or diff against main.

## Routing — gstack-* (slash-command only)

30. The `gstack-*` family (51 skills imported from garrytan/gstack: ship, investigate, autoplan, plan-*, openclaw-*, careful, guard, freeze/unfreeze, context-save/restore, retro, qa, qa-only, design-*, browse, scrape, benchmark, etc.) is invoked **only** when the user types the explicit slash command (e.g. `/gstack-ship`, `/gstack-investigate`, `/gstack-openclaw-ceo-review`). Do NOT auto-trigger any `gstack-*` skill from general phrasing — they overlap with `review-*`, `impeccable`, and `skill-creator` and would conflict.
