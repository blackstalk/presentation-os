# Architecture

## Overview

Presentation OS is organized around four concerns:

1. **Standards** — what every presentation must do
2. **Process** — how presentations are created and reviewed
3. **Skills** — who (or what) does each type of work
4. **Tooling** — how external tools are integrated

These concerns are deliberately separated. Changing a tool should not require changing a standard. Adding a skill should not require changing a process.

---

## Component Model

### Platform Layer
The platform layer defines standards, philosophy, and the document hierarchy that all projects inherit. This layer changes rarely. Changes here affect every presentation project.

**Contents:** CLAUDE.md, docs/, the skills taxonomy

### Project Layer
Each presentation project lives in its own directory and has its own CLAUDE.md. Projects inherit platform standards and override only what is specific to their context.

**Contents:** Project CLAUDE.md, slide content, project-specific assets

### Integration Layer
External tools are accessed through integration skills. Integration skills translate platform-standard instructions into tool-specific implementations.

**Contents:** `.claude/skills/integrations/`

---

## Skills Architecture

```
.claude/skills/
│
├── directors/
│   └── presentation-director       # Single entry point for end-to-end workflow
│                                    # Delegates to specialists; never implements
│
├── specialists/
│   ├── presentation-designer       # Design review: hierarchy, pacing, whitespace
│   ├── diagram-architect           # Diagrams: SVG, Mermaid, animation concepts
│   ├── speaker-coach               # Speaker: pacing, transitions, timing
│   ├── demo-builder                # Demos: interactive elements, embeds
│   └── content-strategist          # Narrative: flow, section structure, adaptation
│
└── integrations/
    ├── html-slides                 # Bridge to html-slides skill (Reveal.js)
    ├── ui-ux-pro-max               # Bridge to ui-ux-pro-max skill (design critique)
    └── future-tools                # Extensibility guide for new tools
```

### Call Flow

Presentation work enters through the director. The director coordinates everything else.

```
User → presentation-director
          ├── content-strategist      (narrative architecture, slide content)
          ├── presentation-designer   (design review, hierarchy, pacing)
          ├── diagram-architect       (visual explanations, diagram creation)
          ├── speaker-coach           (delivery review, transitions, timing)
          └── html-slides integration (output generation)
                └── html-slides skill (Reveal.js implementation)
```

Specialists never call other specialists directly. All cross-specialist coordination flows through the director.

---

## Document Architecture

```
CLAUDE.md                      Platform operating manual — inherited by all projects
docs/                          Authoritative platform documentation
  tooling/                     External tool integration guides
components/                    Reusable slide components
templates/                     Starter project templates
examples/                      Reference implementations
.claude/skills/                Claude Code skill registry
  directors/
  specialists/
  integrations/
```

---

## Extensibility Principles

**Add, don't modify.** New capabilities are added as new skills or integrations, not as changes to existing ones.

**Delegate, don't replicate.** If an external tool does something well, delegate to it rather than rebuilding the capability inside Presentation OS.

**Document the boundary.** Every integration must document what Presentation OS owns versus what the external tool owns.

**Stay agnostic.** Platform standards must be expressible in any implementation technology. A standard that only works with Reveal.js is not a platform standard — it is a Reveal.js convention.

---

## The Separation Principle in Practice

When adding capability, ask:

- Should the standard live in CLAUDE.md? → It applies to all presentations
- Should it live in a specialist? → It is domain-specific expertise
- Should it live in an integration? → It is tool-specific translation
- Should it live in a project CLAUDE.md? → It applies only to this presentation

If the answer is unclear, it probably belongs one level higher than your instinct.
