# Interaction Standards

Interactive elements in presentations — demos, embedded experiences, navigable content — have specific design requirements that differ from static slides.

---

## Principles

**Interaction must serve comprehension.** An interactive element that delights but does not inform is a distraction. Every interactive element should make the presentation's argument clearer, not more entertaining.

**Never require the audience to interact.** Interactive elements should be explorable but not mandatory. A presentation that requires the audience to click, type, or participate to follow the core argument has failed its design.

**Demos can fail. Plan for it.** Every live demo must have a fallback: a screenshot, a recording, or a verbal description that communicates the same point. The argument must survive the demo failing.

**Test in the delivery environment.** A demo that works on your laptop may not work projected at full screen, through a video conferencing screen share, or in a conference room AV system. Test there.

---

## Types of Interactive Elements

### Navigable Sections

Presentations with non-linear navigation (overview mode, linked sections) allow audiences to ask "how does this relate to X?" and have that question answered immediately.

**When to use:** Long presentations (30+ slides) where audiences may have varying depth of interest in different sections.

**Implementation:** Reveal.js overview mode (`Esc`), internal links with `data-preview-link`.

### Live Demos

Live demonstrations of software, workflows, or prompts.

**Requirements before delivery:**
- Defined demo script with each step and its timing target
- A fallback for each demo step (screenshot or verbal description)
- Environment pre-configured and tested in the presentation environment
- Known-good state to return to if something goes wrong

### Embedded Experiences

Interactive content embedded within slides — clickable prototypes, data explorers, calculators.

**Requirements:**
- Must load reliably without network dependency (prefer offline embedding)
- Must not require audience authentication
- Must have a static fallback if the embed fails to load

### Prompt Walkthroughs

Step-by-step display of AI prompt interactions.

**Requirements:**
- Pre-generated — never run live prompts during a presentation
- Show enough context for the interaction to be meaningful
- Explain why the prompt is designed the way it is, not just what it produces
- Highlight the key moments of the interaction, not every token

### Media Integration

Video or audio embedded in slides.

**Requirements:**
- Media files bundled with the presentation (no streaming URLs for high-stakes presentations)
- Captions for all audio content (accessibility)
- Text alternative for content communicated only through audio or video
- Test autoplay behavior in the delivery environment — it behaves differently across browsers and OS configurations

---

## Keyboard Navigation

All HTML presentations must support keyboard navigation:

| Key | Action |
|---|---|
| Space / Right arrow / Down arrow | Next slide |
| Left arrow / Up arrow | Previous slide |
| `Esc` | Overview mode |
| `S` | Speaker notes view |
| `F` | Fullscreen |
| `B` | Blackout (blank screen) |

Interactive elements within slides must also be keyboard-accessible. Never rely on hover states alone to reveal critical information — keyboard and touch users cannot hover.

---

## Touch and Mobile

Presentations are increasingly viewed on mobile devices by remote participants and async viewers.

- Touch swipe must navigate slides correctly
- Text must be legible without zoom on mobile viewport
- Interactive elements must have tap targets of at least 44×44px
- Do not rely on right-click or hover-only interactions

---

## The Fallback Rule

For every interactive element, define the fallback before building the interaction.

If the fallback is embarrassing — if the presentation breaks without the interaction — the interaction is carrying too much weight. Redesign so the argument works without it.
