# Design System Strategy: The Cognitive Vault

## 1. Overview & Creative North Star
This design system is built to transform a utilitarian extension into a high-end digital sanctuary. The **Creative North Star** is "The Digital Curator"—a design philosophy that balances the rigid security of a vault with the effortless fluid intelligence of an AI assistant. 

To move beyond the "standard extension" aesthetic, we utilize **intentional asymmetry** and **tonal depth**. Large, editorial-style headings sit in open white space, while functional elements are clustered into "Cognitive Containers" that feel nested and tactile. We break the grid by allowing interactive elements to overlap surface transitions, creating a sense of 3D layering that guides the user’s eye to the primary action.

---

## 2. Colors & Surface Logic
The palette is anchored in a sophisticated Indigo (`primary: #2b3896`), providing an authoritative and secure foundation. 

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning content. Boundaries must be defined through background color shifts. For example, a dashboard menu should use `surface_container_low` against a main content area of `surface`. This creates a seamless, "molded" look rather than a boxy, fragmented one.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of premium materials:
*   **Base Layer:** `surface` (#f8f9fa) – The canvas.
*   **Sub-Section Layer:** `surface_container` (#edeeef) – For grouping secondary information.
*   **Floating Vaults:** `surface_container_lowest` (#ffffff) – For the most critical interactive cards or "Vault" entries, giving them a natural, bright lift.

### The "Glass & Gradient" Rule
To evoke "Intelligence," use Glassmorphism for floating extension popovers. Apply `surface_container_lowest` at 85% opacity with a `16px` backdrop blur. For primary CTAs, apply a subtle linear gradient from `primary` (#2b3896) to `primary_container` (#4551af) at a 135-degree angle to add a "liquid" professional polish.

---

## 3. Typography: Editorial Authority
We utilize a pairing of **Manrope** (Display/Headlines) and **Inter** (Body/Labels) to balance character with legibility.

*   **Display & Headline (Manrope):** These are the "Curator" voice. Use `display-md` (2.75rem) with tighter letter-spacing (-0.02em) for hero moments. This creates an authoritative, high-contrast look that feels "Web3 Premium."
*   **Body & Labels (Inter):** The "Assistant" voice. `body-md` (0.875rem) is the workhorse. It provides a clean, geometric counter-balance to the expressive headings.
*   **Visual Hierarchy:** Use `on_surface_variant` (#454652) for secondary body text to ensure the `on_surface` (#191c1d) headlines remain the focal point.

---

## 4. Elevation & Depth
Depth in this system is achieved through **Tonal Layering** and light physics, not structural lines.

*   **The Layering Principle:** Instead of shadows, place a `surface_container_lowest` card on a `surface_container_high` background. The contrast in luminance creates a "soft lift" that feels architectural.
*   **Ambient Shadows:** For floating elements like the extension popup, use an extra-diffused shadow: `box-shadow: 0 12px 40px rgba(43, 56, 150, 0.08)`. Note the use of the `primary` indigo color in the shadow to mimic natural light refraction.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke, use `outline_variant` at 20% opacity. Never use 100% opaque borders.
*   **Glassmorphism:** Elements like tooltips or floating action buttons should use semi-transparent `surface` fills with backdrop-blur to feel integrated into the "Cognitive Vault" environment.

---

## 5. Components

### Buttons & Interaction
*   **Primary Vault Button:** Rounded `md` (0.375rem). Uses the Indigo gradient. On hover, the elevation increases via a slight increase in `primary_container` brightness.
*   **Ghost Actions:** No background. Uses `on_surface_variant` and the `primary` color only for the icon.

### Input Fields (The "Fill" Experience)
*   **Structure:** No bottom border. Inputs are `surface_container_highest` with a `sm` (0.125rem) radius. 
*   **States:** On focus, the background shifts to `surface_container_lowest` and a 2px "Ghost Border" of `primary` appears.

### Cognitive Cards & Lists
*   **Forbid Dividers:** Do not use lines to separate list items. Use `2.5` (0.5rem) of vertical spacing and alternating `surface` / `surface_container_low` background shifts to distinguish rows.
*   **Status Indicators:** Use `error` (#ba1a1a) and `tertiary` (Teal for success) sparingly as small, high-contrast pips or soft "glow" pulses rather than large banners.

### Vault Progress Indicator
A custom component for "AutoFillUp." A thin, `0.5` (0.1rem) height bar using a gradient from `tertiary` to `primary` to show completion of form filling, signifying "Seamless Efficiency."

---

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical margins (e.g., more white space on the left than the right) for headline sections to create an editorial feel.
*   **Do** use `primary_fixed_dim` for "read-only" vault data to give it a sophisticated, "archived" look.
*   **Do** rely on the Spacing Scale (specifically `8` and `12`) to create "breathing room" between functional groups.

### Don't
*   **Don't** use pure black (#000000) for text. Use `on_surface` to maintain the indigo-tinted tonal harmony.
*   **Don't** use standard `4px` borders. If the "No-Line" rule is broken, the design system loses its premium "Vault" feel and reverts to a generic template.
*   **Don't** use high-opacity shadows. If a shadow is clearly visible as a "dark smudge," it is too heavy; it should feel like a soft glow of ambient light.