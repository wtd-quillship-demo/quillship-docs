# Community AI-Readiness Pattern Catalog

A curated catalog of patterns that make documentation more or less readable to AI agents and LLMs, surfaced by attendees of [Write the Docs Portland 2026 Writing Day](https://www.writethedocs.org/conf/portland/2026/writing-day/) on Sunday, May 3, 2026.

---

## How this catalog is built

We use **two surfaces** during Writing Day:

1. **The Pattern Tracker (live working surface)** — a Google Sheet where every contributor logs every pattern they spot, in real time. It's messy, fast, and grows row-by-row throughout the day.
   - Tracker file in this repo: [pattern-tracker.xlsx](pattern-tracker.xlsx)
   - Live shared sheet: _(link added once shared)_

2. **This catalog (curated artifact)** — a polished markdown doc published end-of-day (or shortly after the conference), drawn from the most useful patterns surfaced in the tracker. Each pattern gets a name, a description, an example, a fix recipe, and the contributor(s) credited.

> **Important:** This file does not auto-update from the Sheet. The Sheet is the live working surface; this catalog is the curated end-of-day artifact. Patterns make it into this file when they're cleaned up, deduplicated, and credited.

---

## Reading the catalog

Each entry follows the format:

```
### Pattern name
**What it looks like:** concrete example or signal
**Why AI struggles with it:** one or two sentences
**Fix:** what to do instead
**Example before/after:** in the Quillship demo or a real audited site
**Spotted by:** contributor first names
```

---

## Patterns

> _Patterns will be added here as the day's tracker rows are reviewed and curated. The catalog will be committed to this file and pushed before the end of the conference._

### 1. _(first pattern goes here)_

---

## Contributors

_(Names added with permission as the catalog is curated.)_

---

## Anti-patterns we expected to find (preview)

These are the patterns the demo docs were seeded with — the catalog will confirm or refine them based on what attendees actually surface:

1. **Wall of prose** — multiple paragraphs without headings or bullets. LLMs cannot retrieve discrete answers from undifferentiated text.
2. **Untagged code block** — fenced code without a language identifier. Breaks both syntax highlighting for humans and reliable parsing for tools.
3. **Vague reference** — "see the appropriate page" without a link. Dead-ends both readers and crawlers.
4. **Undefined acronym** — RT, SSE, ACF used without spelling out at first use. LLMs hallucinate meanings.
5. **Buried prerequisites** — install instructions assume the environment is already set up. Quickstart fails for newcomers.
6. **No `llms.txt` / no machine-readable index** — site has no front-door for LLMs and crawlers.
7. **Circular FAQ** — "What is X? See our X page." Provides zero information at the point of question.
8. **Broken anchor** — `[link](#section-that-doesnt-exist)`. Confuses both humans and link checkers.
9. **Missing TL;DR** — long page with no summary at top. LLMs fall back to truncating arbitrarily.
10. **Buried lede** — actual answer is in paragraph 4. LLMs may stop reading or pick a wrong earlier sentence.
11. **Tautological glossary** — "CDN: Content Delivery Network." Expansion without explanation.
12. **Generic guidance** — "configure as needed" / "set the appropriate value." Forces the reader to guess.
13. **Empty stub commands** — CLI reference that names commands without flags, args, or examples.
14. **Topic explosion in one page** — mentioning SSR, real-time, dynamic routes, WebSockets in one paragraph each. Each gets too little to be useful.
15. **Numbers buried in prose** — "a few hundred per minute" instead of a table with concrete values.

---

## License

CC0 — public domain. Reuse this catalog however you want.
