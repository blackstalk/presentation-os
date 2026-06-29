# Animation

Animation in presentations is a communication tool, not a special effect.

Every animation should have a reason. If the reason is "it looks cool," remove it.

---

## The Two Valid Reasons for Animation

**1. Controlling information reveal**

Animation allows the presenter to control when each piece of information appears. This is the most powerful use — it prevents the audience from reading ahead and lets the presenter guide attention deliberately.

Use fragments to show the conclusion only after you have built the argument. Show the problem before you show the solution. Ask the question before you reveal the answer.

**2. Showing relationships or change**

Animation can demonstrate how things connect, transform, or relate in ways that static images cannot. A diagram that builds piece by piece as the presenter explains each component is clearer than the same diagram shown all at once.

---

## Fragment Patterns (Reveal.js)

Fragments control the reveal sequence within a slide.

| Fragment Class | Effect | When to Use |
|---|---|---|
| `fragment` (default) | Appears instantly | Most reveal sequences |
| `fragment fade-in` | Appears with opacity fade | Softer reveals in narrative sections |
| `fragment fade-up` | Appears with upward motion | List items in narrative sections — use sparingly |
| `fragment highlight-red` | Highlights existing content | "This is the important part" moments |
| `fragment highlight-blue` | Highlights existing content | Neutral emphasis |
| `fragment highlight-green` | Highlights existing content | Positive or success emphasis |
| `fragment strike` | Crosses out existing content | "We tried this; it didn't work" |

**Avoid:**
- Zoom transitions for fragment reveals (too aggressive)
- Bounce or shake effects (distracting, no communicative value)
- Revealing items in a sequence that does not match the verbal narrative

---

## Slide Transitions

Slide transitions connect sections and set pacing rhythm. They should be decided at the section level, not the slide level.

| Transition | Character | Best For |
|---|---|---|
| `fade` | Calm, professional | Universal default |
| `slide` | Clean, directional | Linear narrative progressions |
| `none` | Immediate, no distraction | Dense content sections |

**Avoid in most presentations:**
- `convex`, `concave`: Visually aggressive, can cause motion discomfort
- `zoom`: Only appropriate where zoom carries semantic meaning (e.g., drilling into detail)

**Rule:** Use consistent transitions within a section. Change transition style only at deliberate section breaks. Do not mix transitions randomly.

---

## Auto-Animate (Reveal.js)

Auto-animate creates smooth transitions between elements that share a `data-id` attribute across two consecutive slides.

**Good uses:**
- Showing a concept expand from a summary statement to a detailed diagram
- Demonstrating system state change
- Transitioning from an overview to a close-up

**Bad uses:**
- Decorative movement with no communicative purpose
- Creating complex markup overhead for minimal visual payoff

---

## Progressive Diagram Reveal

Complex diagrams benefit from sequential reveal — building the diagram as the speaker explains each component.

**Recommended pattern:**

1. Show the complete diagram structure in low-opacity (40–50%)
2. Reveal each component with a fragment as the speaker discusses it
3. Highlight the active component while the others remain dim
4. On the final fragment, restore full opacity to the complete diagram

This approach:
- Controls where the audience is looking at each moment
- Gives the speaker natural pacing cues
- Makes complex diagrams digestible without requiring multiple diagram files

---

## Motion Safety

Before finalizing any animation sequence:

- [ ] Every animation serves reveal-control or relationship-demonstration
- [ ] The audience can understand the content without the animation (static fallback works)
- [ ] Animation pace matches the verbal explanation (not faster, not slower)
- [ ] No animation would cause discomfort for motion-sensitive viewers
- [ ] The sequence has been tested from the presenter's perspective (click count, timing)
