# Changelog

All notable changes to Presentation OS are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [0.1.1] — 2026-06-29

### Added

- `docs/project-bootstrap.md` — explains the project model (framework vs. project separation), how Claude works across repos, and how to bootstrap a new project
- `docs/project-lifecycle.md` — 10-stage lifecycle from Bootstrap to Archive / Reuse
- `templates/project-starter/` — complete starter template for new presentation projects:
  - `CLAUDE.md` — project context template (audience, goal, constraints, overrides)
  - `README.md` — project overview template
  - `PRESENTATION_OS.md` — framework inheritance contract (version, local path, inherited standards, Claude instructions)
  - `docs/project-brief.md` — brief template with sign-off checklist
  - `docs/audience.md` — deep audience profile template
  - `docs/content-outline.md` — story map and slide sketch template
  - `docs/demo-plan.md` — demo script and safety checklist template
  - `docs/speaker-notes.md` — notes strategy and timing template
  - `docs/asset-plan.md` — asset inventory template
  - `docs/references.md` — sources and research template
  - `slides/`, `assets/images/`, `assets/diagrams/`, `assets/videos/`, `references/` — directory structure with READMEs

### Updated

- `CLAUDE.md` — added Project Model section (project separation, PRESENTATION_OS.md, how Claude works across repos)
- `README.md` — added "Creating a New Presentation Project" section with workflow steps
- `ROADMAP.md` — restructured as versioned milestones; added v0.1.1 as current
- `templates/README.md` — updated to reflect available project-starter template

---

## [0.1.0] — 2026-06-29

### Added

- Initial repository structure and architecture
- `CLAUDE.md` operating manual — platform standards, philosophy, and skill orchestration model
- `README.md` project overview
- `ROADMAP.md` phased development plan
- Core documentation suite:
  - `docs/philosophy.md` — core beliefs and design principles
  - `docs/architecture.md` — system architecture and component model
  - `docs/storytelling.md` — narrative frameworks and slide-level structure
  - `docs/presentation-lifecycle.md` — full lifecycle from brief to retrospective
  - `docs/accessibility.md` — WCAG standards and accessibility philosophy
  - `docs/animation.md` — animation principles and fragment patterns
  - `docs/speaker-guidance.md` — speaker notes, pacing, and timing
  - `docs/diagram-standards.md` — SVG, Mermaid, and diagram patterns
  - `docs/interaction-standards.md` — interactive elements and demo patterns
  - `docs/project-templates.md` — how to bootstrap a new presentation project
- External tool integration guides:
  - `docs/tooling/html-slides.md`
  - `docs/tooling/ui-ux-pro-max.md`
  - `docs/tooling/future-tools.md`
- Skills taxonomy with vision documentation:
  - Directors: `presentation-director`
  - Specialists: `presentation-designer`, `diagram-architect`, `speaker-coach`, `demo-builder`, `content-strategist`
  - Integrations: `html-slides`, `ui-ux-pro-max`, `future-tools`
- Placeholder directories with README files: `components/`, `templates/`, `examples/`
