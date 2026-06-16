---
name: build-carousel
description: |
  Produce a LinkedIn carousel SPEC (slide-by-slide copy + visual brief +
  image-gen prompts) that the user assembles into a multi-slide PDF in
  Canva, Figma, or similar. This skill does NOT export a finished PDF.
  Carousels are the highest-performing format on LinkedIn in 2026 (often
  5-10x the engagement of equivalent text posts). Use when the user has
  an idea with multiple discrete steps, a framework, a comparison, a
  before/after, a list of items worth a slide each, or anything where
  swiping is part of the experience. Trigger phrases include "make a
  carousel," "build a slide deck for LinkedIn," "turn this into a
  carousel," "I have a framework to share," or when a seed from
  find-ideas is marked "Best fit for: build-carousel." Output is a slide
  plan (cover + 6-12 content slides + outro) with copy for each slide,
  written in the user's voice, plus visual direction notes for each
  slide and a final image-generation prompt or visual brief.
license: MIT
---

# Build carousel

Carousels are currently the strongest format on LinkedIn. They reward more design effort, hold more dwell time per swipe, and pass more algorithmic signal per post than text or video. This skill exists to plan and write a carousel from an idea, not to design it (the user or their designer does that), but to produce slide-level copy and a clear visual brief that a designer can execute.

## Why this skill exists

LinkedIn document carousels (uploaded as PDFs) currently outperform equivalent text posts by 5-10x on engagement, and educational carousels with 8-12 slides perform best. Each swipe counts as an engagement signal. The format works because it requires more effort to create (a quality signal), keeps the reader on LinkedIn (the platform rewards this), and the swipe behavior holds attention longer than scrolling past text.

But carousels can also fail badly. Slides full of stock photos and motivational quotes have the lowest engagement of any LinkedIn format. The difference between a carousel that works and one that does not is whether each slide does its own job. This skill exists to make sure each slide earns its place.

## When to use this skill

Trigger when:
- The user passes a seed from find-ideas marked for carousel
- The user has a framework, a how-to, a comparison, a before/after, or a list of 5+ items
- The user has a piece of work (an internal doc, a process, a decision tree) that has natural sequential structure
- The user has tried text posts on a topic and wants to try the same topic as a carousel

Do NOT trigger when:
- The content is a single point. Send to write-post.
- The content is a long argument that needs prose, not slides. Send to write-longform.
- The content is best told on camera. Send to write-video-script.

## What you need from the user

The angle (one sentence), plus the underlying material (the framework, the steps, the items, the comparison data). If they have only the angle, ask:

"What are the 5-12 concrete points that make up this carousel? Or do you want me to help you list them?"

If voice-profile.md exists, read it for the copy. Also note: do they prefer minimal design or more visual? (If they have not said, default to minimal text-forward.)

## How a carousel is structured

A good carousel has three parts:

**1. The cover slide.** One job: make people swipe. The cover is the carousel's hook. It should have:
- A title that is the carousel's promise (specific, not generic)
- A subtitle or visual cue that signals there is more to see
- Optional: a slide count or progress indicator ("1 of 9")

Bad covers: "5 Lessons I Learned" / "Tips for Better Productivity" / motivational quotes attributed to "anonymous"

Good covers: "What we changed after a $40K mistake" / "The 7-question script we use before every customer call" / "Why our onboarding emails get 90% open rates (and your subject lines won't work for you)"

**2. Content slides (6-12).** Each slide does one job and stands alone if removed from context. The reader who only swipes through quickly should still get value.

Each content slide should have:
- A header (the slide's one point, written as a complete claim, not a label)
- Body text (30-80 words, conversational)
- A visual cue (a diagram, a number, an icon, a screenshot) when applicable

Common slide patterns:
- Step in a process
- Item in a list, with explanation
- Before/after comparison
- Question + answer
- Misconception + correction
- Definition + example

Bad slides: pure text with a bold header. Slides full of bullet points. Slides that just repeat the cover. Slides with a single quote and nothing else.

**3. Closing slide.** Two options:
- A single takeaway sentence that lands the whole carousel
- A call to action that is not a sales pitch (a question for the reader, an invitation to share their version, a link to a longer resource the user actually has)

The closing is also the place to credit collaborators or link to the source material. Keep it light.

## How to draft

1. Read voice-profile.md if it exists.

2. Build the slide list first, before writing copy. Each slide gets a one-line description: what is this slide's job. Get this right before writing any prose. If you cannot name what each slide's job is, the carousel has too many slides or too few.

3. Write the cover. Spend the most effort here. The cover decides whether anyone sees the rest.

4. Write the content slides. Each slide: header (one claim), body (one short paragraph), visual note.

5. Write the closer.

6. Apply humanizer rules to all copy: no em dashes, no AI vocabulary, no rule-of-three padding, no "the real question is." Be specific. Vary sentence length within each slide.

7. Write visual direction notes for the designer or AI image tool.

## Output format

```
# [Carousel title]

## Slide 1: Cover

Header: [the cover title]
Subtitle: [optional]
Visual direction: [what should be on the cover visually]

## Slide 2: [one-line description of this slide's job]

Header: [the claim]
Body:
[the prose]
Visual direction: [diagram, number, icon, screenshot, etc.]

## Slide 3: ...

[continue for each slide]

## Slide N: Closing

[takeaway or CTA]
Visual direction: [usually the user's name and any handle/link]

---

## Image generation prompts (if user wants AI-generated visuals)

For Slide 1 cover: "[prompt]"
For Slide N visual: "[prompt]"

## Notes for design

[Any overall design notes: color palette, font preferences, density target. If voice-profile.md indicates the user is minimal/dense/etc., note it here.]
```

## Example

Seed from find-ideas:
> Angle: I changed my mind on type validation after spending a year arguing for it. The catalyst was shipping a script without Pydantic and it being fine.

User confirms: "Make this a carousel."

Slide plan (before writing copy):
1. Cover: hook the reader on the contradiction
2. The position I held: types everywhere
3. The thing that happened: 12-field script, no Pydantic
4. What I expected to happen: production fire
5. What actually happened: nothing
6. What I noticed about my old arguments: most bugs I cited never happened
7. The new default: type what has caused problems, justify the rest
8. The trade-off I am accepting
9. Closer: the reader's turn

Now the copy:

```
## Slide 1: Cover
Header: I spent a year arguing for type validation. Then I shipped a script without it.
Subtitle: What I changed my mind about.
Visual direction: A code block snippet showing a Pydantic class crossed out with a line through it. Minimal, monochrome, terminal aesthetic.

## Slide 2: The position I held
Header: I argued for static typing on every endpoint.
Body:
For a year, I was the loudest voice for type validation on our team. I wrote the RFC. I held up merges. I left a hundred review comments with the same suggestion: type this.
Visual direction: A faded screenshot of a code review with "needs proper validation" highlighted.

## Slide 3: The thing that happened
Header: Last week I shipped a script without a single type annotation.
Body:
A 12-field JSON payload. A queue write. I almost spent half a day writing a Pydantic model. I didn't. I shipped it raw.
Visual direction: A small terminal screenshot or a single line of code.

## Slide 4: What I expected
Header: I expected a production fire by Wednesday.
Body:
The arguments I had been making for a year all predicted what would go wrong. Malformed payloads. Schema drift. The 3am page.
Visual direction: A blank PagerDuty notification or generic alert icon.

## Slide 5: What actually happened
Header: Nothing.
Body:
The script has been running for a week. No errors. No pages. No drift. The thing I was worried about did not happen.
Visual direction: A flat green status indicator or "0 incidents" tile.

## Slide 6: What I noticed
Header: Most of the bugs I cited had never actually happened.
Body:
The malformed payload was hypothetical. The schema drift was theoretical. I was arguing the worst case as if it were the common case. It wasn't.
Visual direction: A simple before/after diagram showing "what I argued" vs "what happens in practice."

## Slide 7: The new default
Header: Type the things that have actually caused problems. Justify the rest.
Body:
Smaller change than it sounds. I would have rejected this default in a review six months ago. But it matches the actual evidence, not my anxieties.
Visual direction: A decision tree or simple flowchart in monochrome.

## Slide 8: What I am accepting
Header: I am giving up some defensibility. I am gaining a lot of time.
Body:
This will sometimes bite me. When it does, I will add the validation. That is okay. The cost of being wrong about a specific script is lower than the cost of slowing every script down for hypotheticals.
Visual direction: A simple scale or two-pan balance illustration.

## Slide 9: Closing
Body:
Curious whether anyone else has had this shift. What is something you argued for and then walked back?
Visual direction: User's name, role, and LinkedIn handle. Optional: link to a related write-up if they have one.

---

## Image generation prompts (if requested)
Slide 1 cover: "A terminal screen showing Python code with a Pydantic class struck through, monochrome, minimal, 1080x1080 square."
Slide 6 diagram: "A simple before/after diagram in flat design, two columns labeled 'what I argued' and 'what happened,' no color, no clutter."

## Notes for design
Voice profile suggests minimal aesthetic. Stick to monochrome. Avoid stock photos. Each slide should have one focal element. Font: Inter or similar clean sans-serif. Slide count: 9 (within the optimal 8-12 range).
```

## What this skill does not do

- Design the actual slides. The user or their designer does that. This skill produces the plan, the copy, and the visual brief.
- Pad to 12 slides if the content only supports 7. Better a tight 7-slide carousel than a bloated 12-slide one.
- Use generic visual placeholders ("stock photo of business meeting"). Either the visual is specific to the content or there is no visual.
- Bury a sales pitch in slide 9. If the user wants a sales carousel, redirect to a different format; sales carousels do not perform on the main feed.
- Generate carousels from no input. If the user has only the angle and no underlying material, send them back to find-ideas.
