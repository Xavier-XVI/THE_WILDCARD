# Business Discovery Agent
### A folder-based specialist for extracting how a business actually operates
This Github repo is a submission for Week #8 THE WILDCARD, Clief's Note skool competition.


> **Live demo:** [https://xavier-xvi.github.io/THE_WILDCARD/](https://xavier-xvi.github.io/THE_WILDCARD/)

**Built by:** Xavier Vincent  
**Purpose:** Run a structured, async discovery interview with a client — and produce a build-ready spec document — without a single scheduled call.

NOTE: This github repo contains a real case based on a client information. I publish his public information with his approval ( I dont publich private or the real outcome after running this agent).

---

## For Judges — How to Test This System

You don't need to contact Colin Thompson to evaluate this system. Everything you need is in this folder.

**Option A — Read the evidence (5 minutes)**
1. Read `demo/full_session_transcript.md` — a complete simulated session from opening to output delivery, showing every rule in operation
2. Read `tests/edge_cases.md` — 8 behavioral scenarios proving how the agent handles failure modes
3. Read `samples/sample_output_human.md` — the actual output document a client would receive
4. Read `samples/sample_output_builder.md` — the actual spec a builder would act on

**Option B — Test it yourself (15 minutes)**
1. Open Claude and create a new Project
2. Paste the contents of `identity.md` + `rules.md` into the system prompt field
3. Upload `client_profiles/colin_thompson_oligye.md` and all files in `reference/`
4. Start a conversation and type: **"I'm ready to start."**
5. Use `demo/colin_character_brief.md` to roleplay as Colin — it tells you exactly how he would respond
6. Check your session against the behavioral checklist at the end of the character brief

**What to look for:**
- Does the agent open with a specific, personal reference before asking a single question?
- Does it avoid asking anything already on the website?
- Does it probe vague answers exactly once — not twice?
- Does it catch contradictions and raise them warmly?
- Does it ask the JTBD question in Round 3?
- Does it ask the magic wand question in Round 4?
- Does the review feel like a celebration, not a verification exercise?
- Does it produce SVG diagrams and two output formats?

**Where the methodology lives:** `rules.md` — every rule is named, numbered, and testable.

---

## What This Is

This folder contains a pre-configured AI agent that interviews a business owner about how their practice actually runs. It arrives prepared, asks informed questions, accepts documents and files, and ends the session with two output documents:

1. A human-readable spec for the consultant (Xavier) and client (Colin) to review and sign off
2. A builder-ready spec for an AI agent or developer to build from directly

The agent was built for Oligye Enterprises (Colin C. Thompson, life coach) but is designed to be adapted for any service business.

---

## How Artifacts & Session State Work

### Artifacts (Files Colin Shares)
When Colin shares any document, template, email, screenshot, or recording during the session, the agent handles everything:
- Names it automatically (`coaching_agreement_v2`, `intro_confirmation_email`, etc.)
- Adds it to a running artifact catalog
- Processes it before asking the next question
- References it by name in follow-up questions
- Includes the full catalog in the session state when the session is saved

**Colin never needs to save, file, or label anything.** He just shares it. The agent does the rest.

After Xavier receives the session output, he saves the artifacts into `client_sessions/colin/artifacts/` for builder reference. See the README in that folder for the naming convention.

### Session Continuity (Pausing and Resuming)
**The simplest path: return to the same conversation.** Claude Projects remember the full conversation history. Colin can close the tab, come back a week later, and the agent knows exactly where they stopped. No saving, no commands, no uploads.

**If Colin says he's leaving** ("gotta go," "I'll come back," "not enough time") — the agent automatically generates a session checkpoint without being asked. This protects against session loss even when Colin forgets.

**`SAVE SESSION` command** is available for edge cases: switching devices, starting a fresh conversation, or sharing mid-session progress with Xavier. When used, the agent generates a complete session state document (progress, all answers, artifact catalog, deferred questions) and instructs Colin to upload it once to the Claude Project.

**Colin never needs to remember where he was, re-explain what was covered, or restart from scratch.**

### Progress Display
After every completed round, the agent displays a visual progress tracker:
```
✅ Round 0 · Artifacts
✅ Round 1 · Business Snapshot
⬜ Round 2 · Lead Journey  ← Next
⬜ Round 3 · Delivery & Intent
⬜ Round 4 · Friction & Reality
⬜ Review · Output

Approx. 30 min done · 60 min remaining
To pause: SAVE SESSION
```
Colin always knows exactly where he is and how much is left.

---

## For Colin — How to Run Your Session

### Step 1 — Set Up Your Claude Project

1. Open Claude (claude.ai) on your computer or phone
2. Create a new **Project**
3. Name it: `Business Discovery — Oligye`

### Step 2 — Add the System Prompt

1. In your Project settings, find the **Custom Instructions** or **System Prompt** field
2. Copy the full contents of `identity.md` and paste it in
3. Then copy the full contents of `rules.md` and paste it below the identity — in the same field
4. Save

### Step 3 — Upload the Reference Files

In the Project's knowledge/files section, upload all of the following:

- `client_profiles/colin_thompson_oligye.md`
- `reference/coaching_business_model.md`
- `reference/lead_journey_map.md`
- `reference/common_tools_stack.md`
- `reference/output_spec_human.md`
- `reference/output_spec_builder.md`

### Step 4 — Start the Conversation

Open a new conversation in the Project and type:

> **"I'm ready to start."**

The agent will take it from there.

### Step 5 — Answer at Your Own Pace

- Share files, screenshots, recordings, or emails at any point — just drag them into the chat. The agent handles naming, filing, and processing automatically.
- Each round takes about 15–20 minutes. The agent shows your progress after every round so you always know where you are.
- There are no wrong answers. The messier and more honest, the better.
- **To pause:** just close the tab. When you're ready to continue, open the same conversation — not a new one. The agent will remember exactly where you stopped.
- **If you say you're leaving** ("gotta go," "I'll come back later," etc.) the agent will automatically generate a session checkpoint — no command needed.
- **`SAVE SESSION`** is only needed if you're switching devices or starting a fresh conversation.

### Step 6 — Receive and Send the Output

When the session is complete and the agent delivers your output documents:
1. Email both documents to Xavier at [Xavier's email]
2. Subject line: **Colin Thompson — Discovery Complete**

That's it. Xavier takes it from there.

---

## For Xavier — How to Adapt This for a New Client

### Step 1 — Create a New Client Profile

1. Copy `client_profiles/_TEMPLATE.md`
2. Rename it to `client_profiles/[client-name].md`
3. Fill in everything you can from public sources before the session
4. Add your known open questions and automation hypotheses

### Step 2 — Customize the Opening (Optional)

The agent's opening message references Colin specifically (his website, his client testimonials). For a new client, update the opening example in `examples.md` or add a note to the client profile so the agent knows what specific detail to reference.

### Step 3 — Send the Folder to Your Client

Give the client the folder and walk them through the setup steps above (Steps 1–5 in the Colin section). The README they follow is the same — just update the client name and Xavier's email address.

### Step 4 — Receive and Review

When you receive the two output documents from the client:
1. Review the human-readable doc first
2. Mark it up with any questions or gaps you want to clarify
3. Schedule a brief call with the client (if needed) to close the gaps — but this call should be short: 20–30 minutes, not 2 hours
4. Once both you and the client sign off on the human-readable doc, pass the builder-ready doc to your builder agent

---

## Folder Structure

```
THE_WILDCARD/
│
├── brief.md                          ← Competition brief (Xavier's problem statement)
├── identity.md                       ← Who the agent is and how it shows up
├── rules.md                          ← Full interview methodology, all 5 phases
├── examples.md                       ← Sample exchanges showing the method in action
├── README.md                         ← This file
│
├── client_profiles/
│   ├── _TEMPLATE.md                  ← Copy this for every new client
│   └── colin_thompson_oligye.md      ← Pre-researched profile for Colin
│
└── reference/
    ├── coaching_business_model.md    ← Life coaching domain knowledge
    ├── lead_journey_map.md           ← Standard coaching client journey
    ├── common_tools_stack.md         ← Tools coaches typically use
    ├── output_spec_human.md          ← Format for the human-readable output doc
    └── output_spec_builder.md        ← Format for the builder-ready output doc
```

---

## Design Principles

**The agent arrives prepared, not blank.**
Before asking a single question, the agent reads the client profile and all reference files. It knows the client's services, their stated process, and their tools. It never asks what a website could answer.

**Scenario-based, not process-based.**
The agent asks "walk me through the last person who reached out to you" — not "describe your lead generation process." Real examples produce real answers. Processes produce ideal descriptions.

**The job to be done, not just the steps.**
For each service, the agent explicitly captures why the client does coaching — what their clients are really trying to change, and what success feels like for them. This is what separates a spec that produces good automation from one that produces mechanical automation.

**The friction is the gold.**
Round 4 is specifically designed to surface what breaks, what gets avoided, and what the client would automate first if they could. This is where the highest-value automation opportunities live.

**Review is a celebration, not a test.**
The agent presents the output to the client as "look what we built together" — not "please verify this is accurate." The framing matters. Clients who feel proud of what emerged are more engaged in the confirmation process.

**Two outputs, two audiences.**
The human-readable document is for the consultant and client to confirm together. The builder-ready document is structured, field-by-field, with no narrative prose — designed to be acted on directly by an AI builder without any interpretation.

---

## Adapting for Other Business Types

This folder was built for a life coaching business. To adapt it for a different type of service business:

1. Replace `reference/coaching_business_model.md` with a domain model for the new business type
2. Replace `reference/lead_journey_map.md` with the standard client journey for that industry
3. Replace `reference/common_tools_stack.md` with tools common in that industry
4. Create a new client profile using `_TEMPLATE.md`
5. The `identity.md`, `rules.md`, `examples.md`, and output specs are largely universal — minimal changes needed

The methodology — prepared arrival, scenario questions, JTBD capture, friction inventory, SVG review, two-format output — applies to any service business discovery.
