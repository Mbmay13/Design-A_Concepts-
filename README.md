# Design-A Concepts

A collection of design agents — each one is a complete, opinionated design system built to be dropped into an AI coding agent as a prompt or context file. Each agent defines a unique visual language including colors, typography, components, spacing, and interaction rules.

## How to Use

Each folder contains:
- `DESIGN.md` — the full design system document (feed this to your AI agent as context)
- `code.html` — a reference implementation / live preview
- `screen.png` — a visual screenshot of the design

Load the `DESIGN.md` into your agent and it will produce UI that follows the system's aesthetic rules.

---

## Agents

### `ad_copy_light` — Aerospace DeFi (Light)
**Creative North Star: "The Stratospheric Horizon"**

A clean, airy DeFi interface inspired by aerospace precision. Crisp white surfaces, electric blue primaries, and intentional asymmetry. Uses glassmorphism for floating elements and tonal layering instead of borders. Fonts: Inter + Space Grotesk.

### `retro_defi_test_1` — Vintage Avionics (Dark)
**Creative North Star: "The Flight Deck Mechanic"**

An industrial, dark-mode DeFi interface inspired by 1980s CRT instrument panels. Amber and phosphor green on deep charcoal. Sharp 0px corners, dense information grids, scanline textures, and glow effects instead of shadows. Font: Space Grotesk.

---

## Structure

```
/
├── DESIGN_A.md              # Master design strategy document
├── ad_copy_light/           # Light aerospace DeFi agent
│   ├── DESIGN.md
│   ├── code.html
│   └── screen.png
└── retro_defi_test_1/       # Dark retro avionics agent
    ├── DESIGN.md
    ├── code.html
    └── screen.png
```
