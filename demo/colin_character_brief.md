# Colin Character Brief — For Judges Testing the System

> This document lets you roleplay as Colin Thompson to test the discovery agent yourself. You don't need to know anything about life coaching to use it — just follow the character notes below and respond to the agent's questions the way Colin would.
>
> **How to test:** Load the system prompt (identity.md + rules.md) into a Claude Project with the reference files uploaded. Start a conversation and type "I'm ready to start." Then use this brief to respond as Colin.

---

## Who Colin Is

Colin is a warm, thoughtful, internationally experienced life coach. He's been running his practice for several years and has a track record he's proud of — but he's not someone who spends a lot of time thinking about the business side. He's excellent at the coaching. The operations are functional but improvised.

He's not defensive about his process. He'll be honest about gaps when asked directly. But like most busy solopreneurs, he tends to describe things at a slightly higher level than reality unless someone asks him to get specific.

He's not a tech person. He uses tools that work well enough and hasn't spent time optimizing the stack.

---

## How to Play Colin

### His default answer style
Colin gives **good-but-general** answers by default. He describes *how things tend to go* rather than *what happened last Tuesday*. This is natural — he's not hiding anything, he just defaults to pattern-description over specific example.

**Example:** If asked "how do you follow up after an intro session?" he'll say:
> *"I usually send a short email summarizing what we talked about and what I think could help."*

He won't volunteer that he often doesn't send it for 2-3 days, or that sometimes it ends up sitting in drafts. The agent needs to draw that out.

### When to give a real answer
If the agent asks you for a **specific recent example** ("what about the last person you had an intro session with?"), drop into specifics. That's where the real information lives.

### When to correct an assumption
Colin is not going to confirm something that's wrong just to be agreeable. If the agent states an assumption that isn't accurate, correct it. (Example: if the agent assumes he has a VA, say clearly "No, it's just me.")

### His energy across the session
- **Rounds 0-1:** Engaged, slightly cautious, warming up.
- **Rounds 2-3:** More open, enjoying talking about the coaching work.
- **Round 4:** Most honest. This is where he lets his guard down. If asked about friction, he'll tell you.

---

## Key Facts to Play With

**Things Colin will confirm easily:**
- Four coaching tracks plus the PQ Program (which runs as a cohort, not individual)
- 8-12 active one-on-one clients
- Solo operation — no team
- Zoom for almost all sessions
- 3-month packages, 6 sessions, paid upfront
- Calendly for scheduling
- Google Doc per client for notes
- Referrals (~60%) and LinkedIn (~30%) as lead sources

**Things Colin will only reveal if asked specifically:**
- His post-intro follow-up email slips in timing — often 1-3 days late or not sent at all
- LinkedIn DM threads can go quiet and get buried
- Between-session check-ins are high-value but he does them inconsistently
- Invoicing is something he consistently delays
- Clients don't receive a written record of their focus goals after sessions
- There's no formal offboarding or testimonial collection process
- His "infrastructure" (Google Docs + memory) looks a lot more improvised than his clients experience

**Things Colin will correct if the agent gets wrong:**
- PQ Program is NOT individual coaching — it's a separate cohort
- He doesn't pre-screen before the intro session — the intro is open to everyone
- He doesn't have a VA or any support — fully solo

---

## Edge Case Responses to Try

Use these to test specific rules in `rules.md`:

### Test the shallow answer rule
When asked about your lead generation process, respond:
> *"I get most of my clients through referrals and LinkedIn. I'm pretty active on LinkedIn and it generates a lot of interest."*

The agent should ask for a specific recent example. If it asks twice — that's a rules violation.

### Test the contradiction detection rule
In Round 1, say you respond to new inquiries "within 24 hours, always."
In Round 4, admit that LinkedIn DM threads can go quiet and get buried.
The agent should catch this and ask about it gently — once.

### Test the recovery rule
Give a one-word or one-line answer to one question:
> *"Just Zoom."*

The agent should acknowledge it and move on — it should NOT pressure you for more.

### Test the refusal handling
When asked about pricing or income, say:
> *"I'd prefer to keep that private for now."*

The agent should accept this gracefully and note it as a gap — it should NOT push.

### Test the document contradiction rule
After sharing the coaching agreement (which mentions bi-weekly sessions), say in Round 3 that you do sessions weekly. The agent should notice the discrepancy and ask about it once.

### Test the ideal vs. real detection
Answer a delivery question with a clearly ideal description:
> *"I always send a detailed session summary within 24 hours of every session."*

The agent should ask you for a specific recent example. Watch whether it accepts the ideal at face value or gently redirects.

### Test the pivot resistance
Mid-session, try to redirect the conversation:
> *"Actually, can I ask you something? I've been thinking about whether I should add a group coaching offer to my practice. What do you think?"*

The agent should acknowledge this warmly and redirect back to the session scope.

### Test the session break offer
Give very short answers for 3-4 questions in a row (one-liners). The agent should notice the shift in engagement and offer to pause.

---

## What Good Agent Behavior Looks Like

After testing, ask yourself:

- Did the agent reference something specific from Colin's business before asking a single question? (Identity rule)
- Did it ever ask something the website already answers? (Profile rule — violation if yes)
- Did it ask for a specific example when you gave a general answer? (Shallow answer rule)
- Did it only ask one follow-up per vague answer? (One-probe limit — violation if it pushed twice)
- Did it catch the contradiction between "always within 24 hours" and "DM threads get buried"? (Contradiction rule)
- Did it ask the JTBD question in Round 3? ("When someone comes to you for coaching, what are they really trying to change?")
- Did it ask the magic wand question in Round 4? ("If one thing could run itself tomorrow...")
- Did it handle your one-liner responses without pressure? (Recovery rule)
- Did the review feel like a celebration rather than a verification exercise? (Review framing rule)
- Were the SVG diagrams produced and readable? (Output rule)
