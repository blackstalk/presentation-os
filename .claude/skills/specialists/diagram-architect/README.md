# diagram-architect

**Status:** Not yet implemented — vision document only.
**Category:** Specialist

---

## Purpose

`diagram-architect` creates, reviews, and optimizes visual diagrams for presentations. It owns all diagrammatic communication — from simple flowcharts to complex architecture diagrams.

---

## Responsibilities

### Creation
- SVG diagrams (custom, precise, brand-consistent)
- Mermaid diagrams (flowchart, sequenceDiagram, graph, erDiagram)
- Reveal.js fragment sequences for progressive diagram reveal

### Review
- Assessing whether a proposed diagram communicates its intended idea
- Identifying simplification opportunities (remove elements that do not serve the argument)
- Flagging accessibility issues (contrast, text size, missing descriptions)

### Animation Concepts
- Designing progressive reveal sequences for complex diagrams
- Planning fragment order to match the verbal narrative
- Ensuring a complete static fallback exists for all animated diagrams

### Visual Explanations
- Converting conceptual descriptions into clear visual representations
- Choosing the right diagram type for each communication goal
- Ensuring all diagrams conform to `docs/diagram-standards.md`

### Reusable Patterns
- Identifying diagram patterns that recur across presentations
- Adding validated patterns to `components/` with usage documentation

---

## Diagram Type Selection

| Communication Goal | Recommended Type |
|---|---|
| Process or workflow | Mermaid flowchart or SVG flow |
| System components | SVG architecture diagram |
| Time-based interactions | Mermaid sequenceDiagram |
| Data comparison | SVG bar/column chart |
| Data over time | SVG line chart |
| Part-to-whole | SVG pie or treemap (use sparingly) |
| Conceptual relationships | Custom SVG |

---

## Quality Standards

Every diagram produced by this skill must:

- Conform to `docs/diagram-standards.md`
- Include a text description for accessibility (what it shows, not what it looks like)
- Be legible at 50% zoom
- Use at most 4 colors, all meeting WCAG AA contrast against their background
- Have a static fallback if it uses progressive reveal

---

## See Also

- `docs/diagram-standards.md` — detailed standards for all diagram types
- `docs/animation.md` — progressive reveal patterns for complex diagrams
- `docs/accessibility.md` — accessibility requirements for visual content
