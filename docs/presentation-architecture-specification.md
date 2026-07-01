# Presentation Architecture Specification (PAS)

The architectural contract between the blueprint (what the audience will learn) and any rendering engine (html-slides, PowerPoint, Reveal.js, Next.js, or any future tool).

PAS is where planning becomes buildable. A well-written PAS makes the implementation phase fast, predictable, and reviewer-independent.

---

## What PAS Is

PAS is the architectural drawing of a presentation. It answers the question: **How will this experience be constructed?**

It specifies:
- Every slide, numbered and purposeful
- The audience's emotional and cognitive arc from opening to close
- Every diagram and how it will be rendered
- Every animation and why it exists
- Every interactive moment and its fallback
- The rendering strategy and technology configuration
- The timing budget per section
- The accessibility plan
- The handoff contract for the implementation skill

---

## What PAS Is Not

- **Not the Blueprint.** The blueprint defines what the audience will learn. PAS defines how. If you find yourself writing content in PAS, it belongs in the blueprint.
- **Not an implementation.** PAS specifies; it does not build. When you find yourself writing CSS or Reveal.js configuration, stop — that belongs in the prototype.
- **Not a stakeholder document.** PAS is an internal architectural artifact. Stakeholders review the prototype, not the PAS.
- **Not a slide script.** PAS lists slide purpose and type; it does not write slide copy. Headlines and body content live in the slide itself.

---

## When PAS Is Created

PAS is created after the blueprint is complete and before any slide is built or generated. It is the output of Stage 4 in the project lifecycle.

```
Stage 3: Blueprint (what)
      ↓
Stage 4: PAS (how)
      ↓
Stage 5: Internal Review
      ↓
Stage 6: Prototype (html-slides generates from PAS)
```

The `html-slides` skill receives PAS as its primary input. It should not need to interpret intent or make architectural decisions — those are already made.

---

## The Contract Model

PAS formalizes the handoff between content strategy and implementation:

```
content-strategist  →  PAS  →  html-slides  →  Reveal.js Prototype
```

**What Blueprint contributes to PAS:**
- Section structure and narrative arc
- Learning objectives per section
- Identified diagrams, demos, and data moments
- Terminology and concept definitions

**What PAS specifies for html-slides:**
- Numbered slide inventory (purpose, type, section, content summary)
- Diagram rendering decisions (SVG, Mermaid, CSS animation, etc.)
- Fragment/reveal sequences per slide
- Theme, navigation, slide size, and Reveal.js configuration
- Animation triggers and purposes
- Interaction patterns and fallbacks

**What html-slides never has to decide:**
- Whether to use animations
- How many slides a section needs
- What type of diagram to render
- When to use fragments vs. full-slide reveals

Those decisions are made in PAS, not delegated to the build tool.

---

## PAS Structure

A complete PAS contains ten sections.

---

### 1. Learning Journey

The audience's emotional and cognitive arc — not just slide order. The Learning Journey guides every design decision: visual weight, pacing, interaction density, moment of maximum complexity.

| Stage | Target Audience State | How It Is Achieved |
|---|---|---|
| Opening | Curious | Open with an unresolved tension — a mystery, a paradox, or a statistic that doesn't make sense yet |
| [Section Name] | [Target state] | [Design mechanism] |
| ... | ... | ... |
| Closing | Ready to apply | Discussion prompt that invites the room to own the answer |

**Design implication:** If the Learning Journey calls for "Aha!" at a specific moment, the slides leading to it should withhold the complete picture — building toward the reveal rather than front-loading the conclusion.

---

### 2. Slide Inventory

The authoritative numbered list of every slide in the presentation. This is the single source of truth for slide count, order, type, and purpose.

| # | Slide Title | Purpose | Type | Section | Fragment Count | Notes |
|---|---|---|---|---|---|---|
| 01 | ... | ... | Hero | 1 | 0 | ... |
| 02 | ... | ... | Concept | 1 | 2 | ... |
| ... | | | | | | |

**Slide types:**

| Type | When to use |
|---|---|
| Hero | Section opener — establishes section tension or theme |
| Concept | Explains a single idea |
| Data | Presents a chart, metric, or statistic |
| Diagram | Shows a visual model, map, or relationship |
| Comparison | Side-by-side contrast of two things |
| Demo | Dedicated moment for a live or recorded demo |
| Callout | Emphasizes a single statement, quote, or stat |
| Discussion | Invites audience participation |
| Transition | Bridges two sections — brief, often text-only |
| Closing | Final call to action, summary, or next step |

---

### 3. Learning Objectives Map

Maps learning objectives from the blueprint to specific slides. Ensures every objective from the blueprint is addressed somewhere in the presentation.

| Objective | Tier | Addressed in Slide(s) |
|---|---|---|
| ... | T1 / T2 / T3 | #, # |

A learning objective with no slide assignment is a gap. A slide with no learning objective is a candidate for the cut test.

---

### 4. Component Inventory

Reusable UI components this presentation requires. Each component is specified once here; referenced by slide number in the slide inventory.

| Component | Purpose | Slide(s) | Implementation Notes |
|---|---|---|---|
| MetricCard | Display a single metric with label and trend | 18, 20, 22 | Dark background, number + label |
| ... | | | |

---

### 5. Diagram Inventory

Every diagram, its rendering technology, and its reveal strategy. The rendering decision belongs in PAS — not in the build phase.

| # | Diagram Name | Rendering | Reveal Strategy | Slide | Text Description |
|---|---|---|---|---|---|
| D1 | Modern Search Ecosystem | Custom SVG | 6-fragment progressive build | 14 | "Five-layer diagram showing..." |
| D2 | Zero-Click Flow | SVG / Mermaid | 3-fragment branch reveal | 22 | "Flowchart showing..." |
| ... | | | | | |

**Rendering options and when to use each:**

| Option | Use when |
|---|---|
| SVG (custom) | Diagram needs custom visual design; layout is non-standard |
| Mermaid | Flowcharts, sequence diagrams, simple relationship maps |
| CSS animation | Diagram builds in stages using simple transitions |
| HTML + JS | Diagram requires interactivity or data binding |
| Static image | Diagram is sourced externally and not rebuilt |

Every diagram requires a text description for accessibility. Text descriptions are authored in PAS, not during the build phase.

---

### 6. Animation Inventory

Every animation in the presentation: what animates, its trigger, and its purpose.

| Slide | Element | Animation Type | Trigger | Purpose |
|---|---|---|---|---|
| 14 | Ecosystem layer 2 | Fragment fade-in | Presenter advance | Reveal control — pace the build |
| ... | | | | |

**Valid purposes (from `docs/animation.md`):**
- Reveal control — pace the disclosure of information
- Show relationship — make a connection visible

Any animation that serves neither purpose should be removed from the inventory.

---

### 7. Interaction Inventory

Every moment that requires audience interaction or special presenter handling.

| Slide | Interaction Type | Mechanism | Fallback |
|---|---|---|---|
| 30 | Live demo | Browser — Perplexity.ai | Screenshot at `assets/images/screenshot-perplexity.png` |
| 35 | Discussion prompt | Verbal — open question to room | Skip if time constrained |
| ... | | | |

Every interaction with an external dependency (network, live tool, third-party service) requires a documented fallback.

---

### 8. Rendering Strategy

The technical configuration of the presentation output.

**Framework:** Reveal.js
**Theme:** [Specify — e.g., custom dark, based on Moon or Black]
**Slide size:** [e.g., 1920×1080 or 1280×720]
**Navigation:** [Linear / Grid / Both]
**Fragment default behavior:** [Fade / Slide / Highlight]
**Auto-animate:** [Enabled / Disabled]
**Speaker notes:** [Visible in presenter mode / Exported separately]
**Export format:** [HTML / PDF / Both]

---

### 9. Timing Budget

Time allocation per section. The PAS timing budget is the target that the speaker rehearses against.

| # | Section | Target Time | Slide Count | Notes |
|---|---|---|---|---|
| 1 | ... | X min | Y | ... |
| **Total** | | **X–Y min** | **N** | |

**Timing budget rules:**
- Total target should be 80–90% of the available session time (leave room for natural pacing and questions within sections)
- Sections with demos run longer than slide count suggests — add 2–3 min per live demo

---

### 10. Accessibility Plan

How this presentation meets WCAG AA across every slide.

| Requirement | Approach | Verified by |
|---|---|---|
| Color contrast (4.5:1 body / 3:1 large) | Theme color choices enforced in CSS | `ui-ux-pro-max` review |
| Text descriptions for all diagrams | Authored in Diagram Inventory above | `presentation-designer` review |
| Keyboard navigation | Reveal.js default + custom interactive slides | Pre-delivery test |
| Speaker notes as standalone doc | All notes authored in complete prose | `speaker-coach` review |
| Legible at 50% scale | Typography minimums enforced in theme | Manual check |

---

## PAS Output

A completed PAS is submitted to the `html-slides` skill as the build specification. The skill renders each slide according to its type, fragment count, animation triggers, and rendering strategy — without needing to make architectural decisions.

**PAS is done when:**
- Every slide in the inventory has a type, purpose, and section assignment
- Every learning objective maps to at least one slide
- Every diagram has a rendering decision and a text description
- Every animation has a documented purpose
- Every interactive moment has a fallback
- The timing budget totals within the session target
- The accessibility plan is complete
