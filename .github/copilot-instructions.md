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
2. **`image-to-code`** — screenshot/reference image to frontend code.
3. **`huashu-design`** — HTML prototypes/demos/slides/animations (incl. 做原型, 设计Demo, 交互原型, 动画Demo).
4. **`app-store-screenshots`** — App Store/Play listing screenshots and feature graphics.
5. **`canvas-design`** — static `.png`/`.pdf` visual deliverables only.
6. **`algorithmic-art`** — generative/p5.js art.
7. **`web-artifacts-builder`** — explicit multi-component claude-style artifact request.
8. **`minimalist-ui`** — explicit minimalist/editorial style.
9. **`industrial-brutalist-ui`** — explicit brutalist/Swiss style.
10. **`ui-ux-pro-max`** — deep cross-stack UI/UX planning.
11. **`theme-factory`** — reusable color/font theme generation or application.
12. **`brand-guidelines`** — Anthropic brand styling.
13. **`impeccable`** — default for all other production frontend work.
14. **`frontend-design`**, **`design-taste-frontend`**, **`redesign-existing-projects`**, **`emil-design-eng`** — slash-command only.

## Routing — documents

15. Use `docx` for Word `.docx` tasks.
16. Use `pdf` for PDF tasks.
17. Use `pptx` for PowerPoint `.pptx` tasks.
18. Use `xlsx` for spreadsheet tasks (`.xlsx`, `.xlsm`, `.csv`, `.tsv`).

## Routing — writing

19. Use `doc-coauthoring` for structured docs/specs/proposals.
20. Use `internal-comms` for status/leadership/FAQ/incident/newsletter updates.
21. Use `slack-gif-creator` only for Slack GIF requests.

## Routing — engineering

22. Use `claude-api` for Anthropic SDK/API tasks.
23. Use `mcp-builder` to build/scaffold MCP servers.
24. Use `skill-creator` to create/edit/evaluate skills.
25. Use `webapp-testing` for Playwright-based local webapp testing.

## Routing — workflow

26. Use `caveman` only when the user asks for brevity, compression, or fewer tokens.
27. Use `caveman-help` for the caveman command card.
28. Use `fiux` only on explicit `/fiux` (or Fiux mode request) for token-efficient advanced execution.
29. Use `review-delta` when the user asks to review changes, the last commit, or quick impact review.
30. Use `review-pr` when the user asks to review a PR, pull request, branch diff, or diff against main.

## Routing — gstack-* (slash-command only)

31. `gstack-*` skills are slash-command only (for example `/gstack-ship`, `/gstack-investigate`). Do not auto-trigger them from general phrasing.
