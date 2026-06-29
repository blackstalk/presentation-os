# Project Bootstrap

## What Is a Presentation OS Project?

A Presentation OS project is an independent presentation repository that inherits the framework's philosophy, standards, and AI workflow — without living inside the framework itself.

Presentation OS is the framework. Projects are consumers of it.

---

## Why Projects Live Outside the Framework

Presentation OS is a stable, shared platform. Presentations are specific, time-bound, and often have their own git history, branding, collaborators, and lifecycle.

Keeping them separate means:
- The framework evolves independently of any specific presentation
- Each presentation has its own repo, README, and history
- The framework stays clean — no project-specific content, assets, or slides
- Multiple projects reference the same framework version simultaneously

**The relationship is inheritance, not containment.**

```
~/Development/
├── presentation-os/              ← The framework (this repo)
├── working-smarter-ai-workshop/  ← A presentation project
├── mcp-workshop/                 ← Another presentation project
└── github-actions-workshop/      ← Another presentation project
```

---

## Recommended Project Structure

```
[presentation-slug]/
├── CLAUDE.md                # Project operating context — read first
├── README.md                # Project overview
├── PRESENTATION_OS.md       # Framework inheritance reference
├── docs/
│   ├── project-brief.md     # Audience, goal, constraints (Phase 1)
│   ├── audience.md          # Deep audience profile
│   ├── content-outline.md   # Story map and slide sketch (Phase 2)
│   ├── demo-plan.md         # Demo scripts and fallbacks
│   ├── speaker-notes.md     # Notes strategy and timing targets
│   ├── asset-plan.md        # Asset inventory and production status
│   └── references.md        # Sources and research
├── slides/                  # Generated presentation output
├── assets/
│   ├── images/
│   ├── diagrams/
│   └── videos/
└── references/              # Downloaded source material
```

---

## How a Project References Presentation OS

Every project includes a `PRESENTATION_OS.md` file in its root. This file:

1. Records the Presentation OS version the project was built against
2. Documents the local path and GitHub URL of the framework
3. Lists which standards are inherited
4. Lists the external tools in use
5. Gives Claude explicit instructions for how to work across the project and framework

`PRESENTATION_OS.md` is the contract between the project and the framework.

---

## How Claude Works Across Framework and Project

A Claude Code session working on a presentation project should:

1. **Read the project `CLAUDE.md`** — audience, goal, constraints, and any platform overrides
2. **Read `PRESENTATION_OS.md`** — which framework version and standards are in effect
3. **Apply Presentation OS standards as inherited defaults** without requiring the user to restate them
4. **Reference framework documentation when needed** via the local path or GitHub link in `PRESENTATION_OS.md`
5. **Only reproduce framework guidance in project files** when the project needs a specific exception

Claude should never ask the user to restate Presentation OS standards. They are inherited by the framework reference.

---

## How External Skills Fit In

External skills (`html-slides`, `ui-ux-pro-max`) are invoked from within the project context, not from the framework.

| Skill | When invoked | Where results live |
|---|---|---|
| `html-slides` | Stage 9 (Final Delivery) | `slides/` |
| `ui-ux-pro-max` | Stage 5 (Design Review) | Findings in session context |

Skills work the same whether you are in the framework repo or a project repo. The framework defines when and why to invoke them; the project provides the content they work on.

---

## Project CLAUDE.md vs. Platform CLAUDE.md

| | Platform CLAUDE.md | Project CLAUDE.md |
|---|---|---|
| **Lives in** | Presentation OS repo | Presentation project repo |
| **Defines** | Universal standards, philosophy, architecture | Audience, goal, branding, constraints |
| **Changes** | Rarely — framework evolution only | Per project |
| **Overrides** | N/A — this is the baseline | Platform standards, when justified |
| **Length** | Comprehensive | As short as possible |

Project CLAUDE.md should be as short as possible. It only defines what is different or specific to this presentation. Everything universal comes from the framework via `PRESENTATION_OS.md`.

---

## Bootstrapping a New Project

1. Copy `templates/project-starter/` from the Presentation OS repo
2. Rename the directory to your project slug (e.g., `mcp-workshop`)
3. Initialize as a git repo: `git init && git branch -m main`
4. Update `PRESENTATION_OS.md` — set the local framework path, confirm the version
5. Update `CLAUDE.md` — fill in title, audience, goal, constraints
6. Complete `docs/project-brief.md` (Stage 2: Brief)
7. Begin work — do not generate slides until the brief is complete

See `docs/project-lifecycle.md` for the full stage-by-stage workflow.
