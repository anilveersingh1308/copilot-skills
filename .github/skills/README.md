# Mapify Skills

- **caveman**: Ultra-terse response mode to reduce output tokens.
  - Test: "/caveman ultra explain this error"
- **caveman-help**: Quick command card for caveman modes.
  - Test: "/caveman-help"
- **review-delta**: Token-efficient review of changed code plus direct impact.
  - Test: "/review-delta" or "review my last commit with blast radius"
- **review-pr**: Structured PR or branch diff review with blast-radius analysis.
  - Test: "/review-pr" or "review this PR against main"
- **design-taste-frontend**: Premium UI rules overriding generic LLM UI defaults.
  - Test: "/design-taste-frontend" or "build a premium anti-slop hero section"
- **minimalist-ui**: Editorial, restrained UI (Notion/Linear vibes).
  - Test: "/minimalist-ui" or "build a minimalist dashboard"
- **industrial-brutalist-ui**: Hard Swiss-type brutalist UI, sharp contrast.
  - Test: "/industrial-brutalist-ui" or "brutalist landing page"
- **image-to-code**: Image-first pipeline: analyze reference image then implement frontend.
  - Test: "/image-to-code" or "build this UI from the screenshot"
- **redesign-existing-projects**: Audit and fix existing UI for layout, spacing, hierarchy.
  - Test: "/redesign-existing-projects" or "audit and redesign this page"
- **ui-ux-pro-max**: Deep UI/UX intelligence (50+ styles, palettes, font pairings, UX rules) across React/Next/Vue/Svelte/SwiftUI/RN/Flutter/Tailwind/shadcn/HTML.
  - Test: "/ui-ux-pro-max" or "design a SaaS dashboard with color + font system"
- **huashu-design**: HTML-first high-fidelity prototypes, interactive demos, slides, animations and design-direction advisor (incl. MP4/GIF export and narrated animation pipeline).
  - Test: "/huashu-design" or "make an interactive HTML prototype" or "做个原型"
- **app-store-screenshots**: App Store / Google Play screenshot generator skill with a bundled Next.js editor template for exportable mobile listing assets and feature graphics.
  - Test: "/app-store-screenshots" or "build App Store screenshots for my app"
- **emil-design-eng**: Emil Kowalski design-engineering philosophy for UI polish, invisible detail, and animation craft. Installed as explicit-invocation only to avoid overlapping with `impeccable`.
  - Test: "/emil-design-eng" or "use Emil Kowalski's design engineering style"
- **impeccable**: Production frontend craft — design, redesign, audit, polish, animate real interfaces with committed visual choices and working code (23 subcommands: craft, shape, audit, animate, bolder, quieter, layout, typeset, colorize, harden, optimize, polish, live, …).
  - Test: "/impeccable" or "polish this dashboard" or "make this landing page bolder"

## Anthropic skills

- **algorithmic-art**: Generative/algorithmic art with p5.js, seeded randomness, flow fields, particle systems.
  - Test: "/algorithmic-art" or "make generative art with code"
- **brand-guidelines**: Apply Anthropic's official brand colors and typography to artifacts.
  - Test: "/brand-guidelines" or "style this in Anthropic brand"
- **canvas-design**: Beautiful static visual art as .png/.pdf (posters, designs).
  - Test: "/canvas-design" or "design a poster"
- **claude-api**: Build, debug, optimize Anthropic SDK apps (caching, thinking, tool use, model migration).
  - Test: "/claude-api" or "add prompt caching to this Claude code"
- **doc-coauthoring**: Structured workflow for co-authoring docs, proposals, specs, decision docs.
  - Test: "/doc-coauthoring" or "help me write a tech spec"
- **docx**: Create/read/edit Word .docx files (TOC, headings, tables, tracked changes, images).
  - Test: "/docx" or "make a Word report with a TOC"
- **frontend-design**: Anthropic's original frontend-design skill (impeccable's parent). Distinctive UI code, avoids generic AI aesthetics.
  - Test: "/frontend-design" or "build a polished landing page"
- **internal-comms**: Status reports, leadership updates, FAQs, incident reports, newsletters.
  - Test: "/internal-comms" or "write a weekly status update"
- **mcp-builder**: Build high-quality MCP servers (FastMCP Python or TS SDK).
  - Test: "/mcp-builder" or "build me an MCP server for X"
- **pdf**: Read/extract/create/merge/split/rotate/watermark/fill/OCR PDFs.
  - Test: "/pdf" or "merge these PDFs"
- **pptx**: Create/parse/edit PowerPoint .pptx (slides, decks, templates, speaker notes).
  - Test: "/pptx" or "make a pitch deck"
- **skill-creator**: Create, edit, evaluate, and optimize Copilot/Claude skills (incl. trigger-description tuning).
  - Test: "/skill-creator" or "create a new skill for X"
- **slack-gif-creator**: Animated GIFs optimized for Slack (size constraints, validation).
  - Test: "/slack-gif-creator" or "make a Slack GIF of X"
- **theme-factory**: Apply 10 preset themes (colors+fonts) to artifacts or generate one on the fly.
  - Test: "/theme-factory" or "apply a theme to this artifact"
- **web-artifacts-builder**: Multi-component claude.ai HTML artifacts with React + Tailwind + shadcn/ui (state, routing).
  - Test: "/web-artifacts-builder" or "build a complex multi-page artifact"
- **webapp-testing**: Playwright-based local webapp testing (UI, screenshots, console logs).
  - Test: "/webapp-testing" or "test this webapp with Playwright"
- **xlsx**: Create/read/edit .xlsx/.xlsm/.csv/.tsv (formulas, formatting, charts, cleanup).
  - Test: "/xlsx" or "fix the messy xlsx in downloads"

## gstack workflow (Garry Tan's gstack, slash-command only)

Imported from [garrytan/gstack](https://github.com/garrytan/gstack). 51 skills installed under `gstack-*`. Most have multi-line/empty descriptions so they DO NOT auto-trigger — invoke explicitly by slash command (e.g. `/gstack-ship`, `/gstack-investigate`).

**Highlights:**
- **gstack-ship**, **gstack-land-and-deploy**, **gstack-setup-deploy** — shipping pipeline
- **gstack-investigate**, **gstack-openclaw-investigate** — debug / root-cause
- **gstack-openclaw-ceo-review**, **gstack-plan-ceo-review** — challenge plans
- **gstack-openclaw-office-hours** — brainstorm/evaluate ideas
- **gstack-openclaw-retro**, **gstack-retro** — weekly engineering retros
- **gstack-autoplan**, **gstack-plan-tune**, **gstack-plan-eng-review**, **gstack-plan-design-review**, **gstack-plan-devex-review** — planning chain
- **gstack-careful**, **gstack-guard**, **gstack-freeze**, **gstack-unfreeze** — safety modes
- **gstack-context-save**, **gstack-context-restore** — session state
- **gstack-design-html**, **gstack-design-review**, **gstack-design-consultation**, **gstack-design-shotgun**, **gstack-devex-review** — design/UX reviews
- **gstack-qa**, **gstack-qa-only**, **gstack-review**, **gstack-canary** — quality gates
- **gstack-browse**, **gstack-scrape**, **gstack-hackernews-frontpage**, **gstack-open-gstack-browser**, **gstack-setup-browser-cookies** — browser
- **gstack-benchmark**, **gstack-benchmark-models**, **gstack-health**, **gstack-landing-report** — measurement
- **gstack-document-generate**, **gstack-document-release**, **gstack-make-pdf** — docs
- **gstack-learn**, **gstack-pair-agent**, **gstack-codex**, **gstack-cso**, **gstack-skillify** — workflow helpers
- **gstack-setup-gbrain**, **gstack-sync-gbrain**, **gstack-upgrade** — gbrain/gstack maintenance

Full list: `Get-ChildItem .github/skills/ -Directory -Filter "gstack-*"`
