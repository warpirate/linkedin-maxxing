# linkedin-maxxing (plugin)

Substance-first LinkedIn skills for Claude. 17 skills covering profile work, idea mining, content drafting across formats, engagement, and performance review. A built-in humanizer pass strips AI writing tells from every drafted piece.

## Skills included

**Foundation:** `train-voice`, `audit-profile`, `rewrite-profile`, `plan-content`

**Production:** `find-ideas`, `write-hook`, `write-post`, `build-carousel`, `write-longform`, `write-video-script`, `repurpose-content`

**Engagement:** `write-comment`, `write-dm`, `write-recommendation`

**Learning loop:** `analyze-performance`, `review-post`

**Quality:** `humanizer` (based on Wikipedia's Signs of AI writing, used by every writing skill)

## How the skills hand off to each other

The skills are designed to be composable. A typical flow:

```
train-voice → voice-profile.md (read by all writing skills)

find-ideas → 2-5 seeds, each pointing at the next skill
   ↓
   ├→ write-post
   ├→ build-carousel
   ├→ write-longform
   └→ write-video-script

[any writing skill] → applies humanizer rules at the end

[after 4+ weeks of posting]
analyze-performance → identifies patterns
review-post → diagnoses individual posts
```

Each skill names its expected hand-off in its `Best fit for:` output line, but the recommendation is advisory. The user can pick any next step.

## Operating principles (shared across all skills)

1. **Substance over templates.** No hook formulas, no PAS/AIDA/HVC. LinkedIn now downranks templated content.
2. **Specifics over abstractions.** A real number beats a generic claim. A specific moment beats a "lesson learned."
3. **One ask, batched questions.** Skills ask sharply, batch multiple questions into one turn, and commit to an output. No interrogation.
4. **Honest about what we cannot conclude.** Performance data is noisy. Skills name uncertainty rather than fabricate confidence.
5. **Refuse to produce slop.** If the user has no specific material, skills tell them so and offer to help collect material instead of inventing it.

## See the repo README for installation, philosophy, and full skill descriptions.
