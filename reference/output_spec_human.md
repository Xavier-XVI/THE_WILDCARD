# Output Spec — Human-Readable Discovery Document

> This is the format for the first output document generated after the review session. It is written for Xavier (the consultant) to review, and for Xavier and Colin to sign off on together before anything goes to a builder. It must be readable by a non-technical person without explanation.

---

## Document Header

```
BUSINESS DISCOVERY DOCUMENT
Client: [Full Name] / [Business Name]
Discovery conducted: [Date or date range]
Prepared by: Business Discovery Agent
Status: DRAFT — Pending Xavier & Colin sign-off
```

---

## Section 1 — Business Overview

**Purpose:** A plain-English description of what this business is and who it serves. Anyone reading this document for the first time should be able to understand the business in 2 minutes.

Include:
- What the business does and who it serves (1–2 sentences)
- The service lines offered, with a one-line description of each
- The typical client (who they are, what brings them here, what they're trying to change)
- The business model in plain language (how the coach earns money)
- Volume and capacity (how many active clients at one time, roughly)
- Whether anyone else is involved in the business or if it is fully solo

---

## Section 2 — How Someone Becomes a Client

**Purpose:** Document the full journey from first awareness to signed client. Include what actually happens, not what ideally should happen.

Include:
- Primary lead sources (ranked by volume if known)
- What first contact looks like (channel, format, typical message)
- How the coach responds (timing, method, content)
- What happens between first contact and the intro session
- How the intro session runs (structure, duration, what's covered)
- What happens immediately after the intro session
- How the coach follows up and what the follow-up contains
- What triggers a "yes" from the prospect and what triggers a no
- Time from first contact to signed client (typical range)

**Visual:** Include SVG lead journey flowchart here.

---

## Section 3 — How Coaching Is Delivered

**Purpose:** Document how the coach actually delivers the service — what happens in sessions and between them.

Include per service (repeat for each main service):
- **Service name:**
- **Typical engagement length:**
- **Session frequency:**
- **What a typical session looks like start to finish** (including any structure or format the coach follows)
- **What the client receives after a session** (notes, summary, action items?)
- **Between-session touchpoints** (who initiates, what channel, how often)
- **How progress is tracked** (tool, format, frequency)
- **What the end of an engagement looks like** (structured close or informal drift)
- **What success looks and feels like for the client** (the job to be done — in the client's own language)

**Visual:** Include SVG service delivery flowchart here.

---

## Section 4 — Tools & Operations Map

**Purpose:** Document every tool used at every stage, and flag what is currently manual.

Format this as a table:

| Stage | Tool Used | Manual or Automated | Notes |
|---|---|---|---|
| Lead capture | | | |
| First response | | | |
| Scheduling | | | |
| Intro session | | | |
| Post-intro follow-up | | | |
| Contract / agreement | | | |
| Onboarding / intake | | | |
| Payment | | | |
| Session delivery | | | |
| Session notes | | | |
| Post-session follow-up | | | |
| Between-session communication | | | |
| Client tracking / progress | | | |
| Invoicing | | | |
| Offboarding | | | |
| Referral request | | | |

**Visual:** Include SVG tools & touchpoints map here.

---

## Section 5 — Friction Inventory

**Purpose:** Document where the process currently breaks down, is inconsistent, or is a known pain point. This is the primary input for automation prioritization.

Include:
- What the coach most consistently delays or avoids (and why, if known)
- Where leads or clients most often fall through the cracks
- What is done inconsistently (sometimes vs. always)
- What the coach would automate first if they could (the magic wand answer — verbatim)
- Any other pain points surfaced during the session

Format each item as:
```
FRICTION POINT: [Description]
STAGE AFFECTED: [Which stage in the journey this affects]
IMPACT: [What it costs — client experience, revenue, time]
ROOT CAUSE: [Structural (no tool/template) or behavioral (has tool, doesn't use)]
AUTOMATION POTENTIAL: High / Medium / Low
```

---

## Section 6 — Known Gaps

**Purpose:** Be transparent about what was not captured in this session. This protects Xavier and sets expectations for Colin.

Include:
- Questions that were not answered or were answered vaguely
- Areas the session did not cover (or ran out of time for)
- Things that need to be confirmed with a document or artifact that was not shared
- Anything that felt like the "ideal" answer rather than the real one

---

## Section 7 — Sign-Off

```
XAVIER REVIEW
Reviewed by: Xavier Vincent
Date:
Status: [ ] Approved for builder handoff  [ ] Needs revision
Notes:


COLIN CONFIRMATION
Confirmed by: Colin C. Thompson
Date:
This document accurately represents how my practice operates: [ ] Yes  [ ] No — see notes below
Notes:
```

---

## Formatting Notes

- Write in plain English throughout — no jargon
- Use Colin's own words and phrases where he provided them (put in quotes)
- Every SVG diagram must have a plain-language caption explaining what it shows
- Flag any automation opportunity with the tag **[AUTOMATION OPPORTUNITY]** inline so Xavier can scan for them quickly
- The document should be readable by someone who has never met Colin and knows nothing about coaching
