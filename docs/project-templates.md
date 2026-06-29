# Project Templates

Every new presentation project inherits the Presentation OS platform and focuses only on what is unique to that presentation.

---

## Starting a New Presentation Project

### 1. Create the Project Directory

```
projects/
└── [presentation-slug]/
    ├── CLAUDE.md          # Project-level operating manual
    ├── brief.md           # Brief document from Phase 1
    ├── story-map.md       # Narrative architecture from Phase 2
    ├── content/           # Slide content (one file per section)
    ├── assets/            # Images, diagrams, media
    └── output/            # Generated presentation files
```

### 2. Write the Project CLAUDE.md

The project CLAUDE.md extends the platform. It must define:

```markdown
# [Presentation Title] — Project Operating Manual

## Audience
[Primary audience: who they are, what they know, what they care about]
[Secondary audience if applicable]

## Goal
[Single sentence: what must be true after this presentation that was not true before]

## Constraints
[Format, length, venue, technical constraints, brand guidelines]

## Success Criteria
[How will we know if this presentation worked?]

## Branding
[Color palette, typefaces, any client or company brand standards]

## Content Scope
[What is in scope. What is explicitly out of scope.]

## Platform Overrides
[Any platform standard this project overrides, and why]
```

### 3. Complete the Brief

Answer these questions in `brief.md`:

1. **Primary audience:** Who are they? Role, level, background, what they care about?
2. **Secondary audience:** Who else might see this?
3. **Goal:** What single thing must this presentation accomplish?
4. **Venue and format:** Live presentation? Async? HTML? Slides?
5. **Length:** How much time does the presenter have?
6. **Constraints:** Brand guidelines, sensitivity, technical environment?
7. **Success criteria:** What does success look like after the presentation?

---

## Template Types

### Technical Deep Dive

For engineering, architecture, and detailed technical content.

**Audience:** Technical practitioners — engineers, architects, data scientists.
**Length:** 30–60 minutes.
**Narrative structure:** Problem → Context → Approach → Implementation → Tradeoffs → Recommendation.
**Design character:** Dark theme, code-first, diagram-heavy, generous use of reveal fragments.
**Key success signal:** Audience understands and can defend the approach.

### Executive Presentation

For leadership, board, and decision-making audiences.

**Audience:** Executives and decision-makers with limited time and broad scope.
**Length:** 15–30 minutes.
**Narrative structure:** Situation → Complication → Recommendation → Evidence → Ask.
**Design character:** Light theme, clean, minimal text, clear metrics.
**Key success signal:** Decision made or clear next step agreed.

### Conference Talk

For public technical or professional conferences.

**Audience:** Mixed technical — some deep experts, many generalists.
**Length:** 30–45 minutes.
**Narrative structure:** Hook → Story → Lessons → Call to action.
**Design character:** Bold, high-contrast, narrative-focused, memorable visual moments.
**Key success signal:** Audience remembers one idea and is moved to try something.

### Product Demonstration

For customers, prospects, or stakeholders evaluating a product.

**Audience:** Buyers or users — varying technical depth.
**Length:** 20–45 minutes.
**Narrative structure:** Problem → Demo → Outcomes → Proof → Next steps.
**Design character:** Product-branded, demo-forward, outcome-focused.
**Key success signal:** Audience sees themselves using the product.

### Client Pitch

For sales, consulting, or partnership proposals.

**Audience:** Client decision-makers and influencers.
**Length:** 30–60 minutes.
**Narrative structure:** Understanding → Vision → Approach → Proof → Investment → Ask.
**Design character:** Client-branded or neutral, professional, trust-building.
**Key success signal:** Client moves to next stage of the process.

### Workshop

For interactive learning and facilitation.

**Audience:** Participants who will actively engage with the material.
**Length:** 60–180 minutes.
**Narrative structure:** Context → Concepts → Practice → Reflection → Application.
**Design character:** Clean, readable, activity-card style for exercises.
**Key success signal:** Participants can apply at least one new skill immediately.

---

## Component Reuse

As you build presentation content, identify reusable patterns and add them to `components/`.

A pattern is worth adding to components when:
- It appears in more than one presentation
- It has a standard implementation that benefits from consistency
- Future presentations would benefit from documentation about how to use it

See `components/README.md` for the component registry and contribution guide.
