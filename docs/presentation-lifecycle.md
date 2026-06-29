# Presentation Lifecycle

Every presentation produced in Presentation OS follows a defined lifecycle. Skipping phases creates rework. Compressing phases reduces quality. The lifecycle is designed to front-load thinking so that execution is fast and confident.

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

## Phase 2: Architecture

**Structure before content.**

**Purpose:** Design the narrative architecture before writing any slide content.

**Key outputs:**
- Story map: the sequence of arguments the presentation will make
- Section outline: major sections and their purpose
- Slide sketch (optional): rough list of slides by type — not by content

**Skill:** `content-strategist`

**Gate:** Architecture is complete when every section can answer "why does this section exist in this presentation for this audience?"

---

## Phase 3: Content

**Write with the architecture in mind.**

**Purpose:** Develop slide-by-slide content, including speaker notes, following the narrative architecture.

**Standards:**
- Every headline is an argument (see `docs/storytelling.md`)
- Every slide passes the Three-Layer Model check
- Speaker notes are complete enough to stand alone as a document
- Diagrams are described in text (created in Phase 4 by `diagram-architect`)

**Skill:** `content-strategist`

**Gate:** Content is complete when every slide has a headline, supporting content, and speaker notes — and passes the cut test.

---

## Phase 4: Design Review

**Review before you build.**

**Purpose:** Validate visual hierarchy, accessibility, and design quality before output generation.

**Process (in order):**
1. `presentation-designer` review — narrative pacing, visual hierarchy, whitespace, consistency
2. `ui-ux-pro-max` design critique — typography, spacing, color, accessibility
3. `diagram-architect` — create all diagrams from Phase 3 descriptions
4. Resolve all P0 and P1 findings

**Gate:** No output is generated until all P0 findings are resolved.

---

## Phase 5: Speaker Prep

**Prepare the person, not just the slides.**

**Purpose:** Prepare for live delivery — timing, transitions, discussion prompts, Q&A readiness.

**Process:**
1. `speaker-coach` review — pacing, transition language, timing estimates
2. Full run-through with timing notes
3. Identify likely questions and prepare answers
4. Confirm speaker notes match intended delivery

**Skill:** `speaker-coach`

**Gate:** Speaker is prepared when timing is within target and all transitions are drafted.

---

## Phase 6: Delivery

**Generate the final output.**

**Purpose:** Produce the final presentation artifact for the chosen format.

**Integration:** Delegate to the appropriate integration skill:
- HTML/Reveal.js → `html-slides` integration
- Other formats → appropriate integration or export tool

**Gate:** Content must not change in the delivery phase. Any content change goes back to Phase 3.

---

## Phase 7: Retrospective

**Learn before you forget.**

**Purpose:** Capture what worked, what to improve, and what to carry forward to future presentations.

**Key questions:**
- Did the presentation achieve its goal?
- What landed well with the audience?
- What would you change?
- What components or patterns should be added to `components/`?

**Output:** Short retrospective note added to the project directory.

---

## Phase Summary

| Phase | Input | Output | Key Skill |
|---|---|---|---|
| 1. Brief | Request | Brief document | — |
| 2. Architecture | Brief | Story map | `content-strategist` |
| 3. Content | Story map | Draft deck | `content-strategist` |
| 4. Design Review | Draft | Reviewed deck | `presentation-designer`, `ui-ux-pro-max`, `diagram-architect` |
| 5. Speaker Prep | Reviewed deck | Speaker notes | `speaker-coach` |
| 6. Delivery | Reviewed deck | Final file | `html-slides` integration |
| 7. Retrospective | Delivered presentation | Retro notes | — |

---

## When to Skip Phases

Phases can be abbreviated for low-stakes presentations (internal demos, rough drafts), but never fully skipped. Even a 10-minute internal demo benefits from a 5-minute brief and a pass through the storytelling principles.

The higher the stakes, the more rigorously each phase should be executed.
