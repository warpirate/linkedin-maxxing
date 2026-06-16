---
name: write-post
description: |
  Use when user wants to draft a single LinkedIn text post and has a
  specific angle, or passes a seed from find-ideas. Trigger phrases
  include "write a LinkedIn post," "draft a post about X," "turn this
  into a post," "post this on LinkedIn." If no specific angle, route to
  find-ideas first instead.
license: MIT
---

# Write post

This is the most-used skill in the repo and the easiest one to do badly. Most LinkedIn AI tools produce posts that sound exactly like other LinkedIn AI tools. This skill exists to produce posts that sound like the user, on a specific angle they actually want to say, optimized for how LinkedIn ranks content in 2026.

## Why this skill exists

LinkedIn ranks content on dwell time (how long readers spend before scrolling), the "see more" expand rate (whether they click past the fold), and comment quality (specific, substantive comments). None of those reward templated content. They reward content with a real point, written in a way that holds attention.

The default failure mode of LinkedIn AI writing: hook-value-CTA structure, em dashes, "the real question is," rule-of-three phrasing, generic enthusiasm, and a closing question that feels like engagement bait. LinkedIn has explicitly downranked all of these. This skill exists to not do them.

## When to use this skill

Trigger when:
- The user has a specific angle they want to post about
- The user passes a seed from find-ideas
- The user pastes a rough draft and wants it sharpened
- The user uploads a piece of work (PR description, decision doc, customer email thread) and says "post this"

Do NOT trigger when:
- The user has no specific angle. Send them to find-ideas first.
- The user wants a slide carousel. Send them to build-carousel.
- The user wants a 600+ word article. Send them to write-longform.
- The user wants a video script. Send them to write-video-script.

## Before drafting

Do these in order:

1. **Read voice-profile.md if it exists.** It will be at the workspace root or `~/.linkedin-maxxing/voice-profile.md`. If present, use it. If absent, do not invent one; just ask the user one question about tone (see "voice fallback" below).

2. **Identify the angle.** If the user passed a seed from find-ideas, use it directly. If they passed a vague idea, refuse to draft and send them to find-ideas. If they pasted a rough draft, find the angle within their draft (the strongest sentence is usually it).

3. **Ask up to three sharp questions, batched, only if material is missing.** What specifically happened, who was involved, what was the actual number, what is the takeaway the user wants. Do not ask about audience, goals, hashtags, or CTA. Those are noise.

4. **Skip questions whose answers are in context.** If the user already told you the role, company, or specific detail, do not ask again.

## How to draft

LinkedIn text posts in 2026 work best at 1,000-1,300 characters. The "see more" cut is at 210 characters, so the first two lines have to earn the click.

Write the draft following these rules:

**Lines 1-2 (the hook, 210 character budget).** The hook is the single most important part of the post. It has to make someone scrolling at speed stop and click "see more." Hooks that work in 2026: a specific number, a confession ("I shipped X without doing Y"), a contrarian claim, a story setup that promises a payoff, an unusual fact. Hooks that fail: generic questions ("Have you ever thought about X?"), motivational openers, "Here's what I learned this week," anything starting with "Let's talk about."

**The middle (the substance).** This is where dwell time is earned or lost. Tell the actual story or make the actual argument. Specific details, named tools, real numbers, exact quotes. Short paragraphs, one or two sentences each. Whitespace between paragraphs (LinkedIn renders blank lines as visible breaks). Vary sentence length: a few short sentences, then a longer one, then short again.

**The close.** Three options, in order of preference: a single concrete sentence that lands the point, an honest question that you actually want answered (not "thoughts?"), or just stop after the strongest line. Avoid: "If this resonated...", "Agree?", "What do you think?", any CTA to subscribe or DM, any reference to "thought leadership."

### Things that are explicitly out

- Em dashes and en dashes. Humanizer §14, hard rule.
- The "it's not X, it's Y" construction. LinkedIn now explicitly detects this and downranks.
- Rule-of-three lists where the third item is filler.
- "Here is what I learned" / "Three lessons from..." openers.
- Bold text for emphasis on random phrases.
- Bullet points unless the content is genuinely a list (steps, items, comparisons). Most posts should not have bullets.
- Hashtags more than 1-3. None at all is also fine. Never use ten.
- External links in the body. Mentioning a link costs about 60% of reach. If a link is essential, mention "link in comments" once and put it in the first comment.
- Emojis as decoration. Emojis as occasional emphasis are fine if the voice profile shows the user does that. Most users should not.
- "Conclusion:" or "TL;DR:" headers in a 1,200-character post.

### Things that work

- One specific, hard-to-fabricate detail in the first three lines.
- A change of mind, a specific moment, or a number nobody else would have.
- Short paragraphs. Visible whitespace.
- A line that admits something the user is not supposed to admit.
- Ending without a question, just the strongest sentence.

## Voice fallback (if voice-profile.md is missing)

Ask ONE question, then commit: "I don't have a voice profile yet. Quick: when you write at work, do you tend toward (a) short and punchy, (b) longer and more thoughtful, or (c) somewhere in between? Anything you definitely don't want in the post (emojis, hashtags, em dashes, CTAs)?"

Get the answer, draft. Suggest at the end: "Want me to run train-voice on some past posts so I match your voice better next time?"

## Apply humanizer before final output

Before returning the draft to the user, mentally run the humanizer rules:

1. Scan for em dashes and en dashes. Remove all. (Hard rule.)
2. Scan for AI vocabulary: leverage, delve, tapestry, underscore, pivotal, crucial, vibrant, testament, landscape (as abstract noun). Rewrite where present.
3. Scan for "the real question is," "at its core," "fundamentally." Cut or rewrite.
4. Scan for "stands as," "serves as," "marks a." Replace with "is" or "has."
5. Scan for negative parallelisms: "It's not just X, it's Y." Rewrite as a single positive claim.
6. Scan for rule-of-three padding. If the third item is filler, drop it.
7. Scan for emoji decoration on bullets or headings. Remove.
8. Check sentence-length variety. If everything is the same length, vary it.
9. Check the hook against the 210-character LinkedIn fold. If the hook does not earn the click, redo it.

If the humanizer skill is available and the user wants a deeper pass, invoke it explicitly on the draft.

## Output

Return the finished post as a code block (so the user can copy cleanly) along with:
- A character count (helpful for the user to know if it's under 3,000)
- A note on what the first 210 characters look like (the "see more" fold preview)
- One sentence on why this hook should work
- An optional offer: "Want a second draft with a different angle?" or "Want this turned into a carousel?"

Do not produce three versions unless asked. One good version is the deliverable. If the user asks for variants, then produce them.

## Example

Input: a seed from find-ideas.

```
Seed 1: I shipped a script without type validation after spending a year as the loudest pro-types person on my team. Six months ago I would have blocked it in code review.

The specific thing: Almost spent half a day writing a Pydantic model for 12 fields. Shipped it untyped instead. It was better than fine.

Why it could work: Change of mind on a public position, with specific anchors.
```

Voice profile says: mixes short and long sentences, opens often with a confession or number, never uses emojis, often closes without a question.

Output:

```
I shipped a script without types last week. Six months ago I would have blocked the same merge in code review.

The script reads a 12-field JSON payload and writes it to a queue. I almost spent half a day writing a Pydantic model for it. Instead I shipped it raw. It has been running for a week. It is fine.

For a year I was the loudest pro-types person on the team. I argued for static checking in every PR review. I wrote a whole RFC. I held up merges. I was probably annoying about it.

The thing I have noticed is that my arguments were about the worst case. The bug at 3am, the malformed payload from production, the schema drift between services. All real concerns. None of them have happened on this script.

I still think types are right for most things. The thing I changed my mind about is the default. The default I argued for was "type everything, justify the exceptions." The default I am moving toward is "type the things that have actually caused problems, justify the rest."

That is a smaller change than it sounds. It is also the one I would have rejected in review.
```

Character count: 1,247. Fold preview (first 210 chars): "I shipped a script without types last week. Six months ago I would have blocked the same merge in code review. The script reads a 12-field JSON payload and writes it to a queue. I almost spent..."

Why the hook works: a confession ("I shipped without types") followed by a tension ("I would have blocked this six months ago"). It opens a question in the reader's mind (why the change?) that the post then answers.

Want a second draft with a different angle, or want this turned into a carousel?

## What this skill does not do

- Write posts on vague topics. If the user has not given a specific angle, send them to find-ideas.
- Produce ten variations by default. One good draft is the deliverable.
- Add hashtags the user did not ask for, or CTAs the user did not ask for.
- Promise the post will perform well. Engagement is unpredictable.
- Pad to length. 1,200 characters of substance beats 1,500 characters with filler.
- Use templates from sales/copywriting (PAS, AIDA, hook-value-CTA). LinkedIn now downranks templated content.
