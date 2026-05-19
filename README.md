# Copilot Skills Pack

Production-ready custom skills for GitHub Copilot, with clear routing so the right skill is selected at the right time.

This repository is designed to be immediately useful after clone, and easy to fork/customize for your own team workflows.

<p align="center">
  <img src="assets/readme/hero.svg" alt="Copilot Skills Pack Hero" width="100%" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Skills-50%2B-0ea5e9?style=for-the-badge" alt="50 plus skills" />
  <img src="https://img.shields.io/badge/Routing-Priority%20Based-14b8a6?style=for-the-badge" alt="priority routing" />
  <img src="https://img.shields.io/badge/Workflow-Fork%20Ready-6366f1?style=for-the-badge" alt="fork ready" />
  <img src="https://img.shields.io/badge/VS%20Code-Copilot%20Optimized-2563eb?style=for-the-badge" alt="copilot optimized" />
</p>

## Visual overview

<p align="center">
  <img src="assets/readme/skill-grid.svg" alt="Skill categories visual grid" width="100%" />
</p>

## Why developers like this repo

<table>
  <tr>
    <td width="33%" valign="top">
      <h3>Predictable skill selection</h3>
      <p>Priority routing and narrow trigger descriptions prevent random skill collisions.</p>
    </td>
    <td width="33%" valign="top">
      <h3>Fast practical workflows</h3>
      <p>Use natural prompts for convenience and slash commands when you need deterministic output.</p>
    </td>
    <td width="33%" valign="top">
      <h3>Fork and scale quickly</h3>
      <p>Everything is repository-based, so teams can clone, fork, and customize with minimal setup.</p>
    </td>
  </tr>
</table>

## Why this repo exists

Most skill packs fail in one of two ways:

- Too many overlapping skills that trigger unpredictably.
- Great skills, but poor onboarding and no clear usage patterns.

This pack solves both:

- Curated skills grouped by practical outcomes.
- Strict routing policy in `.github/copilot-instructions.md`.
- Slash-command-only rules for overlap-prone families.
- Fork-friendly structure with predictable maintenance.

## What you get

- Frontend/UI craftsmanship and design-specific skills.
- App Store / Play Store screenshot generation workflows.
- Document skills (`docx`, `pdf`, `pptx`, `xlsx`).
- Review skills (`review-delta`, `review-pr`).
- Engineering skills (`claude-api`, `mcp-builder`, `skill-creator`, `webapp-testing`).
- GStack workflow family (`gstack-*`, explicit invocation only).

Complete index: `.github/skills/README.md`

## Repository layout

```
.github/
  copilot-instructions.md   # routing and priority policy
  skills/
    <skill-name>/
      SKILL.md              # frontmatter + behavior instructions
      ...                   # optional assets (template/, scripts/, references/)
  skills/README.md          # human-readable skill catalog + test prompts
```

## Quick start (2 minutes)

1. Clone this repo (or your fork).
2. Open it in VS Code.
3. Sign in to GitHub Copilot and Copilot Chat.
4. Start with either natural language prompts or slash commands.

<p align="center">
  <img src="assets/readme/workflow.svg" alt="Prompt to ship workflow" width="100%" />
</p>

## How to use skills effectively

### High-conversion usage model

1. Start with natural language for speed.
2. Switch to slash command when precision matters.
3. Keep prompts goal-first and constraint-aware.
4. Iterate with short follow-ups instead of rewriting full prompts.

### Option A: Natural-language routing

Copilot reads:

- `.github/copilot-instructions.md` (workspace routing policy)
- each skill's `description` in `SKILL.md` (trigger surface)

Example prompts:

- `review this PR against main` -> `review-pr`
- `merge these PDFs` -> `pdf`
- `build App Store screenshots for my app` -> `app-store-screenshots`
- `create a Word report with headings and TOC` -> `docx`

### Option B: Explicit slash command (recommended for precision)

Use slash commands when you want deterministic behavior:

- `/impeccable`
- `/app-store-screenshots`
- `/docx`
- `/review-delta`
- `/gstack-investigate`

If a task is sensitive, high-stakes, or overlap-prone, slash invocation is the best UX.

## Best prompt patterns for better outputs

When asking Copilot to use a skill, include:

- **Goal:** what success looks like.
- **Context:** app type, audience, constraints.
- **Output format:** code, checklist, patch, report.
- **Priority:** speed vs polish vs strictness.

Strong examples:

- `Use /impeccable to redesign this pricing page for clarity and conversion. Keep existing React component structure.`
- `Use /review-delta and focus on regressions, security risks, and missing tests.`
- `Use /app-store-screenshots to scaffold Play Store screenshots for a finance app, clean modern style, export-ready assets.`

## Copy-paste prompt starter pack

### Frontend and design

- `Use /impeccable to refactor this landing page into a cleaner conversion-first layout. Keep existing content, improve hierarchy and spacing.`
- `Use /minimalist-ui to redesign this dashboard in an editorial style with strong typography and low visual noise.`
- `Use /app-store-screenshots to generate App Store + Play Store marketing screenshots for a fitness app with bold headline copy.`

### Reviews and quality

- `Use /review-delta and only report regressions, security risks, and missing tests from changed files.`
- `Use /review-pr and compare this branch with main. Prioritize functional risks and rollout concerns.`
- `Use /webapp-testing to run a smoke test plan and summarize UI issues with repro steps.`

### Documents and deliverables

- `Use /docx to create a polished project proposal with title page, TOC, and clear sectioning.`
- `Use /pdf to merge these reports and add page numbers and a watermark.`
- `Use /pptx to build a 10-slide investor narrative with speaker notes.`

### Engineering and workflow

- `Use /claude-api to add prompt caching and show expected cache-hit improvements.`
- `Use /mcp-builder to scaffold a production-ready MCP server for a ticketing API.`
- `Use /gstack-investigate to run a root-cause-first bug analysis for this error.`

## Routing model (important)

This repo intentionally prevents skill collisions.

- `impeccable` is the default for general frontend polish and redesign.
- `frontend-design`, `design-taste-frontend`, `redesign-existing-projects`, and `emil-design-eng` are explicit-invocation only.
- `gstack-*` is explicit-invocation only.

If you change routing, keep priorities strict or trigger quality will degrade.

## Forking guide (recommended)

1. Fork this repository.
2. Edit `.github/copilot-instructions.md` for your team's routing preferences.
3. Tune `description` fields in skill frontmatter to match your wording.
4. Remove skills you do not use to reduce accidental triggering.
5. Add your own skills in `.github/skills/<name>/`.
6. Keep `.github/skills/README.md` in sync.

## Adding a new skill correctly

1. Copy the skill folder to `.github/skills/<skill-name>/`.
2. Verify `SKILL.md` frontmatter:
   - `name:` exactly matches folder name.
   - `description:` has clear, specific trigger phrases.
3. Copy required sibling assets (for example `template/`, `scripts/`, `references/`).
4. Register the skill in:
   - `.github/skills/README.md`
   - `.github/copilot-instructions.md`
5. Commit and push.

## Troubleshooting

### Skill is not triggering

- Use slash command directly to validate it works.
- Check `name` and folder match.
- Tighten `description` trigger wording.
- Verify no higher-priority routing rule is catching the prompt first.

### Wrong skill triggers

- Make overlapping skills explicit-invocation only.
- Move the intended skill earlier in routing priority.
- Narrow broad description text.

### Works on one machine but not another

- Ensure all `.github/` files are committed and pushed.
- Clone the same repository/fork on the other machine.
- Open that folder in VS Code while signed into Copilot.

### README images do not render

- Verify image paths exist under `assets/readme/`.
- Use repository-relative paths (already used in this README).
- Ensure your Git hosting viewer allows inline SVG rendering.

## Contributing

Issues and PRs are welcome.

Please include in PRs:

- Why routing changed.
- What overlap risks were considered.
- Before/after example prompts.
- Any migration impact for existing users.

## License and attribution

Imported skills may include their own license/notice requirements. Keep attribution files (`LICENSE.txt`, `NOTICE.md`, source references) intact when redistributing.

<!-- SKILL_DIRECTORY_START -->
## Complete skill directory (auto-generated)

Every installed skill is listed below and can be invoked directly with its slash command.

- **Total skills:** 83
- **Gstack skills:** 51
- **Non-gstack skills:** 32

### Non-gstack skills
| Skill | Command | Primary use | Path |
| :--- | :--- | :--- | :--- |
| algorithmic-art | $(@{Name=algorithmic-art; Command=/algorithmic-art; Use=Creating algorithmic art using p5.js with seeded randomness and interactive parameter exploration. Use this wh...; Path=.github/skills/algorithmic-art/SKILL.md}.Command) | Creating algorithmic art using p5.js with seeded randomness and interactive parameter exploration. Use this wh... | [.github/skills/algorithmic-art/SKILL.md](.github/skills/algorithmic-art/SKILL.md) |
| app-store-screenshots | $(@{Name=app-store-screenshots; Command=/app-store-screenshots; Use=Use when the user explicitly wants to create App Store or Google Play listing screenshots, feature graphics, e...; Path=.github/skills/app-store-screenshots/SKILL.md}.Command) | Use when the user explicitly wants to create App Store or Google Play listing screenshots, feature graphics, e... | [.github/skills/app-store-screenshots/SKILL.md](.github/skills/app-store-screenshots/SKILL.md) |
| brand-guidelines | $(@{Name=brand-guidelines; Command=/brand-guidelines; Use=Applies Anthropic's official brand colors and typography to any sort of artifact that may benefit from having ...; Path=.github/skills/brand-guidelines/SKILL.md}.Command) | Applies Anthropic's official brand colors and typography to any sort of artifact that may benefit from having ... | [.github/skills/brand-guidelines/SKILL.md](.github/skills/brand-guidelines/SKILL.md) |
| canvas-design | $(@{Name=canvas-design; Command=/canvas-design; Use=Create static visual art delivered ONLY as .png or .pdf files (posters, prints, single-image designs). Use onl...; Path=.github/skills/canvas-design/SKILL.md}.Command) | Create static visual art delivered ONLY as .png or .pdf files (posters, prints, single-image designs). Use onl... | [.github/skills/canvas-design/SKILL.md](.github/skills/canvas-design/SKILL.md) |
| caveman | $(@{Name=caveman; Command=/caveman; Use=Ultra-terse response mode for token efficiency with full technical accuracy. Use when user asks: caveman mode,...; Path=.github/skills/caveman/SKILL.md}.Command) | Ultra-terse response mode for token efficiency with full technical accuracy. Use when user asks: caveman mode,... | [.github/skills/caveman/SKILL.md](.github/skills/caveman/SKILL.md) |
| caveman-help | $(@{Name=caveman-help; Command=/caveman-help; Use=Quick help for caveman mode commands and levels. Use when asked: caveman help, how to use caveman, caveman com...; Path=.github/skills/caveman-help/SKILL.md}.Command) | Quick help for caveman mode commands and levels. Use when asked: caveman help, how to use caveman, caveman com... | [.github/skills/caveman-help/SKILL.md](.github/skills/caveman-help/SKILL.md) |
| claude-api | $(@{Name=claude-api; Command=/claude-api; Use=Build, debug, and optimize Claude API / Anthropic SDK apps. Apps built with this skill should include prompt c...; Path=.github/skills/claude-api/SKILL.md}.Command) | Build, debug, and optimize Claude API / Anthropic SDK apps. Apps built with this skill should include prompt c... | [.github/skills/claude-api/SKILL.md](.github/skills/claude-api/SKILL.md) |
| design-taste-frontend | $(@{Name=design-taste-frontend; Command=/design-taste-frontend; Use=ONLY USE when the user explicitly types `/design-taste-frontend` or `/taste`. Do NOT auto-trigger on generic '...; Path=.github/skills/design-taste-frontend/SKILL.md}.Command) | ONLY USE when the user explicitly types `/design-taste-frontend` or `/taste`. Do NOT auto-trigger on generic '... | [.github/skills/design-taste-frontend/SKILL.md](.github/skills/design-taste-frontend/SKILL.md) |
| doc-coauthoring | $(@{Name=doc-coauthoring; Command=/doc-coauthoring; Use=Guide users through a structured workflow for co-authoring documentation. Use when user wants to write documen...; Path=.github/skills/doc-coauthoring/SKILL.md}.Command) | Guide users through a structured workflow for co-authoring documentation. Use when user wants to write documen... | [.github/skills/doc-coauthoring/SKILL.md](.github/skills/doc-coauthoring/SKILL.md) |
| docx | $(@{Name=docx; Command=/docx; Use=Use this skill whenever the user wants to create, read, edit, or manipulate Word documents (.docx files). Trig...; Path=.github/skills/docx/SKILL.md}.Command) | Use this skill whenever the user wants to create, read, edit, or manipulate Word documents (.docx files). Trig... | [.github/skills/docx/SKILL.md](.github/skills/docx/SKILL.md) |
| emil-design-eng | $(@{Name=emil-design-eng; Command=/emil-design-eng; Use=This skill encodes Emil Kowalski's philosophy on UI polish, component design, animation decisions, and the inv...; Path=.github/skills/emil-design-eng/SKILL.md}.Command) | This skill encodes Emil Kowalski's philosophy on UI polish, component design, animation decisions, and the inv... | [.github/skills/emil-design-eng/SKILL.md](.github/skills/emil-design-eng/SKILL.md) |
| fiux | $(@{Name=fiux; Command=/fiux; Use=Universal token-efficient execution mode for coding agents. Use ONLY when user explicitly types /fiux (or asks...; Path=.github/skills/fiux/SKILL.md}.Command) | Universal token-efficient execution mode for coding agents. Use ONLY when user explicitly types /fiux (or asks... | [.github/skills/fiux/SKILL.md](.github/skills/fiux/SKILL.md) |
| frontend-design | $(@{Name=frontend-design; Command=/frontend-design; Use=Anthropic's original frontend-design skill (parent of `impeccable`). ONLY USE when the user explicitly types `...; Path=.github/skills/frontend-design/SKILL.md}.Command) | Anthropic's original frontend-design skill (parent of `impeccable`). ONLY USE when the user explicitly types `... | [.github/skills/frontend-design/SKILL.md](.github/skills/frontend-design/SKILL.md) |
| huashu-design | $(@{Name=huashu-design; Command=/huashu-design; Use=花叔Design（Huashu-Design）——用HTML做高保真原型、交互Demo、幻灯片、动画、设计变�...; Path=.github/skills/huashu-design/SKILL.md}.Command) | 花叔Design（Huashu-Design）——用HTML做高保真原型、交互Demo、幻灯片、动画、设计变�... | [.github/skills/huashu-design/SKILL.md](.github/skills/huashu-design/SKILL.md) |
| image-to-code | $(@{Name=image-to-code; Command=/image-to-code; Use=Elite website image-to-code skill for Codex. For visually important web tasks, it must first generate the desi...; Path=.github/skills/image-to-code/SKILL.md}.Command) | Elite website image-to-code skill for Codex. For visually important web tasks, it must first generate the desi... | [.github/skills/image-to-code/SKILL.md](.github/skills/image-to-code/SKILL.md) |
| impeccable | $(@{Name=impeccable; Command=/impeccable; Use=Use when the user wants to design, redesign, shape, critique, audit, polish, clarify, distill, harden, optimiz...; Path=.github/skills/impeccable/SKILL.md}.Command) | Use when the user wants to design, redesign, shape, critique, audit, polish, clarify, distill, harden, optimiz... | [.github/skills/impeccable/SKILL.md](.github/skills/impeccable/SKILL.md) |
| industrial-brutalist-ui | $(@{Name=industrial-brutalist-ui; Command=/industrial-brutalist-ui; Use=Raw mechanical interfaces fusing Swiss typographic print with military terminal aesthetics. Rigid grids, extre...; Path=.github/skills/industrial-brutalist-ui/SKILL.md}.Command) | Raw mechanical interfaces fusing Swiss typographic print with military terminal aesthetics. Rigid grids, extre... | [.github/skills/industrial-brutalist-ui/SKILL.md](.github/skills/industrial-brutalist-ui/SKILL.md) |
| internal-comms | $(@{Name=internal-comms; Command=/internal-comms; Use=A set of resources to help me write all kinds of internal communications, using the formats that my company li...; Path=.github/skills/internal-comms/SKILL.md}.Command) | A set of resources to help me write all kinds of internal communications, using the formats that my company li... | [.github/skills/internal-comms/SKILL.md](.github/skills/internal-comms/SKILL.md) |
| mcp-builder | $(@{Name=mcp-builder; Command=/mcp-builder; Use=Guide for creating high-quality MCP (Model Context Protocol) servers that enable LLMs to interact with externa...; Path=.github/skills/mcp-builder/SKILL.md}.Command) | Guide for creating high-quality MCP (Model Context Protocol) servers that enable LLMs to interact with externa... | [.github/skills/mcp-builder/SKILL.md](.github/skills/mcp-builder/SKILL.md) |
| minimalist-ui | $(@{Name=minimalist-ui; Command=/minimalist-ui; Use=Clean editorial-style interfaces. Warm monochrome palette, typographic contrast, flat bento grids, muted paste...; Path=.github/skills/minimalist-ui/SKILL.md}.Command) | Clean editorial-style interfaces. Warm monochrome palette, typographic contrast, flat bento grids, muted paste... | [.github/skills/minimalist-ui/SKILL.md](.github/skills/minimalist-ui/SKILL.md) |
| pdf | $(@{Name=pdf; Command=/pdf; Use=Use this skill whenever the user wants to do anything with PDF files. This includes reading or extracting text...; Path=.github/skills/pdf/SKILL.md}.Command) | Use this skill whenever the user wants to do anything with PDF files. This includes reading or extracting text... | [.github/skills/pdf/SKILL.md](.github/skills/pdf/SKILL.md) |
| pptx | $(@{Name=pptx; Command=/pptx; Use=Use this skill any time a .pptx file is involved in any way — as input, output, or both. This includes: crea...; Path=.github/skills/pptx/SKILL.md}.Command) | Use this skill any time a .pptx file is involved in any way — as input, output, or both. This includes: crea... | [.github/skills/pptx/SKILL.md](.github/skills/pptx/SKILL.md) |
| redesign-existing-projects | $(@{Name=redesign-existing-projects; Command=/redesign-existing-projects; Use=ONLY USE when the user explicitly types `/redesign-existing-projects` or asks specifically for this skill by n...; Path=.github/skills/redesign-existing-projects/SKILL.md}.Command) | ONLY USE when the user explicitly types `/redesign-existing-projects` or asks specifically for this skill by n... | [.github/skills/redesign-existing-projects/SKILL.md](.github/skills/redesign-existing-projects/SKILL.md) |
| review-delta | $(@{Name=review-delta; Command=/review-delta; Use=Token-efficient delta code review for only changed code and direct impact. Use when asked: review my changes, ...; Path=.github/skills/review-delta/SKILL.md}.Command) | Token-efficient delta code review for only changed code and direct impact. Use when asked: review my changes, ... | [.github/skills/review-delta/SKILL.md](.github/skills/review-delta/SKILL.md) |
| review-pr | $(@{Name=review-pr; Command=/review-pr; Use=Structured pull request or branch diff review with blast-radius analysis. Use when asked: review PR, review pu...; Path=.github/skills/review-pr/SKILL.md}.Command) | Structured pull request or branch diff review with blast-radius analysis. Use when asked: review PR, review pu... | [.github/skills/review-pr/SKILL.md](.github/skills/review-pr/SKILL.md) |
| skill-creator | $(@{Name=skill-creator; Command=/skill-creator; Use=Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to c...; Path=.github/skills/skill-creator/SKILL.md}.Command) | Create new skills, modify and improve existing skills, and measure skill performance. Use when users want to c... | [.github/skills/skill-creator/SKILL.md](.github/skills/skill-creator/SKILL.md) |
| slack-gif-creator | $(@{Name=slack-gif-creator; Command=/slack-gif-creator; Use=Knowledge and utilities for creating animated GIFs optimized for Slack. Provides constraints, validation tools...; Path=.github/skills/slack-gif-creator/SKILL.md}.Command) | Knowledge and utilities for creating animated GIFs optimized for Slack. Provides constraints, validation tools... | [.github/skills/slack-gif-creator/SKILL.md](.github/skills/slack-gif-creator/SKILL.md) |
| theme-factory | $(@{Name=theme-factory; Command=/theme-factory; Use=Toolkit for styling artifacts with a theme. These artifacts can be slides, docs, reportings, HTML landing page...; Path=.github/skills/theme-factory/SKILL.md}.Command) | Toolkit for styling artifacts with a theme. These artifacts can be slides, docs, reportings, HTML landing page... | [.github/skills/theme-factory/SKILL.md](.github/skills/theme-factory/SKILL.md) |
| ui-ux-pro-max | $(@{Name=ui-ux-pro-max; Command=/ui-ux-pro-max; Use=UI/UX design intelligence for web and mobile. Includes 50+ styles, 161 color palettes, 57 font pairings, 161 p...; Path=.github/skills/ui-ux-pro-max/SKILL.md}.Command) | UI/UX design intelligence for web and mobile. Includes 50+ styles, 161 color palettes, 57 font pairings, 161 p... | [.github/skills/ui-ux-pro-max/SKILL.md](.github/skills/ui-ux-pro-max/SKILL.md) |
| webapp-testing | $(@{Name=webapp-testing; Command=/webapp-testing; Use=Toolkit for interacting with and testing local web applications using Playwright. Supports verifying frontend ...; Path=.github/skills/webapp-testing/SKILL.md}.Command) | Toolkit for interacting with and testing local web applications using Playwright. Supports verifying frontend ... | [.github/skills/webapp-testing/SKILL.md](.github/skills/webapp-testing/SKILL.md) |
| web-artifacts-builder | $(@{Name=web-artifacts-builder; Command=/web-artifacts-builder; Use=ONLY USE when the user explicitly asks for a multi-component claude.ai-style HTML ARTIFACT (single self-contai...; Path=.github/skills/web-artifacts-builder/SKILL.md}.Command) | ONLY USE when the user explicitly asks for a multi-component claude.ai-style HTML ARTIFACT (single self-contai... | [.github/skills/web-artifacts-builder/SKILL.md](.github/skills/web-artifacts-builder/SKILL.md) |
| xlsx | $(@{Name=xlsx; Command=/xlsx; Use=Use this skill any time a spreadsheet file is the primary input or output. This means any task where the user ...; Path=.github/skills/xlsx/SKILL.md}.Command) | Use this skill any time a spreadsheet file is the primary input or output. This means any task where the user ... | [.github/skills/xlsx/SKILL.md](.github/skills/xlsx/SKILL.md) |

<details>
<summary><b>Gstack skills (slash-command only)</b></summary>

| Skill | Command | Primary use | Path |
| :--- | :--- | :--- | :--- |
| gstack-autoplan | $(@{Name=gstack-autoplan; Command=/gstack-autoplan; Use=Workflow utility; Path=.github/skills/gstack-autoplan/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-autoplan/SKILL.md](.github/skills/gstack-autoplan/SKILL.md) |
| gstack-benchmark | $(@{Name=gstack-benchmark; Command=/gstack-benchmark; Use=Workflow utility; Path=.github/skills/gstack-benchmark/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-benchmark/SKILL.md](.github/skills/gstack-benchmark/SKILL.md) |
| gstack-benchmark-models | $(@{Name=gstack-benchmark-models; Command=/gstack-benchmark-models; Use=Workflow utility; Path=.github/skills/gstack-benchmark-models/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-benchmark-models/SKILL.md](.github/skills/gstack-benchmark-models/SKILL.md) |
| gstack-browse | $(@{Name=gstack-browse; Command=/gstack-browse; Use=Workflow utility; Path=.github/skills/gstack-browse/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-browse/SKILL.md](.github/skills/gstack-browse/SKILL.md) |
| gstack-canary | $(@{Name=gstack-canary; Command=/gstack-canary; Use=Workflow utility; Path=.github/skills/gstack-canary/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-canary/SKILL.md](.github/skills/gstack-canary/SKILL.md) |
| gstack-careful | $(@{Name=gstack-careful; Command=/gstack-careful; Use=Workflow utility; Path=.github/skills/gstack-careful/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-careful/SKILL.md](.github/skills/gstack-careful/SKILL.md) |
| gstack-codex | $(@{Name=gstack-codex; Command=/gstack-codex; Use=Workflow utility; Path=.github/skills/gstack-codex/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-codex/SKILL.md](.github/skills/gstack-codex/SKILL.md) |
| gstack-context-restore | $(@{Name=gstack-context-restore; Command=/gstack-context-restore; Use=Workflow utility; Path=.github/skills/gstack-context-restore/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-context-restore/SKILL.md](.github/skills/gstack-context-restore/SKILL.md) |
| gstack-context-save | $(@{Name=gstack-context-save; Command=/gstack-context-save; Use=Workflow utility; Path=.github/skills/gstack-context-save/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-context-save/SKILL.md](.github/skills/gstack-context-save/SKILL.md) |
| gstack-cso | $(@{Name=gstack-cso; Command=/gstack-cso; Use=Workflow utility; Path=.github/skills/gstack-cso/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-cso/SKILL.md](.github/skills/gstack-cso/SKILL.md) |
| gstack-design-consultation | $(@{Name=gstack-design-consultation; Command=/gstack-design-consultation; Use=Workflow utility; Path=.github/skills/gstack-design-consultation/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-design-consultation/SKILL.md](.github/skills/gstack-design-consultation/SKILL.md) |
| gstack-design-html | $(@{Name=gstack-design-html; Command=/gstack-design-html; Use=Workflow utility; Path=.github/skills/gstack-design-html/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-design-html/SKILL.md](.github/skills/gstack-design-html/SKILL.md) |
| gstack-design-review | $(@{Name=gstack-design-review; Command=/gstack-design-review; Use=Workflow utility; Path=.github/skills/gstack-design-review/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-design-review/SKILL.md](.github/skills/gstack-design-review/SKILL.md) |
| gstack-design-shotgun | $(@{Name=gstack-design-shotgun; Command=/gstack-design-shotgun; Use=Workflow utility; Path=.github/skills/gstack-design-shotgun/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-design-shotgun/SKILL.md](.github/skills/gstack-design-shotgun/SKILL.md) |
| gstack-devex-review | $(@{Name=gstack-devex-review; Command=/gstack-devex-review; Use=Workflow utility; Path=.github/skills/gstack-devex-review/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-devex-review/SKILL.md](.github/skills/gstack-devex-review/SKILL.md) |
| gstack-document-generate | $(@{Name=gstack-document-generate; Command=/gstack-document-generate; Use=Workflow utility; Path=.github/skills/gstack-document-generate/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-document-generate/SKILL.md](.github/skills/gstack-document-generate/SKILL.md) |
| gstack-document-release | $(@{Name=gstack-document-release; Command=/gstack-document-release; Use=Workflow utility; Path=.github/skills/gstack-document-release/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-document-release/SKILL.md](.github/skills/gstack-document-release/SKILL.md) |
| gstack-freeze | $(@{Name=gstack-freeze; Command=/gstack-freeze; Use=Workflow utility; Path=.github/skills/gstack-freeze/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-freeze/SKILL.md](.github/skills/gstack-freeze/SKILL.md) |
| gstack-guard | $(@{Name=gstack-guard; Command=/gstack-guard; Use=Workflow utility; Path=.github/skills/gstack-guard/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-guard/SKILL.md](.github/skills/gstack-guard/SKILL.md) |
| gstack-hackernews-frontpage | $(@{Name=gstack-hackernews-frontpage; Command=/gstack-hackernews-frontpage; Use=Scrape the Hacker News front page (titles, points, comment counts).; Path=.github/skills/gstack-hackernews-frontpage/SKILL.md}.Command) | Scrape the Hacker News front page (titles, points, comment counts). | [.github/skills/gstack-hackernews-frontpage/SKILL.md](.github/skills/gstack-hackernews-frontpage/SKILL.md) |
| gstack-health | $(@{Name=gstack-health; Command=/gstack-health; Use=Workflow utility; Path=.github/skills/gstack-health/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-health/SKILL.md](.github/skills/gstack-health/SKILL.md) |
| gstack-investigate | $(@{Name=gstack-investigate; Command=/gstack-investigate; Use=Workflow utility; Path=.github/skills/gstack-investigate/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-investigate/SKILL.md](.github/skills/gstack-investigate/SKILL.md) |
| gstack-land-and-deploy | $(@{Name=gstack-land-and-deploy; Command=/gstack-land-and-deploy; Use=Workflow utility; Path=.github/skills/gstack-land-and-deploy/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-land-and-deploy/SKILL.md](.github/skills/gstack-land-and-deploy/SKILL.md) |
| gstack-landing-report | $(@{Name=gstack-landing-report; Command=/gstack-landing-report; Use=Workflow utility; Path=.github/skills/gstack-landing-report/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-landing-report/SKILL.md](.github/skills/gstack-landing-report/SKILL.md) |
| gstack-learn | $(@{Name=gstack-learn; Command=/gstack-learn; Use=Workflow utility; Path=.github/skills/gstack-learn/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-learn/SKILL.md](.github/skills/gstack-learn/SKILL.md) |
| gstack-make-pdf | $(@{Name=gstack-make-pdf; Command=/gstack-make-pdf; Use=Workflow utility; Path=.github/skills/gstack-make-pdf/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-make-pdf/SKILL.md](.github/skills/gstack-make-pdf/SKILL.md) |
| gstack-office-hours | $(@{Name=gstack-office-hours; Command=/gstack-office-hours; Use=Workflow utility; Path=.github/skills/gstack-office-hours/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-office-hours/SKILL.md](.github/skills/gstack-office-hours/SKILL.md) |
| gstack-openclaw-ceo-review | $(@{Name=gstack-openclaw-ceo-review; Command=/gstack-openclaw-ceo-review; Use=Use when asked to review a plan, challenge a proposal, run a CEO review, poke holes in an approach, think bigg...; Path=.github/skills/gstack-openclaw-ceo-review/SKILL.md}.Command) | Use when asked to review a plan, challenge a proposal, run a CEO review, poke holes in an approach, think bigg... | [.github/skills/gstack-openclaw-ceo-review/SKILL.md](.github/skills/gstack-openclaw-ceo-review/SKILL.md) |
| gstack-openclaw-investigate | $(@{Name=gstack-openclaw-investigate; Command=/gstack-openclaw-investigate; Use=Use when asked to debug, fix a bug, investigate an error, or do root cause analysis, and when users report err...; Path=.github/skills/gstack-openclaw-investigate/SKILL.md}.Command) | Use when asked to debug, fix a bug, investigate an error, or do root cause analysis, and when users report err... | [.github/skills/gstack-openclaw-investigate/SKILL.md](.github/skills/gstack-openclaw-investigate/SKILL.md) |
| gstack-openclaw-office-hours | $(@{Name=gstack-openclaw-office-hours; Command=/gstack-openclaw-office-hours; Use=Use when asked to brainstorm, evaluate whether an idea is worth building, run office hours, or think through a...; Path=.github/skills/gstack-openclaw-office-hours/SKILL.md}.Command) | Use when asked to brainstorm, evaluate whether an idea is worth building, run office hours, or think through a... | [.github/skills/gstack-openclaw-office-hours/SKILL.md](.github/skills/gstack-openclaw-office-hours/SKILL.md) |
| gstack-openclaw-retro | $(@{Name=gstack-openclaw-retro; Command=/gstack-openclaw-retro; Use=Weekly engineering retrospective. Analyzes commit history, work patterns, and code quality metrics with persis...; Path=.github/skills/gstack-openclaw-retro/SKILL.md}.Command) | Weekly engineering retrospective. Analyzes commit history, work patterns, and code quality metrics with persis... | [.github/skills/gstack-openclaw-retro/SKILL.md](.github/skills/gstack-openclaw-retro/SKILL.md) |
| gstack-open-gstack-browser | $(@{Name=gstack-open-gstack-browser; Command=/gstack-open-gstack-browser; Use=Workflow utility; Path=.github/skills/gstack-open-gstack-browser/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-open-gstack-browser/SKILL.md](.github/skills/gstack-open-gstack-browser/SKILL.md) |
| gstack-pair-agent | $(@{Name=gstack-pair-agent; Command=/gstack-pair-agent; Use=Workflow utility; Path=.github/skills/gstack-pair-agent/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-pair-agent/SKILL.md](.github/skills/gstack-pair-agent/SKILL.md) |
| gstack-plan-ceo-review | $(@{Name=gstack-plan-ceo-review; Command=/gstack-plan-ceo-review; Use=Workflow utility; Path=.github/skills/gstack-plan-ceo-review/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-plan-ceo-review/SKILL.md](.github/skills/gstack-plan-ceo-review/SKILL.md) |
| gstack-plan-design-review | $(@{Name=gstack-plan-design-review; Command=/gstack-plan-design-review; Use=Workflow utility; Path=.github/skills/gstack-plan-design-review/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-plan-design-review/SKILL.md](.github/skills/gstack-plan-design-review/SKILL.md) |
| gstack-plan-devex-review | $(@{Name=gstack-plan-devex-review; Command=/gstack-plan-devex-review; Use=Workflow utility; Path=.github/skills/gstack-plan-devex-review/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-plan-devex-review/SKILL.md](.github/skills/gstack-plan-devex-review/SKILL.md) |
| gstack-plan-eng-review | $(@{Name=gstack-plan-eng-review; Command=/gstack-plan-eng-review; Use=Workflow utility; Path=.github/skills/gstack-plan-eng-review/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-plan-eng-review/SKILL.md](.github/skills/gstack-plan-eng-review/SKILL.md) |
| gstack-plan-tune | $(@{Name=gstack-plan-tune; Command=/gstack-plan-tune; Use=Workflow utility; Path=.github/skills/gstack-plan-tune/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-plan-tune/SKILL.md](.github/skills/gstack-plan-tune/SKILL.md) |
| gstack-qa | $(@{Name=gstack-qa; Command=/gstack-qa; Use=Workflow utility; Path=.github/skills/gstack-qa/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-qa/SKILL.md](.github/skills/gstack-qa/SKILL.md) |
| gstack-qa-only | $(@{Name=gstack-qa-only; Command=/gstack-qa-only; Use=Workflow utility; Path=.github/skills/gstack-qa-only/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-qa-only/SKILL.md](.github/skills/gstack-qa-only/SKILL.md) |
| gstack-retro | $(@{Name=gstack-retro; Command=/gstack-retro; Use=Workflow utility; Path=.github/skills/gstack-retro/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-retro/SKILL.md](.github/skills/gstack-retro/SKILL.md) |
| gstack-review | $(@{Name=gstack-review; Command=/gstack-review; Use=Workflow utility; Path=.github/skills/gstack-review/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-review/SKILL.md](.github/skills/gstack-review/SKILL.md) |
| gstack-scrape | $(@{Name=gstack-scrape; Command=/gstack-scrape; Use=Workflow utility; Path=.github/skills/gstack-scrape/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-scrape/SKILL.md](.github/skills/gstack-scrape/SKILL.md) |
| gstack-setup-browser-cookies | $(@{Name=gstack-setup-browser-cookies; Command=/gstack-setup-browser-cookies; Use=Workflow utility; Path=.github/skills/gstack-setup-browser-cookies/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-setup-browser-cookies/SKILL.md](.github/skills/gstack-setup-browser-cookies/SKILL.md) |
| gstack-setup-deploy | $(@{Name=gstack-setup-deploy; Command=/gstack-setup-deploy; Use=Workflow utility; Path=.github/skills/gstack-setup-deploy/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-setup-deploy/SKILL.md](.github/skills/gstack-setup-deploy/SKILL.md) |
| gstack-setup-gbrain | $(@{Name=gstack-setup-gbrain; Command=/gstack-setup-gbrain; Use=Workflow utility; Path=.github/skills/gstack-setup-gbrain/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-setup-gbrain/SKILL.md](.github/skills/gstack-setup-gbrain/SKILL.md) |
| gstack-ship | $(@{Name=gstack-ship; Command=/gstack-ship; Use=Workflow utility; Path=.github/skills/gstack-ship/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-ship/SKILL.md](.github/skills/gstack-ship/SKILL.md) |
| gstack-skillify | $(@{Name=gstack-skillify; Command=/gstack-skillify; Use=Workflow utility; Path=.github/skills/gstack-skillify/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-skillify/SKILL.md](.github/skills/gstack-skillify/SKILL.md) |
| gstack-sync-gbrain | $(@{Name=gstack-sync-gbrain; Command=/gstack-sync-gbrain; Use=Workflow utility; Path=.github/skills/gstack-sync-gbrain/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-sync-gbrain/SKILL.md](.github/skills/gstack-sync-gbrain/SKILL.md) |
| gstack-unfreeze | $(@{Name=gstack-unfreeze; Command=/gstack-unfreeze; Use=Workflow utility; Path=.github/skills/gstack-unfreeze/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-unfreeze/SKILL.md](.github/skills/gstack-unfreeze/SKILL.md) |
| gstack-upgrade | $(@{Name=gstack-upgrade; Command=/gstack-upgrade; Use=Workflow utility; Path=.github/skills/gstack-upgrade/SKILL.md}.Command) | Workflow utility | [.github/skills/gstack-upgrade/SKILL.md](.github/skills/gstack-upgrade/SKILL.md) |

</details>
<!-- SKILL_DIRECTORY_END -->