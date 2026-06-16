# linkedin-maxxing

**17 Claude Code skills + slash commands for substance-first LinkedIn growth.** Profile audit, content drafting (posts, carousels, longform, video, DMs, comments), performance analysis, and a Wikipedia-based humanizer. Anti-template, anti-slop, open source, MIT.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Plugin: linkedin-maxxing](https://img.shields.io/badge/Claude%20Code-Plugin-purple.svg)](https://docs.claude.com/en/docs/claude-code/plugins)
[![Skills: 17](https://img.shields.io/badge/Skills-17-blue.svg)](#the-17-skills)
[![Slash commands: 17](https://img.shields.io/badge/Slash%20commands-17-green.svg)](#slash-commands)

## Quick install

```
/plugin marketplace add warpirate/linkedin-maxxing
/plugin install linkedin-maxxing@linkedin-maxxing-marketplace
```

Restart the Claude Code session. Then type `/linkedin-maxxing:` and the autocomplete menu shows all 17 commands.

## Keywords

LinkedIn growth, LinkedIn content creation, LinkedIn AI tools, anti-AI-slop, humanizer, LinkedIn profile optimization, LinkedIn carousels, LinkedIn newsletter, LinkedIn DM writer, content repurposing, creator economy, personal branding, Claude Code plugin, Claude skills, Anthropic.

---

17 skills for growing on LinkedIn without producing slop.

> **How it works:** These skills run inside Claude Code on **content you paste in** (drafts, profile text, past posts, analytics CSV). There is no live LinkedIn API, no scraping, no posting on your behalf. You stay in the loop: the skills draft and critique, you publish.

## Why this exists

Most LinkedIn AI tools optimize for the wrong thing. They generate hooks from templates, evade AI detection, and produce posts in the same voice as 50,000 other posts written the same week. The result is the LinkedIn feed everyone scrolls past.

This repo refuses that approach. LinkedIn's 2026 ranking system rewards dwell time, substantive comments, and content that earns the "see more" click. The way to earn those is not better templates. It is to start with something specific the user actually wants to say, write it in the user's actual voice, and produce clean human-sounding text on the first pass.

So these skills:

- **Refuse templates.** No hook-value-CTA. No PAS, AIDA, or "5 lessons I learned." LinkedIn now downranks these patterns.
- **Refuse scaled outreach.** The DM skill writes one good message at a time, not 100 mail-merged ones.
- **Refuse engagement bait.** Comments are about adding substance, not "great post!" at scale.
- **Bake anti-AI-tell rules into drafting itself.** Every writing skill embeds the Wikipedia "Signs of AI writing" patterns as inline drafting constraints, not as a post-hoc polish. The first output is the clean output.

## The 17 skills

Grouped by where they sit in a sensible workflow.

### Foundation (set up once, reused by everything else)

| Skill | What it does |
|---|---|
| `train-voice` | Reads samples of the user's past writing (LinkedIn export, blog, pasted posts) and produces `voice-profile.md` that downstream writing skills read automatically. |
| `audit-profile` | Diagnoses the user's current LinkedIn profile section by section. Severity-rated issues, prioritized fix list. |
| `rewrite-profile` | Rewrites the full profile as one positioning unit: headline, About, Featured, Experience bullets, Skills. |
| `plan-content` | Defines 3-5 content pillars, audience, and cadence. Outputs `content-plan.md`. |

### Production (the daily content work)

| Skill | What it does |
|---|---|
| `find-ideas` | Interviews the user to surface specific, postable ideas. Outputs 2-5 idea seeds with concrete anchors and which next skill to use. |
| `write-hook` | Generates 3-5 hook variants for the 210-character LinkedIn "see more" fold, with the strongest marked. |
| `write-post` | Drafts a 1,000-1,300 character text post in the user's voice. The workhorse skill. |
| `build-carousel` | Plans and writes a 6-12 slide document carousel with copy and visual brief. The output is a SPEC the user assembles into a PDF in Canva or Figma; the skill does not export the finished PDF. |
| `write-longform` | Writes a 600-2,000 word article or newsletter issue. |
| `write-video-script` | Writes a 30-90 second video script with beats, timing, and on-screen text. |
| `repurpose-content` | Takes one piece of source content (talk, podcast, blog, doc) and produces 3-7 distinct LinkedIn pieces from different angles. |

### Engagement (one-to-one and thread work)

| Skill | What it does |
|---|---|
| `write-comment` | High-signal comments on others' posts. Comments now carry ~15x the algorithmic weight of likes. |
| `write-dm` | Connection requests, cold outreach, follow-ups, replies. One message at a time, no mail-merge. |
| `write-recommendation` | LinkedIn recommendations for former colleagues, with specific anchors instead of templated praise. |

### Learning loop (close the feedback cycle)

| Skill | What it does |
|---|---|
| `analyze-performance` | Clusters posts by pillar, format, hook type, and length. Identifies what is working and what is not. |
| `review-post` | Postmortem on one specific post: hook, body, close, format, timing. Three lessons for the next attempt. |

### Quality reference

| Skill | What it does |
|---|---|
| `humanizer` | The canonical 33-pattern reference (based on Wikipedia's "Signs of AI writing", WikiProject AI Cleanup, MIT licensed). Invoked explicitly when the user wants to humanize external pasted text. The 10 writing skills above embed the same rules inline so their output is humanized on the first pass. |

## How they fit together

A sensible first-time setup:

1. `train-voice` with whatever past writing the user has (LinkedIn data export is best)
2. `audit-profile` to see what is broken
3. `rewrite-profile` to fix the high-priority items
4. `plan-content` to define pillars and cadence

Then a daily/weekly loop:

1. `find-ideas` to surface what to post about
2. The right writing skill (`write-post`, `build-carousel`, `write-longform`, `write-video-script`)
3. `write-comment` for daily engagement on others' posts

And on a longer cadence (every 4-12 weeks):

1. `analyze-performance` to see what is landing
2. `review-post` on the strongest and weakest individual posts
3. Adjust the content plan

## Installation

### Claude Code (recommended)

```
/plugin marketplace add warpirate/linkedin-maxxing
/plugin install linkedin-maxxing@linkedin-maxxing-marketplace
```

Restart the Claude Code session after install so the skills auto-load.

### Manual (other clients)

Each skill is a self-contained `SKILL.md` file under `plugins/linkedin-maxxing/skills/<name>/`. Drop the directory into wherever your client reads skills from. Skills follow the standard frontmatter format (`name`, `description`, `license`) and load based on the description's trigger phrases.

## What this repo does not do

- **Doesn't scale outreach.** If you want to send 100 personalized DMs, this is not the tool.
- **Doesn't game engagement.** No "great post!" comment generators, no follow-for-follow strategies.
- **Doesn't write content from no input.** If you have nothing specific to say, the skills will tell you so and suggest you collect material first.
- **Doesn't promise outcomes.** Engagement is unpredictable. The skills produce work worth posting; what happens after is not guaranteed.
- **Doesn't scrape LinkedIn data.** The read-side skills (`analyze-performance`, `train-voice`) use the free LinkedIn data export (Settings → Data Privacy → Get a copy of your data), not paid scrapers.

## Acknowledgements

The `humanizer` skill is built on [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup. They have done the hardest part of this work and the result is freely available under Creative Commons.

## License

MIT. See `LICENSE`.

## Contributing

Issues and pull requests welcome. Two rules for contributions:

1. New skills must follow the same template: a `description` that leads with "Use when..." and trigger phrases (no workflow summary), a `When NOT to use this skill` section, a `What this skill does not do` section, and a hand-off to other skills where relevant.
2. New writing skills must embed the same inline drafting-constraints block used in the existing 10 writing skills. Zero em dashes. No "leverage," "delve," "tapestry," "stands as," "the real question is," or other patterns from the humanizer's vocabulary list.

The whole point of the repo is to model the standard. If the skills themselves read as AI slop, the user has no reason to trust them.
