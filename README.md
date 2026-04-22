# Oddle Logo — Animation Playground

Interactive GSAP animation prototypes for the Oddle logo thinking/loading states.

**Live demo:** [oddle-logo-animation.vercel.app](https://oddle-logo-animation.vercel.app)

---

## Overview

This project explores different animation approaches for the Oddle logo "O" mark — transforming it from a static brand element into an expressive loading/thinking indicator. The logo is built from 4 SVG elements that can be independently animated:

1. **Tail** — the bean-shaped body
2. **Ring** — the purple stroke circle (eye outline)
3. **Ring BG** — white filled circle (creates the eye interior)
4. **Dot** — the purple pupil

The animations start from the full Oddle logo, transform into a circular "thinking" state, and resolve back seamlessly — no opacity fades, no shrinking tricks.

## Animations

### 01 — Orbital Spinner (Spinning Dot)

The logo transforms into a ring while the dot orbits inside it.

**How it works:**
- Dot spirals outward from the eye center (small circles → touching the ring)
- As the dot reaches the ring, the bean tail shrinks and the ring shifts to center
- Dot orbits continuously at constant angular velocity
- On resolve: dot spirals back to center, ring shifts to eye position, bean grows back

**Versions:**
- **V1** — Ring wiggle (reacts to dot weight) + ring thinning during spin
- **V2** — Clean orbit, no wiggle

### 02 — Pulsing Eye (Pulsing Dots)

The dot pulses outward in alternating purple/white, creating a rhythmic breathing effect.

**How it works:**
- First pulse starts inside the logo at the eye position
- Concentric circles expand outward — purple, white, purple, white — staggered in time
- 2–3 circles visible simultaneously creating a bullseye/tunnel effect
- On resolve: pulse naturally completes one final cycle to reconstruct the ring appearance, then shape-shifts back to the logo

## Design Principles

- **Seamless transitions** — no abrupt jumps between animation phases. Single unified `onUpdate` functions drive multiple properties together.
- **Real-world physics** — momentum, inertia, centrifugal force. The dot's orbit makes the ring wiggle. Spinning slows naturally with friction.
- **No opacity tricks** — shape transformations are physical morphs, not crossfades.
- **Every frame intentional** — no element should shrink to zero or appear from nothing without reason.
- **Start and end frames match** — animations loop seamlessly back to the resting logo state.

## Controls

| Control | Description |
|---------|-------------|
| **Start / End** | Toggle thinking animation on/off |
| **Version** | Switch between animation variants |
| **Size** | Preview at 48px, 80px, or 120px |
| **Speed** | Adjust playback speed (0.1x – 3x) |
| **Light / Dark** | Toggle theme (purple shifts to #9B59E1 in dark mode) |

## Tech Stack

- **GSAP 3.12** — animation engine
- **SVG** — all graphics are vector, scalable to any size
- **Vanilla JS** — no framework, single HTML file
- **Vercel** — deployment

## Project Structure

```
index.html    — everything in one file (HTML + CSS + JS)
README.md     — this file
```

## Figma Reference

- **File:** Oddle Website 2025-2026
- **Page:** Animation (artboards: end-1, end-2, pulse-1 to pulse-4)

## Development

Just open `index.html` in a browser. No build step needed.

```bash
open index.html
```

---

Built with [Claude Code](https://claude.com/claude-code)
