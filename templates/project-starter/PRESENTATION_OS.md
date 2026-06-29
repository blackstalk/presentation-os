# Presentation OS — Framework Reference

This project is built on **Presentation OS**, an opinionated AI-native framework for designing, reviewing, and delivering world-class presentations.

---

## Framework

| Field | Value |
|---|---|
| **Local path** | `~/Repos/presentation-os` *(update to your actual local path)* |
| **GitHub** | https://github.com/blackstalk/presentation-os |
| **Version** | v0.1.1 |

---

## What This Project Inherits

By including this file, this project inherits the following Presentation OS standards:

- **Storytelling** — Three-Layer Model (What / Why / So what), argument-first headlines, open with tension, close with clarity
- **Visual hierarchy** — one dominant idea per slide, maximum three levels, generous whitespace
- **Design language** — semantic color philosophy, typographic scale, layout principles
- **Accessibility** — WCAG AA contrast for all text, text descriptions for all visual content, keyboard navigation
- **Animation** — fragment reveal patterns, slide transition philosophy, motion safety rules
- **Speaker guidance** — notes philosophy (map, not script), pacing, transition writing, apology slide rule
- **Diagram standards** — SVG vs. Mermaid selection, visual standards, progressive reveal, text descriptions
- **Review workflow** — `presentation-designer` → `ui-ux-pro-max` → `speaker-coach` sequence
- **Naming conventions** — files in kebab-case, slides with zero-padded prefix, components in PascalCase

Any override to the above must be documented in the project `CLAUDE.md` under **Platform Overrides**.

---

## External Tools

| Tool | Role | How to Invoke |
|---|---|---|
| `html-slides` | Reveal.js slide generation | Claude Code skill — invoke at Stage 9 (Final Delivery) |
| `ui-ux-pro-max` | Visual design critique | Claude Code skill — invoke at Stage 5 (Design Review) |

---

## Instructions for Claude

1. **Read the project `CLAUDE.md` first.** It defines the audience, goal, constraints, and any platform overrides for this specific presentation.
2. **Apply Presentation OS standards as inherited defaults.** Do not ask the user to restate them — they are inherited by this file.
3. **When project `CLAUDE.md` conflicts with Presentation OS standards,** the project takes priority — but flag the override explicitly.
4. **Do not reproduce Presentation OS documentation in this project.** Reference the framework repo instead.
5. **For slide generation,** delegate to the `html-slides` Claude Code skill.
6. **For design review,** invoke `ui-ux-pro-max`.
7. **Follow the project lifecycle:** Bootstrap → Brief → Outline → Prototype → Design Review → Demo Buildout → Speaker Notes → Rehearsal → Final Delivery → Archive.

---

## Framework Documentation Reference

When you need to consult a specific Presentation OS standard, reference these documents in the framework repo:

| Topic | Document |
|---|---|
| Storytelling | `docs/storytelling.md` |
| Accessibility | `docs/accessibility.md` |
| Animation | `docs/animation.md` |
| Diagrams | `docs/diagram-standards.md` |
| Speaker guidance | `docs/speaker-guidance.md` |
| Interaction and demos | `docs/interaction-standards.md` |
| Presentation lifecycle | `docs/presentation-lifecycle.md` |
| Project lifecycle | `docs/project-lifecycle.md` |
| Project bootstrap | `docs/project-bootstrap.md` |
