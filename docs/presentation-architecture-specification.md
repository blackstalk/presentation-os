# Presentation Architecture Specification (PAS)

PAS is the **Experience Architecture** for a presentation. It answers the question: *How will this experience be designed?*

Not just the slides. The experience:
- What the audience currently understands when they walk in
- What they will be able to *do* when they leave
- What better decisions they will make because of this session
- How their understanding will shift, section by section
- Only then: how the slides will communicate that journey

The slides are one implementation of the experience. PAS is the full experience design.

---

## What PAS Is

PAS is the architectural contract between content strategy (the blueprint) and any rendering engine (html-slides, PowerPoint, Reveal.js, or any future tool). It contains everything a builder needs to generate the presentation without making architectural decisions.

It specifies:
- Capability objectives — what attendees will be able to *do* afterward
- The audience's emotional and cognitive arc (Learning Journey)
- The business decisions each section enables (Decision Outcomes)
- The teaching strategy for each section (Section Architecture)
- Every slide, numbered and purposeful (Slide Inventory)
- Every diagram and how it will be rendered
- Every animation and why it exists
- Every interactive moment and its fallback
- The rendering strategy and technology configuration
- The timing budget per section
- The accessibility plan

---

## What PAS Is Not

- **Not the Blueprint.** The blueprint defines *what* the audience will learn. PAS defines *how*. If you find yourself writing content in PAS, it belongs in the blueprint.
- **Not an implementation.** PAS specifies; it does not build. When you find yourself writing CSS or Reveal.js configuration, stop — that belongs in the prototype.
- **Not a stakeholder document.** PAS is an internal architectural artifact. Stakeholders review the prototype, not the PAS.
- **Not a slide script.** PAS lists slide purpose and type; it does not write slide copy. Headlines and body content live in the slide itself.

---

## When PAS Is Created

PAS is created after the blueprint is complete and before any slide is built or generated. It is the output of Stage 4 in the project lifecycle.

```
Stage 3: Blueprint (what the audience will learn)
      ↓
Stage 4: PAS (how the experience will be designed)
      ↓
Stage 5: Internal Review
      ↓
Stage 6: Prototype (html-slides generates from PAS)
```

The `html-slides` skill receives PAS as its primary input. It should not need to interpret intent or make architectural decisions — those decisions are already made in PAS.

---

## The Contract Model

PAS formalizes the handoff between experience design and implementation:

```
content-strategist
        ↓
   Blueprint (what)
        ↓
  PAS — Experience Architecture (how)
   ├── Capability Matrix
   ├── Learning Journey
   ├── Decision Outcomes
   ├── Section Architecture
   ├── Slide Inventory
   ├── Component / Diagram / Animation / Interaction Inventories
   └── Rendering Strategy + Timing Budget + Accessibility Plan
        ↓
   html-slides
        ↓
 Reveal.js Prototype
```

**What Blueprint contributes to PAS:**
- Section structure and narrative arc
- Learning objectives and knowledge prerequisites per section
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
- What the audience should be able to do by the end

Those decisions are made in PAS, not delegated to the build tool.

---

## PAS Structure

A complete PAS contains thirteen sections, organized in four layers:

**Experience layer** (sections 1–4): The human design — capability, journey, outcomes, teaching strategy
**Architecture layer** (sections 5–8): The structural design — slides, components, diagrams, interactions
**Technical layer** (sections 9–11): The rendering design — strategy, timing, accessibility
**Handoff** (section 12): The implementation contract

---

### 1. Capability Matrix

What attendees will be able to *do* after each section — not what they will *know*, but what they will be able to *do*. Capability objectives are the most important section of PAS: they define what success looks like for every human in the room.

Frame as: *"By the end of [section], the audience can..."*

| Capability | Section | Priority | Audience Segment |
|---|---|---|---|
| [Can explain X to a colleague] | [Section] | T1 / T2 / T3 | All / A / B / C |
| [Can make decision Y] | [Section] | T1 | All |
| ... | | | |

**Priority tiers:**
- **T1 — Must achieve:** If most of the room can't do this, the session failed
- **T2 — Should achieve:** Target for the core audience segment
- **T3 — Stretch:** Achieved by the most engaged attendees

**Note on framing:** Capability objectives replace learning objectives. "Know the definition of AI Overviews" is a learning objective. "Explain to a colleague why their clicks might be declining even though their rankings are fine" is a capability objective. Only write capability objectives.

---

### 2. Learning Journey

The audience's emotional and cognitive arc from opening to close. The Learning Journey guides design decisions for visual weight, pacing, interaction density, and the moment of maximum complexity.

| Stage | Section | Target State | How It Is Achieved |
|---|---|---|---|
| Opening | [Section 1] | [e.g., Curious] | [e.g., Unresolved tension — a paradox they recognize] |
| ... | ... | ... | ... |
| Closing | [Final section] | [e.g., Ready to apply] | [e.g., Discussion they lead, not you] |

**Design implication:** If the Learning Journey calls for "Aha!" at a specific moment, the slides before it should withhold the complete picture — building toward the reveal rather than front-loading the conclusion.

---

### 3. Decision Outcomes

What better decisions the audience will make because of each section. Decision outcomes connect the experience to business value. Every section should enable at least one better decision.

| Section | Better Decisions Enabled |
|---|---|
| [Section name] | [What the audience will decide differently because of this section] |
| ... | ... |

Good decision outcomes are specific to this audience and this context — not generic learning goals. Bad: "Understand AI search." Good: "Marketing managers don't panic when they see declining clicks alongside stable rankings in Lauren's dashboard — they know what's causing it."

---

### 4. Section Architecture

The instructional design for each section — the teaching layer of PAS. For every section, answer four questions before designing any slides.

| | [Section 1] | [Section 2] | ... |
|---|---|---|---|
| **Current understanding** | What does the audience already know / believe about this topic? | | |
| **Desired understanding** | What should they believe or understand by the end? | | |
| **Teaching strategy** | Story, analogy, demo, diagram reveal, discussion, data? | | |
| **Evidence of success** | How will we know it landed? What can they say or do? | | |

**Teaching strategy options:**
- **Mystery** — open with an unresolved question; answer it by the section's close
- **Analogy** — introduce unfamiliar concept through a familiar parallel
- **Demo** — show the thing live; experience precedes explanation
- **Progressive reveal** — build the picture one layer at a time; audience synthesizes as it grows
- **Discussion** — let the room discover the answer; facilitator guides, doesn't tell
- **Data** — a number that shouldn't be possible given existing assumptions

Section Architecture is the input to the Slide Inventory. Every slide type choice and fragment decision should serve the section's teaching strategy.

---

### 5. Slide Inventory

The authoritative numbered list of every slide. This is the single source of truth for slide count, order, type, and purpose.

| # | Slide Title / Argument | Purpose | Type | Section | Fragments | Notes |
|---|---|---|---|---|---|---|
| 01 | [Title slide] | Open the session | Hero | — | 0 | |
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

**Slide count guidance:** A 75–90 minute workshop typically uses 35–50 slides. Demo slides and diagram reveal slides hold for longer — factor 2–4 minutes per demo slide.

---

### 6. Component Inventory

Reusable UI components this presentation requires. Specified once here; referenced by slide number in the Slide Inventory.

| Component | Purpose | Slide(s) | Implementation Notes |
|---|---|---|---|
| [ComponentName] | [Purpose] | [#, #] | [Design notes] |

---

### 7. Diagram Inventory

Every diagram, its rendering technology, and its reveal strategy. The rendering decision belongs in PAS — not in the build phase.

| # | Diagram Name | Rendering | Reveal Strategy | Slide | Text Description |
|---|---|---|---|---|---|
| D1 | [Name] | [Rendering] | [e.g., 6-fragment progressive build] | [#] | [Full text description for accessibility] |

**Rendering options:**

| Option | Use when |
|---|---|
| SVG (custom) | Diagram needs custom visual design; layout is non-standard |
| Mermaid | Flowcharts, sequence diagrams, simple relationship maps |
| CSS animation | Diagram builds in stages using simple transitions |
| HTML + JS | Diagram requires interactivity or data binding |
| Static image | Diagram is sourced externally and not rebuilt |

Every diagram requires a text description. Text descriptions are authored in PAS, not during the build phase.

---

### 8. Animation & Interaction Inventory

**Animations** — every animation, its trigger, and its purpose.

| Slide | Element | Animation Type | Trigger | Purpose |
|---|---|---|---|---|
| [#] | [Element] | [Fragment fade / slide / highlight] | [Presenter advance] | [Reveal control / Show relationship] |

**Valid purposes:** Reveal control (pace the disclosure of information) or Show relationship (make a connection visible). Any animation that serves neither purpose should be removed.

**Interactions** — every moment requiring audience participation or external tool access.

| Slide | Interaction Type | Tool / Mechanism | Fallback |
|---|---|---|---|
| [#] | [Live demo / Discussion / Poll] | [Tool name or verbal] | [Fallback description + asset path] |

Every interaction with an external dependency requires a documented fallback.

---

### 9. Rendering Strategy

The technical configuration of the presentation output.

| Setting | Value |
|---|---|
| Framework | Reveal.js |
| Theme | [e.g., Custom dark — based on Black] |
| Slide size | [e.g., 1920×1080] |
| Navigation | [Linear / Grid] |
| Fragment default | [Fade / Slide] |
| Auto-animate | [Enabled / Disabled] |
| Speaker notes | [In presenter mode / Exported separately] |
| Export format | [HTML / PDF / Both] |

---

### 10. Timing Budget

| # | Section | Target Time | Slides | Notes |
|---|---|---|---|---|
| 1 | [Section name] | [X min] | [N] | |
| **Total** | | **[X–Y min]** | **[N]** | Target 80–90% of session time |

**Timing rules:**
- Total target: 80–90% of the available session time
- Demo slides: add 2–3 minutes per live demo beyond slide count
- Discussion section: set aside 15–20% of total session time regardless of slide count

---

### 11. Accessibility Plan

| Requirement | Approach | Verified By |
|---|---|---|
| Color contrast (4.5:1 body / 3:1 large) | [Theme color choices] | `ui-ux-pro-max` review |
| Text descriptions for all diagrams | Authored in Diagram Inventory above | `presentation-designer` review |
| Keyboard navigation | [Reveal.js default + any custom] | Pre-delivery test |
| Speaker notes as standalone document | Complete prose in all notes | `speaker-coach` review |
| Legible at 50% scale | [Typography minimums enforced in theme] | Manual check |

---

### 12. Implementation Handoff

What the `html-slides` skill receives — a summary of the implementation contract.

**Inputs to html-slides:**
- This PAS document (the authoritative spec)
- `assets/diagrams/` — SVG files per Diagram Inventory
- `assets/images/` — demo fallback screenshots
- `assets/videos/` — screen recordings for demo fallbacks

**Build sequence for html-slides:**
1. Initialize Reveal.js with Rendering Strategy settings
2. Generate slides in Slide Inventory order
3. Apply fragment configuration per Animation Inventory
4. Embed diagrams per Diagram Inventory rendering decisions
5. Include speaker notes in complete prose per speaker-notes strategy
6. Verify keyboard navigation and accessibility plan requirements

**html-slides does not decide:**
- Slide count or order (Slide Inventory is authoritative)
- Whether to animate an element (Animation Inventory is authoritative)
- How to render a diagram (Diagram Inventory is authoritative)
- Section structure (Section Architecture is authoritative)

---

## PAS is Complete When

**Experience layer:**
- [ ] Capability Matrix: every T1 and T2 capability defined; framed as "can do," not "will know"
- [ ] Learning Journey: target state defined for every section
- [ ] Decision Outcomes: at least one business decision improvement per section
- [ ] Section Architecture: current/desired/strategy/evidence defined for every section

**Architecture layer:**
- [ ] Slide Inventory: every slide has a number, type, purpose, and section assignment
- [ ] Capability coverage: every T1 and T2 capability maps to at least one slide
- [ ] Diagram Inventory: every diagram has a rendering decision and a text description
- [ ] Animation Inventory: every animation has a documented purpose
- [ ] Interaction Inventory: every interactive moment has a verified fallback

**Technical layer:**
- [ ] Rendering Strategy: all Reveal.js settings specified
- [ ] Timing Budget: total within session target (80–90% of available time)
- [ ] Accessibility Plan: complete

**Gate:** Internal review complete before prototype generation begins.
