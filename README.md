# Quillship Docs

A Writing Day project for [Write the Docs Portland 2026](https://www.writethedocs.org/conf/portland/2026/writing-day/) — Sunday, May 3, 2026.

> **Goal in one sentence:** Find and fix the patterns that make documentation hard for AI agents and LLMs to use accurately, using a fictional product's deliberately defective docs as our shared sandbox.

---

## Quick links

- 📖 **Live docs site (audit this URL):** [wtd-quillship-demo.github.io/quillship-docs](https://wtd-quillship-demo.github.io/quillship-docs/)
- ✅ **Pick a task:** [Issues labeled `wtd-2026`](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Awtd-2026) (8 to choose from, 3 marked `good-first-issue`)
- 📊 **Pattern tracker (download):** [pattern-tracker.xlsx](pattern-tracker.xlsx)
- 🤖 **AI coding agents — read this first:** [CONTRIBUTING.md](CONTRIBUTING.md)
- 📚 **Community Pattern Catalog (grows during the day):** [PATTERN_CATALOG.md](PATTERN_CATALOG.md)

---

## Browse the (defective) docs

Quillship is a fictional headless CMS. The docs cover the surface area you'd expect from a real one — each page has its own deliberate defect.

### Top level

| Page | What's wrong with it |
|---|---|
| [Home](docs/index.md) | Marketing fluff, no H1, no real "what is this" |
| [Getting Started](docs/getting-started.md) | Code blocks with no language tag |
| [API Reference](docs/api-reference.md) | Wall of prose, no endpoint structure |
| [Authentication](docs/authentication.md) | Vague — no header name, no token format |
| [Webhooks](docs/webhooks.md) | Broken anchors, undefined acronyms |
| [FAQ](docs/faq.md) | Circular answers |

### Concepts

| Page | What's wrong with it |
|---|---|
| [Content Model](docs/concepts/content-model.md) | Wall-of-prose abstractions, no concrete schema example |

### API

| Page | What's wrong with it |
|---|---|
| [GraphQL](docs/api/graphql.md) | Talks about queries without showing one |
| [Rate Limits](docs/api/rate-limits.md) | Numbers buried in prose, no table |

### SDKs

| Page | What's wrong with it |
|---|---|
| [Python](docs/sdks/python.md) | No install command, untagged code |
| [JavaScript](docs/sdks/javascript.md) | Wrong import, no language tags, weak TS section |

### Guides

| Page | What's wrong with it |
|---|---|
| [Quickstart: React](docs/guides/quickstart-react.md) | Skips prerequisites, jumps to advanced topics |
| [Migrate from WordPress](docs/guides/migrate-from-wordpress.md) | 3KB single paragraph |

### Operations

| Page | What's wrong with it |
|---|---|
| [Deployment](docs/ops/deployment.md) | Generic guidance, no concrete env vars or example |

### Reference

| Page | What's wrong with it |
|---|---|
| [CLI](docs/reference/cli.md) | Commands listed without flags, args, or examples |
| [Glossary](docs/reference/glossary.md) | Definitions that don't define anything |

> Tip: skim the live site first ([wtd-quillship-demo.github.io/quillship-docs](https://wtd-quillship-demo.github.io/quillship-docs/)) — that's the URL the audit tool reads. The links above take you to the source markdown on GitHub (where you'll edit).

---

## Project goal & focus

**The problem.** Most docs were written for humans who skim. AI agents and LLMs read them differently — they need structure, chunkable sections, language-tagged code blocks, defined acronyms, working anchors, and a way to discover the site (`llms.txt`, semantic metadata). When docs lack these, AI assistants give your users wrong answers about your product.

**Today's focus.** Each defective page in this repo demonstrates one or more anti-patterns that make docs harder for AI to use. Your job is to **find them, fix them, and watch the AI-readiness score go up.**

A community-authored [Pattern Catalog](PATTERN_CATALOG.md) grows as people contribute — every fix adds a row, every contributor gets credit. We'll publish whatever we surface together, however much that is. **There's no fixed deliverable size and no required time commitment** — stop by for 10 minutes or stay longer, both are useful.

---

## How to participate — stay as long or as short as you like

Writing Day projects are flexible. Bounce between tables. Stop in for 10 minutes or settle in. All three of these paths produce something useful.

### 🟢 Path A — Audit-only (~10 min)

Don't have time to fork? No problem.

1. Walk up to the project table
2. Bring **any docs URL** you care about — your own product, an open-source project, a docs site you love or hate
3. We'll audit it together, walk through the report
4. Add one row to the [pattern tracker](pattern-tracker.xlsx)
5. Leave with a personalized AI-readiness report

### 🟡 Path B — Fork, fix, re-audit (~30-45 min)

The meat of the project. No clone, no terminal, no IDE setup needed.

1. **Fork this repo** (top right of the GitHub page)
2. **Enable GitHub Pages on your fork:** Settings → Pages → Source: `main` branch, root → Save. ~30 seconds later you'll have your own live URL: `https://YOUR-USERNAME.github.io/quillship-docs/`
3. **Pick an Issue** — [Issues labeled `wtd-2026`](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Awtd-2026)
4. **Edit the file directly on github.com** — click the file → click the pencil icon → fix → commit
5. **Audit your fork's GitHub Pages URL** — paste it into the audit tool at the project table
6. **Watch the score go up.** Comment your before/after on the Issue.

### 🔴 Path C — Deeper dive (longer)

For anyone who finds a category of patterns they care about.

1. Tackle 2-3 issues in the same category (all the API ones, all the SDK ones, etc.) — you'll spot family resemblances
2. Co-author the [Community Pattern Catalog](PATTERN_CATALOG.md) — we build it as we go
3. Open a PR back to this repo with one favorite fix — your name lands in the contributors list

---

## Onboarding checklist

Before you start fixing, do these three things:

- [ ] **Read [CONTRIBUTING.md](CONTRIBUTING.md)** — explains AI-readiness in concrete terms (also written so AI coding agents can read it)
- [ ] **Pick one issue** from [the `wtd-2026` filter](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Awtd-2026) — first-timers should pick a [`good-first-issue`](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Agood-first-issue)
- [ ] **Comment on the issue saying you're taking it** — keeps two people from duplicating work

---

## Tools you'll use

- **AI-readiness audit tool** — URL provided at the project table (CloudFront-hosted scanner; no signup, no auth)
- **GitHub.com web editor** — pencil icon on any file, no local setup needed
- **Your favorite editor** — VS Code, Sublime, vim, whatever. Optional.
- **Your AI coding assistant** — Cursor / Copilot / Kiro / Claude / Codex. Totally optional. See [CONTRIBUTING.md](CONTRIBUTING.md).

You only need a GitHub account. That's it.

---

## What "AI-readiness" actually means

A docs site is AI-ready when an LLM can read it once and answer accurate, specific questions about your product. The patterns we'll surface today include:

- **Structure** — clear H1 → H2 → H3 hierarchy, semantic HTML, table of contents
- **Chunkability** — short focused sections an LLM can retrieve independently
- **Code blocks** — language-tagged, runnable, with the install/setup right next to them
- **Discoverability** — `llms.txt`, `sitemap.xml`, schema.org metadata, descriptive page titles
- **Linking** — anchor links that work, no broken references, glossary for acronyms
- **Specificity** — concrete examples instead of vague "configure as needed" prose
- **Self-contained pages** — each page tells you enough to act, without requiring 5 prerequisite reads

The full reference grows in [PATTERN_CATALOG.md](PATTERN_CATALOG.md) during the day.

---

## After the conference

This repo stays public. Fork it, use it as a teaching example, or as a starter for auditing your own docs. The Pattern Catalog we build today becomes a resource the WTD community can keep extending.

---

## Project lead

Bring questions to the project table at Writing Day, or ping in the [WTD Slack](https://www.writethedocs.org/slack/) `#writing-day` channel.

---

## License

CC0 — public domain. Reuse this however you want.

## Acknowledgements

Built for the Write the Docs Portland 2026 community. Quillship is a fictional headless CMS — any resemblance to real products is, well, kind of the point. The defects in the docs are intentional.
