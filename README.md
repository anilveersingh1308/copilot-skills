# Copilot Skills Pack

A curated, production-ready GitHub Copilot skills workspace.

This repository packages reusable custom skills under `.github/skills/` and a routing policy in `.github/copilot-instructions.md` so Copilot picks the right skill for the right task.

## What this repo gives you

- A large, curated skills library for frontend, docs, reviews, workflow, and experimentation.
- Explicit routing rules to reduce overlap and accidental skill activation.
- Slash-command-only handling for families that overlap (for example `gstack-*`).
- A fork-friendly structure that works as soon as you clone and open in VS Code.

## Repository structure

- `.github/skills/`
  - One folder per skill.
  - Each folder contains a `SKILL.md` file (and optional assets/scripts/templates).
- `.github/copilot-instructions.md`
  - Workspace-level routing and priority rules.
- `.github/skills/README.md`
  - Human-readable index of installed skills and test prompts.

## Requirements

- VS Code with GitHub Copilot + Copilot Chat enabled.
- Access to this repository (or your fork).

## Quick start

1. Clone your fork/repo.
2. Open the folder in VS Code.
3. Sign in to GitHub Copilot in VS Code.
4. Start using skills by natural prompt matching or explicit slash commands.

## Usage

### Natural routing

Copilot uses `.github/copilot-instructions.md` plus each skill `description` to choose the best skill.

Example prompts:

- "review this PR against main" -> `review-pr`
- "merge these PDFs" -> `pdf`
- "build App Store screenshots for my app" -> `app-store-screenshots`

### Explicit slash invocation (recommended for precision)

Use slash commands when you want exact control:

- `/impeccable`
- `/app-store-screenshots`
- `/docx`
- `/review-delta`
- `/gstack-ship`

## Skill categories included

- Frontend/UI craft and design systems
- App Store/Play screenshot generation
- Document tooling (`docx`, `pdf`, `pptx`, `xlsx`)
- Review workflows (`review-delta`, `review-pr`)
- Claude API + MCP server building
- GStack workflow bundle (`gstack-*`, slash-command-only)

See `.github/skills/README.md` for the full list.

## Fork and customize (recommended)

1. Fork this repository.
2. Edit `.github/copilot-instructions.md` to match your preferred routing policy.
3. Tune skill `description` lines in `SKILL.md` files to improve trigger quality.
4. Add/remove skills in `.github/skills/`.
5. Commit and push.

### Best practices for high trigger quality

- Keep `description` specific and explicit.
- Prefer slash-command-only for overlapping skills.
- Maintain clear priority ordering in routing rules.
- Avoid broad trigger text that can steal unrelated tasks.

## How to add a new skill

1. Copy skill folder into `.github/skills/<skill-name>/`.
2. Ensure `SKILL.md` frontmatter has:
   - `name` matching folder name
   - focused `description` trigger text
3. If needed, include sibling assets (`template/`, `scripts/`, `references/`, etc.).
4. Update:
   - `.github/skills/README.md`
   - `.github/copilot-instructions.md`
5. Commit and push.

## Collaboration

Issues and PRs are welcome.

When proposing changes, include:

- what trigger behavior changed,
- which overlapping skills were considered,
- before/after examples.

## License and attributions

Each imported skill may carry its own license and attribution requirements in its folder (for example `LICENSE.txt`, `NOTICE.md`, or source references). Keep those files intact when reusing or redistributing.
