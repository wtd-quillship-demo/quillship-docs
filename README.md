# Quillship Docs — Write the Docs Portland 2026 Writing Day

A fictional headless CMS with **deliberately defective documentation**, built for the Writing Day project [Can AI Find Your Docs? A Community Audit and Pattern Catalog](https://www.writethedocs.org/conf/portland/2026/writing-day/).

## 📖 Browse the docs (this is what you audit)

| Page | What's wrong with it |
|---|---|
| [Home](docs/index.md) | Marketing fluff, no H1, no real "what is this" |
| [Getting Started](docs/getting-started.md) | Code blocks with no language tag |
| [API Reference](docs/api-reference.md) | Wall of prose, no endpoint structure |
| [Authentication](docs/authentication.md) | Vague — no header name, no token format |
| [Webhooks](docs/webhooks.md) | Broken anchors, undefined acronyms |
| [Python SDK](docs/sdks/python.md) | No install command, untagged code |
| [Migrate from WordPress](docs/guides/migrate-from-wordpress.md) | 3KB single paragraph |
| [FAQ](docs/faq.md) | Circular answers |

**Live (rendered) site:** [wtd-quillship-demo.github.io/quillship-docs](https://wtd-quillship-demo.github.io/quillship-docs/) — this is the URL you audit

**Source files:** Click any link in the table above to view the markdown on GitHub (where you'll edit it)

---

## What this is

Eight markdown files that look like a real product's docs — and read fine to a human skimming — but are riddled with patterns that make them hard for AI agents and LLMs to use accurately. Things like missing structure, vague references, undefined acronyms, no `llms.txt`, code blocks with no language tag, walls of prose with no headings.

Your mission: **find the patterns, fix them, watch the AI-readiness score go up.**

---

## Three ways to participate

### 🟢 Ring 1 — Drop in for 10 minutes

Don't have time to fork or fix? No problem.

1. Walk up to the project table at Writing Day
2. Bring **any docs URL** you care about — your own product, an open-source project, a docs site you love or hate
3. We'll audit it together, walk through the report
4. Add one row to the [community pattern tracker](./pattern-tracker.csv)
5. Leave with a personalized AI-readiness report

### 🟡 Ring 2 — Fork & fix (45 minutes)

The meat of the day. No clone, no terminal, no IDE setup needed.

1. **Fork this repo** (top right of the GitHub page)
2. **Enable GitHub Pages on your fork:** Settings → Pages → Source: `main` branch, root → Save. ~30 seconds later you'll have your own live URL: `https://YOUR-USERNAME.github.io/quillship-docs/`
3. **Pick an Issue** from the [Issues tab](../../issues) labeled `wtd-2026` — each one targets a different defective file
4. **Edit the file directly on github.com** — click the file → click the pencil icon → fix → commit
5. **Audit your fork's GitHub Pages URL** — paste it into the audit tool
6. **Watch the score go up.** Comment your before/after on the Issue.

### 🔴 Ring 3 — All-in afternoon

For the few who fall in love with the topic.

1. Tackle 3-4 issues
2. Co-author the [Community Pattern Catalog](./PATTERN_CATALOG.md) (we'll build it live during the day)
3. Open a PR back to this repo with one favorite fix — your name lands in the contributors list

---

## What's in this repo

```
quillship-docs/
├── docs/
│   ├── index.md                   # Marketing fluff, no structure
│   ├── getting-started.md         # Code blocks with no language tag
│   ├── api-reference.md           # Wall of prose, no endpoint structure
│   ├── authentication.md          # Vague — no header name, no token format
│   ├── webhooks.md                # Broken anchors, undefined acronyms
│   ├── sdks/
│   │   └── python.md              # Code blocks with no language tag, no install
│   ├── guides/
│   │   └── migrate-from-wordpress.md  # 3KB single paragraph
│   └── faq.md                     # Questions with circular answers
├── pattern-tracker.csv            # Shared findings spreadsheet
├── PATTERN_CATALOG.md             # Community-built deliverable (grows during the day)
├── CONTRIBUTING.md                # Read this if you're using an AI coding agent
└── README.md                      # You are here
```

---

## What "AI-readiness" means

A docs site is AI-ready when an LLM can read it once and answer accurate questions about your product. The patterns we'll surface tomorrow include (but aren't limited to):

- **Structure** — clear headings (H1 → H2 → H3), table of contents, semantic HTML
- **Chunkability** — short focused sections an LLM can retrieve independently
- **Code blocks** — language-tagged, runnable, with the install/setup right next to them
- **Discoverability** — `llms.txt`, `sitemap.xml`, schema.org metadata, descriptive page titles
- **Linking** — anchor links that work, no broken references, glossary for acronyms
- **Specificity** — concrete examples instead of vague "configure as needed" prose
- **Self-contained pages** — each page tells you enough to act, without requiring 5 prerequisite reads

---

## Tools we'll use

- **AI-readiness audit tool** — URL provided at the table (it's a CloudFront-hosted scanner; no signup, no auth)
- **GitHub.com web editor** — pencil icon on any file, no local setup
- **Your favorite editor** — VS Code, Sublime, vim, whatever. Optional.
- **Your AI coding assistant** — Cursor / Copilot / Kiro / Claude / Codex. Totally optional. See [CONTRIBUTING.md](./CONTRIBUTING.md).

---

## After the conference

This repo stays public. Fork it, use it as a teaching example, or as a starter for auditing your own docs. The Pattern Catalog we build tomorrow becomes a resource the WTD community can keep extending.

---

## License

Public domain (CC0). Use any of this however you want.

## Acknowledgements

Built for the Write the Docs Portland 2026 community. All defective docs are intentionally so — Quillship is a fictional product. Any resemblance to real headless CMS docs is, well, kind of the point.
