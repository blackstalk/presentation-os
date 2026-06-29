# Future Tools — Extensibility Guide

Presentation OS is designed to integrate with external tools without changing its core architecture.

This document describes the pattern for adding new tools to the ecosystem, what future tools might look like, and the constraints that protect platform integrity as the ecosystem grows.

---

## The Integration Pattern

Every external tool is accessed through an **integration skill** in `.claude/skills/integrations/`.

An integration skill:
1. Translates Presentation OS intent into tool-specific instructions
2. Validates that tool output conforms to Presentation OS standards
3. Documents the boundary between what Presentation OS owns and what the tool owns

Directors and specialist skills never call external tools directly. They call integration skills. This means:

- Adding a new tool requires creating one integration skill
- No changes to directors or specialists are needed
- Platform standards remain the authority — the tool implements them

---

## The Boundary Rule

Every integration must answer two questions clearly:

**What does Presentation OS provide to this tool?**
(The input the integration translates from platform-standard form into tool-specific form)

**What does Presentation OS validate in this tool's output?**
(The standards the integration enforces before returning results to the director)

If the integration cannot answer these questions, the tool is not ready to integrate.

---

## What Future Tools Could Look Like

### Diagram Generation Tools

A tool that generates SVG or Mermaid diagrams from natural language descriptions would integrate at the `diagram-architect` level. The specialist describes what is needed; the integration handles the generation request and validates that output meets `docs/diagram-standards.md`.

### PowerPoint / Keynote Export

An integration that converts Presentation OS content into `.pptx` or `.key` format, paralleling how `html-slides` handles Reveal.js. Follows the same delegation contract pattern — Presentation OS provides content and design tokens; the tool handles format-specific rendering.

### Design Token Systems

A tool that manages design tokens (colors, typeface scales, spacing) would integrate with both the design review layer and the output generation layer. It ensures consistent visual identity without requiring manual specification in each project.

### MCP Server Integrations

As the MCP ecosystem matures, tools accessible via MCP servers can be integrated using the same pattern — one integration skill per MCP tool, with the integration handling translation and validation.

### Async Review and Collaboration Tools

Integration with comment systems, review workflows, or version control platforms for presentation content. The integration would translate Presentation OS review findings into the tool's comment format and return structured feedback.

---

## Guidelines for New Integrations

**Stay within the boundary.** Document clearly what the tool owns and what Presentation OS owns. When in doubt, platform standards win — the tool implements them, it does not define them.

**Do not change platform standards to accommodate a tool.** If a tool cannot meet the platform's accessibility or design standards, it is not the right tool for this ecosystem.

**Keep integrations thin.** Integration skills translate and validate. They do not reason about presentations or make content decisions. Complex reasoning belongs in specialist or director skills.

**Plan for tool evolution.** Tools update their APIs and capabilities. Write integrations so that tool-side changes require only integration skill updates — not changes to directors or specialists.

**No silent failures.** If a tool cannot produce output that meets platform standards, the integration must surface that clearly rather than passing through non-compliant output.

---

## Adding a New Integration: Checklist

- [ ] Create `.claude/skills/integrations/[tool-name]/README.md` with the delegation contract
- [ ] Document: purpose, responsibilities, what the tool does NOT own
- [ ] Document: when to use, when NOT to use
- [ ] Document: input provided, output validated, output returned
- [ ] Create `docs/tooling/[tool-name].md` with the full integration guide
- [ ] Update the director skill to know when to invoke this integration
- [ ] Update `CHANGELOG.md`
- [ ] If the tool is external (installed skill or MCP server), ensure it is documented in `skills-lock.json` or equivalent
