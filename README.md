# Quillship Docs

A Writing Day project for [Write the Docs Portland 2026](https://www.writethedocs.org/conf/portland/2026/writing-day/) — Sunday, May 3, 2026.

> **Goal in one sentence:** Find and fix the patterns that make documentation hard for AI agents and LLMs to use accurately, using a fictional product's deliberately defective docs as our shared sandbox.

---

## Quick links

- **Audit tool (early prototype — be open to feedback)** — [dzg557ngeo1lr.cloudfront.net](https://dzg557ngeo1lr.cloudfront.net/) — no signup, no auth. Paste any docs URL and it returns an AI-readiness report grouped into Structured Data, Discoverability, Content Quality, and AI Citations. Pass / warning / not-verified per signal — no numeric scoring. The tool is rough; if it misses a fix, that's useful feedback we want to hear.
- **Live docs site (the URL the audit tool reads on this repo):** [wtd-quillship-demo.github.io/quillship-docs](https://wtd-quillship-demo.github.io/quillship-docs/)
- **Repo:** [github.com/wtd-quillship-demo/quillship-docs](https://github.com/wtd-quillship-demo/quillship-docs) — fork from here, edit, push back
- **Pick a task:** [Issues labeled `wtd-2026`](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Awtd-2026) (19 to choose from — 16 page-level, 3 [site-level](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Asite-level), 5 marked `good-first-issue`)
- **Pattern tracker (live shared sheet):** [Quillship Pattern Tracker on Google Sheets](https://docs.google.com/spreadsheets/d/1wdKhOdjaP52pjRpgaVR3DUaVMlJDxNnX/edit?usp=sharing) — view-only; the project lead writes rows during the day. Offline backup: [pattern-tracker.xlsx in repo](pattern-tracker.xlsx).
- **AI coding agents — read this first:** [CONTRIBUTING.md](CONTRIBUTING.md)
- **Community Pattern Catalog (we'll build this together today, starting from zero):** [PATTERN_CATALOG.md](PATTERN_CATALOG.md)
- **Canonical anti-patterns + fix criteria:** [CONTRIBUTING.md → AI-readiness criteria](CONTRIBUTING.md#what-ai-readiness-means-here-canonical-list)

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

**Today's focus.** Each defective page in this repo demonstrates one or more anti-patterns that make docs harder for AI to use. Your job is to **find them, fix them, re-run the audit tool, and tell us whether the tool picked up your fix.** The tool currently flags signals as pass / warning / not-verified across four categories — no numeric scoring. If the tool is unavailable, or it doesn't reflect the change you made, self-audit against the [eight criteria in CONTRIBUTING.md](CONTRIBUTING.md#what-ai-readiness-means-here-canonical-list) and note that in your issue comment. Honest feedback about the tool — including "the tool didn't catch this" — is exactly what we want.

A [Community Pattern Catalog](PATTERN_CATALOG.md) gets built end-of-day from what attendees surface in the [live pattern tracker](https://docs.google.com/spreadsheets/d/1wdKhOdjaP52pjRpgaVR3DUaVMlJDxNnX/edit?usp=sharing) — every contributor with permission is credited. We'll publish whatever we surface together, however much that is. **There's no fixed deliverable size and no required time commitment** — stop by for 10 minutes or stay longer, both are useful.

---

## How to participate — stay as long or as short as you like

Writing Day projects are flexible. Bounce between tables. Stop in for 10 minutes or settle in. All three of these paths produce something useful — and you can mix them. Audit your own docs to see the patterns, then fix a Quillship issue (or vice versa). Both teach the same lesson from different sides.

### Path A — Audit-only (~10 min)

No fork, no fix — just see what the patterns look like in the wild.

1. Open the [audit tool](https://dzg557ngeo1lr.cloudfront.net/)
2. Paste **any docs URL** — the [Quillship live site](https://wtd-quillship-demo.github.io/quillship-docs/), your own product's docs, an open-source project's docs, anything
3. Read the report. Skim the eight criteria in [CONTRIBUTING.md](CONTRIBUTING.md#what-ai-readiness-means-here-canonical-list) to interpret it
4. Tell the project lead at the table to add a row to the [live pattern tracker](https://docs.google.com/spreadsheets/d/1wdKhOdjaP52pjRpgaVR3DUaVMlJDxNnX/edit?usp=sharing) describing the most interesting pattern you saw
5. Leave with an AI-readiness report and a sense of what to fix later — and if the report missed something obvious about the page, jot that down too

### Path B — Fix one issue, re-audit (~30-45 min)

The core loop. Two ways to edit — pick whichever you're more comfortable with.

#### B1. Pick and claim an issue

1. Open [Issues labeled `wtd-2026`](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Awtd-2026). First-timers: filter to [`good-first-issue`](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Agood-first-issue) (~15-25 min each)
2. **Assign the issue to yourself** so nobody else picks it up:
   - On the issue page, in the right sidebar, click the gear icon next to **Assignees**
   - Click **assign yourself** (or search your username and select it)
   - If you can't see the gear (you're not a repo collaborator), leave a comment that says "Taking this" — that works as a soft claim. The project lead at the table can also assign you.

#### B2a (preferred for technical writers) — Clone, edit locally, push to your fork

Most comfortable if you live in an editor. You'll work the same way you would on any docs repo.

1. **Fork this repo** — click **Fork** (top-right) → **Create fork**
2. **Clone your fork:**
   ```bash
   git clone https://github.com/YOUR-USERNAME/quillship-docs.git
   cd quillship-docs
   ```
3. **Open the file** named in the issue (e.g. `docs/api-reference.md`) in your editor
4. **Edit, save, commit, push:**
   ```bash
   git add docs/api-reference.md
   git commit -m "Fix #3: structure api-reference into resource groups"
   git push
   ```
5. **Enable GitHub Pages on your fork** (one-time, takes ~30 seconds):
   - On your fork, click **Settings** → **Pages** (left sidebar)
   - Under **Build and deployment** → **Source**, select **Deploy from a branch**
   - Under **Branch**, pick `main` and `/ (root)` → click **Save**
   - Your live URL: `https://YOUR-USERNAME.github.io/quillship-docs/`
6. **Re-run the audit on your fork's URL** at [the audit tool](https://dzg557ngeo1lr.cloudfront.net/). In an issue comment, share: which signal(s) moved (e.g. "`llms.txt` went from ✗ to ✓"), or — if the tool didn't pick up your fix — say so. That's useful feedback on the tool itself.

#### B2b (alternative) — Edit on github.com directly, no clone, no terminal

Fastest path if you don't want to set up local tooling.

1. **Fork this repo** — click **Fork** (top-right) → **Create fork**
2. **Open the file** in your fork — navigate to e.g. `docs/api-reference.md`
3. **Click the pencil icon** (top-right of the file view) → edit in the browser → scroll to the bottom → **Commit changes** (commits straight to your fork's `main`)
4. **Enable GitHub Pages** (same one-time step as above): Settings → Pages → Deploy from a branch → `main` + `/ (root)` → Save → your URL is `https://YOUR-USERNAME.github.io/quillship-docs/`
5. **Re-run the audit** at [the audit tool](https://dzg557ngeo1lr.cloudfront.net/) and comment on the issue: which signals moved, or whether the tool missed the change you made

#### B3. Comment your audit feedback on the issue

Whichever editing path you took, drop a quick comment on the issue thread before marking it done:

- **Did the tool detect your fix?** Yes / Partial / No
- **Which signal moved?** (e.g. "`llms.txt` went from ✗ to ✓", or "all code blocks now show as language-tagged")
- **Or — if the tool missed the fix entirely** — say that. The tool is a rough prototype and honest feedback is more useful than a clean report.

That's how the [Pattern Catalog](PATTERN_CATALOG.md) gets credited contributors at the end of the day, and how we learn what the audit tool needs to detect next.

### Path C — Deeper dive (longer)

For anyone who finds a category of patterns they care about.

1. Tackle 2-3 issues in the same category (all the API ones, all the SDK ones, etc.) — you'll spot family resemblances
2. Co-author the [Community Pattern Catalog](PATTERN_CATALOG.md) — we build it as we go
3. Open a PR back to this repo with one favorite fix — your name lands in the contributors list

---

## Onboarding checklist

Before you start fixing, do these three things:

- [ ] **Read [CONTRIBUTING.md](CONTRIBUTING.md)** — explains AI-readiness in concrete terms (also written so AI coding agents can read it)
- [ ] **Pick one issue** from [the `wtd-2026` filter](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Awtd-2026) — first-timers should pick a [`good-first-issue`](https://github.com/wtd-quillship-demo/quillship-docs/issues?q=is%3Aissue+is%3Aopen+label%3Agood-first-issue)
- [ ] **Assign the issue to yourself** (sidebar → Assignees → assign yourself) so nobody else picks it up. If you can't (not a collaborator), comment "Taking this" — that works as a soft claim.

---

## Tools you'll use

- **AI-readiness audit tool** — [dzg557ngeo1lr.cloudfront.net](https://dzg557ngeo1lr.cloudfront.net/) (no signup, no auth). If it's down or you'd rather not use it, the [eight criteria in CONTRIBUTING.md](CONTRIBUTING.md#what-ai-readiness-means-here-canonical-list) work as a manual self-audit checklist.
- **Your editor** — VS Code, Sublime, vim, whatever. Recommended for technical writers (clone the fork, edit locally, push).
- **GitHub.com pencil-icon editor** — alternative if you don't want to clone. Edits commit straight to your fork's `main`.
- **Your AI coding assistant** — Cursor / Copilot / Kiro / Claude / Codex. Totally optional. See [CONTRIBUTING.md](CONTRIBUTING.md).

You only need a GitHub account. That's it.

---

## What "AI-readiness" actually means

A docs site is AI-ready when an LLM can read it once and answer accurate, specific questions about your product.

**The canonical list of eight criteria — and the anti-patterns each one covers — lives in [CONTRIBUTING.md → AI-readiness criteria](CONTRIBUTING.md#what-ai-readiness-means-here-canonical-list).** That's the list to self-audit against. The audit tool covers many of these signals but not all of them — part of today's exercise is finding out which ones it picks up reliably and which ones it misses.

The [Pattern Catalog](PATTERN_CATALOG.md) is the curated end-of-day artifact built from what attendees actually surface in the [live pattern tracker](https://docs.google.com/spreadsheets/d/1wdKhOdjaP52pjRpgaVR3DUaVMlJDxNnX/edit?usp=sharing) during the day.

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
