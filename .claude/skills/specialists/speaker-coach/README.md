# speaker-coach

**Status:** Not yet implemented — vision document only.
**Category:** Specialist

---

## Purpose

`speaker-coach` prepares speakers for live delivery. It reviews presentations from the speaker's perspective — not the audience's visual experience, but the speaker's experience delivering it.

---

## Responsibilities

### Pacing
- Reviewing slide timing estimates against content density
- Flagging slides likely to be rushed or over-dwelt
- Recommending where to add pauses or breathing points

### Transitions
- Writing verbal transitions between slides and sections
- Ensuring transitions are logical, not merely sequential ("and now...")
- Crafting transitions that advance the argument rather than just marking progress

### Discussion Prompts
- Creating audience engagement prompts for appropriate moments
- Preparing check-in questions for long presentations
- Designing Q&A warm-up prompts that generate productive discussion

### Timing
- Estimating total presentation time based on content and pacing
- Flagging timing risk — presentations likely to run over
- Recommending which sections to cut or compress if timing is tight

### Audience Engagement
- Identifying moments where audience attention is likely to drop
- Recommending engagement techniques (questions, pauses, interactives)
- Reviewing the closing for clarity and call-to-action effectiveness

### Speaker Confidence
- Identifying slides likely to cause speaker hesitation (too complex, too data-heavy)
- Recommending simplification or additional speaker notes where needed
- Flagging "apology slides" — slides the speaker will need to apologize for

---

## Output Format

`speaker-coach` returns:

1. **Timing estimate** — Total time and per-section breakdown
2. **Pacing notes** — Specific slides flagged for timing issues, with recommended adjustments
3. **Transition drafts** — Suggested verbal transitions for each slide or section break
4. **Engagement opportunities** — Recommended moments for audience interaction with specific prompts
5. **P0 risks** — Any issues that could derail delivery (unclear slide, missing fallback, impossible timing)

---

## The Apology Slide Rule

An apology slide is any slide the speaker is likely to apologize for during delivery ("sorry, this is a lot" or "I know this is hard to read").

`speaker-coach` flags every apology slide. The resolution is never to accept the apology — it is to fix the slide.

---

## See Also

- `docs/speaker-guidance.md` — the full speaker philosophy this skill applies
- `docs/storytelling.md` — narrative principles that inform transition design
- `docs/presentation-lifecycle.md` — where this skill fits (Phase 5)
