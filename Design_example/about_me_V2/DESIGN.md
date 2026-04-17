# Design System: The Editorial Architect

## 1. Overview & Creative North Star

### Creative North Star: "The Editorial Curator"
This design system moves away from the rigid, boxy constraints of traditional portfolio templates. It treats the digital screen as a high-end physical publication—think *Kinfolk* meets *Monocle*. The goal is to convey "Trustworthy Authority" through intentional asymmetry, masterful use of white space, and a sophisticated layering of tonal surfaces.

By leveraging **Manrope’s** geometric yet approachable rhythm and a high-contrast scale, we create an environment where the content doesn't just sit on the page—it is curated within it. We break the "web-native" look by using overlapping elements and unconventional compositions that feel human, bespoke, and premium.

---

## 2. Colors & Surface Philosophy

The palette is anchored in deep, ink-like tones (`primary_container`) contrasted against "paper" whites (`surface`), with a surgical application of `tertiary` (Emerald) to draw the eye to key actions.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** To achieve a high-end editorial feel, boundaries must be defined solely through background color shifts.
*   **Example:** A project gallery section (`surface_container_low`) should sit flush against the main `background` without a divider. The transition of color is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine stationery.
*   **Level 0 (Base):** `surface` (#fcf8fa) - Use for the main canvas.
*   **Level 1 (Subtle Inset):** `surface_container_low` (#f6f3f5) - Use for large secondary content blocks (e.g., an "About Me" section).
*   **Level 2 (Active Elevation):** `surface_container_lowest` (#ffffff) - Use for interactive cards or floating elements to create a "lifted" effect against the slightly greyish base.

### The "Glass & Gradient" Rule
To prevent the design from feeling "flat" or "bootstrap-generic," utilize:
*   **Glassmorphism:** For navigation bars or floating modals, use `surface` at 80% opacity with a `24px` backdrop-blur.
*   **Signature Textures:** Apply a subtle linear gradient on primary CTAs moving from `primary` (#000000) to `primary_container` (#131b2e) at a 135-degree angle. This adds "soul" and depth to the ink-black elements.

---

## 3. Typography

**Primary Typeface:** Manrope (Modern Sans-Serif)
Manrope was chosen for its high legibility and "crisp" corporate-yet-modern feel.

*   **Display (lg/md):** Reserved for high-impact hero statements. Use `primary` color and `-0.02em` letter spacing to create a tight, authoritative "headline" look.
*   **Headline (lg/md/sm):** Used for section titles. Ensure generous top-padding to let the typography breathe.
*   **Body (lg/md):** Set in `on_surface_variant` (#45464d). Never use pure black for long-form text; the slight grey reduces eye strain and increases the perceived quality of the interface.
*   **Label (md/sm):** Always uppercase with `0.05em` tracking. Use for overlines or small meta-data to create a clear stylistic distinction from body copy.

---

## 4. Elevation & Depth

We eschew traditional Material Design shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by stacking. Place a `surface_container_lowest` card on a `surface_container_high` background. The contrast in "paper brightness" creates a natural, soft lift.
*   **Ambient Shadows:** For floating elements (e.g., a "Download CV" FAB), use an ultra-diffused shadow:
    *   `box-shadow: 0 20px 40px rgba(27, 27, 29, 0.05);` (The shadow color is derived from `on_surface`).
*   **The "Ghost Border" Fallback:** If a container lacks sufficient contrast, use a "Ghost Border": `outline_variant` at **15% opacity**. This provides a hint of structure without the "box" feel.
*   **Intentional Asymmetry:** Break the grid. Allow images to bleed off the edge of a container or overlap two different surface tiers to create a sense of movement.

---

## 5. Components

### Buttons
*   **Primary:** Background `primary` (#000000), text `on_primary`. Roundedness: `md` (0.375rem). The sharp-but-soft corner creates a "custom" feel.
*   **Tertiary (Accent):** Background `tertiary_container`, text `on_tertiary_container` (Emerald). Use these sparingly for "Success" states or high-conversion "Hire Me" triggers.

### Cards & Lists
*   **Forbid Dividers:** Do not use `<hr>` tags or border-bottoms. Use `32px` or `48px` of vertical whitespace to separate list items. 
*   **Interactive State:** On hover, a card should transition from `surface` to `surface_container_highest` with a smooth `cubic-bezier(0.4, 0, 0.2, 1)` timing function.

### Text Inputs
*   **Styling:** Use a "filled" style with `surface_container_high`. Only show a bottom-border of `2px` in `primary` when the field is focused. This keeps the form feeling "architectural" and clean.

### Custom Component: The "Work Experience" Timeline
Avoid the "dot-on-a-line" cliché. Use a large `headline-lg` year (e.g., 2024) in `surface_variant` color as a background element, with the job details layered on top in `body-lg`. This creates a sense of depth and sophisticated layering.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use extreme whitespace. If you think there is enough space, add 16px more.
*   **Do** use "Negative Space" as a functional element to group related items.
*   **Do** ensure all iconography uses a consistent `2px` stroke weight to match the "crisp" Manrope letterforms.

### Don’t:
*   **Don't** use 100% opaque borders. They clutter the visual field and feel "templated."
*   **Don't** use default blue for links. Use `tertiary_fixed_dim` (Emerald) or a simple underline on `on_surface`.
*   **Don't** center-align long blocks of text. Stick to asymmetrical, left-aligned compositions for an editorial feel.
*   **Don't** use "Drop Shadows" that are visible as a dark blur. Shadows should be felt, not seen.