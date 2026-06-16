---
name: write-longform
description: |
  Use when user has an idea that genuinely needs 600+ words, wants to
  build a LinkedIn newsletter cadence, or wants a piece that lives
  permanently on their profile rather than in the feed. Trigger phrases
  include "write a LinkedIn article," "write a newsletter," "this needs
  to be long-form," "I have a lot to say about this," or when a
  find-ideas seed is marked "Best fit for: write-longform."
license: MIT
---

# Write longform

LinkedIn long-form content is genuinely different from a 1,300-character feed post. The pacing is different, the rhythm is different, the relationship with the reader is different. This skill exists to write articles and newsletters that hold a reader's attention for 600 to 2,000 words, in the user's voice, without the slop patterns that work poorly even in long form.

## Why this skill exists

LinkedIn is investing heavily in long-form content. Newsletters in particular get their own distribution mechanism: subscribers receive push notifications and email when a new issue is published, which sidesteps the main feed's ranking algorithm entirely. Articles get separate distribution from posts, persist on the user's profile, and tend to be the format that hiring managers and prospects actually read when checking someone out.

But long-form is harder than short-form. A weak feed post is forgettable. A weak article is embarrassing because the reader committed real time to it. This skill exists to make sure the time investment pays off for the reader.

## When to use this skill

Trigger when:
- The seed from find-ideas is marked write-longform
- The user has a topic with multiple sub-points that need real development
- The user is building a newsletter cadence
- The user wants something for their profile that says "I have thought about this seriously"
- The user has a body of work (multiple posts, internal docs, talks) they want to consolidate

Do NOT trigger when:
- The content is a single point. Send to write-post.
- The content has visual or sequential structure. Send to build-carousel.
- The content is a quick reaction or update. Long-form is the wrong format for hot takes.

## What you need from the user

1. The angle and the position the piece will argue.
2. The underlying material (notes, related posts, an outline, a transcript, a doc).
3. Article or newsletter? Newsletter has subscribers and recurring framing; article is one-off.
4. Target length. Default: 800-1,200 words for articles, 600-800 for newsletter issues. Adjust on user request.

If voice-profile.md exists, read it.

## How long-form works in 2026

A LinkedIn article or newsletter that works has four traits:

**1. A real claim, not a survey.** The piece argues something. "Five trends in B2B SaaS" is not a piece; it is a list of trends. "B2B SaaS is undervaluing customer success because it confuses retention with renewal" is a piece. The claim should be specific enough that someone could disagree with it.

**2. Earns the time investment.** Every paragraph should be earning the reader's next paragraph. If a paragraph could be cut without losing the argument, cut it. Length is not a virtue.

**3. Specific, anchored evidence.** Numbers, examples, named cases, quotes. Long-form fails when it tries to substitute eloquence for evidence. The reader committed time; they want to come away with something concrete.

**4. A point of view, not a survey of points of view.** "On one hand X, on the other hand Y, the truth is probably somewhere in between" is the worst possible long-form pattern. Take a side. Acknowledge the opposing view in one paragraph and then defend yours.

## Structure

Long-form benefits from sub-headers more than feed posts do. The reader can navigate. The piece feels less like a wall of text. Use 3-5 sub-headers for an 800-word piece, 5-8 for a 1,500-word piece.

A common structure that works (do not treat as a template; the piece should serve the argument):

1. **Open with the claim and the moment that produced it.** First paragraph names the argument. Second paragraph anchors it to a specific moment, story, or piece of evidence. If you do not anchor by paragraph two, the reader leaves.

2. **The opposing view, fairly.** One paragraph. State the strongest version of the position you are arguing against. This is what separates a real piece from a strawman piece.

3. **Why you think the opposing view is wrong.** This is the heart of the article. Make the actual argument. Use specific evidence. Name the names you can name, cite the numbers you have.

4. **Where you might be wrong.** One paragraph acknowledging the limits of your claim. This is what separates a confident piece from an arrogant piece.

5. **What follows from the claim.** What should the reader do, think, or stop doing? Concrete, not "consider the implications."

6. **Close.** A single paragraph that lands the argument. No CTA, or a CTA that is genuinely useful (subscribe to the newsletter, read a related piece, share their counterexample).

## Newsletter-specific notes

Newsletters have subscribers who chose to receive them. This changes the writing in three ways:

1. **You can assume context.** Subscribers have read previous issues. You can reference them. "Last issue I argued X. Today I want to take that further."
2. **You can be more conversational.** The reader opted in; they are not a stranger.
3. **You have a name and a cadence to honor.** Each issue should fit the newsletter's premise. If the newsletter is "Notes from an early-stage PM," every issue should fit that frame.

For a first newsletter issue, set the premise. What is the newsletter about, how often does it publish, what kind of pieces should the reader expect.

## How to draft

1. Read voice-profile.md.
2. Identify the claim. If the user did not state it clearly, ask: "What is the one sentence you would defend if pushed? That's the article."
3. Build a 3-5 sub-header outline before writing prose. Send it to the user if helpful; otherwise just use it.
4. Write the piece. Aim for the target length, but the argument's needs outrank the length target. A tight 700-word piece beats a padded 1,200-word piece.
5. Apply humanizer rules across the full piece. No em dashes. No AI vocabulary. No "the real question is." No rule-of-three padding. Vary sentence length. Vary paragraph length.
6. Read it aloud (mentally). If a sentence stumbles, rewrite it.

## Output format

Return the article as markdown, with:
- A title (specific, not generic)
- Sub-headers
- Prose
- A closing paragraph
- For newsletters: an issue number or date stamp if relevant
- Word count
- A two-line note on the structure choices (what claim it argues, what opposing view it engages)

## Example

Angle: B2B SaaS undervalues customer success because the team measures renewal, not retention. The two are different.

User confirms: "Make this an article, ~1,000 words."

Output (truncated):

```markdown
# B2B SaaS is measuring the wrong thing about customer success

The team I joined last year had a 94% renewal rate and a customer success function in serious trouble. Renewal rates were green. Customer feedback was red. Two of our largest accounts were planning to leave at the next renewal window and had told their account managers. The board did not know.

This is the gap I want to write about. Renewal is what shows up on the dashboard. Retention is what the customer is actually doing. They look the same on a one-year contract. They diverge sharply on a three-year one. Almost every CS team I have worked with measures the first and assumes it tells them about the second.

## The argument I want to engage with first

The strongest case for measuring renewal is that it is the only metric that matters at the contract boundary. A customer who renews paid the bill. A customer who stays engaged but does not renew is a story about engagement, not revenue. From a finance standpoint, renewal is the truth.

This argument is correct as far as it goes. The problem is that it assumes renewal is the leading indicator. It is not. By the time renewal happens, the decision was made months ago, often a year ago. Measuring renewal is measuring an outcome you cannot influence.

## What retention actually looks like

[continues for ~600 more words, with named examples and specific numbers]

## Where I might be wrong

The case against retention metrics is that they are noisy. A customer's product usage can drop because their team is reorganizing, not because they are leaving. A churned account can look healthy on retention metrics right up until the cancellation email. This is real. But the answer is not to give up on retention; it is to instrument it better.

## What follows from this

If you run a CS team, you probably already track usage. The question is whether usage is a top-line metric or a debugging tool. Make it top-line. Put it next to renewal in your weekly review. Investigate the accounts where the two metrics diverge.

The accounts where they diverge are the accounts that will surprise you in 18 months. That is what I wish I had known a year ago.
```

(~1,050 words total. Article argues a specific claim, engages the opposing view in section two, anchors with the 94%/board story, closes with an actionable implication.)

## What this skill does not do

- Pad to length. The argument decides the length, not the target.
- Survey the field without taking a side. Long-form without a position reads as a research paper for an audience that wanted an article.
- Use formal academic voice when the user writes informally, or vice versa. The voice profile decides.
- Write "ultimate guides" or listicles. Send to build-carousel for list-shaped content.
- Promise SEO results, traffic, or specific reach numbers. Long-form on LinkedIn has different distribution mechanics from blog SEO, and outcomes vary widely.
