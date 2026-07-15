# content-repurposer-skill

[![License: Apache 2.0](https://img.shields.io/badge/license-Apache_2.0-blue?style=flat-square)](LICENSE) [![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=flat-square&logo=anthropic&logoColor=white)](https://claude.com/claude-code) ![Status](https://img.shields.io/badge/status-active-success?style=flat-square)

**Drafts for:**

![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)
![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)
![Substack](https://img.shields.io/badge/Substack-FF6719?style=for-the-badge&logo=substack&logoColor=white)
![Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)
![GitHub%20Pages](https://img.shields.io/badge/GitHub%20Pages-181717?style=for-the-badge&logo=github&logoColor=white)
![Newsletter](https://img.shields.io/badge/Newsletter-2C2D72?style=for-the-badge&logo=minutemailer&logoColor=white)

A Claude Code plugin for drafting technical writing across six formats from a single topic — **in your voice**, not generic LLM marketing voice. Plus an orchestrator that produces all formats in one pass.

Given a topic, one skill drafts for one format. Pick the format you want; the skill loads a shared voice profile, classifies the topic, and writes. Or invoke `repurpose-all` to get every format at once. The default voice profile in this repo is calibrated to krishanavatar ([krishanavatar.github.io](https://krishanavatar.github.io/)). The interesting part isn't the default voice; it's the **mechanism** for capturing yours. See [Make This Yours](#make-this-yours).

## What you get

Six format skills, one orchestrator, one shared voice profile, no marketing fluff:

| Skill                 | Format                                                  | Length        | Register                       |
|-----------------------|---------------------------------------------------------|---------------|--------------------------------|
| `linkedin-write`      | LinkedIn post (asks length intent per run)              | 500-2400 ch   | Sharp / contrarian             |
| `twitter-write`       | Tweet or thread on X (asks mode: quote/opinion/share/wow/thread) | ≤280 ch or 3-7 tweets | Sharpest / most compressed     |
| `substack-write`      | Substack post                                           | 600-1200 w    | Sharp / contrarian             |
| `newsletter-write`    | Newsletter issue (subject + preheader + body)           | 300-600 w     | Between sharp and measured     |
| `medium-write`        | Medium article                                          | 1500-3000 w   | Measured engineer              |
| `github-page-write`   | Hand-rolled HTML post for a static blog (two themes)    | 1800-2800 w   | Measured engineer, long-form   |
| `repurpose-all`       | **Orchestrator** — one topic, drafts across every format you select, in one pass | varies | Adapts per format              |

## Install

Clone wherever you keep your tools:

```bash
git clone https://github.com/krishanavatar/content-repurposer-skill.git
cd content-repurposer-skill
./install.sh
```

The script symlinks the seven skills into `~/.claude/skills/`. Pass a path as the first argument to override: `./install.sh /custom/skills/dir`. **Restart your Claude Code session** to pick them up.

After install, create the `shared` symlink inside each skill directory (required for shared file resolution):

```bash
for s in linkedin-write twitter-write newsletter-write github-page-write medium-write substack-write repurpose-all; do
  ln -sfn ../../shared skills/$s/shared
done
```

## Use

After restarting your session, invoke any skill by name.

**Single-format invocations:**

```
Use linkedin-write to draft a post about why agentic systems fail in production despite passing benchmarks.

Use twitter-write — topic: AI shrinkflation in frontier models.

Use github-page-write for a write-up on real-time pub/sub architecture.

medium-write — topic: contextual retrieval is a chunk-level upgrade, not a retrieval strategy.
```

**Repurpose across formats in one pass:**

```
Use repurpose-all on this topic: why most teams ship agentic systems that pass evals but fail in production.
```

## Make This Yours

### Step 1 — Replace `shared/voice-rules.md`
Update with your identity, default register, per-format tone dial, and words you actually use.

### Step 2 — Populate `shared/voice-samples.md` with your real writing
Paste 4-6 verbatim openings from your own published posts. These are calibration anchors — the shape, not the substance.

### Step 3 — Edit `shared/pet-peeves.md`
Add your personal pet peeves. Remove anything you want to keep.

### Step 4 — Adjust `shared/topic-modes.md`
Rename and re-bucket modes to match the topics you write about.

### Step 5 — Tune `shared/platform-styles.md`
Edit the profile table to match your audience mix per platform.

### Step 6 — Update each SKILL.md description
The frontmatter `description:` in each `skills/<name>/SKILL.md` mentions krishanavatar. Change to your name/handle.

### Step 7 — Update `github-page-write` for your own site
This skill fetches templates from a blog repo. Point `gh api repos/...` at your own repo and template paths, or rewrite to output Markdown with frontmatter for Jekyll/Hugo/etc.

## Architecture

`shared/` holds five files every skill loads on every invocation:

| File                       | Purpose                                                                 |
|----------------------------|-------------------------------------------------------------------------|
| `shared/voice-rules.md`    | Voice register, per-format dial, emoji control, encouraged patterns     |
| `shared/voice-samples.md`  | Verbatim openings from real posts — calibration anchors                 |
| `shared/pet-peeves.md`     | Hard blacklist + regex sweep run against every draft before delivery    |
| `shared/topic-modes.md`    | Topic → mode map (security / agents / leadership / cost-infra)          |
| `shared/platform-styles.md`| Per-platform style: audience, technical depth, headline, density        |

Each skill's `SKILL.md` is short and points at these shared files. Edit the shared files and every skill picks up the change immediately.

The `shared/` directory needs to be symlinked into each skill folder (`skills/<name>/shared/`) so `SKILL.md` can reference it with single-level relative paths.

## What's deliberately NOT in here

- **Auto-publish integrations.** No LinkedIn API, no Substack API, no Twitter API. The skill drafts; you review and post manually.
- **LinkedIn-marketing tooling** (profile optimizer, thread monitor, engagement analytics).

## License

Apache 2.0. See [LICENSE](./LICENSE).

Forked from [asadani/content-repurposer-skill](https://github.com/asadani/content-repurposer-skill) — mechanism by Anuj Sadani, voice profile updated for krishanavatar.

## Credits

Built by [krishanavatar](https://krishanavatar.github.io/). Original mechanism by [Anuj Sadani](https://asadani.github.io/).
