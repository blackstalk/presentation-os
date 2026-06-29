# Presentation OS — Operating Manual

> Every Claude Code session for a Presentation OS project begins by reading this file.

## Vision

Presentation OS is an opinionated AI-native framework for designing, reviewing, and delivering world-class presentations. It is not a slide generator. It is the operating system that makes every future presentation dramatically easier to create — and dramatically better.

Every presentation project plugs into this system rather than reinventing architecture from scratch.

## What Presentation OS Owns

- Standards and design philosophy
- Storytelling architecture and narrative frameworks
- Visual hierarchy principles
- Interaction and animation philosophy
- Accessibility standards
- Speaker experience guidelines
- Review workflows and milestone gates
- Reusable component patterns
- Documentation standards
- AI collaboration patterns and skill orchestration

## What Presentation OS Does NOT Own

- Reveal.js or any HTML presentation framework
- PowerPoint, Keynote, or other authoring tools
- CSS, JavaScript, or HTML implementations
- Figma, Sketch, or design software
- Any specific rendering technology

Those are implementation choices. Presentation OS delegates to external tools and skills.

---

## Project Model

Presentation OS is the framework. Presentation projects are separate repositories.

```
~/Development/
├── presentation-os/              ← This repo — the framework
├── working-smarter-ai-workshop/  ← A presentation project
├── mcp-workshop/                 ← Another presentation project
└── github-actions-workshop/      ← Another presentation project
```

### Every Project Includes PRESENTATION_OS.md

Each presentation project contains a `PRESENTATION_OS.md` file in its root. This file:
- Records the Presentation OS version the project was built against
- Documents the local framework path and GitHub URL
- Lists inherited standards
- Lists active external tools
- Gives Claude explicit instructions for working across the project and framework

`PRESENTATION_OS.md` is the contract between the project and the framework.

### Project CLAUDE.md vs. Platform CLAUDE.md

| | Platform CLAUDE.md (this file) | Project CLAUDE.md |
|---|---|---|
| **Lives in** | Presentation OS repo | Presentation project repo |
| **Defines** | Universal standards, philosophy, architecture | Audience, goal, branding, constraints |
| **Changes** | Rarely — framework evolution only | Per project |
| **Length** | Comprehensive | As short as possible |

Project CLAUDE.md files should be as short as possible — only what is specific to that presentation. Everything universal is inherited from the framework via `PRESENTATION_OS.md`.

### How Claude Works Across Repos

When working in a presentation project, Claude should:

1. Read the project `CLAUDE.md` first — audience, goal, constraints, overrides
2. Read `PRESENTATION_OS.md` — which framework version and standards are in effect
3. Apply platform standards as inherited defaults without requiring the user to restate them
4. Reference framework docs via the local path in `PRESENTATION_OS.md`
5. Never reproduce platform documentation in the project — only exceptions

See `docs/project-bootstrap.md` for the full project model and bootstrapping guide.

---

## Architecture

### Skills Taxonomy

Claude Code skills are organized into three categories:

```
.claude/skills/
├── directors/       # Orchestrators — coordinate specialists, never implement
├── specialists/     # Domain experts — own one area deeply
└── integrations/    # External tool bridges — translate intent to tool instructions
```

**Directors** coordinate the full presentation creation process. They decide what work to delegate and to whom. They do not implement — they orchestrate.

**Specialists** own a specific domain: design review, diagram creation, speaker coaching, content strategy, or interactive demos. Each specialist has narrow, deep focus. Specialists never reach across domain boundaries.

**Integrations** bridge Presentation OS to external tools. They translate Presentation OS intent and standards into tool-specific instructions. Adding a new tool means adding a new integration — not changing directors or specialists.

### The Separation Principle

Never add logic to a director that belongs in a specialist.
Never add logic to a specialist that belongs in an integration.
Never implement in an integration what should be a platform standard.

### Document Hierarchy

Every presentation project has two CLAUDE.md files:

1. **Platform CLAUDE.md** (this file) — inherited standards, architecture, philosophy
2. **Project CLAUDE.md** — project-specific audience, goals, branding, constraints

Project CLAUDE.md files inherit platform standards and override only what is explicitly different. A project-level override must document why.

---

## Design Language

### Visual Hierarchy
- One dominant idea per slide
- Maximum three levels: primary, secondary, supporting
- Generous whitespace — slides are not documents
- Typography establishes hierarchy; layout reinforces it; color confirms it

### Color Philosophy
- Color communicates meaning, not decoration
- Accessibility-first: all color pairs meet WCAG AA minimum
  - Body text: 4.5:1 contrast ratio minimum
  - Large text / UI: 3:1 contrast ratio minimum
- Dark backgrounds for technical and engineering content
- Light backgrounds for executive and narrative content
- Never use more than four semantic colors in a single presentation

### Typography
- One typeface family per presentation (two maximum: display + mono)
- Strict scale: title → heading → body → caption — nothing outside this hierarchy
- Maximum two weights in simultaneous use
- Line length: 60–75 characters for body; shorter for slide context
- Never justify body text

### Layout Principles
- Align to a consistent grid — visual alignment is a trust signal
- Content should never touch the edge of the frame
- Asymmetric layouts convey dynamism; symmetric layouts convey authority
- Group related items; separate unrelated items

---

## Storytelling Principles

### The Three-Layer Model

Every slide operates on three layers simultaneously:

| Layer | Question | Common Failure |
|-------|----------|----------------|
| **What** | What information is being communicated? | Overloading with data |
| **Why** | Why does it matter to this specific audience? | Generic relevance |
| **So what** | What should they think, feel, or do differently? | Missing the call |

A slide that delivers only "What" is a document. A slide that delivers all three is a moment.

### Narrative Architecture

- **Open with tension**, not context — earn attention before providing background
- **Build toward insight**, not just information — each slide should change understanding
- **Land on a clear call** to action, belief shift, or next step
- Every section earns its place by moving the story forward
- Cut anything that does not move the story forward

### Slide-Level Storytelling

- The headline is an **argument**, not a label
- Good headline: "Latency doubled when we added auth middleware"
- Bad headline: "Latency Results"
- Supporting content proves the headline — not the other way around
- One headline per slide, always

### Section Openers

Every section should answer: "Why does this matter, right now, to this audience?"

Do not open sections with an agenda slide. Open with a question, a tension, or a fact that creates curiosity.

---

## Presentation Lifecycle

See `docs/presentation-lifecycle.md` for the full lifecycle guide.

| Phase | Focus | Key Output |
|-------|-------|------------|
| 1. Brief | Audience, goal, constraints | Brief document |
| 2. Architecture | Narrative structure, section outline | Story map |
| 3. Content | Slide-by-slide development | Draft deck |
| 4. Design Review | Visual hierarchy, accessibility | Reviewed deck |
| 5. Speaker Prep | Pacing, transitions, timing | Speaker notes |
| 6. Delivery | Generated output | Final file |
| 7. Retrospective | What worked, what to carry forward | Retro notes |

---

## Review Workflow

Before any presentation milestone, complete in order:

1. **Self-review against storytelling principles** — every slide passes the Three-Layer Model check
2. **`presentation-designer` review** — hierarchy, pacing, whitespace, consistency
3. **`ui-ux-pro-max` design critique** — typography, spacing, color, accessibility
4. **`speaker-coach` review** — timing, transitions, discussion prompts
5. **Resolve all P0 findings** before proceeding to the next phase

A P0 finding is any issue that:
- Breaks the narrative flow
- Fails accessibility standards
- Causes audience confusion
- Misrepresents data

---

## Documentation Standards

- Every document answers **one question** — no omnibus documents
- Docs describe intent and philosophy; implementations describe mechanics
- Always explain **WHY**, not just WHAT
- Cross-reference liberally — documents form a connected graph
- Never leave a TODO in documentation — either complete it or delete the section

---

## Naming Conventions

### Files and Directories
- `kebab-case` for all files and directories
- Prefer descriptive over short: `visual-hierarchy.md` beats `design.md`

### Slides
- Zero-padded numeric prefix: `01-opening`, `02-problem`, `03-solution`
- Slug matches the slide's core argument, not its position in an agenda

### Components
- PascalCase for component identifiers: `DiagramFrame`, `CalloutBlock`, `SpeakerNote`
- Suffix describes purpose, not implementation

---

## Accessibility Philosophy

Accessibility is an extension of excellent design, not a compliance exercise.

**Every presentation must:**
- Meet WCAG AA color contrast minimum for all text
- Include text descriptions for all visual content (diagrams, charts, images)
- Support keyboard navigation for any interactive elements
- Include speaker notes that function as a standalone document
- Remain legible at 50% scale (for stream viewers and screenshot sharing)

**Accessibility is non-negotiable.** A presentation that excludes audience members has failed its purpose.

See `docs/accessibility.md` for detailed standards.

---

## External Tool Integration

External tools are invoked by skills, not directly by Claude sessions working on presentations.

| Tool | Category | Role |
|------|----------|------|
| `html-slides` | Integration | Reveal.js generation, presentation scaffolding, export |
| `ui-ux-pro-max` | Integration | Design critique, visual polish, typography review |

See `docs/tooling/` for detailed integration guides including when to use and when NOT to use each tool.

---

## Future Claude Skills

Skills are not yet implemented. Placeholder documentation lives in `.claude/skills/`.

When implementing skills:
- **Directors** are entry points — one director per major workflow
- **Specialists** are the workers — one specialist per domain
- **Integrations** are bridges — one integration per external tool

New presentations should invoke `presentation-director`. The director decides which specialists and integrations to involve. Callers never invoke specialists directly.

See `.claude/skills/` for the full skill registry and vision documents.

---

## Long-Term Vision

Presentation OS should eventually power:

- AI Workshops and Technical Deep Dives
- Executive and Board Presentations
- Conference Talks and Keynotes
- Product Demonstrations and Client Pitches
- Portfolio Case Studies
- Internal Training Programs

Each of these is a **project** that inherits this platform — not a reinvention of it.
