# Fiux Guide

Fiux is a command-style operating mode for your Copilot skill workspace.

Use it when you want:

- simple prompts,
- advanced implementation quality,
- minimum token usage,
- complete end-to-end execution.

## Command

Use:

- `/fiux <your request>`

Examples:

- `/fiux fix login bug and add tests`
- `/fiux redesign this dashboard with better UX`
- `/fiux review my last commit for regressions`
- `/fiux create a Word proposal from this outline`

## How Fiux works

1. Understands your request in simple language.
2. Selects the best skill in your workspace.
3. Executes code/document changes directly.
4. Validates results.
5. Responds with a concise summary.

## Output style

Fiux keeps responses short and practical:

1. Result
2. Changes made
3. Validation
4. Next step (optional)

## Recommended prompt formula

Use this pattern for best quality:

`/fiux <goal> + <constraints> + <output format>`

Examples:

- `/fiux build pricing page, keep existing React components, improve visual hierarchy`
- `/fiux optimize this Python script for speed, keep behavior unchanged, include tests`
- `/fiux convert this draft into a polished .docx report with TOC`

## Token-saving tips

1. Ask one clear task at a time.
2. Mention constraints early (framework, style, deadline).
3. Use explicit commands when precision matters.
4. Ask for "concise" if you want even shorter responses.

## Skill mapping inside Fiux

- Frontend: `impeccable` (default)
- Store screenshots: `app-store-screenshots`
- Docs: `docx`, `pdf`, `pptx`, `xlsx`
- Reviews: `review-delta`, `review-pr`
- API/agents: `claude-api`, `mcp-builder`, `skill-creator`
- Web QA: `webapp-testing`
- gstack: only explicit `/gstack-*`

## For teams

Commit this file and `.github/skills/fiux/SKILL.md` so every machine and teammate gets the same Fiux behavior after clone.
