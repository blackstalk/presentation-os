# ui-ux-pro-max Integration Guide

## What It Is

`ui-ux-pro-max` is a Claude Code skill specializing in visual design critique, UX review, and design polish. It brings deep expertise in typography, spacing, visual hierarchy, accessibility, and interaction design.

Presentation OS uses it as a design reviewer in Phase 4, after the narrative and presentation-level review (`presentation-designer`) is complete.

---

## Responsibilities

`ui-ux-pro-max` owns:

- Visual hierarchy critique (primary/secondary/supporting element relationships)
- Typography assessment (scale, weight, tracking, legibility)
- Spacing and layout analysis (grid alignment, breathing room, density)
- Color and contrast review (WCAG compliance, semantic use, palette coherence)
- Accessibility verification (contrast ratios, text alternatives, motion safety)
- Interaction design feedback (keyboard nav, focus states, hover vs. click)
- Polish and refinement recommendations (consistency, finishing details)

---

## What ui-ux-pro-max Does NOT Own

- Slide content or narrative decisions → Presentation OS content workflow
- Presentation generation or HTML output → `html-slides`
- Speaker coaching → `speaker-coach`
- Diagram creation → `diagram-architect`
- Whether the story is compelling → `presentation-designer`, `content-strategist`

---

## When to Use

Use `ui-ux-pro-max` during **Phase 4: Design Review**, specifically:

- After narrative architecture is validated and slide content is complete
- After the `presentation-designer` review is complete
- Before any final output is generated
- When a specific design decision requires expert visual judgment
- When formal accessibility compliance verification is needed

---

## When NOT to Use

Do not use `ui-ux-pro-max`:

- Before slide content is complete — design critique of empty or placeholder slides is not useful
- Before `presentation-designer` has reviewed narrative quality — fix story issues before visual ones
- As a substitute for `presentation-designer`:
  - `presentation-designer` reviews narrative, presentation-level hierarchy, and communication effectiveness
  - `ui-ux-pro-max` reviews visual, typographic, and UX-level quality
  - Both reviews are needed; they are not interchangeable
- For decisions about what content to include — those belong in content strategy

---

## Delegation Contract

Presentation OS provides `ui-ux-pro-max` with:

| Input | Notes |
|---|---|
| Full slide content | Visual format or detailed description of every slide |
| Design intent | Audience type, tone, formality level |
| Brand constraints | Color palette, typefaces, client requirements |
| Platform standards | Reference to Presentation OS accessibility and design standards |
| Specific concerns | Any areas to focus review attention |

`ui-ux-pro-max` returns findings organized by severity:

| Severity | Definition |
|---|---|
| **P0** | Must fix before delivery — accessibility failures, critical hierarchy breaks |
| **P1** | Should fix before delivery — significant issues with clear solutions |
| **P2** | Consider fixing — improvements with tradeoffs worth evaluating |
| **Strengths** | What is working well and should be preserved |

---

## Call Flow

```
presentation-director
  └── ui-ux-pro-max integration skill
        ├── Provides platform standards as review criteria
        ├── Structures presentation content for review
        └── ui-ux-pro-max skill
              └── Design critique and accessibility review
```

---

## Phase 4 Review Sequence

Within Phase 4, reviews run in this order:

1. `presentation-designer` — narrative, pacing, communication effectiveness
2. `ui-ux-pro-max` — typography, spacing, color, accessibility
3. `diagram-architect` — diagram creation and review
4. Resolve all P0 and P1 findings before proceeding to Phase 5
