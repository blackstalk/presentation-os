# presentation-director

**Status:** Not yet implemented — vision document only.
**Category:** Director

---

## Purpose

`presentation-director` is the primary entry point for end-to-end presentation creation in Presentation OS.

It is an orchestrator, not an implementer. Its role is to coordinate the right specialists and integrations at the right time — and never to do specialist work itself.

---

## Responsibilities

- Receive presentation requests and translate them into a structured lifecycle workflow
- Guide the presentation through lifecycle phases (Brief → Architecture → Content → Design Review → Speaker Prep → Delivery → Retrospective)
- Delegate content strategy to `content-strategist`
- Delegate design review to `presentation-designer`
- Delegate diagram creation to `diagram-architect`
- Delegate speaker preparation to `speaker-coach`
- Delegate demo and interactive element creation to `demo-builder`
- Delegate output generation to the appropriate integration skill (`html-slides`, etc.)
- Coordinate cross-specialist review sequences (sequence, inputs, gates)
- Gate progression between phases based on review completion and P0 resolution

---

## What It Does NOT Do

The director should never be the most capable skill in any domain.

- Write slide content → `content-strategist`
- Review design → `presentation-designer`, `ui-ux-pro-max`
- Create diagrams → `diagram-architect`
- Coach speakers → `speaker-coach`
- Build demos → `demo-builder`
- Generate HTML → `html-slides` integration

If the director is doing specialist work, something is wrong with the skill boundary.

---

## Orchestration Model

```
presentation-director
  │
  ├── Phase 1: Brief
  │     └── Elicits audience, goal, constraints, success criteria
  │
  ├── Phase 2: Architecture
  │     └── content-strategist — narrative structure, section outline, story map
  │
  ├── Phase 3: Content
  │     └── content-strategist — slide-by-slide development, speaker notes
  │
  ├── Phase 4: Design Review
  │     ├── presentation-designer — hierarchy, pacing, consistency
  │     ├── ui-ux-pro-max integration — typography, spacing, accessibility
  │     └── diagram-architect — diagram creation from Phase 3 descriptions
  │
  ├── Phase 5: Speaker Prep
  │     └── speaker-coach — pacing, transitions, timing, discussion prompts
  │
  ├── Phase 6: Delivery
  │     └── html-slides integration — Reveal.js generation and validation
  │
  └── Phase 7: Retrospective
        └── Captures lessons and routes component patterns to components/
```

---

## Implementation Notes

When implementing this skill:

- The director is a thin routing layer — complex reasoning belongs in specialists
- Phase gating must be configurable (some projects abbreviate phases for low-stakes presentations)
- The director must be able to resume mid-workflow without starting over
- All specialist invocations should produce logs for retrospective review
- Error recovery: if a specialist returns P0 findings, the director routes back to the appropriate phase rather than proceeding

---

## See Also

- `docs/presentation-lifecycle.md` — the lifecycle phases this skill orchestrates
- `docs/architecture.md` — the full skills taxonomy
- `.claude/skills/specialists/` — the specialists this director coordinates
- `.claude/skills/integrations/` — the integrations this director invokes
