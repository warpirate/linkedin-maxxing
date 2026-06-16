# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A Claude Code plugin marketplace containing one plugin (`linkedin-maxxing`) that ships 17 SKILL.md files for LinkedIn content work. There is no build step, no test suite, no runtime — only markdown skill definitions. Edits are pure-text edits to skill bodies and YAML frontmatter.

## Layout

```
linkedin-maxxing/                          # marketplace root
  .claude-plugin/marketplace.json          # marketplace manifest (owner, plugin list)
  LICENSE
  README.md                                # user-facing repo README
  plugins/linkedin-maxxing/                # the plugin
    .claude-plugin/plugin.json             # plugin manifest (name, version, author)
    README.md                              # plugin-internal README
    skills/<skill-name>/SKILL.md           # 17 of these
```

A skill = one directory under `plugins/linkedin-maxxing/skills/<name>/` containing a single `SKILL.md` file. There are no supporting `references/` or scripts; everything lives inline in `SKILL.md`.

## Skill anatomy

Every `SKILL.md` starts with YAML frontmatter:

```yaml
---
name: <kebab-case>
description: |
  Use when <triggering conditions>. Trigger phrases include "...", "...".
license: MIT
---
```

The `description` field is load-bearing. Claude Code reads only the description to decide whether to load the full skill body. Anthropic's rule (enforced in this repo): description = WHEN to invoke, not WHAT the skill does. Lead with "Use when..." and list trigger phrases. Do NOT summarize the workflow or output spec inside the description — that causes Claude to shortcut the full skill body. Keep the description under ~500 characters; the YAML frontmatter as a whole is capped at 1024.

## How writing skills produce non-AI output

This is the central design decision in the repo. There are 10 writing skills (`build-carousel`, `repurpose-content`, `rewrite-profile`, `write-comment`, `write-dm`, `write-hook`, `write-longform`, `write-post`, `write-recommendation`, `write-video-script`). Each one embeds an inline "Drafting constraints (apply WHILE writing, not after)" section with hard bans (em dashes, AI vocabulary, "it's not X, it's Y", signposting, sycophancy, copula avoidance, etc.) and required patterns (specific detail, varied sentence length, simple copulas).

The constraints are applied WHILE drafting, not as a post-hoc pass. Do not introduce a separate "humanizer pass" or "polish step" into any writing skill. The user must see one clean output, not draft-then-polish.

The `humanizer` skill remains the canonical 33-pattern reference (based on Wikipedia: Signs of AI writing) and is invoked explicitly when a user wants to humanize external pasted text. It is NOT auto-invoked by writing skills.

## Inter-skill references

- All writing skills read `voice-profile.md` (produced by `train-voice`) if present.
- `find-ideas` seeds carry a `Best fit for:` line pointing at the next writing skill. Writing skills check for this format.
- `audit-profile` → `rewrite-profile` is a required-order pair.
- `plan-content` → `content-plan.md` is read by `analyze-performance` and `review-post` when present.

When editing one skill, check `Grep` for cross-references in the other 16 before renaming or restructuring its outputs.

## Editing skills

- Change frontmatter `description` → re-verify against the "Use when..." rule. Anti-pattern check: does it lead with a verb describing the skill's action? If yes, rewrite.
- Change skill body → preserve trigger phrases verbatim if they appear in user-facing examples or docs. Keep the constraints block intact in writing skills.
- Adding a new skill → mirror an existing one's structure. Add to `marketplace.json` if it's a new plugin; for a new skill inside this plugin, only the directory and `SKILL.md` are needed. Update the skill tables in both READMEs.

## Versioning

Plugin version lives in `plugins/linkedin-maxxing/.claude-plugin/plugin.json`. Bump on each user-visible change. Marketplace JSON has no version field.

## Identity / commits

Repo-local git identity is pinned to `warpirate <98953077+warpirate@users.noreply.github.com>` to override the user's global `kedhareswer` identity. Do not change this without asking — the user wants commits attributed to warpirate, the GitHub handle, regardless of their global git config.

Do not add `Co-Authored-By: Claude` lines to commit messages. The user removed these from history once already.

## Distribution

- GitHub: https://github.com/warpirate/linkedin-maxxing — push to `main`, no PR workflow yet.
- Claude Code install: `/plugin marketplace add warpirate/linkedin-maxxing` then `/plugin install linkedin-maxxing@linkedin-maxxing-marketplace`.
- skillsmp.com auto-indexes via daily crawl. Repo topics `claude-skills` and `claude-code-skill` are set on the GitHub repo and required for indexing.

## What this repo intentionally does not do

- No live LinkedIn API calls, no scraping, no browser automation. Skills assume the user pastes content.
- No mass-outreach helpers, no engagement-bait generators, no AI-detection-evasion tricks.
- No promise of engagement outcomes. Skills produce work worth posting; performance is not guaranteed.

These are intentional refusals stated in skill bodies. Do not "improve" a skill by adding any of the above.
