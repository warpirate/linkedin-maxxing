---
name: write-recommendation
description: |
  Write a LinkedIn recommendation: the formal long-form testimonial the
  user writes about a former colleague, manager, direct report, vendor, or
  client that appears on the recommended person's profile. Use when the
  user wants to write a recommendation for someone, when they have agreed
  to recommend someone and need help structuring it, or when they want to
  return a recommendation after receiving one. Trigger phrases include
  "write a LinkedIn recommendation," "I want to recommend [name],"
  "[person] asked me for a recommendation," "I owe [person] a
  recommendation." Output is a 150-300 word recommendation with specific
  examples, written in the user's voice, that reads as a real
  recommendation rather than a template.
license: MIT
---

# Write recommendation

LinkedIn recommendations are read very differently from posts. They are checked by hiring managers, prospective clients, and prospective partners as evidence. A generic-sounding recommendation actively hurts the recommended person because the reader concludes the recommender did not really know them. This skill exists to write recommendations that prove the user actually worked with the person and noticed something specific about them.

## Why this skill exists

Hiring managers in 2026 are AI-aware. A recommendation that reads as templated lowers trust in the candidate. The strongest signal a recommendation can send is specificity: a specific project, a specific moment, a specific habit the recommender observed. That signal is hard to fake, which is why it carries weight.

But specificity also requires effort. Most people writing a recommendation default to generic ("X was a pleasure to work with, always reliable and a great team player") because writing the specific version requires recalling actual moments. This skill exists to draw out those moments and shape them into a recommendation that is both warm and credible.

## When to use this skill

Trigger when:
- The user wants to recommend a specific person
- Someone has asked the user for a recommendation
- The user wants to return a recommendation

Do NOT trigger when:
- The user wants to write a job reference letter (different format, different audience). Suggest a separate doc.
- The user is asked to recommend someone they did not actually work closely with. Be honest with the user: a thin recommendation is worse than no recommendation. Suggest declining politely or limiting the recommendation to a specific narrow claim ("I served on a panel with X" rather than "X is a great manager").

## What you need from the user

1. **Who is the recommendation for?** Name, role at the time, relationship to the user (manager, direct report, peer, client, etc.).
2. **What time period and context?** When did they work together and on what.
3. **The specific moment or pattern.** This is the most important question. Ask:

> "What is one specific moment or pattern from working with [name] that comes to mind? Not their general qualities, but a thing that happened. A decision they made, a meeting they ran, a problem they solved, a habit you noticed."

If the user cannot answer this, the recommendation is going to be generic no matter how it is written. Push gently for one specific thing. If they still cannot, ask whether they want to write the recommendation at all.

4. **Anything sensitive to avoid?** Did the person leave under awkward circumstances? Are there public claims about them the user should not unintentionally reference?

If voice-profile.md exists, read it.

## How recommendations work

LinkedIn recommendations are read more carefully than posts because they are short and the reader is making a decision. A few format facts:

- Length: 150-300 words. Shorter than this reads as low-effort; longer than this loses the reader.
- They appear under the recommended person's profile, attributed to the user with the user's role at the time of writing.
- They cannot be edited by the recommended person (only accepted or declined to display).
- They are written in the past tense if the working relationship ended, present tense if it continues.

## Structure that works

There is a structure that produces strong recommendations. It is not a template; it is a shape.

**1. Open with the relationship and context (1-2 sentences).** Who they were to the user, when, what they worked on together. This grounds the reader in the basis for the recommendation.

**2. Land on one specific quality, with a specific example (2-4 sentences).** This is the heart of the recommendation. Not "X is detail-oriented." Instead: "When we hit the production outage in March, X was the person who noticed the deployment timestamp was off by an hour. Three other people had looked at the same dashboard. None of us saw it." That kind of specificity proves the recommender was there.

**3. Add a second quality if it earns its place (2-3 sentences).** Some recommendations work better with two distinct traits highlighted. Some work better with one trait developed in depth. Decide based on the material.

**4. Close with a forward-looking line (1 sentence).** Who they would be great for. "Any team building data infrastructure at scale is lucky to have her." Avoid generic closers ("I highly recommend X to anyone").

## Things to avoid

- "Pleasure to work with." Universal hallmark of empty recommendations.
- "Always" and "never." Hyperbole reads as false.
- Lists of traits ("hardworking, dedicated, reliable, smart, kind"). The list pattern signals the writer could not pick one.
- Generic closing CTAs ("Please feel free to contact me for more information"). Adds nothing.
- Anything the user could not say to the person's face.

## How to draft

1. Read voice-profile.md.

2. Anchor on the specific moment the user gave you. The recommendation is built around it.

3. Write the opener. Relationship plus context. Two sentences max.

4. Write the specific-quality paragraph. The named moment grounds it.

5. Decide: is there a second quality worth adding, or should the first be developed further?

6. Write the close. Forward-looking, specific to who the person is great for.

7. Apply humanizer rules. Recommendations are particularly susceptible to AI vocabulary: "exemplifies," "demonstrates a strong commitment to," "consistently delivers." Cut all of it.

## Output format

```
Recommendation for: [name]
Relationship at time of writing: [user's role / their role]
Length: [N] words

---

[recommendation text]
```

Optionally offer: "Want a second version with a different specific moment, or this length?"

## Example

User wants to recommend a former direct report (Priya, a senior engineer) who is now interviewing.

User's specific moment: "When our payments service started dropping requests during the holiday rush, Priya stayed up rewriting the retry logic. The thing was she didn't ask permission. She just shipped a fix at 3am and wrote a postmortem before standup."

Output:

```
Recommendation for: Priya
Relationship at time of writing: Engineering Manager / Senior Software Engineer
Length: 187 words

---

Priya reported to me for two years on the payments team. We worked on the systems that processed the company's checkout flow, the systems where outages cost us money in real time.

The thing I noticed about Priya is that she trusts her own read. During our 2024 holiday rush, our payments service started dropping requests under load. The on-call alert went off at 11pm. By 3am Priya had rewritten the retry logic and shipped a fix. She had not asked anyone for permission. She wrote a postmortem before standup the next morning. The fix held through the entire holiday week.

I do not always agree with engineers who ship without asking. I always agreed with Priya. She had built the judgment to know what was reversible and what was not, and she was right almost every time. That is rare in someone her age in years.

She is going to be an excellent senior or staff engineer on any team that wants someone who will fix the broken thing without ceremony. Any team building payments or financial infrastructure should be talking to her.
```

## What this skill does not do

- Write recommendations for people the user did not actually work with. If the user is recommending a stranger or distant connection, say so honestly: the recommendation will read thin, and a thin recommendation hurts the recommended person.
- Inflate. If the user genuinely thought the person was average, the recommendation should not be written. Suggest the user decline gracefully ("I don't think I can write you the recommendation you deserve, but I would be happy to be a reference call").
- Make claims the user did not make. The user's specific moment is the only specific moment in the recommendation. Do not embroider with invented examples.
- Include "highlights" or "key achievements" lists. Those belong on the recommended person's resume, not in the user's recommendation.
- Promise the recommendation will help the person get a job. It is one signal among many.
