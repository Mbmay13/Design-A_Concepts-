# Design System Strategy: Aerospace DeFi

## 1. Overview & Creative North Star

### Creative North Star: "The Stratospheric Horizon"
This design system moves beyond the cluttered complexity of traditional DeFi. It is inspired by the precision of aerospace engineering and the clarity of high-altitude vistas. We shift from "web app" to "digital cockpit," where data is paramount but the experience remains light, airy, and expansive.

To break the "template" look, we employ **Intentional Asymmetry**. Layouts should utilize large amounts of negative space, allowing core transaction modules to "float" above the surface. Elements may overlap—such as a data visualization bleeding slightly out of its container—to create a sense of movement and technical sophistication. This is not a flat grid; it is a layered environment of depth and atmospheric perspective.

---

## 2. Colors

The palette is anchored in deep oceanic blues and electric highlights, creating a high-contrast environment that feels both secure and innovative.

### Palette Roles
- **Primary (`#0047d0`) & Primary Container (`#2660f5`):** Used for the most critical actions—swapping, locking, and connecting. These represent the "Electric Blue" energy of the system.
- **Surface & Background (`#f9f9f9`):** The "Crisp White" foundation. It provides a clean, clinical backdrop that allows data to stand out.
- **Tertiary (`#555554`):** Used for auxiliary data and aerospace-themed iconography.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to section content. Boundaries must be defined solely through background color shifts. For example, a card should be `surface-container-lowest` sitting on a `surface` background. If you need to separate a header, use a subtle tonal shift to `surface-container-low` rather than a divider line.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- Use `surface-container-low` for large section backgrounds.
- Use `surface-container-highest` or `surface-container-lowest` for nested interactive modules (like a swap input).
- This "tonal nesting" creates intuitive hierarchy without visual noise.

### The "Glass & Gradient" Rule
Floating elements (modals, dropdowns, sticky navs) should utilize **Glassmorphism**. Apply a semi-transparent surface color with a `backdrop-blur` of 12px–20px. 
**Signature Texture:** Main CTAs should not be flat. Use a linear gradient from `primary` (`#0047d0`) to `primary_container` (`#2660f5`) at a 135-degree angle to give action buttons a "gem-like" technical polish.

---

## 3. Typography

The typography uses a dual-engine approach: **Inter** for functional readability and **Space Grotesk** for technical labeling.

- **Display & Headlines (Inter):** Set with tight tracking (-0.02em) and bold weights. These should feel authoritative and editorial. Use `display-lg` for hero statements to anchor the page.
- **Body (Inter):** Balanced and neutral. Use `body-md` for standard data to ensure clarity during high-frequency trading.
- **Labels (Space Grotesk):** This is our "technical" font. Used for `label-md` and `label-sm` on data points (APR, TVL, Gas). The geometric nature of Space Grotesk reinforces the high-tech, aerospace aesthetic.

The hierarchy is intentionally dramatic: very large display type contrasted with small, precise technical labels to create a premium, editorial feel.

---

## 4. Elevation & Depth

### The Layering Principle
Depth is achieved through **Tonal Layering**. Place a `surface-container-lowest` card (Pure White) on a `surface` background (`#f9f9f9`). This 1-2% difference in luminosity creates a soft, sophisticated lift that feels more modern than a heavy shadow.

### Ambient Shadows
For "floating" components like the Swap Module:
- **Blur:** 40px to 64px.
- **Opacity:** 4% to 6%.
- **Color:** Use a tinted version of `on-surface` (e.g., `#00164f` at 5% opacity) to mimic natural light passing through a high-tech material.

### The "Ghost Border" Fallback
If a border is required for extreme contrast or accessibility, use a **Ghost Border**: the `outline-variant` token at **15% opacity**. Never use 100% opaque borders; they shatter the "atmospheric" illusion.

---

## 5. Components

### Buttons
- **Primary:** Gradient (`primary` to `primary_container`), `rounded-full`, `title-sm` (Inter, Bold). 
- **Secondary:** Glass-style. Semi-transparent `primary_fixed` with a `backdrop-blur`.
- **States:** On hover, the gradient should shift 180 degrees; on press, use a subtle `inner-shadow` to simulate a physical click.

### Input Fields (The "Flight Deck" Inputs)
- **Styling:** No borders. Use `surface-container-high` as the background.
- **Typography:** Value input should be `headline-sm`. Token symbols (e.g., ETH, AERO) should be in `label-md` (Space Grotesk).
- **Focus:** Instead of a border, use a subtle outer glow of `primary` at 20% opacity.

### Cards & Lists
- **Rule:** Forbid divider lines.
- **Separation:** Use `spacing-8` (2rem) of vertical white space or shift the background to `surface-container-low` for alternating list items.
- **Interactive:** Cards should have a subtle scale-up effect (1.02x) on hover to signify interactability.

### Specialized Component: "The Data Horizon" (Graph/Chart)
- Use a `primary` stroke for line charts with a fading gradient fill that terminates into the background. Use `surface-tint` for "glow" points on data peaks.

---

## 6. Do's and Don'ts

### Do
- **Do** use aerospace-themed iconography (vectors of wings, velocity lines, and orbital paths).
- **Do** prioritize "white space" as a functional tool to reduce user cognitive load in complex DeFi transactions.
- **Do** use asymmetric layouts (e.g., a left-aligned headline with a right-aligned card that sits slightly higher).

### Don't
- **Don't** use 1px solid black or grey borders. This is the fastest way to make a premium system look "cheap."
- **Don't** use sharp corners for containers. Stick to the `md` (0.75rem) and `lg` (1rem) roundedness scale to keep the "aerodynamic" feel.
- **Don't** use standard drop shadows. Always use ambient, diffused blurs.
- **Don't** clutter the screen with dividers. If you can't separate it with color or space, reconsider the information architecture.