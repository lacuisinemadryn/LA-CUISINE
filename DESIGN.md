# Design System Strategy: The Artisanal Hearth

## 1. Overview & Creative North Star
This design system is built upon the Creative North Star of **"The Artisanal Hearth."** 

Reflecting the rugged yet refined landscape of Puerto Madryn, the system bridges the gap between the raw Patagonian coast and the sophisticated warmth of high-end gastronomy. We are moving away from the "template" look of modern food apps. Instead, we embrace an editorial, high-contrast aesthetic that feels like a premium lifestyle magazine. 

The experience is defined by intentional asymmetry—where large-scale typography overlaps high-quality, desaturated food photography—and a tactile sense of depth achieved through tonal layering rather than structural lines. This isn't just a menu; it is a curated culinary journey.

## 2. Colors: Tonal Depth over Borders
The palette is grounded in the earth and sea of Chubut. We use deep terracotta to stimulate appetite and charcoal to provide a sophisticated, grounded weight.

### The "No-Line" Rule
To maintain a high-end, seamless feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined through background color shifts. For example, a featured dish card using `surface-container-lowest` (#ffffff) should sit atop a `surface-container-low` (#f4f3f1) section. This creates a natural, soft transition that feels architectural rather than digital.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine linen paper.
*   **Base:** Use `surface` (#faf9f6) for the primary background.
*   **Nesting:** Use `surface-container-low` (#f4f3f1) for secondary content areas. 
*   **Focus:** Use `surface-container-highest` (#e3e2e0) for interactive elements like search bars or inactive tabs to provide a subtle "inset" feel.

### The "Glass & Gradient" Rule
Floating navigation bars and overlaying modal headers should utilize **Glassmorphism**. Apply a semi-transparent `surface` color with a `backdrop-blur` (12px–20px). For CTAs, utilize a subtle linear gradient from `primary` (#902e00) to `primary_container` (#b93d00) at a 135-degree angle. This adds a "glow" and dimension that flat colors lack.

## 3. Typography: Editorial Authority
The typography pairing reflects a conversation between tradition (Serif) and modern hospitality (Sans-Serif).

*   **Display & Headlines (Noto Serif):** Used for dish names, storytelling headers, and price points. The bold weight of `display-lg` (3.5rem) should be used aggressively to create focal points, often overlapping image containers to break the grid.
*   **Body & Labels (Plus Jakarta Sans):** Used for ingredient lists, descriptions, and functional UI. `body-md` (0.875rem) provides a clean, breathable reading experience.
*   **Tonal Contrast:** Use `on_surface_variant` (#54433c) for descriptions to reduce visual noise, reserving `on_surface` (#1a1c1a) for critical information.

## 4. Elevation & Depth
In this system, depth is a feeling, not a feature.

*   **The Layering Principle:** Use the `surface-container` tiers to create hierarchy. A card should feel like it is resting on a table, not floating in a void. 
*   **Ambient Shadows:** For floating elements (like a "Book a Table" FAB), use a highly diffused shadow: `box-shadow: 0 12px 32px rgba(26, 28, 26, 0.06)`. The shadow must be tinted with the `on_surface` color to look natural.
*   **The "Ghost Border" Fallback:** If a container requires definition against an identical background, use a "Ghost Border": `outline_variant` (#dac1b8) at 15% opacity. Never use 100% opaque lines.
*   **Roundedness:** Adhere to a soft, organic scale. Use `xl` (1.5rem) for main image containers and `md` (0.75rem) for interactive buttons. This mimics the weathered stones of the Patagonian shoreline.

## 5. Components

### Buttons
*   **Primary:** Background `primary` (#902e00), text `on_primary` (#ffffff), `xl` roundedness. No border.
*   **Secondary:** Background `secondary_container` (#d2e2ee), text `on_secondary_container` (#55656f).
*   **Tertiary:** Text-only using `primary` color, bold weight, with a `0.7rem` (2) spacing gap for the icon.

### Cards & Menu Items
*   **Rule:** **Absolutely no divider lines.**
*   **Structure:** Separate menu items using the `6` (2rem) spacing token. 
*   **Visuals:** Food imagery must occupy at least 40% of the card area. Use `surface-container-low` for the card background to create a soft contrast against the `surface` page.

### Chips (Dietary/Categories)
*   **Style:** `surface-container-high` (#e9e8e5) background with `label-md` text. Use `full` (9999px) roundedness to create a "pebble" shape.

### Input Fields
*   **State:** Use `surface-container-highest` (#e3e2e0) for the field background with a `Ghost Border` on focus.
*   **Typography:** Labels must use `label-md` in `on_surface_variant`.

### Signature Component: The "Chef’s Recommendation" Overlay
A layout pattern where a `display-md` serif headline sits 50% off the edge of a high-quality `xl` rounded image, creating a layered, editorial look that breaks the vertical scroll rhythm.

## 6. Do's and Don'ts

### Do:
*   **Do** use wide margins (token `10` or `12`) to create a sense of luxury and "breathing room."
*   **Do** use high-quality imagery with warm, natural lighting.
*   **Do** nest containers (`surface-container-lowest` inside `surface-container-low`) to define interaction areas.
*   **Do** use the `primary` (#902e00) color sparingly as a "spice" rather than a dominant background.

### Don't:
*   **Don't** use 1px solid dividers or borders.
*   **Don't** use pure black (#000000) for text; always use the `on_surface` (#1a1c1a) or `secondary` tokens.
*   **Don't** cram content. If in doubt, increase the spacing by one level in the scale.
*   **Don't** use standard "drop shadows" with high opacity; they cheapen the artisanal feel.