# ui-ux-pro-max Integration Skill

**Status:** Not yet implemented — vision document only.
**Category:** Integration

---

## Purpose

This integration skill bridges Presentation OS and the `ui-ux-pro-max` Claude Code skill (design critique and visual polish).

It prepares presentation content for design review, provides platform standards as review criteria, and validates that review findings are actionable within the Presentation OS severity framework.

---

## Delegation Contract

**Input received from director:**

| Input | Notes |
|---|---|
| Full slide content | Visual format or detailed description of every slide |
| Design intent | Audience type, tone, formality level |
| Brand constraints | Color palette, typefaces, client requirements |
| Specific focus areas | Any areas to concentrate review attention |

**Passed to ui-ux-pro-max skill:**

- Presentation content in reviewable format
- Presentation OS design standards as explicit review criteria:
  - WCAG AA contrast minimums
  - Typographic hierarchy rules
  - Whitespace and layout principles
  - Color philosophy (semantic, maximum 4 colors)
- Design intent and audience context
- Specific concerns if any

**Validated in output before returning to director:**

- [ ] All findings categorized by P0/P1/P2 severity
- [ ] Accessibility findings explicitly labeled
- [ ] Every finding includes a specific recommendation (not just an observation)
- [ ] Strengths section present

**Returned to director:**

- Structured review with P0/P1/P2 findings
- Strengths to preserve
- Summary of accessibility compliance status

---

## Phase 4 Review Sequence

Within Phase 4, this integration runs second:

1. `presentation-designer` review (narrative, hierarchy, pacing)
2. **`ui-ux-pro-max` integration** (typography, spacing, color, accessibility) ← this skill
3. `diagram-architect` review (diagram creation and review)
4. Resolve all P0 and P1 findings

---

## See Also

- `docs/tooling/ui-ux-pro-max.md` — full integration guide
- `docs/accessibility.md` — the accessibility standards this review enforces
- `.claude/skills/specialists/presentation-designer/README.md` — the complementary specialist
