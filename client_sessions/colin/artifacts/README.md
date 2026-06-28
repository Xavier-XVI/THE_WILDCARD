# Artifacts — Colin C. Thompson / Oligye Enterprises

> This folder is Xavier's reference copy of everything Colin shared during the discovery session. It is populated by Xavier after receiving the session output — not by Colin during the session.
>
> During the session, the agent maintains the artifact catalog internally and includes it in the session state file. Xavier uses that catalog to organize files here after delivery.

---

## What Goes Here

Every file, document, template, or recording Colin shared during discovery:

| File | Type | Received | Notes |
|---|---|---|---|
| `coaching_agreement_v2.pdf` | Contract | Round 0 | 3-page. 24hr cancellation, bi-weekly default, confidentiality |
| `intro_confirmation_email.txt` | Email template | Round 0 | Warm tone, Zoom link, no prep questions |
| *(additional files as received)* | | | |

---

## File Naming Convention

When saving artifacts here, use this format:

```
[round_received]_[descriptive_name].[extension]
```

Examples:
- `r0_coaching_agreement_v2.pdf`
- `r0_intro_confirmation_email.txt`
- `r2_calendly_screenshot.png`
- `r3_session_notes_example.docx`

---

## How to Use These Files

Artifacts here are the **source of truth** behind the output specs. When the builder spec says `[NOT CONFIRMED — see artifact]`, the answer is likely in one of these files.

The builder should reference these files alongside `samples/sample_output_builder.md`. Do not build from the spec alone when originals are available.

---

## How This Folder Gets Populated

1. Colin completes the discovery session (or a session block)
2. The agent generates the session state + artifact catalog on `SAVE SESSION`
3. Colin emails the session state to Xavier
4. Xavier saves each artifact Colin shared into this folder using the naming convention above
5. Xavier updates the table at the top of this README as files are added
