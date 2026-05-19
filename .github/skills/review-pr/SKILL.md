---
name: review-pr
description: "Structured pull request or branch diff review with blast-radius analysis. Use when asked: review PR, review pull request, review branch, review diff against main, full PR review, /review-pr."
---

# Review PR

## Goal

Produce a structured PR or branch diff review with risk, impact, and actionable fixes while keeping context lean.

## Input

Optional:
- PR number
- branch name
- base branch (default `main`)

## Workflow

1. Determine diff scope: `git diff <base>...<branch>` or current branch vs `main`.
2. List changed files and group by area.
3. For each high-impact file, read only the changed regions plus minimal surrounding context.
4. Identify blast radius: callers, dependents, public API changes, schema or migration changes.
5. Check test coverage for changed behavior; flag untested changes.
6. Highlight breaking changes, security, and performance risks.

## Output Format

- Title summary: one line
- Overall risk: low, medium, high
- Blast radius: counts and key files or symbols
- File-by-file findings (only changed files):
  - Change intent
  - Issues (bugs, style, security, perf)
  - Impact on callers or consumers
- Missing tests: list with target
- Recommendations: ordered, actionable

## Token Rules

- Never load full repository.
- Prefer diff plus targeted reads.
- Skip unchanged files entirely.
- Use short, structured bullets over prose.

## Safety Rules

- Flag destructive migrations and irreversible changes explicitly.
- Flag credential, key, or secret exposure with high severity.
