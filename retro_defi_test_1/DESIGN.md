# Design System Document: Vintage Avionics

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Flight Deck Mechanic."** 

This is not a modern, "airy" web interface. This is a high-fidelity instrument panel designed for the high-stakes environment of Aerospace DeFi. It breaks from contemporary "soft" design trends by embracing **Industrial Brutalism** and **Tactile Rigidity**. We replace organic curves with sharp 0px corners and substitute decorative whitespace with a dense, information-rich grid that feels like a pressurized cockpit. The goal is to make the user feel like they are piloting a multi-million dollar asset through deep space, where every pixel is a mission-critical data point.

---

## 2. Colors & Surface Logic
The palette is rooted in the "Amber" and "Phosphor Green" aesthetics of 1980s CRTs, set against the void of deep charcoal.

### The Color Tokens
*   **Surface (The Hull):** `#131313`. This is the base of the instrument panel.
*   **Primary (Amber Alerts):** `#ffd597` (Text) and `#ffba43` (Active states). Used for critical navigation and call-outs.
*   **Secondary (System OK):** `#4ce346`. Used for successful transactions, positive yields, and "System Go" indicators.
*   **Tertiary (Hyper-Data):** `#00fe41`. A more vibrant green for high-frequency data streams.

### The "No-Line" Rule (Refined for Avionics)
While the prompt mentions "heavy borders," in this premium execution, we prohibit standard 1px grey dividers. Instead:
1.  **Structural Framing:** Use the `outline` token (`#9f8e78`) at 2px or 3px thickness for major containers to mimic metal casing.
2.  **Internal Sectioning:** Internal divisions must be defined by **Background Shifts**. A `surface_container_low` (`#1c1b1b`) module sits atop a `surface` background. No lines are needed to separate the two; the tonal shift is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of hardware modules:
*   **Level 0 (The Background):** `surface` (#131313).
*   **Level 1 (The Module):** `surface_container` (#201f1f).
*   **Level 2 (The Data Readout):** `surface_container_high` (#2a2a2a).
*   **Level 3 (The Active Input):** `surface_container_highest` (#353534).

### Signature Textures
To avoid a flat "vector" look, apply a subtle **Scanline Overlay** or a 2% noise grain to the `surface`. For CTAs, use a linear gradient from `primary` to `primary_container` to simulate the glow of an incandescent bulb behind a plastic button.

---

## 3. Typography
The typography is the "Voice of the Machine." We use **Space Grotesk** (serving as a modernized monospace surrogate) to maintain high legibility while retaining a technical, engineered feel.

*   **Display (The Radar):** `display-lg` (3.5rem). Used for massive numerical readouts (e.g., Total Value Locked).
*   **Headlines (The Protocol):** `headline-md` (1.75rem). Used for section titles. Must be in ALL CAPS to reinforce the military-grade aesthetic.
*   **Body (The Logs):** `body-md` (0.875rem). Use for descriptions.
*   **Labels (The Metadata):** `label-sm` (0.6875rem). Use `primary` or `secondary` colors for labels to make them look like glowing status indicators.

**Typography Rule:** All numerical data must use a monospaced tracking style. If a font supports tabular figures, enable them. Every digit must align perfectly in a vertical column.

---

## 4. Elevation & Depth
In a cockpit, there is no "light source" from the top-left. Light comes from the glowing screens themselves.

*   **The Layering Principle:** Depth is achieved by "stepping" the surface colors. To make an element pop, do not use a shadow; instead, wrap it in a `surface_bright` (#3a3939) frame.
*   **Glow over Shadows:** Instead of traditional drop shadows, use a **Glow Effect** (Outer Glow). For a floating modal, use a 0px offset, 15px blur shadow using the `primary` color at 15% opacity. This mimics CRT light bleed.
*   **Glassmorphism:** Use for "HUD Overlays." Apply a 10px backdrop-blur to a container with 40% opacity `surface_container_highest`. This allows "radar" or "chart" data to remain visible underneath the active window.

---

## 5. Components

### Buttons (Tactile Switches)
*   **Primary:** Sharp 0px corners. Background: `primary_container`. Border: 2px `outline` on bottom and right to simulate a "raised" physical key. Text: `on_primary_fixed` (Deep Brown/Black).
*   **States:** On `:active`, remove the border and shift background to `primary` to simulate the button being physically depressed.

### Input Fields (Data Entry)
*   **Style:** `surface_container_lowest` background. 2px solid `outline_variant` border. 
*   **Focus State:** Border changes to `secondary` (Green) with a 2px "outer glow" of the same color. Cursor should be a solid, blinking block.

### Cards & Modules
*   **Constraint:** Forbid divider lines. Use `surface_container` for the card body and `surface_container_highest` for the header bar.
*   **Spacing:** Use a strict 8px (0.5rem) grid. Elements should feel "packed" but organized.

### Specialized Component: The "Status Ribbon"
*   A narrow horizontal bar at the top or bottom of every module. It uses `secondary` if the data is live and `error` if the connection is lost. This is the primary indicator of system health.

---

## 6. Do's and Don'ts

### Do
*   **DO** use strict 0px border-radii for everything. No exceptions.
*   **DO** use "Ghost Borders" (`outline_variant` at 20% opacity) for extremely complex data tables where background shifts aren't enough.
*   **DO** capitalize all UI labels (e.g., "EXECUTE SWAP" instead of "Execute swap").
*   **DO** align all text to a hard grid. If a line ends, the next element should start on the next grid line.

### Don't
*   **DON'T** use soft drop shadows or rounded corners. It breaks the "Avionics" immersion.
*   **DON'T** use 1px grey borders to separate content. Use tonal shifts or heavy (2px+) "casing" borders.
*   **DON'T** use gradients for anything other than a "glow" effect. All surfaces should be flat, solid colors to maintain the early computer interface feel.
*   **DON'T** use "Standard" icons. All iconography must be geometric, pixel-aligned, and utilize the same line-weight as the typography.

---

## 7. Interaction Note
All transitions must be instantaneous or use a "flicker" animation (mimicking a CRT monitor powering on). Avoid smooth, 300ms "ease-in-out" transitions. Use "step-end" timing functions to maintain the mechanical, retro-tech feel.