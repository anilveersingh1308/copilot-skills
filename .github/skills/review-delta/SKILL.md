---
name: review-delta
description: "Token-efficient delta code review for only changed code and direct impact. Use when asked: review my changes, review last commit, quick code review, blast radius review, changed files review, /review-delta."
---

# Review Delta

## Goal

Review only changed code plus immediate impact to minimize tokens while catching real risks.

## Input

Optional target:
- file path
- function name
- commit range

## Workflow

1. Determine changed scope first (prefer latest commit or staged diff).
2. Read only changed hunks and nearby context.
3. Expand one hop to likely impacted callers/tests.
4. Classify risk: low, medium, high.
5. Report concrete findings with file and line references.

## Review Focus

- correctness regressions
- missing null and bounds checks
- API contract changes and caller impact
- missing or stale tests for changed behavior
- performance or security risks in changed paths

## Output Format

- Summary: one line
- Risk: low, medium, high
- Findings: ordered by severity
- Blast radius: impacted files or symbols
- Recommended fixes: short actionable list

## Token Rules

- Never load full repository context for delta review.
- Prefer diff and targeted reads over full-file scans.
- Keep response concise unless user asks for detail.
