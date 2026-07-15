---
name: linkedin-write
description: Write a LinkedIn post in krishanavatar's voice — sharp, contrarian-but-grounded, first-person, no engagement-bait. Asks length intent before drafting and returns post body plus 2 alternate hooks.
---

# linkedin-write

Drafting a LinkedIn post for krishanavatar. LinkedIn is one of krishanavatar's two **sharp/contrarian-edge** formats (the other is Substack). Lead with a punchy hook, deliver one idea, close clean.

## Step 1 — Load context (mandatory)

Read these files:

1. `shared/voice-rules.md`
2. `shared/voice-samples.md`
3. `shared/pet-peeves.md`
4. `shared/topic-modes.md`
5. `shared/platform-styles.md`
6. `references/hook-formulas.md`

## Step 2 — Ask length intent

Ask the user ONCE:

> "Length? **short** (<500 chars, single observation+implication), **medium** (~1300 chars, hook+2-3 paras+payoff), or **long** (~2000+ chars, mini-essay with sections)?"

Wait for the answer. Default to medium if no response.

## Step 3 — Classify topic mode + apply platform style profile

Apply `topic-modes.md`. If security → forensic voice. If architecture/agent → sharp technical opinion. If leadership/governance → measured but still owned.

Then apply the **linkedin** row from `shared/platform-styles.md`: technical depth 2, headline aggressiveness 4, density 2.

## Step 4 — Pick a hook pattern

Choose ONE pattern from `references/hook-formulas.md` that fits the topic.

## Step 5 — Draft the post

**Constraints:**
- **First person.** "I" — owned opinions.
- **One idea per post.**
- **Scannable spacing.** Short paragraphs (1-3 lines), single blank lines between.
- **No more than 3 hashtags**, and only if topically meaningful.
- **Emoji:** follow the Emoji Control section in `shared/voice-rules.md`. Default level is `low`.
- **Closer:** crisp takeaway OR one genuine open question. Never engagement-bait.

**Length targets:**
- short: ≤500 characters total.
- medium: 1100-1400 characters.
- long: 1800-2400 characters.

## Step 6 — Pre-delivery checks

1. Run the regex sweep from `shared/pet-peeves.md`. Any hit → rewrite.
2. Confirm character count matches the requested length tier.
3. Confirm: no em-dashes joining clauses, no rule-of-three, no engagement-bait CTA, first-person.

## Step 7 — Save and deliver

Derive a kebab-case topic slug. Get today's date in `YYYY-MM-DD` form. Save to:

```
./drafts/<YYYY-MM-DD>-<topic-slug>/linkedin.md
```

If the file already exists, suffix with `-v2`, `-v3`, etc.

**Also print in chat:**

```
─── POST ───
<post body>

─── ALTERNATE HOOK 1 ───
<single hook line>

─── ALTERNATE HOOK 2 ───
<a different angle hook line>

─── META ───
characters: <N>
hashtags: <list or "none">
hook pattern used: <e.g., dichotomy / demoting / pragmatic-flex / observation-flip>
emoji level: <none | low | medium | high>
saved to: <path>
```
