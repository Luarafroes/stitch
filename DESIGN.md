# Design System Specification: The Sonic Editorial

## 1. Overview & Creative North Star
This design system is an evolution of dark-mode aesthetics, pivoting away from "safe" corporate minimalism toward a high-energy, premium editorial experience. We are defining a North Star we call **"The Sonic Editorial."** 

The objective is to merge the rhythmic energy of a modern digital music platform with the prestige of a high-end streetwear lookbook. We break the "template" look by rejecting rigid, boxed-in layouts in favor of intentional asymmetry, massive typographic contrast, and depth created through light rather than lines. The interface shouldn't just sit there; it should feel like it’s vibrating with curated energy.

---

## 2. Colors & Atmospheric Depth
Our palette is anchored in deep obsidian (`#0e0e0f`) but punctuated by hyper-saturated accents. The primary engine of this system is the tension between the dark surface and the electric `primary` (#97a9ff) and `secondary` (#ff6b98) tones.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. We define boundaries through tonal shifts. 
- Use a `surface-container-low` section to sit against a `surface` background. 
- Content blocks are separated by vertical air (see Spacing) or subtle shifts in the surface tier, never by a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of semi-transparent materials.
- **Base Layer:** `surface` (#0e0e0f).
- **Secondary Content:** `surface-container-low` (#131314).
- **Interactive Cards:** `surface-container-high` (#201f21).
- **Nesting:** When placing a container inside another, always jump at least two steps in the hierarchy (e.g., a `surface-container-highest` card inside a `surface-container-low` section) to ensure the "lift" is perceptible without high contrast.

### The Glass & Gradient Rule
To achieve a "Pop" aesthetic that feels premium:
- **Glassmorphism:** For floating overlays or navigation bars, use `surface_variant` (#262627) at 60% opacity with a `20px` to `40px` backdrop-blur. 
- **Signature Gradients:** For Hero CTAs and high-impact moments, use a linear gradient transitioning from `primary` (#97a9ff) to `primary_container` (#859aff) at a 135-degree angle. This adds "soul" and prevents the vibrance from feeling flat or "cheap."

---

## 3. Typography
We utilize a high-contrast pairing to bridge the gap between "Streetwear Brutalism" and "Clean Tech."

- **The Display Voice (Space Grotesk):** This is our character font. Use `display-lg` and `display-md` for headlines that break the grid. Don't be afraid to use tight letter-spacing (-2%) for a more aggressive, editorial feel. 
- **The Functional Voice (Manrope):** All body copy and labels use Manrope. It is clean, geometric, and stays out of the way, allowing the display font to lead.

**Hierarchy as Identity:**
- **Drama:** Use `display-lg` (3.5rem) immediately adjacent to `body-sm` (0.75rem). This extreme "Scale Gap" is a hallmark of high-end design. 
- **Labels:** Always use `label-md` in uppercase with `0.05rem` letter-spacing when paired with `secondary` (#ff6b98) text to denote "Trendy/New" status.

---

## 4. Elevation & Depth
We reject traditional drop shadows. Depth in this system is organic and atmospheric.

- **The Layering Principle:** Avoid "Elevated" shadows. Instead, "stack" surface tiers. A `surface-container-lowest` card placed on a `surface-container-low` section creates a natural "sunken" effect that feels sophisticated and intentional.
- **Ambient Glows:** If a component must float (like a FAB or a Tooltip), use an **Ambient Shadow**. The shadow color should be a 10% opacity version of `surface_tint` (#97a9ff) with a blur value of `24` or higher. This mimics a neon glow rather than a muddy shadow.
- **The Ghost Border:** If a border is required for accessibility (e.g., in high-density data), use the `outline_variant` token at **15% opacity**. This creates a "suggestion" of a boundary that doesn't break the editorial flow.

---

## 5. Components

### Buttons
- **Primary:** Pill-shaped (`rounded-full`), using the `primary` to `primary_container` gradient. Text is `on_primary_fixed` (Black).
- **Secondary:** `rounded-full` with a "Ghost Border" (outline-variant @ 20%). On hover, fill with `surface_bright` (#2c2c2d).
- **Tertiary:** No background. Text uses `secondary` (#ff6b98) with an underline that only appears on hover.

### Cards & Lists
- **The "No-Divider" Mandate:** Forbid the use of line dividers.
- **Execution:** Separate list items using `spacing-4` (1.4rem). Use a `surface-container-highest` background for the active/hovered state.
- **Layout:** Use asymmetrical padding. Try `spacing-5` for the left padding and `spacing-8` for the right to create a "pushed" editorial look.

### Input Fields
- **Base:** Use `surface_container_highest` with `rounded-md`.
- **Active State:** Change the background to `surface_bright` and add a `2px` bottom-only stroke of `primary`.
- **Error:** Text uses `error` (#ff6e84); the container remains dark but gains a soft `error_container` glow.

### Signature Component: The "Spotlight" Chip
A custom element for this system. A selection chip using `secondary_container` (#bb0058) with `on_secondary` (#47001d) text. When selected, it should have a subtle outer glow (Ambient Shadow) in the `secondary` color.

---

## 6. Do's and Don'ts

### Do
- **Do** allow typography to bleed off-center. Asymmetry is your friend in high-end editorial.
- **Do** use `spacing-16` and `spacing-20` for section breaks to let the content breathe.
- **Do** use `secondary` (#ff6b98) sparingly as a "vibe" accent—think of it as a highlighter for the most important 5% of the screen.

### Don't
- **Don't** use pure `#000000`. Stick to `surface` (#0e0e0f) to maintain the premium "matte" finish.
- **Don't** use standard Material Design "Drop Shadows." They feel dated and corporate.
- **Don't** put borders around images. Let the imagery define its own shape against the `surface` background.
- **Don't** use icons as the primary focal point. In this system, Typography is the hero; icons are strictly supportive.