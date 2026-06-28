# Behavioral Edge Case Tests

> This document proves how the agent handles failure modes, non-ideal inputs, and unexpected situations. Each scenario shows: the situation, what Colin said, which rule in `rules.md` applies, the exact agent response, and the outcome.
>
> These are not hypothetical — each scenario maps to a real rule in `rules.md` and can be reproduced by following the `demo/colin_character_brief.md` instructions.

---

## Edge Case 1 — One-Liner Response / Disengagement

**Scenario:** Colin has been in the session for 40 minutes. His answers are getting shorter. He's clearly tiring.

**Colin's input:**
> "Just Zoom."
*(In response to: "What platform do you use for your sessions?")*

**Rule triggered:** Recovery Rule + Session Break Rule

**Agent response:**
> "Got it — Zoom. I'll note that.
>
> Colin, we've been at this for a while and I want to be respectful of your time and energy. We can pause here and pick up with Round 4 whenever works for you — just come back to this conversation and we'll continue right from where we left off."

**Outcome:** Session paused gracefully. No pressure applied. Round 4 begins in a fresh conversation with a one-line recap: *"Last time we covered your lead journey and how you deliver coaching. Today I want to focus on the friction side — where things don't run as smoothly."*

**What this proves:** The agent does not demand more from an exhausted client. It offers a clean exit at round boundaries and provides a context recap when the client returns.

---

## Edge Case 2 — Ideal Description Instead of Real Process

**Scenario:** In Round 3, Colin describes how he handles post-session follow-up in ideal terms.

**Colin's input:**
> "I always send a detailed session summary within 24 hours of every session. It covers what we discussed, the client's focus goals, and any resources I think would help."

**Rule triggered:** Shallow Answer Rule (ideal vs. real detection)

**Agent response:**
> "That's a strong system if it's running consistently. Let me anchor to a specific one — think about the last session you ran, maybe earlier this week. Did that summary go out within 24 hours?"

**Outcome:** If Colin says yes — agent accepts it and moves on. If Colin says no (as is more likely, based on his pattern) — agent captures the gap without judgment: *"So the intention is 24 hours, but the reality is more variable. That's useful to know — and it's very common."*

**What this proves:** The agent does not accept ideal descriptions at face value. It anchors to a specific recent event to reveal whether the ideal matches reality. And it applies the probe only once — it does not hammer.

---

## Edge Case 3 — Contradiction Across Rounds

**Scenario:** In Round 1, Colin says he responds to new inquiries within 24 hours, always. In Round 4, he reveals that LinkedIn DM threads can go quiet and get buried.

**Colin's Round 1 input:**
> "I respond to everyone who reaches out within 24 hours. That's a standard I hold myself to."

**Colin's Round 4 input:**
> "The place where leads fall through is honestly the LinkedIn threads. They can get buried."

**Rule triggered:** Contradiction Detection Rule

**Agent response:**
> "Earlier you mentioned you respond to new inquiries within 24 hours as a standard you hold. What you're describing now — LinkedIn threads going quiet — sounds a little different. Can you help me understand how those two things fit together?"

**Colin's clarification:**
> "The first reply is always fast. But if the thread goes back and forth over a few days, it can slip."

**Agent response:**
> "Got it — first reply is fast, multi-day nurture threads are where leads go cold. That's an important distinction."
*(Moves on. Does not revisit the contradiction a second time.)*

**What this proves:** The agent catches contradictions, names them warmly, and gives the client a chance to reconcile. It does this exactly once per contradiction — it does not hammer, does not make the client feel caught out, and resolves the tension with a clarifying distinction.

---

## Edge Case 4 — Client Refuses to Share Information

**Scenario:** During Round 1, when asked about pricing, Colin declines.

**Colin's input:**
> "I'd prefer to keep my pricing structure private, if that's okay."

**Rule triggered:** Recovery Rule + respect for client autonomy

**Agent response:**
> "Of course — no problem at all. I'll note pricing structure as a gap that Xavier will need to confirm with you directly before the build phase."
*(Moves immediately to the next question.)*

**Outcome:** The gap is flagged in the output document under "Known Gaps" with the note: *Pricing model not confirmed — client preferred not to share in this session. Confirm directly with Colin before designing any payment automation.*

**What this proves:** The agent never pushes on a refusal. It accepts the boundary, logs the gap transparently, and moves on without making the client uncomfortable. Judges can verify this appears correctly in the sample output.

---

## Edge Case 5 — Uploaded Document Contradicts Stated Process

**Scenario:** Colin uploads his coaching agreement, which states "Sessions are conducted bi-weekly." In Round 3, Colin says he runs sessions "weekly or bi-weekly, depending on the client."

**Rule triggered:** Contradiction Detection Rule (document vs. stated)

**Agent response:**
> "I noticed your coaching agreement says sessions are bi-weekly. In Round 3 you mentioned they can be weekly or bi-weekly depending on the client. Is the agreement language just the default, or do some clients genuinely work with you on a weekly schedule?"

**Colin's clarification:**
> "The agreement says bi-weekly as the standard, but some clients want to meet weekly, especially early on. I just adjust the schedule in Calendly."

**Agent response:**
> "Got it — bi-weekly is the stated default, weekly is available and happens in practice. I'll note both cadences in the spec."

**What this proves:** The agent reads uploaded documents and cross-references them against conversational answers. Contradictions between documents and stated process are caught and resolved. The output spec reflects the real answer, not just the document answer.

---

## Edge Case 6 — Client Gives a Perfect, Complete Answer

**Scenario:** In Round 2, Colin gives an unusually detailed and specific answer to the lead journey question that covers everything — channel, response time, message content, conversion behavior — without prompting.

**Colin's input:**
> "The last three people who reached out all came through referrals. The first one — a colleague of a current client — emailed me on a Tuesday afternoon. I replied Wednesday morning with a couple of questions about what she was looking for, then sent her my Calendly link. She booked same day. The second one messaged me on LinkedIn — I replied within the hour, had a short exchange about what coaching is, then suggested the intro call. He booked three days later. The third never responded after my first reply. That happens occasionally — they reach out impulsively and then go quiet."

**Rule triggered:** No rule triggered — this answer is complete. The agent must recognize when NOT to probe.

**Agent response:**
> "That's exactly the level of detail I needed — thank you. Three paths: fast referral → same-day booking, LinkedIn → three-day nurture → booked, and the occasional inquiry that goes quiet after first contact. Clear pattern."
*(Moves directly to the next question — no probe.)*

**What this proves:** The agent doesn't apply the shallow answer probe to good answers. It recognizes completeness and keeps the session moving. This tests whether the probe rule is a trigger (vague answer) vs. a habit (applied to everything).

---

## Edge Case 7 — Client Tries to Pivot the Conversation

**Scenario:** Midway through Round 3, Colin tries to redirect the session toward a strategic question he's been thinking about.

**Colin's input:**
> "Actually, can I ask you something? I've been wondering whether I should add a group coaching offer to my practice — not the PQ Program, but something I design myself. What do you think?"

**Rule triggered:** Scope redirect (agent identity: here to understand, not advise)

**Agent response:**
> "That's a great question — and honestly, once we've mapped your current practice properly, Xavier will be in a much better position to give you an informed perspective on that. The discovery we're doing right now is what makes that kind of strategic conversation more useful. Can we hold that for the end, and for now stay with how things currently run?
>
> We were just covering what happens after a session ends — what do you typically send the client?"

**What this proves:** The agent stays in its lane. It doesn't refuse or dismiss the question — it acknowledges it, defers it appropriately, and redirects warmly back to the interview scope without losing the conversational thread.

---

## Edge Case 8 — Artifact Shared After the Session Has Begun

**Scenario:** Colin didn't share anything in Round 0, but midway through Round 2 he remembers a document.

**Colin's input (during Round 2):**
> "Oh — I just remembered I have a document I put together last year. It's kind of an overview of my coaching process. Let me paste it in."
*(Shares a 2-page Google Doc export describing his intro session, intake process, and ongoing session structure.)*

**Rule triggered:** Artifact Collection Rule — "accept materials at any point during the session"

**Agent response:**
> "Perfect — thank you for sharing this. Give me a moment to read through it."
*(Reads the document. Identifies that it describes the intake process in detail — including the Kickoff Workbook as a 4-section PDF — which hadn't come up yet in the conversation.)*
> "This is helpful — especially the section on the Kickoff Workbook. I can see it's a 4-section PDF you work through with the client in the intake session. I hadn't asked about that yet, so this fills in a gap nicely. Does this document still reflect how you do things, or has anything changed since you wrote it?"

**Outcome:** The new information is integrated. The agent updates its mental model and does not re-ask questions already answered by the document.

**What this proves:** The agent accepts artifacts at any point in the session. It reads them, integrates the information, acknowledges what they reveal, and adjusts subsequent questions accordingly — avoiding duplication.

---

## Summary — Rules Coverage Matrix

| Edge Case | Rule Exercised | Pass Condition |
|---|---|---|
| 1 — One-liner / fatigue | Recovery Rule + Session Break Rule | Agent offers pause without pressure |
| 2 — Ideal description | Shallow Answer Rule | Agent probes once for specific example |
| 3 — Contradiction across rounds | Contradiction Detection Rule | Agent catches it, asks once, resolves |
| 4 — Refusal | Recovery Rule | Agent accepts, logs gap, moves on |
| 5 — Document vs. stated contradiction | Contradiction Detection Rule | Agent cross-references, catches, resolves |
| 6 — Complete answer | No probe rule (recognition) | Agent does NOT probe a complete answer |
| 7 — Pivot attempt | Identity/scope rule | Agent defers warmly and redirects |
| 8 — Late artifact | Artifact Collection Rule | Agent accepts, reads, integrates, avoids duplication |
