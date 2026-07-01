# Presentation Architecture Specification

**Project:** [Project name]
**Version:** 1.0
**Blueprint reference:** `docs/content-outline.md`, `docs/learning-objectives.md`
**Target rendering engine:** html-slides (Reveal.js)
**Framework version:** Presentation OS v0.2.0

PAS is the Experience Architecture for this presentation. It answers: *How will this experience be designed?* — not just the slides, but what people think, understand, remember, and can do afterward.

See `docs/presentation-architecture-specification.md` in the Presentation OS framework for the full PAS standard and contract model.

---

## 1. Capability Matrix

What attendees can *do* after each section — not what they will *know*, but what they will be able to *do*.

Frame as: *"By the end of [section], the audience can..."*

| Capability | Section | Priority | Audience Segment |
|---|---|---|---|
| [Can explain X to a colleague] | [Section] | T1 | All |
| [Can make decision Y confidently] | [Section] | T1 | All |
| [Can apply concept Z to their work] | [Section] | T2 | [Segment] |

**Priority:** T1 — Must achieve | T2 — Should achieve | T3 — Stretch

---

## 2. Learning Journey

The audience's emotional and cognitive arc from opening to close.

| Stage | Section | Target State | How It Is Achieved |
|---|---|---|---|
| Opening | [Section 1] | [e.g., Curious] | [Opening tension — an unresolved question] |
| [Stage 2] | [Section 2] | [Target state] | [Design mechanism] |
| ... | ... | ... | ... |
| Closing | [Final section] | [e.g., Ready to apply] | [Discussion the room leads] |

---

## 3. Decision Outcomes

What better decisions the audience will make because of each section.

| Section | Better Decisions Enabled |
|---|---|
| [Section name] | [What they will decide differently] |
| ... | ... |

---

## 4. Section Architecture

The teaching design for every section. Complete this before designing any slides.

| | [Section 1] | [Section 2] | [Section 3] |
|---|---|---|---|
| **Current understanding** | [What they already know or believe] | | |
| **Desired understanding** | [What they should believe by the end] | | |
| **Teaching strategy** | [Mystery / Analogy / Demo / Progressive reveal / Discussion / Data] | | |
| **Evidence of success** | [What they can say or do that proves it landed] | | |

---

## 5. Slide Inventory

The authoritative numbered list of every slide.

**Slide types:** Hero | Concept | Data | Diagram | Comparison | Demo | Callout | Discussion | Transition | Closing

| # | Slide Title / Argument | Purpose | Type | Section | Fragments | Notes |
|---|---|---|---|---|---|---|
| 01 | [Title slide] | Open the session | Hero | — | 0 | |
| 02 | [Section 1 opener] | Establish opening tension | Hero | 1 | 0 | |
| ... | | | | | | |

**Slide count:** [Total]

| Section | Slides | Slide Range |
|---|---|---|
| 1. [Name] | [N] | #01–#XX |
| 2. [Name] | [N] | #XX–#XX |

---

## 6. Component Inventory

| Component | Purpose | Slide(s) | Notes |
|---|---|---|---|
| [ComponentName] | [Purpose] | [#, #] | [Design notes] |

---

## 7. Diagram Inventory

**Rendering options:** Custom SVG | Mermaid | CSS animation | HTML+JS | Static image

| # | Diagram Name | Rendering | Reveal Strategy | Slide | Text Description |
|---|---|---|---|---|---|
| D1 | [Name] | [Rendering] | [e.g., 4-fragment progressive build] | [#] | [Full text description for accessibility] |

---

## 8. Animation & Interaction Inventory

**Animations** — valid purposes: Reveal control | Show relationship

| Slide | Element | Animation Type | Trigger | Purpose |
|---|---|---|---|---|
| [#] | [Element] | [Fragment type] | [Presenter advance] | [Purpose] |

**Interactions**

| Slide | Interaction Type | Tool / Mechanism | Fallback |
|---|---|---|---|
| [#] | [Demo / Discussion / Poll] | [Tool or verbal] | [Fallback + asset path] |

---

## 9. Rendering Strategy

| Setting | Value |
|---|---|
| Framework | Reveal.js |
| Theme | [e.g., Custom dark] |
| Slide size | [e.g., 1920×1080] |
| Navigation | [Linear / Grid] |
| Fragment default | [Fade / Slide] |
| Auto-animate | [Enabled / Disabled] |
| Speaker notes | [In presenter mode / Exported] |
| Export format | [HTML / PDF / Both] |

---

## 10. Timing Budget

| # | Section | Target Time | Slides | Notes |
|---|---|---|---|---|
| 1 | [Section name] | [X min] | [N] | |
| **Total** | | **[X–Y min]** | **[N]** | 80–90% of session time |

---

## 11. Accessibility Plan

| Requirement | Approach | Verified By |
|---|---|---|
| Color contrast (4.5:1 body / 3:1 large) | [Theme color choices] | `ui-ux-pro-max` review |
| Text descriptions for all diagrams | Authored in Diagram Inventory | `presentation-designer` review |
| Keyboard navigation | Reveal.js default + custom | Pre-delivery test |
| Speaker notes as standalone document | Complete prose in all notes | `speaker-coach` review |
| Legible at 50% scale | Typography minimums in theme | Manual check |

---

## PAS Completion Checklist

- [ ] **Capability Matrix:** T1 and T2 capabilities framed as "can do," not "will know"
- [ ] **Learning Journey:** Target state defined for every section
- [ ] **Decision Outcomes:** At least one better decision enabled per section
- [ ] **Section Architecture:** Current/desired/strategy/evidence complete for every section
- [ ] **Slide Inventory:** Every slide has number, type, purpose, section assignment
- [ ] **Capability coverage:** Every T1 and T2 capability maps to at least one slide
- [ ] **Diagram Inventory:** Every diagram has rendering decision and text description
- [ ] **Animation Inventory:** Every animation has a documented purpose
- [ ] **Interaction Inventory:** Every interactive moment has a verified fallback
- [ ] **Rendering Strategy:** All Reveal.js settings specified
- [ ] **Timing Budget:** Total within session target (80–90% of available time)
- [ ] **Accessibility Plan:** Complete
- [ ] **Internal review:** Sign-off received before prototype generation
