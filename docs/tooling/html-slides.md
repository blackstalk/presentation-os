# html-slides Integration Guide

## What It Is

`html-slides` is a Claude Code skill that generates Reveal.js HTML presentations. It handles the technical implementation of web-based slides — markup, structure, animations, speaker notes, transitions, and code highlighting.

The installed skill lives at `.claude/skills/html-slides/`. Presentation OS accesses it through the `html-slides` integration skill (`.claude/skills/integrations/html-slides/`), which handles translation and validation.

---

## Responsibilities

The `html-slides` skill owns:

- Reveal.js HTML structure and generation
- Presentation file scaffolding
- Speaker notes markup (`<aside class="notes">`)
- Fragment and animation implementation
- Slide transitions (type and speed)
- Code highlighting blocks with line-number support
- Background treatments (color, image, gradient, video)
- Presentation export and packaging

---

## What html-slides Does NOT Own

- Narrative architecture or storytelling decisions → `content-strategist`
- Design critique or visual hierarchy review → `presentation-designer` or `ui-ux-pro-max`
- Speaker coaching or pacing guidance → `speaker-coach`
- Diagram design or creation → `diagram-architect`
- What content goes on any slide → Presentation OS content workflow
- Whether the content meets platform standards → Presentation OS integration skill validates

---

## When to Use

Use `html-slides` when:

- The presentation output format is HTML / browser-based (Reveal.js)
- All content, design review, and speaker prep phases are complete (Phase 6: Delivery)
- You need a Reveal.js file generated from finalized slide content

---

## When NOT to Use

Do not use `html-slides` when:

- Slide content has not completed design review (design review must come first)
- The presentation format is not HTML-based — use the appropriate tool for PowerPoint, Keynote, PDF, etc.
- You are still in content or architecture phases — `html-slides` is a delivery tool, not a drafting tool
- You are making content decisions — those belong in the content phases

---

## Delegation Contract

Presentation OS provides `html-slides` with:

| Input | Notes |
|---|---|
| Complete slide content | Headlines, body content, speaker notes for every slide |
| Design tokens | Color palette (hex values), typeface names, size scale |
| Animation sequences | Fragment order and fragment classes for each slide |
| Transition preferences | Type and speed per section or globally |
| Accessibility requirements | Alt text, aria labels for all visual content |

`html-slides` returns:

| Output | Notes |
|---|---|
| Reveal.js HTML file | Self-contained or CDN-linked |
| Validation report | Any standards issues found in generation |

---

## Call Flow

```
presentation-director
  └── html-slides integration skill
        ├── Translates Presentation OS content to Reveal.js structure
        ├── Validates accessibility attributes are present
        └── html-slides skill
              └── Generates Reveal.js HTML
```

---

## Standards Enforced by the Integration

The `html-slides` integration validates that generated output includes:

- Speaker notes for every slide
- Alt text / aria labels for all non-decorative visual content
- Correct fragment sequences matching the design review
- No inline styles that override the design token system
- Keyboard navigation support (default in Reveal.js; verify it is not disabled)
