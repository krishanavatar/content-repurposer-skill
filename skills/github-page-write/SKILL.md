---
name: github-page-write
description: Write a long-form post for krishanavatar's blog at krishanavatar.github.io. Outputs a complete topic-slug/index.html with inline CSS, ready to commit. Use when krishanavatar wants to publish on their own site.
---

# github-page-write

You are drafting a long-form post for krishanavatar's blog at `krishanavatar.github.io`. The site is hand-rolled HTML — every post lives in `<topic-slug>/index.html` with **fully inline CSS** from a single template that ships both light and dark mode.

## Step 1 — Load context (mandatory, in this order)

Read these files:

1. `shared/voice-rules.md`
2. `shared/voice-samples.md`
3. `shared/pet-peeves.md`
4. `shared/topic-modes.md`
5. `shared/platform-styles.md`

Then fetch the **live source-of-truth** from krishanavatar's blog repo via the `gh` CLI:

```bash
gh api repos/krishanavatar/krishanavatar.github.io/contents/CLAUDE.md --jq '.content' | base64 -d
gh api repos/krishanavatar/krishanavatar.github.io/contents/_template/article.html --jq '.content' | base64 -d
```

If `gh` is not available or the fetch fails, ask the user to provide the template paths or auth.

## Step 2 — Theme

There is **one template** shipping both light and dark mode — the reader toggles. Do not ask which theme to use. Keep all theming machinery intact: the inline no-flash script, the `.theme-toggle` button, and the `[data-theme="dark"]` CSS block.

## Step 3 — Pick slug

From the topic, propose a kebab-case slug. The final output goes to `<slug>/index.html`.

## Step 4 — Draft the post

Voice register: **measured engineer**, still opinionated. Target 8-12 min reading time (~1800-2800 words). Apply `topic-modes.md` to adjust register.

Apply the **github-page** row from `shared/platform-styles.md`: technical depth 5, headline aggressiveness 2, density 5.

**Structure:**

1. **Hero block** — eyebrow label, H1 title, deck, meta line.
2. **Optional banner** — accent-bg card with a one-line thesis.
3. **Numbered sections** (8-12) — each begins with an uppercase section-label and a serif H2.
4. **Side-by-side or comparison table** when there's a dichotomy.
5. **Plain-english explainer card** for concepts a non-specialist might miss.
6. **Callout** for warnings/asides.
7. **Code blocks** for technical content.
8. **Closer section** — "The Frame to Leave On" — 3-line distillation.
9. **Footer** — `krishanavatar.github.io · <month> <year>` left, `← back to index` link right.

Apply all rules from `shared/voice-rules.md`. **Emoji:** default `low`.

## Step 5 — Generate the HTML

Take the template and replace every `{{PLACEHOLDER}}` token with real content. Preserve ALL inline CSS and class names exactly.

## Step 6 — Pre-delivery checks

1. Run the regex sweep from `shared/pet-peeves.md`. Any hit → rewrite.
2. Confirm: no em-dash joining clauses; no rule-of-three; first-person throughout.
3. Confirm: HTML is a single complete file with `<!doctype html>`, `<head>`, `<body>`.

## Step 7 — Save and deliver

Save to `./drafts/<YYYY-MM-DD>-<topic-slug>/github-page.html`.

Print in chat:
- The topic slug.
- Reading-time estimate.
- The full save path.
- *"To publish: copy `github-page.html` into the krishanavatar.github.io repo as `<blog-slug>/index.html` and commit."*
