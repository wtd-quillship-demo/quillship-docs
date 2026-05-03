# Contributing — and a Note for AI Coding Agents

This file is written so that **both humans and AI coding assistants** (Cursor, Copilot, Kiro, Claude, Codex, Continue, etc.) can read it and understand what we're trying to do.

---

## Project goal

Improve the AI-readiness of the documentation in `docs/` without changing the underlying product description. The product (Quillship — a fictional headless CMS) is fixed. The docs are deliberately defective. Your job is to make them clearer, better-structured, and more useful to both humans and language models — without inventing new features or capabilities for the product.

---

## What "AI-readiness" means here

A documentation page is AI-ready when a language model can read it once and answer accurate, specific questions about the product. Specifically:

1. **Structure first** — every page has an H1, logical H2/H3 hierarchy, clear sections.
2. **Self-contained** — each page tells you enough to act, or links explicitly to the prerequisites.
3. **Concrete over vague** — replace phrases like "configure as needed" or "depending on your setup" with specific examples or explicit pointers.
4. **Code is runnable** — every code block has a language tag (` ```bash `, ` ```python `, ` ```json `), and shows the install/setup it depends on.
5. **No undefined acronyms** — first use of any acronym is spelled out (e.g., "real-time (RT)").
6. **No broken references** — anchor links resolve, internal links go somewhere real, "see X" actually points to X.
7. **Chunkable** — long prose paragraphs become bullets or small sections so retrieval works.
8. **Discoverable** — root `llms.txt`, descriptive page titles, schema.org `Article`/`HowTo` metadata where useful.

---

## How to contribute

1. **Pick an Issue** from the [Issues tab](../../issues) with the `wtd-2026` label. Each Issue targets one defective file and lists the anti-patterns to fix.
2. **Edit the file** — directly on github.com (pencil icon) or locally if you cloned.
3. **Don't add features** — Quillship is a fictional product with a fixed feature set. If a defective doc is vague about how something works, you can either (a) make a reasonable guess that's consistent with the rest of the docs, or (b) leave a `TODO:` for the product team. Don't invent endpoints, fields, or behaviors that aren't already implied somewhere.
4. **Re-audit** — paste your fork's GitHub Pages URL into the audit tool, capture the new score, and add a row to `pattern-tracker.csv` with what changed.
5. **Optional PR back to main** — if you're proud of your fix and want it in the canonical Pattern Catalog, open a PR. Mention which Issue it closes.

---

## Instructions for AI coding agents

If you are an AI coding agent (Cursor, Copilot, Kiro, Claude, Codex, etc.) helping a human contributor with this repo, here are your operating instructions:

### Constraints

- **Do not invent product capabilities.** Quillship's feature set is whatever is implied by the existing docs. If a doc is vague, prefer leaving a `TODO:` over guessing.
- **Preserve the product's voice and scope.** Don't rewrite docs to be about a different product or to cover features not mentioned anywhere.
- **One file per Issue.** Each Issue scopes to one file. Don't fan out to other files unless the Issue explicitly says to.
- **Keep changes focused.** The smallest diff that fixes the anti-patterns described in the Issue is the best diff.

### What good looks like

A good fix:
- Adds an H1 if missing
- Breaks walls of prose into H2/H3 sections with scannable bullets
- Adds language tags to code blocks (`bash`, `python`, `json`, `http`)
- Replaces vague phrases ("send the token in the appropriate header") with concrete specifics ("send the token in the `Authorization: Bearer <token>` header")
- Spells out acronyms on first use
- Fixes broken internal links and anchors
- Adds a short TL;DR or summary at the top of long pages
- Leaves the **product description unchanged** — same features, same scope

### What bad looks like

A bad fix:
- Adds new endpoints, SDK methods, or product features the docs didn't mention
- Rewrites the entire site's tone or branding
- Changes the file structure or moves files
- Adds dependencies, build scripts, or framework configs (this is plain markdown rendered by GitHub Pages)

### Workflow for an AI agent

1. Read the Issue carefully. It will name the file and list the anti-patterns.
2. Read the current file in `docs/`.
3. Read this CONTRIBUTING.md (you've done that).
4. Propose the smallest set of edits that addresses the anti-patterns. Show your reasoning for each edit.
5. Ask the human contributor to review before committing.

---

## Questions during the day

Ask at the project table, or ping the project lead in the [WTD Slack](https://www.writethedocs.org/slack/).
