# Builder Specification Document
## Colin C. Thompson / Oligye Enterprises

```
Status:              SIMULATED — Based on demo/full_session_transcript.md
Human-readable doc:  Pending sign-off (see samples/sample_output_human.md)
Builder doc version: 1.0
For:                 AI builder agent or developer
```

> Fields marked `[NOT CONFIRMED]` must be resolved with Xavier or Colin before building that component. Fields marked `[VAGUE]` were described imprecisely in discovery — confirm interpretation before building. Fields marked `[CONFIRMED]` are verified from the discovery session or public sources.

---

## Section 1 — Business Context

```
BUSINESS TYPE:       Solo life coaching practice
SERVICES:            Career coaching, personal development, executive coaching,
                     relocation coaching (one-on-one); Positive Intelligence Program (cohort, separate workflow)
ACTIVE CLIENTS:      8–12 one-on-one simultaneously [CONFIRMED]
TEAM:                Solo — no VA, no support [CONFIRMED]
TIMEZONE:            International — clients in Shanghai, Washington DC, likely others [CONFIRMED]
CLIENT PROFILE:      Professionals from mid-to-senior career level seeking career change,
                     personal growth, or leadership development [CONFIRMED]
BRAND SENSITIVITY:   HIGH — client relationship is deeply personal. Any automation must
                     feel warm and human, not transactional. Colin's brand is built on
                     personal connection. All templated copy requires his voice.
PQ PROGRAM NOTE:     The Positive Intelligence Program® is a licensed external product.
                     Do NOT automate any PQ-specific workflow without confirming
                     compliance with Positive Intelligence Inc. licensing terms.
```

---

## Section 2 — Current Process Map

**STEP 1: Lead Arrives — Referral**
```
TRIGGER:         Past or current client introduces Colin to a new prospect
OWNER:           Prospect (initiates contact)
CURRENT METHOD:  Direct email to CoachColinT@Oligye.com
FREQUENCY:       ~60% of new leads
OUTPUT:          Inbound email in Colin's inbox
TIMING:          Varies — depends on when prospect reaches out
CURRENT ISSUES:  None at this stage; referrals arrive pre-qualified
```

**STEP 2: Lead Arrives — LinkedIn**
```
TRIGGER:         Prospect sees content or profile on LinkedIn, sends DM
OWNER:           Prospect (initiates contact)
CURRENT METHOD:  LinkedIn DM
FREQUENCY:       ~30% of new leads
OUTPUT:          DM thread in LinkedIn inbox
TIMING:          Varies
CURRENT ISSUES:  Multi-day DM threads can go quiet and get buried.
                 No follow-up trigger or CRM to track these. [CONFIRMED]
```

**STEP 3: Lead Arrives — Website**
```
TRIGGER:         Prospect finds website via search or direct visit, submits contact form
OWNER:           Prospect (initiates contact)
CURRENT METHOD:  Website contact form (WordPress/Elementor)
FREQUENCY:       ~10% of new leads
OUTPUT:          Form submission notification (method unknown) [NOT CONFIRMED — where does this land?]
TIMING:          Varies
CURRENT ISSUES:  No auto-acknowledgment sent to prospect after form submission [AUTOMATION OPPORTUNITY]
```

**STEP 4: Coach Responds to Lead**
```
TRIGGER:         Colin sees the inquiry (email, DM, or form notification)
OWNER:           Colin (manual)
CURRENT METHOD:  Manual reply — email or DM. Template unclear. [VAGUE — confirm if template exists]
FREQUENCY:       Every new lead
OUTPUT:          Personal reply message
TIMING:          Same-day for first reply [CONFIRMED]
CURRENT ISSUES:  Multi-message threads (especially LinkedIn) can lose momentum over days.
                 No CRM to track lead status. [CONFIRMED]
```

**STEP 5: Scheduling Link Sent**
```
TRIGGER:         After initial exchange establishes interest
OWNER:           Colin (manual — sends link)
CURRENT METHOD:  Calendly link sent in email or DM
FREQUENCY:       Every qualified lead
OUTPUT:          Prospect receives scheduling link
TIMING:          During or at end of initial exchange
CURRENT ISSUES:  Link is sent manually — no automated trigger [AUTOMATION OPPORTUNITY]
```

**STEP 6: Prospect Books Intro Session**
```
TRIGGER:         Prospect clicks Calendly link and selects a time
OWNER:           Prospect + Calendly (automated)
CURRENT METHOD:  Calendly
FREQUENCY:       Every booked intro
OUTPUT:          Automated Calendly confirmation to both parties; Colin's calendar updated
TIMING:          Immediate on booking
CURRENT ISSUES:  No pre-session intake form or prep questions sent to prospect [AUTOMATION OPPORTUNITY]
```

**STEP 7: Personal Confirmation Email Sent**
```
TRIGGER:         Colin sends manually after seeing booking notification
OWNER:           Colin (manual)
CURRENT METHOD:  Email — personal confirmation template (shared in discovery)
FREQUENCY:       Every booked intro
OUTPUT:          Warm, low-pressure email to prospect confirming session details and Zoom link
TIMING:          Manual — varies [AUTOMATION OPPORTUNITY — could be automated via Calendly follow-up]
CURRENT ISSUES:  Timing is inconsistent; relies on Colin checking Calendly notifications
```

**STEP 8: Intro Session Runs**
```
TRIGGER:         Scheduled session time
OWNER:           Colin + Prospect
CURRENT METHOD:  Zoom (~90%) or phone (~10%) [CONFIRMED]
FREQUENCY:       Every lead who books
OUTPUT:          Mutual assessment of fit; prospect decides whether to move forward
TIMING:          45–60 minutes [CONFIRMED]
CURRENT ISSUES:  No structured recording or note-taking system mentioned [NOT CONFIRMED]
```

**STEP 9: Post-Intro Follow-Up Email**
```
TRIGGER:         Should be: immediately after intro session ends
OWNER:           Colin (manual — BROKEN)
CURRENT METHOD:  Manual email — rough template exists, customization required
FREQUENCY:       Intended every intro; actual frequency unknown — INCONSISTENT [CONFIRMED]
OUTPUT:          Email with: summary of conversation, Colin's assessment, recommended next steps
TIMING:          INTENDED: same day. ACTUAL: 1–3 days delay, or not sent [CONFIRMED]
CURRENT ISSUES:  THIS IS THE HIGHEST-PRIORITY FRICTION POINT.
                 Template exists but customization creates friction. Timing slips cost conversions.
                 Colin's own assessment: "I've probably lost clients over that gap."
                 MAGIC WAND ANSWER: This is what Colin said he would automate first. [CONFIRMED]
```

**STEP 10: Client Says Yes — Agreement Sent**
```
TRIGGER:         Prospect verbally commits to moving forward
OWNER:           Colin (manual)
CURRENT METHOD:  [NOT CONFIRMED — delivery method for coaching agreement]
FREQUENCY:       Every new client
OUTPUT:          Coaching agreement sent for signature
TIMING:          [NOT CONFIRMED]
CURRENT ISSUES:  [NOT CONFIRMED]
```

**STEP 11: Agreement Signed**
```
TRIGGER:         Prospect reviews and signs coaching agreement
OWNER:           Prospect
CURRENT METHOD:  [NOT CONFIRMED — DocuSign, PDF return, platform?]
FREQUENCY:       Every new client
OUTPUT:          Signed agreement
TIMING:          [NOT CONFIRMED]
CURRENT ISSUES:  [NOT CONFIRMED]
```

**STEP 12: Payment Collected**
```
TRIGGER:         Agreement signed / client onboarded
OWNER:           Colin + Client
CURRENT METHOD:  [NOT CONFIRMED — Stripe, PayPal, invoice, platform?]
FREQUENCY:       Start of every package (3-month, 6 sessions)
OUTPUT:          Full package payment received upfront
TIMING:          Before sessions begin [CONFIRMED]
CURRENT ISSUES:  Invoicing is consistently delayed — Colin defers this task [CONFIRMED]
```

**STEP 13: Intake / Kickoff Workbook**
```
TRIGGER:         After agreement signed and payment received
OWNER:           Colin + Client
CURRENT METHOD:  [NOT CONFIRMED — PDF, Google Doc, platform?]
FREQUENCY:       Every new client
OUTPUT:          Completed Kickoff Workbook — identifies client's focus area
TIMING:          [NOT CONFIRMED — completed before first session or during intake session?]
CURRENT ISSUES:  [NOT CONFIRMED]
```

**STEP 14: Ongoing Session Runs**
```
TRIGGER:         Scheduled session time (recurring)
OWNER:           Colin + Client
CURRENT METHOD:  Zoom [CONFIRMED]
FREQUENCY:       6 sessions per 3-month package (weekly or bi-weekly) [CONFIRMED]
OUTPUT:          Client leaves with 1–3 focus goals for the period until next session
TIMING:          60 minutes [CONFIRMED]
CURRENT ISSUES:  None in delivery; gaps are in what surrounds the session (pre/post)
```

**STEP 15: Post-Session Notes**
```
TRIGGER:         Session ends
OWNER:           Colin (manual)
CURRENT METHOD:  Google Doc per client — updated after each session [CONFIRMED]
FREQUENCY:       Every session
OUTPUT:          Coach-side notes. Client receives nothing. [CONFIRMED]
TIMING:          During or immediately after session
CURRENT ISSUES:  Client has no written record of their focus goals. [AUTOMATION OPPORTUNITY — PRIORITY 2]
```

**STEP 16: Post-Session Client Communication**
```
TRIGGER:         Should be: immediately after session
OWNER:           Colin (manual — INCONSISTENT)
CURRENT METHOD:  Ad hoc email or message if something specific came up
FREQUENCY:       INCONSISTENT — not standard [CONFIRMED]
OUTPUT:          Varies — sometimes a follow-up message, often nothing
TIMING:          Varies
CURRENT ISSUES:  No standard. Client accountability is weakened by missing written commitments.
```

**STEP 17: Between-Session Check-In**
```
TRIGGER:         Should be: mid-point between sessions (e.g., 3-4 days after session)
OWNER:           Colin (manual — INCONSISTENT)
CURRENT METHOD:  Ad hoc message — email or messaging app [NOT CONFIRMED — which channel?]
FREQUENCY:       INCONSISTENT — "some weeks for all clients, other weeks for none" [CONFIRMED]
OUTPUT:          Brief check-in on focus goal progress
TIMING:          Mid-week, varies
CURRENT ISSUES:  High-value but no system. Entirely dependent on Colin's bandwidth that week.
                 [AUTOMATION OPPORTUNITY — PRIORITY 3]
```

**STEP 18: Engagement Close**
```
TRIGGER:         Final session in the package
OWNER:           Colin + Client
CURRENT METHOD:  Natural conversation — no formal structure [CONFIRMED]
FREQUENCY:       End of every package
OUTPUT:          Reflection on the engagement. Some clients renew, some don't.
TIMING:          During the 6th session
CURRENT ISSUES:  No formal close process. No testimonial collection. No structured re-engagement path.
                 [AUTOMATION OPPORTUNITY — PRIORITY 4]
```

**STEP 19: Referral Ask**
```
TRIGGER:         Should be: near end of successful engagement
OWNER:           Colin
CURRENT METHOD:  None — referrals happen organically [CONFIRMED]
FREQUENCY:       Not systematic
OUTPUT:          Occasional referral
TIMING:          Ad hoc
CURRENT ISSUES:  60% of leads come from referrals. No system to encourage this.
                 [AUTOMATION OPPORTUNITY]
```

---

## Section 3 — Tools Inventory

```
TOOL:                    Calendly
FUNCTION:                Session scheduling
STAGE(S):                Steps 5, 6, 7
INTEGRATION CAPABILITY:  Yes — Zapier/Make integration available; webhook on booking
CURRENT AUTOMATION:      Partially automated (auto-confirmation; reminder emails possible)
REPLACE OR KEEP:         Keep. Augment with pre-session intake form and automated follow-up trigger.

TOOL:                    Zoom
FUNCTION:                Session delivery
STAGE(S):                Steps 8, 14
INTEGRATION CAPABILITY:  Yes — API and Zapier integration available
CURRENT AUTOMATION:      Manual scheduling via Calendly integration
REPLACE OR KEEP:         Keep.

TOOL:                    Google Docs
FUNCTION:                Session notes and client tracking
STAGE(S):                Steps 15, 17
INTEGRATION CAPABILITY:  Yes — Google Workspace API
CURRENT AUTOMATION:      Fully manual
REPLACE OR KEEP:         Keep for now, or augment with a template trigger. Consider migration
                         to a coaching platform (CoachAccountable, Paperbell) in Phase 2.

TOOL:                    Email (platform unknown)
FUNCTION:                All client communication
STAGE(S):                Steps 4, 7, 9, 16, 17
INTEGRATION CAPABILITY:  [NOT CONFIRMED — Gmail? Outlook? If Gmail: full Zapier/Make support]
CURRENT AUTOMATION:      Fully manual
REPLACE OR KEEP:         Keep. Automate triggers via Zapier/Make.

TOOL:                    LinkedIn
FUNCTION:                Lead generation + first contact for ~30% of leads
STAGE(S):                Steps 2, 4
INTEGRATION CAPABILITY:  Limited — LinkedIn DM automation is constrained by platform TOS
CURRENT AUTOMATION:      Fully manual
REPLACE OR KEEP:         Keep for content/lead gen. DM automation NOT recommended (TOS risk).
                         Focus automation on moving LinkedIn leads to email as quickly as possible.

TOOL:                    [NOT CONFIRMED — Coaching Agreement delivery]
FUNCTION:                Contract signing
STAGE(S):                Steps 10, 11
INTEGRATION CAPABILITY:  Depends on tool
CURRENT AUTOMATION:      [NOT CONFIRMED]
REPLACE OR KEEP:         [NOT CONFIRMED — confirm tool, then assess]

TOOL:                    [NOT CONFIRMED — Payment]
FUNCTION:                Package payment collection
STAGE(S):                Step 12
INTEGRATION CAPABILITY:  Depends on tool
CURRENT AUTOMATION:      [NOT CONFIRMED]
REPLACE OR KEEP:         [NOT CONFIRMED]
```

---

## Section 4 — Automation Opportunities (Prioritized)

**OPPORTUNITY 1: Post-Intro Follow-Up Email**
```
PRIORITY:                HIGH — Magic wand answer. Highest conversion impact.
STAGE AFFECTED:          Step 9
CURRENT STATE:           Manual email, template exists, customization causes delay,
                         timing slips by 1–3 days or email not sent
DESIRED STATE:           Follow-up email sent within 30 minutes of intro session ending,
                         with 3 custom fields for Colin to fill in before sending
TRIGGER:                 Calendly event end time + X minutes (or Colin marks session complete)
ACTION:                  Pre-populated email draft sent to Colin's inbox with:
                         [Client name], [one thing that stood out], [what Colin recommends].
                         Colin reviews, personalizes 3 fields, hits send.
OUTPUT:                  Follow-up email in prospect's inbox within the hour
PERSONALIZATION:         YES — 3 fill-in fields required before sending
TOOLS INVOLVED:          Calendly (webhook) → Zapier/Make → Email draft or CRM
DEPENDENCIES:            Email platform confirmed. Calendly webhook access.
RISK:                    LOW — still requires Colin to send; reduces friction, doesn't remove human touch
MAGIC WAND SCORE:        1 — Colin explicitly named this as his #1 priority
```

**OPPORTUNITY 2: Post-Session Focus Goal Summary to Client**
```
PRIORITY:                HIGH — Client accountability gap
STAGE AFFECTED:          Step 16
CURRENT STATE:           Client receives no written record of focus goals. Ad hoc follow-up only.
DESIRED STATE:           Within 1 hour of session end, client receives a clean summary of
                         their 1-3 focus goals for the period ahead
TRIGGER:                 Session end (via Calendly or manual "session complete" flag from Colin)
ACTION:                  Prompt Colin to enter 1-3 focus goals → auto-send formatted summary to client
OUTPUT:                  Clean email to client: "Here's what you committed to until we speak again..."
PERSONALIZATION:         YES — Colin enters the focus goals; format is automated
TOOLS INVOLVED:          Calendly or simple web form → Zapier/Make → Email
DEPENDENCIES:            Opportunity 1 must be in place first (same trigger infrastructure)
RISK:                    LOW
MAGIC WAND SCORE:        2 — Strongly implied by session (Colin described the gap clearly)
```

**OPPORTUNITY 3: Mid-Week Between-Session Check-In**
```
PRIORITY:                HIGH — Client outcomes gap
STAGE AFFECTED:          Step 17
CURRENT STATE:           Check-ins happen inconsistently — "some weeks for everyone, some for no one"
DESIRED STATE:           Each client receives a brief, warm check-in message 3-4 days after
                         each session, automatically, on their preferred channel
TRIGGER:                 3-4 days after each session (calculated from session calendar)
ACTION:                  Send personalized check-in: "Hi [Name], how's [focus goal] going?"
OUTPUT:                  Message to client via their preferred channel (email default)
PERSONALIZATION:         YES — client name and focus goal pulled from session summary (Opp 2)
TOOLS INVOLVED:          Zapier/Make + Email (or WhatsApp/Telegram with platform approval)
DEPENDENCIES:            Opportunity 2 must be in place (focus goals stored to trigger this)
RISK:                    MEDIUM — message must feel personal not automated; copy requires Colin review
MAGIC WAND SCORE:        2 — Strongly implied (Colin described the gap and its impact on outcomes)
```

**OPPORTUNITY 4: Offboarding + Testimonial + Alumni Sequence**
```
PRIORITY:                MEDIUM — Long-term business development
STAGE AFFECTED:          Steps 18, 19
CURRENT STATE:           Engagements end naturally with no structured close, no testimonial
                         request, no re-engagement path
DESIRED STATE:           After final session: structured close email, reflection prompt,
                         testimonial request, 90-day alumni check-in
TRIGGER:                 Final session in package (session 6 of 6)
ACTION:                  4-email sequence over 30-90 days:
                         Day 0: Reflection + "what changed" prompt
                         Day 3: Testimonial request
                         Day 30: Check-in — how are things going?
                         Day 90: Re-engagement offer
OUTPUT:                  Testimonials collected systematically; alumni relationships maintained;
                         re-engagement rate increases
PERSONALIZATION:         YES — each email uses client name and references their focus area
TOOLS INVOLVED:          Email automation (ConvertKit, Mailchimp, or CRM sequence)
DEPENDENCIES:            Requires client email list and automation platform
RISK:                    LOW — standard email sequence
MAGIC WAND SCORE:        3 — Inferred (Colin mentioned clients returning and the lack of structure)
```

**OPPORTUNITY 5: Contact Form Auto-Acknowledgment**
```
PRIORITY:                LOW-MEDIUM — Small friction, easy win
STAGE AFFECTED:          Step 3
CURRENT STATE:           No automatic response when someone submits the website contact form
DESIRED STATE:           Instant auto-reply: "Thanks for reaching out, Colin will be in touch within 24 hours"
TRIGGER:                 Website contact form submission
ACTION:                  Auto-reply email sent to form submitter
OUTPUT:                  Prospect receives immediate acknowledgment; Colin has time to respond personally
PERSONALIZATION:         Minimal — name from form field
TOOLS INVOLVED:          WordPress form plugin → Email
DEPENDENCIES:            Access to WordPress backend
RISK:                    VERY LOW
MAGIC WAND SCORE:        3 — Inferred
```

---

## Section 5 — Data & Content Assets

```
ASSET:          Post-intro follow-up email template
TYPE:           Email
STATUS:         Exists — not provided (Colin described it as "a rough template")
LOCATION:       Unknown — likely in Colin's email drafts
NOTES:          Builder needs this template to design the automation. Xavier to request from Colin.

ASSET:          Post-booking personal confirmation email
TYPE:           Email
STATUS:         Exists — provided in discovery session
LOCATION:       In discovery session transcript (demo/full_session_transcript.md)
NOTES:          Warm, low-pressure tone. No prep questions. Can be used as-is or improved.

ASSET:          Coaching Agreement
TYPE:           Contract (3-page PDF)
STATUS:         Exists — reviewed in discovery. Delivery method not confirmed.
LOCATION:       Colin's files
NOTES:          Contains 24-hour cancellation policy, bi-weekly session default, confidentiality terms.

ASSET:          Kickoff Workbook
TYPE:           Intake form / workbook
STATUS:         Exists — format and delivery method not confirmed
LOCATION:       Colin's files
NOTES:          Referenced on website and in coaching agreement. Exact contents unknown.

ASSET:          Session notes template
TYPE:           Google Doc structure
STATUS:         Exists (informal) — not provided
LOCATION:       Colin's Google Drive (one per client)
NOTES:          No standard format confirmed. Builder should propose a template.

ASSET:          Between-session check-in message copy
TYPE:           Message template
STATUS:         Does not exist — needs to be created
LOCATION:       N/A
NOTES:          Builder should draft 2-3 variations in Colin's voice for review.

ASSET:          Offboarding email sequence
TYPE:           Email sequence (4 emails)
STATUS:         Does not exist — needs to be created
LOCATION:       N/A
NOTES:          Must match Colin's warm, coaching-focused tone.
```

---

## Section 6 — Constraints & Non-Negotiables

```
CONSTRAINT:     All automated communication must feel personal, not templated
REASON:         Colin's brand is built on human connection. Clients who feel
                they're receiving automated messages will disengage.

CONSTRAINT:     PQ Program workflows must not be automated without licensing review
REASON:         Positive Intelligence Inc. has specific delivery requirements for licensed
                coaches. Any automation touching PQ cohort management requires their approval.

CONSTRAINT:     LinkedIn DM automation is not permitted
REASON:         LinkedIn TOS prohibits automated messaging via third-party tools.
                Risk of account suspension.

CONSTRAINT:     Client data must be handled with discretion
REASON:         Coaching conversations are confidential. Any tool that stores or processes
                session content must be vetted for data security and privacy compliance
                given Colin's international client base.

CONSTRAINT:     All email copy requires Colin's review before deployment
REASON:         Voice and tone are core to the coaching relationship. Generic copy will
                undermine the brand. Colin must approve every template.
```

---

## Section 7 — Recommended Build Sequence

```
PHASE 1 — Quick Wins (Build first, 1–2 weeks)
1. Contact form auto-acknowledgment (Opportunity 5) — 1 hour to build
2. Post-intro follow-up email draft trigger (Opportunity 1) — highest impact, moderate build
3. Calendly → email confirmation automation (replace manual personal email)

PHASE 2 — Core Infrastructure (Build second, 2–4 weeks)
4. Post-session focus goal summary to client (Opportunity 2)
5. Mid-week between-session check-in (Opportunity 3) — requires Opp 2 in place
6. Coaching Agreement e-signature automation (pending tool confirmation)
7. Payment / invoicing automation (pending tool confirmation)

PHASE 3 — Advanced / Next Iteration (Build later)
8. Offboarding + testimonial + alumni sequence (Opportunity 4)
9. Systematic referral prompt
10. Client portal / progress tracking upgrade (CoachAccountable or Paperbell migration assessment)
11. PQ Program enrollment automation (pending licensing review)
```

---

## Section 8 — Open Questions for the Builder

```
QUESTION:       What email platform does Colin use?
WHY IT MATTERS: Determines integration method (Gmail vs. Outlook changes the automation stack)
WHO TO ASK:     Colin

QUESTION:       How is the Coaching Agreement currently sent and signed?
WHY IT MATTERS: Determines whether to augment existing tool or introduce e-signature platform
WHO TO ASK:     Colin

QUESTION:       What is the format and content of the Kickoff Workbook?
WHY IT MATTERS: Intake automation depends on this — PDF vs. Google Form vs. platform changes the build
WHO TO ASK:     Colin (request the document)

QUESTION:       How does payment currently work?
WHY IT MATTERS: Invoicing automation requires knowing the payment platform
WHO TO ASK:     Colin

QUESTION:       Where does the website contact form submission go?
WHY IT MATTERS: Auto-acknowledgment automation requires access to the form trigger
WHO TO ASK:     Colin (or Xavier with WordPress access)

QUESTION:       What channel does Colin use for between-session messages?
WHY IT MATTERS: If WhatsApp or Telegram, automation path is different from email
WHO TO ASK:     Colin

QUESTION:       Can the post-intro follow-up template be shared?
WHY IT MATTERS: Phase 1 build starts here — need the template to design the automation
WHO TO ASK:     Xavier to request from Colin
```
