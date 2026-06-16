---
name: write-dm
description: |
  Use when user wants to send a LinkedIn message to one specific person
  rather than post publicly: a connection request note, cold outreach,
  warm intro reply, follow-up after no response, or reply to someone who
  DM'd them. Trigger phrases include "write a LinkedIn DM," "write a
  connection request," "I need to message [person]," "follow up on the
  message I sent," "reply to this person."
license: MIT
---

# Write DM

Most LinkedIn DMs are either generic templates ("I'd love to connect and explore synergies") or so over-engineered with fake personalization that the recipient can smell the AI on first read. This skill exists to write DMs that sound like the user, are short enough to actually be read, and ask for something specific instead of dancing around it.

## Why this skill exists

LinkedIn DM volume has exploded with AI-assisted outreach tools, and recipients are now numb to the standard patterns. The "I noticed you went to [school] and I also love [random shared interest], let's hop on a quick call" template is dead. Response rates on templated cold DMs have collapsed.

What still works: short, specific, honest messages from one person to another. This skill exists to write those, not to scale outreach.

## When to use this skill

Trigger when:
- The user wants to send a connection request with a note
- The user wants to send a cold outreach DM to one specific person
- The user wants to follow up on a message that went unanswered
- The user wants to reply to a DM they received
- The user wants to thank someone after a meeting or call

Do NOT trigger when:
- The user wants to write a public post. Send to write-post.
- The user wants to scale outreach (sending 100 similar DMs). Refuse politely. Mass templated outreach is what killed DM response rates; this skill writes one good message at a time.
- The user wants to write a comment. Send to write-comment.

## What you need from the user

1. **Who is the recipient?** Name, role, company, and any context the user has (how they know each other, what the recipient has posted recently, mutual connections, prior interactions).
2. **What is the user trying to get?** A response. A meeting. A specific piece of advice. A job referral. Be honest with yourself; the message will be honest with the recipient.
3. **What kind of message is this?** Connection request (300-char limit, see below), cold DM, warm reply, follow-up.

If voice-profile.md exists, read it. DMs should match the user's voice but in a slightly more direct register than posts.

## How LinkedIn DMs work in 2026

A few format-specific things:

**Connection requests.** Limited to 300 characters. Most platforms cap personalized note slots, and even when present they should be used. A request with a real note has roughly 3-5x the acceptance rate of one without.

**Standard DMs.** No character limit, but anything over ~200 words is unlikely to be read in full. Aim for 50-150 words.

**Voice and video DMs.** Possible but rare. Skip unless the user specifically asks.

**InMail (Premium feature).** Same rules as a regular DM, slightly more polished register because InMail signals the sender paid for it.

## Principles for any DM

**Be specific in the first sentence.** Not "I came across your profile and was impressed by your background." Specific means: a thing the recipient has done, a post they wrote, a project they shipped. Not generic praise.

**Get to the ask quickly.** A short DM that asks honestly performs better than a long DM that buries the ask. The recipient can decide quickly whether to engage.

**No fake intimacy.** "Hope you are doing well in these trying times" reads as a template even when sincere. Just start with the substance.

**No "quick call" without a reason.** If you ask for a 15-minute call, name what the call is for. "Could I ask you about how you approach X" gives the recipient something concrete to say yes or no to.

**Match the recipient's register.** Look at the recipient's posts. If they write casually, write casually. If they write formally, write formally. If they post in another language, ask the user if they want the DM in that language.

**One ask per message.** Asking for an intro AND advice AND a meeting in one DM signals desperation. Pick one. The others can come if the first lands.

## How to draft

1. Read voice-profile.md.

2. Identify the most specific true thing the user knows about the recipient. (A recent post, a project, a shared connection, a moment from a conference.) This is the opener.

3. State the ask honestly. What is the user actually asking for? A call, a referral, a reply, a piece of advice, an introduction. Say it directly.

4. End with the simplest next step. "Open to a 20-minute call next week?" "Happy to send a one-pager if you want to skim before deciding." Anything that makes the response one tap or one line.

5. Apply humanizer rules. No em dashes. No "the real question is." No "I hope this finds you well." No "quick favor."

## Output format

For connection requests:
```
[message text]

Character count: [N] / 300
```

For standard DMs:
```
[message text]

Word count: [N]
Notes: [what kind of response this is designed to invite. Options: a yes/no, a meeting confirmation, a longer reply]
```

## Examples

**Connection request example.**

User wants to connect with a CTO they admire after the CTO published an article they read.

Output:
```
I read your piece on engineering metrics last week. The point about velocity becoming useless past 20 people matched what we hit at our last company. Would value being connected.

Character count: 219 / 300
```

What this avoids: generic praise, mutual interests fishing, "let's explore synergies."

**Cold DM example.**

User is a junior PM wanting to ask a senior PM (a stranger) for advice on transitioning into B2B SaaS.

Output:
```
I'm a consumer PM trying to make the move to B2B SaaS and your post about the metrics tradeoff in early-stage B2B was the most useful thing I've read on the transition. Quick question: when you were making the move, what was the one thing you wish you had done before joining your first B2B company? Happy if the answer is "nothing." Either way, thanks for the post.

Word count: 67
Notes: This is designed to invite a 1-3 sentence reply, not a meeting. Asking for too much from a stranger lowers response rate. If they reply, the user can ask for more later.
```

**Follow-up example.**

User sent a cold DM two weeks ago and got no response.

Output:
```
Following up on this in case it got lost. No worries if not the right ask or right time.

Word count: 19
Notes: Short, no guilt, gives the recipient a graceful out. If this also gets no response, do not follow up again; they are not interested.
```

**Reply to received DM.**

A founder DMs the user (a developer) asking about contract work.

Output (assuming the user is open to the conversation):
```
Thanks for the note. Briefly: yes, I'm open to contract conversations for the right thing. What are you trying to build, and what is the timeline? If it makes sense to talk, I'm free Tuesday or Thursday afternoon.

Word count: 41
Notes: Direct yes, two qualifying questions, one concrete next step. Avoids overcommitting and avoids dragging out the back-and-forth.
```

## What this skill does not do

- Generate a batch of DMs to different recipients with mail-merge personalization. That is what killed DM response rates. If the user asks, refuse and explain.
- Invent things about the recipient. If the user does not actually know something specific about the recipient, the DM should be honest about that ("I don't know you, but I read X and...") rather than fake familiarity.
- Use "I'd love to connect" / "exploring synergies" / "circling back" / "touching base" / any sales-template language.
- Promise the DM will get a response. Response rates depend on the recipient, timing, and luck. The skill writes a DM worth sending; whether it lands is not in the skill's control.
- Write DMs the user could not defend to the recipient if the recipient screenshotted it. If the message would be embarrassing to be quoted on, rewrite it.
