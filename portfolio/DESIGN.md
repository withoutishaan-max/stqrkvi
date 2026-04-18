# Design System Specification: The Cinematic Noir

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Cinematic Noir."** 

We are moving away from the "SaaS-standard" look—characterized by flat cards and rigid, predictable grids—and moving toward a high-end editorial experience. This system leverages the deep, atmospheric void of space to create a sense of infinite depth. By utilizing intentional asymmetry, light-leaks, and glassmorphism, we position the agency as a high-tech monolith: authoritative, mysterious, and precision-engineered.

This system breaks the template through **tonal layering**. We don't use lines to separate ideas; we use light and shadow to define existence. Elements should feel like they are floating in a dark, pressurized environment, illuminated only by the rhythmic "pulse" of our neon red accents.

---

## 2. Colors & Surface Philosophy
The palette is rooted in the `surface` (#131313) and the `primary` neon-red spectrum. 

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. Boundaries between content blocks must be defined solely through background color shifts or subtle tonal transitions. For example, a `surface-container-low` section sitting directly on a `surface` background creates a sophisticated "step" in depth without the visual clutter of a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of smoked glass. Use the `surface-container` tiers to define importance:
*   **Background:** `surface` (#131313)
*   **Base Layer:** `surface-container-low` (#1b1b1b)
*   **Interactive Cards:** `surface-container-high` (#2a2a2a)
*   **Floating Modals/Popovers:** `surface-container-highest` (#353535)

### The "Glass & Gradient" Rule
To achieve the signature "PlutoTech" look, floating elements must utilize **Glassmorphism**. Use semi-transparent `surface` colors (e.g., 60-80% opacity) paired with a `backdrop-filter: blur(20px)`. 

### Signature Textures
Main CTAs and Hero backgrounds should not be flat. Use a subtle linear gradient transitioning from `primary` (#ffb3ac) to `primary_container` (#ff544e) at a 135-degree angle. This provides the visual "soul" and professional polish required for a premium tech brand.

---

## 3. Typography
Our typography is a dialogue between technical precision and human-centric readability.

*   **Display & Headlines (Space Grotesk):** This is our "Engineered" voice. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero sections. The geometric nature of Space Grotesk communicates the agency's tech-forward identity.
*   **Body & Titles (Manrope):** Manrope provides the "Human" touch. It is approachable and highly legible. Use `body-lg` (1rem) for general copy to maintain an editorial, airy feel.
*   **Labels (Inter):** Reserved for technical metadata and micro-copy. Inter’s neutrality ensures that even the smallest text remains functional and clear.

---

## 4. Elevation & Depth
Depth is not a decoration; it is a functional tool for hierarchy.

*   **The Layering Principle:** Stacking surface tiers creates a soft, natural lift. Instead of a shadow, place a `surface_container_lowest` (#0e0e0e) element inside a `surface_container_high` (#2a2a2a) area to create an "inset" technical look.
*   **Ambient Shadows:** For floating elements, shadows must be extra-diffused. Use a 40px to 60px blur with only 6% opacity. The shadow color should be a tinted version of `on_surface` to mimic natural light refraction through glass.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, it must be a **Ghost Border**. Use the `outline_variant` (#5d3f3c) token at 15% opacity. Never use 100% opaque, high-contrast borders.
*   **Grid Overlays:** To reinforce the "Tech Agency" vibe, apply a subtle 24px square grid overlay using a `0.05` opacity `on_surface` color across hero backgrounds.

---

## 5. Components

### Buttons
*   **Primary:** A "Glow" button. No border. Background is the `primary` gradient. On hover, apply a `box-shadow` of 0px 0px 20px `primary_container` at 40% opacity.
*   **Secondary:** Glassmorphism style. `surface_variant` with a 20px blur and a "Ghost Border" of `outline`.
*   **Sizing:** Use `lg` (0.5rem) roundedness for all buttons to maintain a modern, sleek profile.

### Cards & Lists
*   **The "No-Divider" Rule:** Forbid the use of divider lines in lists. Use vertical whitespace (32px or 48px from the spacing scale) or a subtle shift from `surface` to `surface_container_low` to separate items.
*   **Hover-Lift:** Cards should utilize a subtle `translateY(-4px)` on hover, accompanied by a soft glow from the `primary` token bleeding from the bottom edge.

### Navigation
*   **Fixed Navbar:** Must be `surface` at 70% opacity with a heavy `backdrop-blur`. Use a `surface-container-lowest` bottom border at 1px, but only at 10% opacity.

### Input Fields
*   **Style:** Minimalist. No background fill—only a bottom "Ghost Border" using `outline_variant`. On focus, the border animates to `primary` (#ffb3ac) with a subtle 4px outer glow.

### Chips
*   **Action Chips:** Use `secondary_container` for the background with `on_secondary_container` for text. Keep roundedness at `full` (9999px) for a distinct functional contrast against square cards.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical layouts (e.g., a headline aligned left with body text offset to the right column) to create an editorial feel.
*   **Do** prioritize negative space. If a layout feels "crowded," double the spacing.
*   **Do** use the `tertiary` (#67d7e1) color sparingly for "Success" or "New" indicators to provide a refreshing "cold" contrast to the "warm" red.

### Don't:
*   **Don't** use pure white (#FFFFFF) for body text. Use `on_surface` (#e2e2e2) to reduce eye strain in dark mode.
*   **Don't** use standard drop shadows. If it looks like a "box shadow" from 2015, it's wrong. Think "ambient glow."
*   **Don't** use 100% solid black for large surfaces unless it is the base `surface_container_lowest`. It kills the depth perception of the glass layers.
