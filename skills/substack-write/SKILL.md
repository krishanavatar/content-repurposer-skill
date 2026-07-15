---
name: substack-write
description: Write a Substack post in krishanavatar's voice — sharp/contrarian edge, 600-1200 words, email-first cadence, subject line and dek, no engagement-bait.
---

# substack-write

Drafting a Substack post for krishanavatar. Substack is one of krishanavatar's two **sharp/contrarian-edge** formats — closer to LinkedIn in tone, but with longer breath and full prose paragraphs.

## Step 1 — Load context (mandatory)

Read these files:

1. `shared/voice-rules.md`
2. `shared/voice-samples.md`
3. `shared/pet-peeves.md`
4. `shared/topic-modes.md`
5. `shared/platform-styles.md`

## Step 2 — Classify topic mode + apply platform style profile

Apply `topic-modes.md`. Then apply the **substack** row from `shared/platform-styles.md`: technical depth 3, headline aggressiveness 4, density 3.

## Step 3 — Plan the structure

1. **Subject line** — punchy, specific, ≤8 words.
2. **Dek** — 1 sentence. Sets up the tension.
3. **Opening** — a hook line from one of the cadences in `voice-samples.md`.
4. **3-5 short sections** — each is 2-4 paragraphs.
5. **One concrete example or number per section.**
6. **Closer** — 2-3 lines. Crisp takeaway OR one genuine open question. Never engagement-bait.

## Step 4 — Draft

Tone: closer to LinkedIn-sharp. Owned opinions. First person. Email-first. **Emoji:** default `low`.

## Step 5 — Pre-delivery checks

1. Run the regex sweep from `shared/pet-peeves.md`. Any hit → rewrite.
2. Confirm word count is in the 600-1200 range.
3. Confirm closer is not engagement-bait.

## Step 6 — Save and deliver

Save to `./drafts/<YYYY-MM-DD>-<topic-slug>/substack.md`. Format:

```markdown
# Subject: <subject line>
Dek: <dek>

---

<body in Markdown>
```

Print in chat:

```
─── SUBJECT ───
<subject line, ≤8 words>

─── DEK ───
<one sentence>

─── POST ───
<body in Markdown>

─── META ───
words: <N>
saved to: <path>
```
