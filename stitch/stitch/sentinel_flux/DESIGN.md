# Design System Specification: The Cognitive Vault

## 1. Overview & Creative North Star
This design system is anchored by the Creative North Star: **"The Cognitive Vault."** 

In the high-stakes environment of automated form-filling and data security, we move away from the "utilitarian tool" aesthetic toward a "premium digital concierge" experience. This system rejects the cluttered, line-heavy density typical of Chrome extensions. Instead, it utilizes **Organic Editorialism**—a blend of high-contrast typography, intentional white space (even in constrained pop-up dimensions), and asymmetric layouts that guide the eye through "intelligent" focal points. We don't just fill forms; we curate a secure data-entry experience that feels sophisticated and effortless.

---

## 2. Color & Surface Architecture
The color palette balances the authority of Deep Security Blue with the ethereal glow of AI-accent Indigo.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Boundaries must be articulated through background color shifts.
- To separate a header from a body, transition from `surface` (#f3faff) to `surface-container-low` (#e6f6ff).
- This creates a seamless, "molded" appearance that feels custom-engineered rather than assembled from a kit.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of frosted glass.
- **Base Level:** `surface` (#f3faff)
- **Primary Content Area:** `surface-container-low` (#e6f6ff)
- **Interactive Cards/Elements:** `surface-container-lowest` (#ffffff) to provide a soft, "raised" feel.
- **Overlays/Modals:** `surface-container-highest` (#cfe6f2) to imply density and importance.

### The "Glass & Gradient" Rule
To evoke "Intelligence," use Glassmorphism for floating tooltips or floating action buttons. 
- Use semi-transparent `surface` colors with a `backdrop-blur` of 8px–12px.
- **Signature Texture:** Apply a subtle linear gradient (from `primary` #000666 to `primary-container` #1a237e) on main CTAs. This adds a "soul" to the button, making it feel energized by the AI processing beneath the surface.

---

## 3. Typography
We utilize a dual-font strategy to balance editorial flair with technical precision.

- **The Voice (Manrope):** Used for `display` and `headline` scales. Its geometric yet warm curves suggest a "friendly intelligence." Large-scale headers should use `display-sm` (2.25rem) even in small popups to create an authoritative, high-end editorial feel.
- **The Engine (Inter):** Used for `title`, `body`, and `label` scales. Inter provides the high X-height necessary for readability in the dense environments of web forms.

**Hierarchy as Identity:** Use `title-lg` (1.375rem) for field categories and `label-sm` (0.6875rem) for metadata. The high contrast between these sizes creates an "expensive" look, prioritizing scanning speed and clarity.

---

## 4. Elevation & Depth
In this system, depth is a functional tool, not a decoration.

- **Tonal Layering:** Hierarchy is achieved by stacking `surface-container` tiers. A `surface-container-lowest` (#ffffff) card sitting on a `surface-container-low` (#e6f6ff) background creates a natural lift.
- **Ambient Shadows:** For floating elements, shadows must be ultra-diffused. Use a blur of 16px–24px and an opacity of 4% using the `on-surface` (#071e27) color. This mimics natural light reflecting off a deep blue surface.
- **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` (#c6c5d4) at 15% opacity. Never use 100% opaque borders.
- **Glassmorphism:** Use `surface_variant` (#cfe6f2) at 80% opacity with a blur to create "frosted" panels that allow the user's web content to peak through, reinforcing the extension's role as an overlay.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`). Large corner radius (`xl`: 0.75rem). Use `on_primary` (#ffffff) for text.
- **Secondary:** `secondary_container` (#8596ff) background with `on_secondary_container` (#11278e) text. No border.
- **Tertiary:** Text-only using `primary` (#000666) with a subtle `surface_container_high` hover state.

### Input Fields
- **Base State:** `surface_container_lowest` (#ffffff) background. No border. Use a "Ghost Border" at 10% opacity for definition.
- **Focus State:** Transition the "Ghost Border" to `primary` (#000666) at 40% opacity and add a subtle 2px outer glow.
- **Success State (Filled by AI):** Use `tertiary_fixed_dim` (#88d982) for a subtle background tint and `on_tertiary_fixed_variant` (#005312) for the checkmark icon.

### Cards & Lists
- **No Dividers:** Forbid the use of line dividers. Use `spacing.4` (0.9rem) or `spacing.5` (1.1rem) of vertical white space to separate items.
- **Active State:** Change the background from `surface_container_low` to `surface_container_highest` to indicate selection.

### AI Progress Indicator (Signature Component)
- A pulsing gradient ring using `secondary` (#4355b9) and `tertiary_fixed` (#a3f69c) to represent the "Security + Intelligence" synergy.

---

## 6. Do's and Don'ts

### Do
- **Do** use asymmetric margins (e.g., `spacing.8` on the left, `spacing.6` on the right) to create an editorial, non-templated flow.
- **Do** use `roundedness.xl` (0.75rem) for containers to soften the "Security Blue" and make it feel modern and approachable.
- **Do** lean into `surface_container_low` for the majority of the app's background to reduce eye strain.

### Don't
- **Don't** use pure black (#000000) for text. Always use `on_surface` (#071e27) to maintain the "Deep Security Blue" tonal harmony.
- **Don't** use standard "Success Green" (#00FF00). Use the specified `tertiary` tokens for a more sophisticated, "Success Green" that looks trustworthy, not neon.
- **Don't** use hard-edged shadows. If a shadow feels "visible," it is too heavy. It should feel like a presence, not a shape.