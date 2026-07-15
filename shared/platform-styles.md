# Platform Style Profiles

Voice is constant (see `voice-rules.md`, `voice-samples.md`, `pet-peeves.md`). Register varies mildly per format (the per-format dial in `voice-rules.md`). This file controls **audience-driven writing style** — how the same argument is *delivered* for each platform's audience.

## Axis scales

**Technical depth (1–5)**
- 1 = concept only, no code
- 2 = at most one inline config line or command
- 3 = one short snippet, explained for non-experts
- 4 = multiple code/config blocks, explained
- 5 = full code/internals, reader is expected to run it

**Headline aggressiveness (1–5)** — always inside the no-engagement-bait rule
- 1 = plain / SEO-descriptive
- 3 = clear-benefit with mild intrigue
- 5 = curiosity-gap / strong stakes, still honest

**Skimmability / density (1–5)**
- 1 = atomic, sparse
- 3 = pull-quotes + medium prose
- 5 = dense long-form: sections, tables, code

## Profiles

| Platform | Audience | Tech depth | Headline | Density |
|---|---|---|---|---|
| **twitter/x** | Practitioners scrolling fast | 1–2 | 4 punchy/aphoristic | 1 atomic |
| **linkedin** | Peers, eng leaders, hiring managers | 2 | 4 scroll-stopping first line | 2 whitespace, short paras |
| **newsletter** | Opted-in inbox readers | 2–3 | 3 clear-benefit subject | 2–3 scannable |
| **substack** | Subscribers who came for a point of view | 3 | 4 intriguing subject | 3 pull-quote, medium prose |
| **medium** | Broad tech-curious discovery audience | 3–4 | 5 curiosity-gap allowed, honest body | 4 H2 sections, dense prose |
| **github-page** | Engineers who arrived via search/link and may run the code | 5 | 2 plain-descriptive, SEO-clear | 5 long-form, code, tables |

**Twitter threads exception:** A 3–7 tweet thread tolerates technical depth ~3 and density ~3.

## Precedence

1. **`voice-rules.md` + `pet-peeves.md` are absolute.**
2. **`topic-modes.md` can raise substance, never lower it.**
3. **`platform-styles.md` sets the per-platform baseline** within rules 1 and 2.
