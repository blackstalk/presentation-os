# Project Lifecycle

A Presentation OS project moves through ten stages from bootstrap to archive. Each stage has a clear purpose, gate, and output.

Stages 2–9 correspond to the phases in `docs/presentation-lifecycle.md`. The project lifecycle adds Bootstrap before and Archive/Reuse after, and splits the production phases into more granular stages.

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

## Stage 3: Outline

**Purpose:** Design the narrative architecture before writing slide content.

**Actions:**
- Complete `docs/content-outline.md` (story map, section outline, slide sketch)
- Validate that each section earns its place in the narrative
- Identify where demos, diagrams, and data visualizations are needed

**Gate:** Every section can answer "why does this section exist in this presentation for this audience?" The slide sketch is agreed.

---

## Stage 4: Prototype

**Purpose:** Develop slide-by-slide content from the outline.

**Actions:**
- Write slide headlines (arguments, not labels)
- Write supporting content for each slide
- Write draft speaker notes for each slide
- Apply the Three-Layer Model check (What / Why / So what) to every slide

**Gate:** Every slide has a headline, supporting content, and speaker notes. Every slide passes the cut test.

---

## Stage 5: Design Review

**Purpose:** Validate visual hierarchy, accessibility, and design quality before output generation.

**Actions:**
- Run `presentation-designer` review — hierarchy, pacing, consistency
- Run `ui-ux-pro-max` design critique — typography, spacing, color, accessibility
- Create all diagrams (using `diagram-architect` or following `docs/diagram-standards.md`)
- Resolve all P0 and P1 findings

**Gate:** All P0 findings resolved. Design approved.

---

## Stage 6: Demo Buildout

**Purpose:** Prepare all interactive elements, demos, and prompt walkthroughs.

**Actions:**
- Complete `docs/demo-plan.md`
- Build, record, or pre-generate all demos
- Test every demo in the delivery environment (not just locally)
- Document a fallback for each demo step

**Gate:** Every demo has been tested in the delivery environment and has a documented fallback.

---

## Stage 7: Speaker Notes

**Purpose:** Finalize speaker notes and prepare for delivery.

**Actions:**
- Complete `docs/speaker-notes.md` — strategy, timing targets, discussion prompts
- Finalize all slide-by-slide speaker notes
- Run `speaker-coach` review
- Full timed run-through

**Gate:** Timing is within target. All transitions are drafted. Speaker notes function as a standalone document.

---

## Stage 8: Rehearsal

**Purpose:** Practice delivery in conditions as close to real as possible.

**Actions:**
- Full run-through in the delivery environment (same room, same screen setup if possible)
- Time each section
- Identify remaining rough edges
- Final round of cuts or simplifications if needed

**Gate:** Speaker has completed at least one full run-through within target time.

---

## Stage 9: Final Delivery

**Purpose:** Generate the final output and deliver.

**Actions:**
- Generate slides via `html-slides` or chosen tool
- Final review of generated output against the approved content
- Deliver the presentation
- Collect real-time audience signals

**Gate:** Delivered.

---

## Stage 10: Archive / Reuse

**Purpose:** Capture what worked, preserve assets, and carry patterns forward.

**Actions:**
- Write a retrospective (what worked, what to improve, what to carry forward)
- Identify reusable components or patterns — contribute to Presentation OS `components/`
- Tag the git repo with the delivery version (`git tag v1.0`)
- Archive or share the recording if applicable

**Gate:** Retrospective written. Repository tagged.

---

## Stage Summary

| Stage | Purpose | Key Output |
|---|---|---|
| 1. Bootstrap | Set up project | Initialized repo, PRESENTATION_OS.md |
| 2. Brief | Define audience and goal | project-brief.md, audience.md |
| 3. Outline | Design narrative structure | content-outline.md |
| 4. Prototype | Write slide content | Draft slides + speaker notes |
| 5. Design Review | Validate design quality | Reviewed and approved content |
| 6. Demo Buildout | Prepare interactive elements | demo-plan.md, tested demos |
| 7. Speaker Notes | Finalize delivery prep | speaker-notes.md, timed run-through |
| 8. Rehearsal | Practice delivery | Full run-through completed |
| 9. Final Delivery | Generate and deliver | Delivered presentation |
| 10. Archive / Reuse | Capture and carry forward | Retrospective, tagged repo |
