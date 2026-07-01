# Presentation Architecture Specification

**Project:** [Project name]
**Version:** 1.0
**Blueprint reference:** `docs/content-outline.md`, `docs/learning-objectives.md`
**Target rendering engine:** html-slides (Reveal.js)
**Framework version:** Presentation OS v0.2.0

See `docs/presentation-architecture-specification.md` in the Presentation OS framework for the full PAS standard and contract model.

---

## 1. Learning Journey

The audience's emotional and cognitive arc from opening to close. Every design decision in this PAS should serve the target states below.

| Stage | Target Audience State | How It Is Achieved |
|---|---|---|
| Opening | [e.g., Curious] | [e.g., Open with an unresolved tension or paradox] |
| [Section 2 name] | [Target state] | [Design mechanism] |
| [Section 3 name] | [Target state] | [Design mechanism] |
| [Section N name] | [Target state] | [Design mechanism] |
| Closing | [e.g., Ready to apply] | [e.g., Discussion prompt that invites the room to own the answer] |

---

## 2. Slide Inventory

The authoritative numbered list of every slide. This is the single source of truth for slide count, order, type, and purpose.

**Slide types:** Hero | Concept | Data | Diagram | Comparison | Demo | Callout | Discussion | Transition | Closing

| # | Slide Title / Argument | Purpose | Type | Section | Fragments | Notes |
|---|---|---|---|---|---|---|
| 01 | [Title slide] | Open the session | Hero | — | 0 | |
| 02 | [Section 1 opener] | Establish opening tension | Hero | 1 | 0 | |
| 03 | | | | | | |
| ... | | | | | | |

**Slide count:** [Total]
**Section breakdown:**

| Section | Slides | Range |
|---|---|---|
| 1. [Name] | [N] | #01–#XX |
| 2. [Name] | [N] | #XX–#XX |

---

## 3. Learning Objectives Map

Maps every learning objective from `docs/learning-objectives.md` to the slides that address it.

| Objective | Tier | Slides |
|---|---|---|
| [Objective 1] | T1 | #, # |
| [Objective 2] | T1 | # |
| [Objective 3] | T2 | #, # |

**Unaddressed objectives:** [List any T1 or T2 objectives with no slide — these are gaps]

---

## 4. Component Inventory

Reusable UI components this presentation requires.

| Component | Purpose | Slide(s) | Notes |
|---|---|---|---|
| [ComponentName] | [Purpose] | [#, #] | [Implementation notes] |

---

## 5. Diagram Inventory

Every diagram, its rendering decision, and its reveal strategy.

**Rendering options:** Custom SVG | Mermaid | CSS animation | HTML+JS | Static image

| # | Diagram Name | Rendering | Reveal Strategy | Slide | Text Description |
|---|---|---|---|---|---|
| D1 | [Diagram name] | [Rendering] | [e.g., 4-fragment progressive build] | [#] | [Text description for accessibility] |

---

## 6. Animation Inventory

Every animation in the presentation. Only animations that serve a valid purpose should appear here.

**Valid purposes:** Reveal control | Show relationship

| Slide | Element | Animation Type | Trigger | Purpose |
|---|---|---|---|---|
| [#] | [Element] | [Fragment fade / slide / highlight / other] | [Presenter advance] | [Reveal control / Show relationship] |

---

## 7. Interaction Inventory

Every moment requiring audience interaction or external tool access.

| Slide | Interaction Type | Tool / Mechanism | Fallback |
|---|---|---|---|
| [#] | [Live demo / Discussion prompt / Poll] | [Tool name or verbal] | [Fallback description + asset path] |

---

## 8. Rendering Strategy

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

## 9. Timing Budget

| # | Section | Target Time | Slides | Notes |
|---|---|---|---|---|
| 1 | [Section name] | [X min] | [N] | |
| 2 | [Section name] | [X min] | [N] | |
| **Total** | | **[X–Y min]** | **[N]** | Target 80–90% of session time |

---

## 10. Accessibility Plan

| Requirement | Approach | Verified By |
|---|---|---|
| Color contrast (4.5:1 body / 3:1 large) | [Theme color choices] | `ui-ux-pro-max` review |
| Text descriptions for all diagrams | Authored in Diagram Inventory above | `presentation-designer` review |
| Keyboard navigation | [Reveal.js default + any custom] | Pre-delivery test |
| Speaker notes as standalone document | Complete prose in all notes | `speaker-coach` review |
| Legible at 50% scale | [Typography minimums enforced in theme] | Manual check |

---

## PAS Status

**Complete when:**
- [ ] Every slide has a type, purpose, and section assignment
- [ ] Every T1 and T2 learning objective maps to at least one slide
- [ ] Every diagram has a rendering decision and a text description
- [ ] Every animation has a documented purpose (reveal control or show relationship)
- [ ] Every interactive moment has a verified fallback
- [ ] Timing budget totals within session target (80–90% of available time)
- [ ] Accessibility plan is complete
- [ ] Internal review complete — sign-off before prototype generation
