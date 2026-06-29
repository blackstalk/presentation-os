# Presentation OS

A reusable AI-first platform for designing, reviewing, building, and delivering world-class presentations.

---

## What This Is

Presentation OS is an operating system for presentations — not a presentation itself.

It defines the standards, philosophy, architecture, and AI collaboration patterns that make every future presentation dramatically easier to create and dramatically better.

Every presentation project is a **plug-in** to this system. The system handles the hard parts so each project focuses only on what is unique to that presentation.

## What This Is Not

- A slide deck
- A Reveal.js project
- A PowerPoint template
- A design tool

## Repository Structure

```
├── CLAUDE.md                        # Platform operating manual — read first
├── README.md                        # This file
├── ROADMAP.md                       # Long-term vision and phases
├── CHANGELOG.md                     # Version history
│
├── docs/
│   ├── philosophy.md                # Core beliefs and design principles
│   ├── architecture.md              # System architecture and component model
│   ├── storytelling.md              # Narrative frameworks and slide-level structure
│   ├── presentation-lifecycle.md    # Full lifecycle from brief to retrospective
│   ├── accessibility.md             # WCAG standards and accessibility philosophy
│   ├── animation.md                 # Animation principles and fragment patterns
│   ├── speaker-guidance.md          # Speaker notes, pacing, and timing
│   ├── diagram-standards.md         # SVG, Mermaid, and diagram patterns
│   ├── interaction-standards.md     # Interactive elements and demo patterns
│   ├── project-templates.md         # How to bootstrap a new presentation project
│   └── tooling/
│       ├── html-slides.md           # Reveal.js integration guide
│       ├── ui-ux-pro-max.md         # Design review integration guide
│       └── future-tools.md          # How to add new tools to the ecosystem
│
├── .claude/skills/
│   ├── directors/                   # Orchestrator skills
│   │   └── presentation-director/
│   ├── specialists/                 # Domain expert skills
│   │   ├── presentation-designer/
│   │   ├── diagram-architect/
│   │   ├── speaker-coach/
│   │   ├── demo-builder/
│   │   └── content-strategist/
│   └── integrations/                # External tool bridges
│       ├── html-slides/
│       ├── ui-ux-pro-max/
│       └── future-tools/
│
├── components/                      # Reusable presentation components
├── templates/                       # Starter templates for common presentation types
└── examples/                        # Worked examples of complete presentations
```

## Getting Started

1. Read `CLAUDE.md` — the platform operating manual
2. Read `docs/presentation-lifecycle.md` — the end-to-end workflow
3. Read `docs/project-templates.md` — how to start a new presentation project

## Philosophy

> Every future presentation should be a project that plugs into this system rather than reinventing presentation architecture.

Presentation OS is opinionated about storytelling, visual hierarchy, accessibility, and speaker experience. It is deliberately unopinionated about implementation technology.

See `docs/philosophy.md` for the full design philosophy.
