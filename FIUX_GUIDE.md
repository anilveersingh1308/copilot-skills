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

## Low-token defaults in /fiux

By default, Fiux should:

1. keep reasoning brief,
2. execute directly,
3. summarize command output,
4. avoid long explanations,
5. ask only one clarifying question when absolutely needed.

Use `"/fiux detailed"` only when you want deeper explanation.

## Token budget estimator

Use this quick estimator before running a request.

### Selection overhead (skill routing)

1. Clear intent + low overlap: 120 to 300 tokens
2. Normal prompt + 1 to 2 possible skills: 250 to 700 tokens
3. Ambiguous prompt + many overlaps: 700 to 1,500+ tokens

### Execution overhead (work itself)

1. Small single-file edit: 400 to 1,500 tokens
2. Medium multi-file change with validation: 1,500 to 5,000 tokens
3. Large refactor or heavy QA loop: 5,000+ tokens

### Practical total estimate

Total tokens ~= selection overhead + execution overhead + response tokens

### Fast budgeting examples

1. `/fiux fix typo in README`:
	- selection 150 + execution 500 + response 120 ~= 770
2. `/fiux review last commit for regressions`:
	- selection 300 + execution 1,400 + response 250 ~= 1,950
3. `/fiux redesign dashboard and improve accessibility`:
	- selection 500 + execution 3,500 + response 300 ~= 4,300

## How to cut token usage by 30% to 60%

1. Start with explicit slash command (`/fiux`, `/impeccable`, `/review-pr`) instead of broad natural text.
2. Include target scope in one line (feature/file/component).
3. Request concise output unless details are needed.
4. Avoid mixing many goals in one prompt.
5. Use follow-up prompts for iterations instead of restating full context.

## Prompt templates (cost-optimized)

1. `/fiux <single goal> in <scope>, keep <constraint>, output <format>, concise`
2. `/fiux review <branch/commit> for <risk-type>, return only findings`
3. `/fiux optimize <file/module> for <metric>, keep behavior unchanged`

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
