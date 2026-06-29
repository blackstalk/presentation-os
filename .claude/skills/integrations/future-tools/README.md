# future-tools — Integration Extensibility

**Status:** Documentation only — no skill implementation needed.
**Category:** Integration (Extensibility Pattern)

---

## Purpose

This directory documents how future tool integrations should be structured when added to Presentation OS. It is a living guide, not an implementation.

---

## The Integration Pattern

Every new external tool follows the same four-step pattern:

1. **Create** `.claude/skills/integrations/[tool-name]/README.md` with the delegation contract
2. **Document** `docs/tooling/[tool-name].md` with the full integration guide
3. **Update** the director skill to know when to invoke this integration
4. **Record** the change in `CHANGELOG.md`

Directors and specialist skills never call external tools directly — they call integration skills. This keeps the boundary clean.

---

## Future Integration Candidates

### Diagram Generation
Tools that generate SVG or Mermaid diagrams from natural language descriptions, integrating at the `diagram-architect` level.

### PowerPoint / Keynote Export
An integration parallel to `html-slides` that converts Presentation OS content into `.pptx` or `.key` format.

### Design Token Management
A tool managing design tokens (colors, typefaces, spacing) shared across presentation projects, integrating with both review and output layers.

### MCP Server Tools
As the MCP ecosystem grows, presentation-adjacent tools (design tools, diagram tools, export tools) become integration candidates using this same pattern.

### Async Review and Collaboration
Integration with comment and review workflow tools, translating Presentation OS review findings into tool-native comment formats.

---

## What Makes a Good Integration Candidate

A tool is worth integrating when:

- It does one thing better than a general-purpose approach can
- The integration boundary is clear — what Presentation OS owns versus what the tool owns
- The tool is reliable enough to depend on in a presentation workflow
- The delegation contract (input → tool → validation → output) can be fully specified

---

## The Boundary Rule

Before integrating any tool, answer:
- What does Presentation OS provide to this tool?
- What does Presentation OS validate in this tool's output?

If you cannot answer both clearly, the integration is not ready.

---

## See Also

- `docs/tooling/future-tools.md` — the full extensibility guide
- `docs/architecture.md` — the integration layer in the platform architecture
