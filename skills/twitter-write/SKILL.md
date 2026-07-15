---
name: twitter-write
description: Write a Twitter/X post in krishanavatar's voice. Five modes — quote (aphoristic single line), opinion (sharp contrarian take), share (working-on/reading note with optional link), wow (surprising number plus implication), thread (3-7 tweet structured argument). Asks mode before drafting.
---

# twitter-write

Drafting a Twitter / X post for krishanavatar. Twitter is the sharpest, most compressed of all formats. **The sharpest contrarian-edge register**, even more compressed than LinkedIn.

## Step 1 — Load context (mandatory)

Read these files:

1. `shared/voice-rules.md`
2. `shared/voice-samples.md`
3. `shared/pet-peeves.md`
4. `shared/topic-modes.md`
5. `shared/platform-styles.md`

## Step 2 — Ask mode

Ask the user ONCE:

> "Mode? **quote** (single ≤280-char aphoristic line) / **opinion** (sharp contrarian take) / **share** (working-on or reading note, optional link) / **wow** (surprising number plus implication) / **thread** (3-7 tweet structured argument)"

Wait for the answer. Default to **opinion** if no response.

## Step 3 — Classify topic mode + apply platform style profile

Apply `shared/topic-modes.md`. Then apply the **twitter/x** row from `shared/platform-styles.md`: technical depth 1–2, headline aggressiveness 4, density 1. Thread mode: depth ~3, density ~3.

## Step 4 — Draft by mode

### Mode: quote
- One line. ≤280 characters. Aphoristic or observation-flip cadence. No hashtags. No URL. No CTA.

### Mode: opinion
- One tweet (≤280) if the take fits. Otherwise a 2-tweet mini-thread.
- Lead with the contrarian observation. Land with the implication.
- No hashtags. No CTA. No "Hot take:" framing.

### Mode: share
- One tweet (≤280). Brief context + your one-line take + optional URL at the end.

### Mode: wow
- One tweet (≤280). A specific number or finding that flips an assumption, plus the implication.

### Mode: thread
- 3-7 tweets numbered `1/`, `2/`, `3/` etc.
- Tweet 1 is the hook — must work as a standalone tweet.
- Final tweet: crisp takeaway or callback. No "RT if you agree".

## Step 5 — Voice constraints (all modes)

- **First person.** "I" — owned opinions.
- **Emoji:** default `low` — most tweets should have zero emoji. Max 1 emoji per tweet at `medium`.
- **No hashtags** in modes quote / opinion / wow / thread. In `share` mode, max 1 hashtag.
- **No CTA.**

## Step 6 — Pre-delivery checks

1. Run the regex sweep from `shared/pet-peeves.md`. Any hit → rewrite.
2. Confirm every tweet is ≤280 characters.
3. Confirm no engagement-bait CTA.

## Step 7 — Save and deliver

Save to `./drafts/<YYYY-MM-DD>-<topic-slug>/twitter.md`. Print in chat.

For single-tweet modes:

```
─── TWEET ───
<tweet body>

─── ALTERNATE ───
<a different angle>

─── META ───
characters: <N>/280
mode: <quote | opinion | share | wow>
saved to: <path>
```

For thread mode:

```
─── THREAD ───
1/ <tweet 1 — hook>

2/ <tweet 2>
...

─── META ───
tweets: <N>
character counts: <comma-separated list>
saved to: <path>
```
