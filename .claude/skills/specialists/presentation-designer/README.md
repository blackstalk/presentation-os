# presentation-designer

**Status:** Not yet implemented — vision document only.
**Category:** Specialist

---

## Purpose

`presentation-designer` reviews presentations for narrative quality, visual design, and communication effectiveness. It operates at the presentation level — the story, the slide sequence, the overall communication arc.

It is the first design review step in Phase 4 and runs before `ui-ux-pro-max`.

---

## Focus Areas

### Hierarchy
- Does each slide have a single dominant element?
- Is the primary idea immediately clear without reading every word?
- Does the slide communicate one idea, or does it compete with itself?

### Pacing
- Are dense slides balanced with simpler slides?
- Is the fragment and reveal sequence well-designed — does information appear in the right order?
- Are complex ideas given sufficient space, or are they rushed?

### Whitespace
- Is there sufficient breathing room on each slide?
- Do elements have clear spatial relationships that communicate grouping?
- Does the layout feel crowded or open?

### Readability
- Is text legible at projection scale?
- Are font sizes appropriate for the venue and format?
- Is line length controlled for readability?

### Typography
- Is the typographic hierarchy consistent throughout?
- Are weight and size used to communicate importance — not decoration?
- Is the typeface appropriate for the audience and tone?

### Accessibility
- Do color choices meet WCAG AA standards? (Detailed audit is `ui-ux-pro-max`'s domain)
- Does the presentation work without color, for colorblind viewers?
- Are all visual elements described in speaker notes?

### Storytelling
- Does each headline make an argument, not just a label?
- Does the presentation open with tension?
- Does it close with clarity and a call to action?
- Does every slide earn its place in the story?
- Would any slides pass the cut test (would removing them change audience understanding)?

### Consistency
- Is visual language consistent throughout?
- Are component patterns (callouts, diagrams, data visualizations) applied consistently?
- Do section breaks feel deliberate and appropriately weighted?

---

## Output Format

`presentation-designer` returns a review organized by:

1. **P0 findings** — Must fix before proceeding (narrative breaks, accessibility failures, misleading content)
2. **P1 findings** — Should fix before proceeding (significant issues with clear improvements available)
3. **P2 findings** — Consider fixing (refinements with tradeoffs)
4. **Strengths** — What is working well and should be preserved

Every finding includes: what is wrong, why it matters, and a specific recommendation for how to address it.

---

## Relationship to ui-ux-pro-max

These two skills are complementary, not redundant.

| `presentation-designer` | `ui-ux-pro-max` |
|---|---|
| Presentation-level: narrative flow, slide sequence, communication effectiveness | Design-level: typography, spacing, color systems, accessibility tooling |
| Runs first in Phase 4 | Runs second in Phase 4 |
| Story and structure | Visual and UX |

Both reviews are required before Phase 5.

---

## See Also

- `docs/storytelling.md` — the narrative framework this skill applies
- `docs/accessibility.md` — the accessibility standards this skill checks
- `docs/presentation-lifecycle.md` — where this skill fits in the lifecycle
