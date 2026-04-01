# Design System Strategy: The Curated Retailer

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Concierge."** 

We are moving away from the "SaaS-dashboard" aesthetic. Instead, we are leaning into high-end editorial layouts that mirror the experience of a luxury retail flagship store. The system is defined by **intentional asymmetry, expansive breathing room, and tonal depth.** We replace rigid boxes with layered surfaces, creating a fluid environment that feels both authoritative and inviting. 

This design system avoids the "templated" look by prioritizing content hierarchy over structural lines, ensuring that whether a user is browsing rewards in the customer portal or managing data in the admin dashboard, the experience feels bespoke, intentional, and premium.

---

## 2. Colors & Surface Philosophy
The palette utilizes a "Midnight & Harvest" foundation. The Primary `deep navy (#001723)` provides a bedrock of trust, while the Secondary `Gold (#775a19)` serves as a luminous accent for achievement.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections or containers. Boundaries must be established through:
1.  **Background Color Shifts:** Placing a `surface-container-low` component on a `surface` background.
2.  **Tonal Transitions:** Using the hierarchy of the `surface-container` tokens to imply edges.
3.  **Negative Space:** Using the Spacing Scale (specifically values `8` through `12`) to create mental groupings.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of premium materials. 
- **Base Layer:** `surface` (#f8f9fa).
- **Secondary Layer:** `surface-container-low` (#f3f4f5) for large content areas.
- **Top Layer:** `surface-container-lowest` (#ffffff) for active interactive cards or "hero" modules.

### The Glass & Gradient Rule
To inject "soul" into the interface:
- **Floating Navigation:** Use `surface_variant` with a 70% opacity and a `20px` backdrop-blur to create a "frosted glass" effect.
- **Signature Gradients:** For primary CTAs and High-Value status cards (Gold/Silver), apply a subtle linear gradient from `primary` to `primary_container`. This adds a tactile, shimmering quality that flat fills cannot replicate.

---

## 3. Typography: The Editorial Voice
We utilize two sans-serif powerhouses: **Manrope** for its modern, geometric elegance and **Inter** for its technical precision.

*   **Display & Headlines (Manrope):** Use `display-lg` and `headline-md` to create an editorial feel. These should be set with tight letter-spacing (-0.02em) to feel "tucked" and professional.
*   **Titles & Body (Manrope):** `title-lg` serves as the primary navigation anchor. `body-lg` (1rem) is our standard for readability, ensuring the "retail" focus remains accessible.
*   **Labels (Inter):** `label-md` and `label-sm` are reserved for metadata, status tags, and admin table headers. Inter’s high x-height ensures clarity even at the smallest scales in the data-heavy admin dashboard.

---

## 4. Elevation & Depth
We eschew the "material" look for a more organic, ambient approach to depth.

*   **The Layering Principle:** Instead of shadows, use the "Stacking Rule." An element of high importance uses `surface-container-lowest` (pure white) to "pop" against the `surface-dim` or `surface-container` background.
*   **Ambient Shadows:** When an element must float (e.g., a modal or dropdown), use a shadow with a blur of `40px`, an offset of `y: 8px`, and an opacity of `4%` using a tint of the `on-surface` color. It should feel like a soft glow, not a dark smudge.
*   **The "Ghost Border" Fallback:** In high-density admin views where contrast is vital, use the `outline-variant` token at **15% opacity**. This provides a "suggestion" of a container without breaking the editorial flow.

---

## 5. Components & Loyalty Statuses

### Loyalty Status Visual Identity
Status is communicated through "Aura Glows" (subtle gradients) rather than just icons:
- **Basic:** `primary_fixed_dim` (#a7cbe4) - Clean, clinical, and foundational.
- **Bronze:** `on_secondary_fixed_variant` (#5d4201) - Earthy and sturdy.
- **Silver:** `tertiary_fixed_dim` (#c7c6c6) - Metallic, sleek, and cool.
- **Gold:** `secondary` (#775a19) - Rich, high-contrast, and shimmering.

### Core Components
*   **Buttons:** 
    *   *Primary:* Solid `primary` with `XL` (1.5rem) rounded corners. 
    *   *Secondary:* `outline-variant` (Ghost Border style) with `on_primary_fixed_variant` text.
*   **Cards:** Forbid divider lines. Separate card headers from body content using a shift from `surface-container-highest` (header) to `surface-container-lowest` (body). Use `DEFAULT` (0.5rem) rounding for a "soft-tech" feel.
*   **Input Fields:** Use `surface-container-low` for the fill. No bottom border. On focus, transition the background to `surface-container-lowest` and add a `2px` "Ghost Border" of the `primary` color.
*   **Data Tables (Admin):** Use `label-md` for headers. Replace row dividers with alternating "Zebra" stripes using `surface` and `surface-container-low`.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins. If a container is flush-left, give the right side an extra `spacing-12` of breathing room to create an editorial "ragged" edge.
*   **Do** layer text over subtle image overlays using `surface-tint` at low opacity to maintain readability.
*   **Do** use `rounded-full` for status chips to make them feel like "gems" or physical retail tags.

### Don't:
*   **Don't** use black (#000000) for text. Always use `on-surface` (#191c1d) to maintain the premium, "ink-on-paper" feel.
*   **Don't** use 1px dividers to separate list items. Use `spacing-3` of vertical white space instead.
*   **Don't** use standard "Blue" for links. Use `primary` with a thick, `2px` underline that is offset by `spacing-0.5` for a sophisticated look.

---

## 7. Spacing Strategy
Our spacing is based on a **0.35rem base unit**. 
- Use **`spacing-2` (0.7rem)** for tight internal component padding (e.g., inside a chip).
- Use **`spacing-6` (2rem)** for standard gutter widths.
- Use **`spacing-16` (5.5rem)** for vertical section separation in the customer portal to ensure the brand feels "expensive" and uncrowded.