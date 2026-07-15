---
name: repurpose-all
description: Orchestrator — one topic, drafts across every format in one pass. Default produces LinkedIn, Twitter, Newsletter, GitHub Pages, Medium, Substack. Skips per-skill clarifying questions using sensible defaults.
---

# repurpose-all

Drafting one topic across multiple formats in a single response for krishanavatar.

## Step 1 — Load context (mandatory)

Read the shared voice files ONCE:

1. `shared/voice-rules.md`
2. `shared/voice-samples.md`
3. `shared/pet-peeves.md`
4. `shared/topic-modes.md`
5. `shared/platform-styles.md`

Then read each format's SKILL.md:

6. `../linkedin-write/SKILL.md`
7. `../twitter-write/SKILL.md`
8. `../newsletter-write/SKILL.md`
9. `../github-page-write/SKILL.md`
10. `../medium-write/SKILL.md`
11. `../substack-write/SKILL.md`
12. `../linkedin-write/references/hook-formulas.md`

## Step 2 — Ask format selection (one question only)

> "Generate which formats? Default is **all six** (linkedin, twitter, newsletter, github-page, medium, substack). Reply with **all**, or a comma-separated subset."

Wait for the answer. Default to **all** if no response.

## Step 3 — Detect emoji level

Parse the user's invocation for an emoji override. Default to `low`.

## Step 4 — Apply sensible defaults (do NOT ask per format)

| Format          | Default                                                    |
|-----------------|------------------------------------------------------------|
| linkedin        | length = **medium** (~1300 chars)                          |
| twitter         | mode = **opinion**                                         |
| newsletter      | length = **default** (300-600 words)                       |
| github-page     | produce a Markdown skeleton only (not full HTML)           |
| medium          | length = **default** (1500-3000 words)                     |
| substack        | length = **default** (600-1200 words)                      |

For github-page: output a Markdown skeleton with section headings. Tell the user to invoke `github-page-write` separately for the styled HTML file.

## Step 5 — Classify topic mode

Apply `shared/topic-modes.md` once. Use the resulting mode consistently across all formats.

## Step 6 — Draft each requested format

Reuse the same core argument across formats. The thesis is constant; structure, length, and register adapt per platform's `platform-styles.md` row.

**Pet peeves apply to every format.** Run the regex sweep from `shared/pet-peeves.md` against every draft.

## Step 7 — Save all formats

Create `./drafts/<YYYY-MM-DD>-<topic-slug>/`. Save:
- `linkedin.md`, `twitter.md`, `newsletter.md`, `medium.md`, `substack.md`, `github-page-skeleton.md`

## Step 8 — Deliver

```
═══════════════════════════════════════
TOPIC: <one-line topic restatement>
TOPIC MODE: <security | architecture-agents | leadership | cost-infra>
FORMATS: <list>
EMOJI LEVEL: <none | low | medium | high>
SAVED TO: ./drafts/<YYYY-MM-DD>-<topic-slug>/
═══════════════════════════════════════

─── LINKEDIN ───────────────────────
<post body>

ALTERNATE HOOKS:
- <hook 1>
- <hook 2>

meta: <chars> chars

─── TWITTER ────────────────────────
<tweet body>

meta: <chars>/280

─── NEWSLETTER ─────────────────────
subject: <≤8 words>
preheader: <≤120 chars>

<body>

meta: <words> words

─── GITHUB PAGE (Markdown skeleton) ─
# <title>
> <dek>

## 1. <Section>
<paragraphs>

## The Short Version
<3-line distillation>

meta: est <N> min read
note: run `github-page-write` for the styled HTML file.

─── MEDIUM ────────────────────────
# <title>
> <dek>

<body>

meta: <words> words

─── SUBSTACK ───────────────────────
subject: <≤8 words>
dek: <one sentence>

<body>

meta: <words> words

═══════════════════════════════════════
DONE.
═══════════════════════════════════════
```

## Step 9 — Pre-delivery check

- Same core thesis across all formats.
- Pet peeves regex passes for every draft.
- First-person throughout, no engagement-bait.
- Each format applied its `platform-styles.md` row.
- Emoji level consistent (per-format ceilings respected).
- Every file in the drafts directory was written.
