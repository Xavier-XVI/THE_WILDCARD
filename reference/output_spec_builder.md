# Output Spec — Builder-Ready Discovery Document

> This is the format for the second output document. It is written for an AI builder agent (or a human developer) who will design and build an automated solution. It is structured, explicit, and leaves nothing to interpretation. The builder should be able to work from this document without ever contacting the client.

---

## Document Header

```
BUILDER SPECIFICATION DOCUMENT
Client: [Full Name] / [Business Name]
Discovery date: [Date or date range]
Human-readable doc: Confirmed by Xavier & Colin — [Date]
Builder document version: 1.0
```

---

## Section 1 — Business Context (Compressed)

A compressed summary for the builder. They do not need the full story — just enough to make good decisions.

```
BUSINESS TYPE: [e.g., Solo life coaching practice]
SERVICES: [List with one-line each]
ACTIVE CLIENTS: [Approximate number]
TEAM: [Solo / Has VA / Has team]
TIMEZONE: [Primary timezone]
CLIENT PROFILE: [Who the clients are — 1 sentence]
BRAND SENSITIVITY: [e.g., High — client relationship is personal; automation must feel human]
```

---

## Section 2 — Current Process Map (Structured)

Document every step in the current process. For each step:

```
STEP: [Name]
TRIGGER: [What causes this step to happen]
OWNER: [Who does it — Coach / Client / Tool]
CURRENT METHOD: [How it is done today — tool name or "manual"]
FREQUENCY: [Every session / Once per client / Ad hoc / etc.]
OUTPUT: [What is produced or sent]
TIMING: [When it happens relative to trigger — immediately / same day / within X days]
CURRENT ISSUES: [What breaks or slips here]
```

Repeat for every step in this sequence:
1. Lead arrives (first contact)
2. Coach responds to lead
3. Intro session is scheduled
4. Pre-session prep (if any)
5. Intro session runs
6. Post-intro follow-up
7. Client says yes — agreement sent
8. Agreement signed
9. Payment collected
10. Intake / Kickoff Workbook
11. First paid session scheduled
12. Ongoing session runs
13. Post-session follow-up
14. Between-session check-in
15. Client progress tracked
16. Engagement closes
17. Offboarding / testimonial request
18. Referral ask

---

## Section 3 — Tools Inventory

```
TOOL: [Name]
FUNCTION: [What it does in the business]
STAGE(S): [Which steps above it is used in]
INTEGRATION CAPABILITY: [Has API / Zapier / Make integration — Yes / No / Unknown]
CURRENT AUTOMATION LEVEL: [Fully manual / Partially automated / Fully automated]
REPLACE OR KEEP: [Keep as is / Replace with X / Augment with automation]
```

---

## Section 4 — Automation Opportunities (Prioritized)

List every identified automation opportunity. Sort by priority: High first.

```
OPPORTUNITY: [Name]
PRIORITY: [High / Medium / Low]
STAGE AFFECTED: [Which step(s) in Section 2]
CURRENT STATE: [What happens today — manual, inconsistent, missing]
DESIRED STATE: [What should happen — specific and measurable]
TRIGGER: [What event should initiate the automation]
ACTION: [What the automation does]
OUTPUT: [What is produced or sent]
PERSONALIZATION REQUIRED: [Yes / No — if yes, what needs to be customized per client]
TOOLS INVOLVED: [What tool(s) should handle this]
DEPENDENCIES: [What needs to be in place first]
RISK: [Any sensitivity or risk in automating this — e.g., client relationship, brand tone]
MAGIC WAND SCORE: [1 = Client explicitly requested / 2 = Strongly implied / 3 = Inferred]
```

---

## Section 5 — Data & Content Assets

List every asset the builder needs access to or needs to create.

```
ASSET: [Name — e.g., "Post-intro follow-up email template"]
TYPE: [Email / Form / Contract / Workbook / Script / Prompt / etc.]
STATUS: [Exists — provided / Exists — not provided / Does not exist — needs to be created]
LOCATION: [Where it currently lives, if known]
NOTES: [Any context the builder needs]
```

---

## Section 6 — Constraints & Non-Negotiables

Things the builder must not violate.

```
CONSTRAINT: [Description]
REASON: [Why this matters — brand, legal, client relationship, licensing]
```

Common constraints for coaching businesses:
- Automation must never feel automated — client relationship is personal
- The Positive Intelligence Program® has licensing constraints — confirm with client before automating any PQ-related workflow
- Client data is sensitive — any tool that stores client information must comply with relevant data protection requirements
- Communication tone must match the coach's voice — all templated copy needs coach review before deployment

---

## Section 7 — Recommended Build Sequence

Tell the builder where to start. Sequence based on highest impact + lowest friction.

```
PHASE 1 — Quick Wins (Build first)
[List 2–3 highest-priority automations that are simple to implement]

PHASE 2 — Core Infrastructure (Build second)
[List the foundational automations that everything else depends on]

PHASE 3 — Advanced / Nice to Have (Build later)
[List lower-priority automations for a second iteration]
```

---

## Section 8 — Open Questions for the Builder

Things that were not confirmed in discovery and need follow-up before building.

```
QUESTION: [What needs to be answered]
WHY IT MATTERS: [How the answer affects what gets built]
WHO TO ASK: [Xavier / Colin / Colin's team]
```

---

## Formatting Rules for This Document

- Every field must be filled or marked `[NOT CONFIRMED — needs follow-up]`
- Never leave a field blank — blank fields are invisible to a builder
- No narrative prose — structured fields only
- If something was described vaguely in discovery, flag it: `[VAGUE — builder should confirm before building]`
- If something contradicted itself in the session, flag it: `[CONTRADICTION — Xavier to clarify with Colin]`
- The builder should be able to read this document and start designing without asking a single question
