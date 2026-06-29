# Diagram Standards

Diagrams are a presentation superpower when used well and a source of confusion when used poorly.

---

## When to Use a Diagram

Use a diagram when:
- The **relationship between elements** is the point — not the elements themselves
- A process has steps that build on each other in non-obvious ways
- Scale, proportion, or distribution communicates differently than words can
- The audience needs to orient in a system before details are meaningful

Do not use a diagram when:
- A sentence would communicate the same information more clearly
- The diagram is decorative (visual interest with no communicative function)
- The complexity of the diagram exceeds what the audience can absorb in the available time

When in doubt, try writing the insight as a sentence first. If the sentence is sufficient, skip the diagram.

---

## Diagram Type Selection

| Communication Goal | Recommended Type | Tool |
|---|---|---|
| Process or workflow | Flowchart | Mermaid `flowchart` or SVG |
| System components | Architecture diagram | SVG (preferred), Mermaid `graph` |
| Time-based interactions | Sequence diagram | Mermaid `sequenceDiagram` |
| Data comparison | Bar/column chart | SVG or chart component |
| Data over time | Line chart | SVG or chart component |
| Part-to-whole | Pie or treemap | SVG — use sparingly |
| Conceptual relationships | Custom visual | SVG |

---

## SVG vs. Mermaid

**Use SVG when:**
- Custom visual styling is required (brand colors, precise layout)
- The diagram contains non-standard elements (icons, images, custom shapes)
- Pixel-level precision is needed
- The diagram will be reused across presentations as a component

**Use Mermaid when:**
- Speed matters more than visual precision
- The diagram is a quick sketch to validate structure before SVG investment
- Standard diagram types (flowchart, sequence) fit the use case without modification

---

## Visual Standards for All Diagrams

### Color
- Use semantic color: green = positive/healthy, red = negative/error/risk, blue = neutral/informational, yellow/amber = warning
- Maximum 4 colors per diagram
- All color pairs must meet WCAG AA contrast against their background

### Typography
- Label text minimum: 14px within diagrams
- Use the presentation's primary typeface for all diagram text
- Labels must be legible at 50% zoom

### Spacing
- Use a consistent base unit — 8px or 16px grid
- Never allow elements to touch each other or the frame edge
- Consistent padding inside grouped containers

### Density
- If a diagram takes longer than 30 seconds to orient to, it is too complex
- Break complex diagrams into a reveal sequence (fragments) or multiple slides
- Prefer showing the same insight with fewer elements

---

## Sequence Diagram Guidelines

- Limit to 4–5 participants. More than that requires splitting into multiple diagrams
- Label every arrow that is not obvious from context
- Group related message sequences with `loop`, `alt`, or `opt` blocks

---

## Architecture Diagram Guidelines

- Group related components visually (bounded boxes, shared backgrounds)
- Use consistent iconography — never mix metaphors
- Include a legend if using custom symbols or color coding
- Show data flow direction with arrows
- Label the type of connection (HTTP, event, queue) not just its existence

---

## Progressive Reveal for Complex Diagrams

Complex diagrams benefit from building piece by piece as the speaker narrates.

**Standard pattern:**
1. Show the full diagram structure at reduced opacity (40%)
2. Use fragments to reveal components in narrative order
3. Highlight the active component; dim the others
4. Final fragment restores full opacity

See `docs/animation.md` for implementation guidance.

---

## Text Descriptions (Accessibility)

Every diagram must have a text description for accessibility.

The description communicates what the diagram shows — not what it looks like.

**Correct:** "Data flow from user input through validation, processing, and storage, with error paths returning to the validation layer for retry."

**Incorrect:** "Blue boxes connected by arrows on a white background."

Place descriptions in speaker notes. For HTML presentations, also include as an `aria-label` or adjacent `<p>` element.
