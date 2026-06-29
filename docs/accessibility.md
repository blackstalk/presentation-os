# Accessibility

Presentation OS treats accessibility as a quality standard, not a compliance checklist.

A presentation that cannot be understood or experienced by part of its audience has failed.

---

## Color and Contrast

All text in presentations must meet WCAG AA minimum contrast ratios:

| Text Type | Minimum Contrast Ratio |
|---|---|
| Body text (< 18pt regular, < 14pt bold) | 4.5:1 |
| Large text (≥ 18pt regular, ≥ 14pt bold) | 3:1 |
| UI components and meaningful icons | 3:1 |

**Never use color alone to convey meaning.** Every color-based distinction must also be conveyed through shape, pattern, label, or position. This ensures the presentation is legible for colorblind viewers.

Recommended verification tools:
- APCA contrast calculator
- WebAIM Contrast Checker
- Browser DevTools accessibility panel

---

## Visual Content

Every visual element that conveys information must have a text alternative.

**Diagrams:** Provide a text description of what the diagram communicates — not a description of what it looks like.
- Correct: "Flow showing how user data moves from collection through validation to storage, with error paths returning to validation."
- Incorrect: "Blue boxes connected by arrows."

**Charts and graphs:** Provide the key insight as text. The visual amplifies; the text delivers. Include axis labels and data source.

**Decorative images:** Images used purely for visual interest (backgrounds, abstract textures) do not require alt text. All informational images always do.

---

## Typography

Legibility at scale is a non-negotiable requirement. Test every presentation at 50% zoom — this simulates stream viewers, screenshot readers, and attendees far from the screen.

- Body text minimum: 24px for projected/screen presentations
- Caption text minimum: 18px
- Never use fonts below 16px in any context
- Avoid condensed or decorative typefaces for body content — they sacrifice legibility for style
- Test on a dark background and a light background if the presentation uses both

---

## Motion and Animation

Some audience members experience motion sensitivity (vestibular disorders, ADHD, migraines).

**Rules:**
- Avoid animations that flash or flicker at any frequency
- Prefer subtle transitions (fade, appear) over aggressive ones (spin, bounce, zoom)
- Ensure all animated content is also accessible in a static state — the argument does not depend on seeing the animation
- Do not use autoplaying video or animation as a primary content mechanism

When in doubt, choose the calmer option.

---

## Keyboard and Navigation

For any interactive presentation (HTML-based):

- All navigation must be keyboard-accessible
- Focus indicators must be visible (never `outline: none` without an alternative)
- Interactive elements must have clear focus states
- Tab order must follow the visual and logical reading order
- Touch navigation must work for mobile viewers

---

## Speaker Notes as Standalone Document

Speaker notes serve a dual purpose:

1. **For the speaker:** delivery reminders, transitions, timing cues
2. **For accessibility:** a complete text version of what is being communicated verbally

Speaker notes must be written so that a person who cannot see the slides — or who is reading a transcript — can understand the full presentation through notes alone.

This is good speaker preparation that also serves accessibility. It is not additional work; it is the same work done well.

---

## Pre-Delivery Checklist

Before any presentation milestone, verify:

- [ ] All color pairs meet WCAG AA contrast ratios
- [ ] Color is not the only way any information is conveyed
- [ ] All diagrams, charts, and images have text descriptions
- [ ] All text is legible at 50% zoom
- [ ] No animations cause discomfort for motion-sensitive viewers
- [ ] Speaker notes function as a standalone document
- [ ] Keyboard navigation works for all interactive elements (HTML presentations)
