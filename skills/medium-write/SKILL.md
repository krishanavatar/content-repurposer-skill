---
name: medium-write
description: Write a Medium article in krishanavatar's voice — measured engineer register, opinionated but evidence-first, 1500-3000 words, H2 sections, inline citations. Outputs both Markdown and paste-ready semantic HTML.
---

# medium-write

Drafting a Medium article for krishanavatar. Medium is a **measured engineer** register — opinionated, but the sharpest edges get softened into argument and evidence.

## Step 1 — Load context (mandatory)

Read these files:

1. `shared/voice-rules.md`
2. `shared/voice-samples.md`
3. `shared/pet-peeves.md`
4. `shared/topic-modes.md`
5. `shared/platform-styles.md`

## Step 2 — Classify topic mode + apply platform style profile

Apply `topic-modes.md`. Then apply the **medium** row from `shared/platform-styles.md`: technical depth 3–4, headline aggressiveness 5, density 4.

## Step 3 — Plan the structure

1. **Title** — curiosity-gap or strong-stakes title encouraged (Medium is a discovery feed). Must be honest.
2. **Dek** — 1-2 sentence subtitle.
3. **Opening** — a hook line, then a paragraph naming the question the article answers.
4. **5-8 `## H2` sections.** Each: a tight argument + at least one piece of evidence.
5. **At least one code/config block** if the topic is technical.
6. **Comparison content without an HTML table.** Use a fenced code block with ASCII table or a labeled list.
7. **Closer section** — "What I'd Take Away" or "The Short Version" — 3-5 line distillation.

## Step 4 — Draft

First person. No em-dash separators. No rule-of-three. No marketing words. **Emoji:** default `low`.

## Step 5 — Pre-delivery checks

1. Run the regex sweep from `shared/pet-peeves.md`. Any hit → rewrite.
2. Confirm every claim has a number, citation, or anecdote anchor.
3. Confirm structure has H2 sections and a real closer.

## Step 6 — Save and deliver

Save **two files** to `./drafts/<YYYY-MM-DD>-<topic-slug>/`:

1. **`medium.md`** — full Markdown article.
2. **`medium.html`** — semantic HTML for pasting into Medium's editor.

For `medium.html`: convert to clean semantic HTML. Medium strips CSS on paste, so do not rely on styling. Map: title → `<h1>`, H2 → `<h2>`, paragraphs → `<p>`, bold → `<strong>`, code → `<pre><code>`. **No `<table>` — use `<pre><code>` for ASCII tables or `<ul>` lists.**

Print the Markdown version in chat, then:

```
**To paste into Medium:**
1. Open `medium.html` in a browser.
2. Select all and copy.
3. Paste into Medium's story editor.

**Meta**
- word count: <N>
- reading time: <N> min
- saved to: <dir> (medium.md + medium.html)
```
