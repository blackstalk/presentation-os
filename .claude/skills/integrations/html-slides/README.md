# html-slides Integration Skill

**Status:** Not yet implemented — vision document only.
**Category:** Integration

---

## Purpose

This integration skill bridges Presentation OS and the `html-slides` Claude Code skill (Reveal.js generation).

It translates Presentation OS content, design standards, and animation concepts into `html-slides` instructions — and validates that the generated output meets Presentation OS standards before returning it to the director.

---

## Relationship to the Installed html-slides Skill

The installed `html-slides` skill (at `.claude/skills/html-slides/SKILL.md`) is the Reveal.js implementation engine. It knows how to generate HTML presentations.

This integration skill is the Presentation OS wrapper around it:
- The `html-slides` skill handles the **how** (Reveal.js markup, structure, features)
- This integration handles the **what** (content translation) and **whether** (standards validation)

---

## Delegation Contract

**Input received from director:**

| Input | Format |
|---|---|
| Complete slide content | Headlines, body text, speaker notes for every slide |
| Design tokens | Hex color values, typeface names, size scale |
| Animation sequences | Fragment order and fragment classes per slide |
| Transition preferences | Type and speed (global or per-section) |
| Accessibility requirements | Alt text and aria labels for all non-decorative visual content |

**Passed to html-slides skill:**

- Slide content structured in Reveal.js-compatible format
- Theme and styling instructions (or custom CSS from design tokens)
- Fragment markup specifications
- Speaker note content in `<aside class="notes">` format

**Validated in output before returning to director:**

- [ ] Speaker notes present for every slide
- [ ] All non-decorative visuals have aria labels or alt text
- [ ] Fragment sequences match design-reviewed order
- [ ] No inline styles overriding the design token system
- [ ] Keyboard navigation not disabled
- [ ] File is self-contained or CDN dependencies are documented

**Returned to director:**

- Generated HTML file(s)
- Validation report (standards met / issues found)

---

## When This Integration Runs

Phase 6: Delivery — after all content, design review, and speaker prep phases are complete.

This integration must not run before Phase 4 (Design Review) is complete.

---

## See Also

- `docs/tooling/html-slides.md` — full integration guide
- `.claude/skills/html-slides/SKILL.md` — the installed skill being wrapped
