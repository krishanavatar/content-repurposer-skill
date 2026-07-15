---
name: newsletter-write
description: Write a newsletter issue in krishanavatar's voice — register between LinkedIn-sharp and Medium-measured, 300-600 words, subject line plus preheader plus scannable body, plain-text-readable, no engagement-bait.
---

# newsletter-write

Drafting a newsletter issue for krishanavatar. Newsletter sits **between sharp and measured** — direct, scannable, but with room for one real argument. Optimized for email clients: plain-text-readable, no required images.

## Step 1 — Load context (mandatory)

Read these files:

1. `shared/voice-rules.md`
2. `shared/voice-samples.md`
3. `shared/pet-peeves.md`
4. `shared/topic-modes.md`
5. `shared/platform-styles.md`

## Step 2 — Classify topic mode + apply platform style profile

Apply `topic-modes.md`. Then apply the **newsletter** row from `shared/platform-styles.md`: technical depth 2–3, headline aggressiveness 3, density 2–3.

## Step 3 — Plan the structure

1. **Subject line** — ≤8 words, specific, no hype.
2. **Preheader** — 1 sentence, ≤120 chars, complements (does not repeat) the subject.
3. **Opening hook** — one of the cadences from `voice-samples.md`.
4. **Body** — 3-5 short paragraphs OR 1 paragraph + a tight 3-5 item bulleted list.
5. **Closer** — 1-2 lines. Crisp takeaway. No engagement-bait.

## Step 4 — Draft

- First person. Owned opinion. Plain-text readable.
- One number or specific reference at minimum.
- **Emoji:** default `low`.

## Step 5 — Pre-delivery checks

1. Run the regex sweep from `shared/pet-peeves.md`. Any hit → rewrite.
2. Confirm word count is in the 300-600 range.
3. Confirm subject + preheader preview well (no repetition, no clickbait).

## Step 6 — Save and deliver

Save to `./drafts/<YYYY-MM-DD>-<topic-slug>/newsletter.md`. Format:

```markdown
# Subject: <subject line>
Preheader: <preheader>

---

<body>
```

Print in chat:

```
─── SUBJECT ───
<≤8 words>

─── PREHEADER ───
<≤120 chars>

─── BODY ───
<300-600 word post>

─── META ───
words: <N>
saved to: <path>
```
