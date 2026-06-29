# Presentation OS

Presentation OS is an opinionated AI-native framework for designing, reviewing, and delivering world-class presentations.

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

## Creating a New Presentation Project

Presentation projects live **outside** the Presentation OS repo — each in its own repository.

```
~/Development/
├── presentation-os/        ← This repo — the framework
├── my-workshop/            ← A presentation project
└── client-pitch/           ← Another presentation project
```

**To start a new presentation project:**

1. Copy `templates/project-starter/` to your desired location and rename it
2. Initialize a git repo: `git init && git branch -m main`
3. Update `PRESENTATION_OS.md` — set your local framework path, confirm the version
4. Update `CLAUDE.md` — fill in title, audience, goal, and constraints
5. Complete `docs/project-brief.md` before writing any slide content
6. Follow the project lifecycle: Brief → Outline → Prototype → Design Review → Delivery

See `docs/project-bootstrap.md` for the full guide and `docs/project-lifecycle.md` for the stage-by-stage workflow.

---

## Philosophy

> Every future presentation should be a project that plugs into this system rather than reinventing presentation architecture.

Presentation OS is opinionated about storytelling, visual hierarchy, accessibility, and speaker experience. It is deliberately unopinionated about implementation technology.

See `docs/philosophy.md` for the full design philosophy.
