# Presentation Lifecycle

Every presentation produced in Presentation OS follows a defined lifecycle. Skipping phases creates rework. Compressing phases reduces quality. The lifecycle is designed to front-load thinking so that execution is fast and confident.

The lifecycle reflects the **Progressive Fidelity** principle: every phase produces a more concrete artifact than the one before it. Phases move from abstract (why, what) to concrete (how, build, deliver).

---

## Phase 1: Brief

**Define before you design.**

**Purpose:** Establish the foundation that every subsequent decision will be built on.

**Key questions:**
- Who is the primary audience? What do they already know? What do they care about?
- What is the single most important thing this presentation must accomplish?
- What format, length, and venue constraints exist?
- What does success look like? How will we know if this presentation worked?

**Output:** A brief document covering audience, goal, constraints, and success criteria.

**Gate:** No slide is created before the brief is complete.

---

## Phase 2: Blueprint

**Become the subject matter expert before designing the experience.**

**Purpose:** Build the complete content foundation — narrative architecture, domain knowledge, learning objectives — that will drive the PAS. The blueprint answers: *what should the audience learn?*

**Key outputs:**
- Story map: the sequence of arguments the presentation will make
- Section outline: major sections, purpose, and narrative role
- Learning objectives: tiered, testable, audience-specific
- Concept maps, terminology definitions, domain models as needed

**Skill:** `content-strategist`

**Gate:** Every section can answer "why does this section exist in this presentation for this audience?" The blueprint contains everything needed to build the PAS.

**Blueprint is an internal artifact.** Stakeholders review prototypes, not blueprints.

---

## Phase 3: PAS (Presentation Architecture Specification)

**Design the experience before building it.**

**Purpose:** Translate the blueprint into a complete architectural specification. PAS answers: *how will this experience be constructed?* It is the contract between content strategy and implementation.

**Key outputs:**
- Learning Journey — the audience's emotional/cognitive arc
- Slide Inventory — every slide numbered, typed, and purposeful
- Component, Diagram, Animation, and Interaction Inventories
- Rendering Strategy — Reveal.js configuration, theme, navigation
- Timing Budget — per-section time targets
- Accessibility Plan

**Skill:** `presentation-director` (orchestrates specialists for each inventory section)

**Gate:** Every slide is designed at the architectural level. Every diagram has a rendering decision. Every interactive moment has a fallback. The PAS can be handed to `html-slides` without further interpretation.

See `docs/presentation-architecture-specification.md` for the full PAS structure and the contract model.

---

## Phase 4: Prototype

**Build from the architecture.**

**Purpose:** Generate the first interactive version of the presentation using PAS as the build specification. This is the first time anything is visually rendered.

**Process:**
1. Internal review — validate the PAS against the blueprint before generating
2. Delegate to `html-slides` with the completed PAS
3. Generate all slides, diagrams, and fragment sequences per the PAS
4. Verify the prototype is a faithful implementation of the PAS

**Integration:** `html-slides`

**Gate:** All slides rendered. Prototype is demonstrable. Speaker notes present.

---

## Phase 5: Design Review

**Review before releasing.**

**Purpose:** Validate the prototype visually and structurally. First, an internal review for design quality. Then, stakeholder review of the narrative.

**Process (in order):**
1. `presentation-designer` review — narrative pacing, visual hierarchy, whitespace, consistency
2. `ui-ux-pro-max` design critique — typography, spacing, color, accessibility
3. `diagram-architect` — refine all diagrams from Phase 3 specifications if needed
4. Stakeholder review — walk stakeholders through the prototype; collect feedback
5. Resolve all P0 and P1 findings; address stakeholder feedback

**Gate:** No presentation enters speaker prep until all P0 findings are resolved and stakeholders have approved the narrative structure.

---

## Phase 6: Speaker Prep

**Prepare the person, not just the slides.**

**Purpose:** Prepare for live delivery — timing, transitions, discussion prompts, Q&A readiness, demo rehearsal.

**Process:**
1. `speaker-coach` review — pacing, transition language, timing estimates
2. Full demo buildout — scripts, fallbacks, delivery environment testing
3. Full run-through with timing notes
4. Identify likely questions and prepare answers
5. Confirm speaker notes match intended delivery

**Skill:** `speaker-coach`

**Gate:** Speaker is prepared when timing is within target, all demos are tested, and all transitions are drafted.

---

## Phase 7: Delivery

**Generate the final output and present.**

**Purpose:** Produce the final presentation artifact and deliver.

**Integration:** Delegate to the appropriate integration skill:
- HTML/Reveal.js → `html-slides` integration (final production pass)
- Other formats → appropriate integration or export tool

**Gate:** Content must not change in the delivery phase. Any content change goes back to Phase 2 (Blueprint) or Phase 3 (PAS).

---

## Phase 8: Retrospective

**Learn before you forget.**

**Purpose:** Capture what worked, what to improve, and what to carry forward to future presentations.

**Key questions:**
- Did the presentation achieve its goal?
- What landed well with the audience?
- What would you change?
- What components or patterns should be added to `components/`?
- What would the Learning Journey look like if you redesigned it from scratch?

**Output:** Short retrospective note added to the project directory. Repository tagged with delivery version.

---

## Phase Summary

| Phase | Question Answered | Key Output | Artifact |
|---|---|---|---|
| 1. Brief | Why are we doing this? | Brief document | Project Brief |
| 2. Blueprint | What should the audience learn? | Story map, learning objectives | Blueprint |
| 3. PAS | How will the experience be constructed? | presentation-architecture-spec.md | PAS |
| 4. Prototype | Does the architecture work? | Reveal.js prototype | Prototype |
| 5. Design Review | Is it visually correct and stakeholder-approved? | Reviewed and refined prototype | — |
| 6. Speaker Prep | Is the presenter ready? | Speaker notes, rehearsed demos | — |
| 7. Delivery | Is it delivered? | Final presentation | Production |
| 8. Retrospective | What do we carry forward? | Retrospective, tagged repo | Archive |

---

## When to Skip Phases

Phases can be abbreviated for low-stakes presentations (internal demos, rough drafts), but never fully skipped. Even a 10-minute internal demo benefits from a 5-minute brief and a quick PAS pass.

The higher the stakes, the more rigorously each phase should be executed. A Phase 3 (PAS) that takes two hours prevents a Phase 4 (Prototype) that takes two days of rework.
