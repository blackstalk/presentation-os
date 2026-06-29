# demo-builder

**Status:** Not yet implemented — vision document only.
**Category:** Specialist

---

## Purpose

`demo-builder` creates and integrates interactive elements within presentations — live demos, embedded experiences, prompt walkthroughs, and media integration.

---

## Responsibilities

### Interactive Demos
- Designing demo scripts with defined steps, timing, and fallbacks
- Creating fallback plans for each demo step
- Ensuring demos work reliably in the presentation environment (not just locally)
- Preparing pre-recorded backups for critical demo sequences

### Embedded Experiences
- Integrating interactive content within slides (prototypes, explorers, calculators)
- Ensuring embedded content loads reliably without requiring audience authentication
- Creating static fallbacks for all embedded content

### Prompt Walkthroughs
- Designing step-by-step AI prompt interaction displays
- Pre-generating all prompt interactions — never live during delivery
- Writing explanations of design intent behind each prompt (not just the output)
- Highlighting the key moments of the interaction

### Media Integration
- Embedding video or audio at appropriate presentation moments
- Bundling media files with the presentation (no streaming dependencies for high-stakes presentations)
- Providing captions and text alternatives for all audio-visual content

### Live Examples
- Creating code examples designed for live execution
- Designing REPL or interactive coding environments for technical presentations
- Ensuring live examples have a known-good fallback state

---

## Demo Safety Rules

These rules are non-negotiable:

1. **Never rely on live AI calls during delivery.** Pre-generate all AI interactions.
2. **Test in the presentation environment** — not just locally. Video conference screen share, conference room AV, and browser all behave differently.
3. **Every demo step has a fallback.** If step N fails, the speaker continues without it.
4. **Network dependencies are risks.** Prefer offline-capable demos for high-stakes presentations.
5. **Time demos conservatively.** Demos always take longer than expected. Budget for it.

---

## Fallback Rule

For every interactive element, define the fallback before building the interaction.

If the fallback is embarrassing — if the presentation breaks without the interaction — the interaction is carrying too much weight. Redesign so the argument survives the demo failing.

---

## See Also

- `docs/interaction-standards.md` — interaction design principles this skill applies
- `docs/accessibility.md` — accessibility requirements for all interactive content
- `docs/presentation-lifecycle.md` — where demos are integrated (Phase 4–5)
