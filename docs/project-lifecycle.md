# Project Lifecycle

A Presentation OS project moves through thirteen stages from bootstrap to archive. Each stage has a clear purpose, gate, and output. The lifecycle reflects the Progressive Fidelity principle: every stage produces a more concrete artifact than the one before it.

---

## The Artifact Chain

```
Bootstrap → Brief → Blueprint → PAS → Internal Review → Prototype → Stakeholder Review → Design Refinement → Demo Buildout → Speaker Notes → Rehearsal → Delivery → Archive
```

Stages 1–3 produce planning artifacts (why, what). Stages 4–5 produce architectural artifacts (how). Stages 6–7 produce interactive artifacts for review. Stages 8–12 prepare for and execute delivery.

---

## Stage 1: Bootstrap

**Purpose:** Set up the project structure and establish the framework connection.

**Actions:**
- Copy `templates/project-starter/` from Presentation OS
- Rename to the project slug
- Initialize git repo: `git init && git branch -m main`
- Update `PRESENTATION_OS.md` — local path, version
- Create project GitHub repo
- Make first commit

**Gate:** Project has a git repo, a complete `PRESENTATION_OS.md`, and a placeholder `CLAUDE.md`.

---

## Stage 2: Brief

**Purpose:** Define the audience, goal, and constraints before any content is created.

**Actions:**
- Complete `docs/project-brief.md`
- Complete `docs/audience.md`
- Align stakeholders on goal and success criteria

**Gate:** The single goal statement is written, the primary audience is defined, and constraints (format, length, venue) are confirmed.

**No slide is created before the brief is complete.**

---

## Stage 3: Blueprint

**Purpose:** Become the subject matter expert. Design the narrative architecture and document everything the audience needs to learn before any implementation decisions are made.

**Actions:**
- Complete `docs/content-outline.md` (story map, section outline, narrative arc)
- Complete `docs/learning-objectives.md` (tiered objectives)
- Complete `docs/concept-map.md` or equivalent domain model
- Complete `docs/terminology-map.md` and `docs/report-glossary.md` as needed
- Identify where demos, diagrams, and data moments are needed
- Validate that each section earns its place in the narrative

**Gate:** Every section can answer "why does this section exist in this presentation for this audience?" Domain knowledge is complete. The blueprint contains everything needed to build the PAS.

**Blueprint is an internal artifact.** Stakeholders do not review the blueprint — they review the prototype. The blueprint is the input to PAS.

---

## Stage 4: PAS (Presentation Architecture Specification)

**Purpose:** Design the complete experience architecture before any slide is built. PAS is the handoff contract between content strategy and implementation.

**Actions:**
- Create `docs/presentation-architecture-spec.md`
- Write the Learning Journey (audience emotional/cognitive arc)
- Build the Slide Inventory (every slide numbered, typed, purposeful)
- Map learning objectives to slides
- Build the Component Inventory (reusable UI elements)
- Build the Diagram Inventory (every diagram + rendering decision)
- Build the Animation Inventory (every animation + purpose)
- Build the Interaction Inventory (every demo + fallback)
- Define the Rendering Strategy (Reveal.js config, theme, navigation)
- Define the Timing Budget (per-section time targets)
- Define the Accessibility Plan

**Gate:** Every slide is designed at the architectural level. Every diagram has a rendering decision. Every interactive moment has a fallback. The PAS can be handed to `html-slides` without further interpretation.

See `docs/presentation-architecture-specification.md` for the full PAS structure and contract model.

---

## Stage 5: Internal Review

**Purpose:** Validate the architecture internally before anything is shown externally or built. This is the last checkpoint before generating the prototype.

**Key questions:**
- Does the story flow from section to section?
- Is the pacing right? Too many dense slides in a row?
- Are there too many demos? Too few audience interaction moments?
- Is every term introduced before it is used?
- Does the Learning Journey arc match the intended audience experience?
- Does the opening tension get resolved by the close?
- Is every learning objective covered in the slide inventory?

**Actions:**
- Review PAS against the blueprint — does the architecture serve the content strategy?
- Review `docs/recommended-demos.md` — is the demo load realistic?
- Review `docs/recommended-diagrams.md` — are the diagrams the right level of complexity?
- Adjust PAS based on findings

**Gate:** Internal sign-off on the PAS. No prototype is generated until this stage is complete.

---

## Stage 6: Prototype

**Purpose:** Generate the first interactive version of the presentation using the PAS as the build specification.

**Actions:**
- Delegate to `html-slides` skill with the completed PAS
- Generate full Reveal.js HTML from the slide inventory and rendering strategy
- Implement all fragment sequences per the animation inventory
- Create all diagrams per the diagram inventory and rendering decisions
- Verify all speaker notes are present
- Verify keyboard navigation works
- Complete a quick self-review pass: does the prototype match the PAS?

**Gate:** All slides are rendered. The prototype is a faithful implementation of the PAS — not a rough draft. Speaker notes are present. The deck is demonstrable.

---

## Stage 7: Stakeholder Review

**Purpose:** Show the interactive prototype to stakeholders. Humans review visuals, not outlines — this is the first external checkpoint.

**Actions:**
- Schedule a review session with key stakeholders
- Walk through the prototype from start to finish
- Collect feedback — note what's working and what needs to change
- Categorize feedback: content changes vs. design changes vs. architectural changes
- Architectural changes (add/remove sections, restructure the narrative) → revise PAS and regenerate
- Design changes (visual polish, diagram refinements) → Stage 8
- Content changes (headlines, copy) → Stage 8

**Gate:** Stakeholder approval of the narrative structure and learning objectives as demonstrated in the prototype.

---

## Stage 8: Design Refinement

**Purpose:** Resolve stakeholder feedback, polish the visual system, and finalize all diagrams.

**Actions:**
- Address all feedback from Stage 7 stakeholder review
- Run `presentation-designer` review — narrative pacing, visual hierarchy, whitespace, consistency
- Run `ui-ux-pro-max` design critique — typography, spacing, color, accessibility
- Finalize all diagrams (using `diagram-architect` or following `docs/diagram-standards.md`)
- Resolve all P0 and P1 findings
- Update the prototype HTML with all refinements

**Gate:** All P0 findings resolved. All stakeholder feedback addressed. Visual system complete and consistent.

---

## Stage 9: Demo Buildout

**Purpose:** Finalize all demo scripts, capture fallback assets, and verify everything in the delivery environment.

**Actions:**
- Complete `docs/demo-plan.md` with full scripts, step-by-step tables, and fallbacks
- Capture all fallback screenshots and recordings per `docs/asset-plan.md`
- Test every demo in the delivery environment (same computer, browser, connection)
- Test every fallback
- Confirm all external access requirements (Search Console, AI tool accounts)

**Gate:** Every demo has been tested in the delivery environment and has a verified fallback.

---

## Stage 10: Speaker Notes

**Purpose:** Finalize speaker notes and prepare the presentation for delivery.

**Actions:**
- Complete `docs/speaker-notes.md` — strategy, timing targets, discussion prompts, Q&A prep
- Finalize all slide-by-slide speaker notes in complete prose (notes function as a standalone document)
- Run `speaker-coach` review
- Confirm notes include report-connecting bridges and discussion prompts at the right moments

**Gate:** Timing is within target. All transitions are drafted. Speaker notes function as a standalone document.

---

## Stage 11: Rehearsal

**Purpose:** Practice delivery in conditions as close to real as possible.

**Actions:**
- Full run-through in the delivery environment (same room, same screen setup if possible)
- Time each section against the PAS timing budget
- Identify remaining rough edges
- Final cuts or simplifications if running over time
- Confirm all demo accounts and access are ready

**Gate:** Speaker has completed at least one full run-through within target time.

---

## Stage 12: Delivery

**Purpose:** Deliver the presentation.

**Actions:**
- Deliver the presentation
- Collect real-time audience signals (what lands, what confuses, what energizes)
- Note any unscripted moments that worked particularly well

**Gate:** Delivered.

---

## Stage 13: Archive / Reuse

**Purpose:** Capture what worked, preserve assets, and carry patterns forward.

**Actions:**
- Write a retrospective (what worked, what to improve, what to carry forward)
- Identify reusable components or patterns — contribute to Presentation OS `components/`
- Tag the git repo with the delivery version (`git tag v1.0`)
- Archive or share the recording if applicable
- Consider: what would the next version of this presentation include?

**Gate:** Retrospective written. Repository tagged.

---

## Stage Summary

| Stage | Purpose | Key Output | Artifact |
|---|---|---|---|
| 1. Bootstrap | Set up project | Initialized repo | PRESENTATION_OS.md |
| 2. Brief | Define audience and goal | project-brief.md, audience.md | Project Brief |
| 3. Blueprint | Content strategy, domain knowledge | content-outline.md, learning-objectives.md | Blueprint |
| 4. PAS | Experience architecture | presentation-architecture-spec.md | PAS |
| 5. Internal Review | Validate architecture | Approved PAS | — |
| 6. Prototype | Generate interactive version | index.html | Prototype |
| 7. Stakeholder Review | External checkpoint | Approved narrative | — |
| 8. Design Refinement | Polish and resolve feedback | Refined prototype | — |
| 9. Demo Buildout | Prepare interactive elements | demo-plan.md, tested demos | — |
| 10. Speaker Notes | Finalize delivery prep | speaker-notes.md | — |
| 11. Rehearsal | Practice delivery | Full run-through completed | — |
| 12. Delivery | Deliver | Delivered presentation | Production |
| 13. Archive | Capture and carry forward | Retrospective, tagged repo | Archive |
