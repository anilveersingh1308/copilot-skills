---
name: fiux
description: Universal token-efficient execution mode for coding agents. Use ONLY when user explicitly types /fiux (or asks for Fiux mode) to transform a simple query into an advanced, production-quality result with minimum token burn. It should select the best installed workspace skill, execute changes end-to-end, verify outputs, and keep explanations concise and simple.
---

# Fiux Mode

Fiux is a high-signal, low-token orchestration mode.

## Mission

Turn a plain-language request into the best practical result with:

- minimum token usage,
- strong implementation quality,
- clear and simple communication,
- full completion (not partial analysis).

## Activation

Run this mode only when the user explicitly invokes `/fiux` or clearly asks for Fiux mode.

## Operating rules

1. Use one primary skill path first:
   - route to the most relevant installed skill,
   - avoid invoking multiple overlapping skills unless required.
2. Keep output lean:
   - no long theory unless requested,
   - concise progress updates,
   - short final summary focused on outcomes.
3. Execute, do not just propose:
   - implement edits,
   - run verification checks,
   - fix obvious issues before finishing.
4. Optimize for token efficiency:
   - prefer direct actions over large planning text,
   - avoid repeated restatement,
   - avoid dumping full logs unless user asks.
5. Keep language simple:
   - plain English,
   - short actionable statements,
   - practical next steps only.

## Low-token profile (default)

Always apply this profile unless the user explicitly asks for detailed output.

1. Keep analysis to max 5 short bullets.
2. Keep final response under 180 words unless code output requires more.
3. Never dump long logs; summarize key lines only.
4. Ask at most one clarifying question, and only if blocked.
5. Prefer direct edits + verification over long planning text.

## Fiux workflow

1. Parse user request into:
   - objective,
   - constraints,
   - expected output.
2. Select best matching skill from workspace.
3. Execute the work end-to-end.
4. Validate with tests/lint/errors where relevant.
5. Return concise final answer:
   - what changed,
   - where,
   - what was validated,
   - optional next action.

## Skill routing hints in Fiux

- UI/design: `impeccable` (default), or explicit style skill if requested.
- App listing visuals: `app-store-screenshots`.
- Documents: `docx`, `pdf`, `pptx`, `xlsx`.
- Reviews: `review-delta`, `review-pr`.
- API/agent infra: `claude-api`, `mcp-builder`, `skill-creator`.
- Web testing: `webapp-testing`.
- gstack workflows: only when user explicitly asks a `/gstack-*` command.

## Response format in Fiux

Use this compact structure:

1. Result
2. Changes made
3. Validation
4. Next step (optional)

Keep each section short.
