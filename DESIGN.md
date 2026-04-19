# Design System Strategy: Technical Precision & Editorial Depth

## 1. Overview & Creative North Star
**Creative North Star: The Architectural Monograph**
This design system moves away from the "SaaS Dashboard" trope and toward a high-end, data-dense editorial experience. It is inspired by architectural blueprints and technical whitepapers—where high information density is balanced by rigorous grid discipline and luxurious negative space.

To break the "template" look, we employ **Intentional Asymmetry**. Large-scale headlines (`display-lg`) are often offset against dense blocks of monospace metadata. We treat the screen not as a webpage, but as a physical drafting table where layers of information are stacked with surgical precision.

---

## 2. Colors & Surface Logic
The palette is rooted in a deep, obsidian foundation to allow the vibrant primary blue and pure white text to "vibrate" with clarity.

### The Palette
*   **Foundation:** `background` (#131318) / `surface` (#131318)
*   **Primary Accent:** `primary` (#adc6ff) / `primary_container` (#4d8eff)
*   **Technical Accents:** `tertiary` (#ffb786) for warnings or specific "Design Note" highlights.

### The "No-Line" Rule
Prohibit the use of 1px solid borders for sectioning. Structural boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section sitting on a `surface` background creates a clear but sophisticated division. Use `surface-container-highest` only for the most critical interactive elements.

### Surface Hierarchy & Nesting
Treat the UI as a series of nested physical layers:
1.  **Base Layer:** `surface` (The foundation).
2.  **Sectional Layer:** `surface-container-low` (Large content blocks).
3.  **Component Layer:** `surface-container` (Cards and containers).
4.  **Interaction Layer:** `surface-container-high` (Hover states and active tabs).

### The "Glass & Gradient" Rule
To add "soul" to the technical rigidity:
*   **Glassmorphism:** Use semi-transparent `surface-variant` with a 12px-20px `backdrop-blur` for floating navigation or "Design Note" callouts.
*   **Signature Textures:** Apply a subtle linear gradient (from `primary` to `primary_container` at 15% opacity) across large hero backgrounds to prevent a "flat black" look.

---

### 3. Typography: The Dual-Tone Voice
The typography system uses a high-contrast pairing to distinguish between narrative and data.

*   **The Narrative (Inter/Geist):** Used for `display`, `headline`, and `body` scales. This provides a human, readable touch to the technical content. 
    *   *Strategy:* Use `display-lg` for project titles with tight letter-spacing (-0.02em) to create an authoritative, editorial feel.
*   **The Technical (JetBrains Mono / Space Grotesk):** Assigned to `label-md` and `label-sm`.
    *   *Strategy:* All metrics, timestamps, and technical annotations must use the Monospace scale. This signals "Raw Data" and "Accuracy" to the user.

---

## 4. Elevation & Depth
We eschew traditional drop shadows in favor of **Tonal Layering**.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section. This "recessed" look creates a sophisticated, carved-in appearance.
*   **Ambient Shadows:** For floating elements (Modals/Popovers), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow should feel like a soft glow of darkness rather than a hard edge.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` token at **15% opacity**. Never use 100% opaque borders; they disrupt the architectural flow.

---

## 5. Components

### Metrics & Pills
High-contrast indicators of performance.
*   **Style:** `surface-container-highest` background with `primary` text.
*   **Typography:** Monospace (`label-md`), all-caps, tracking +0.05em.

### Large Cards
*   **Structure:** No dividers. Use 32px or 48px padding (from the spacing scale) to create groupings.
*   **Corner Radius:** Use `md` (0.375rem) for a precise, "machined" look. Avoid large "bubbly" radii.

### 'Design Note' Callouts
Specialized editorial components.
*   **Style:** A vertical 2px accent line of `primary` on the left.
*   **Background:** `surface-container-low` with a 10% `primary` tint.
*   **Content:** Combines a `label-sm` (Monospace) header with `body-sm` (Sans-serif) content.

### Input Fields & Controls
*   **Inputs:** `surface-container-lowest` backgrounds with a "Ghost Border" that transitions to `primary` 100% opacity on focus.
*   **Buttons:** 
    *   *Primary:* Solid `primary` with `on_primary` text. No rounded-full; use `sm` (0.125rem) radius for a more technical "button" feel.
    *   *Tertiary:* Ghost style. Only text and an underline that appears on hover.

---

## 6. Do's and Don'ts

### Do
*   **DO** use strict grid alignments. Align the edge of a `display-lg` title with the start of a `body-md` column.
*   **DO** use `primary` sparingly. It should act as a "laser pointer," guiding the eye to the most important metric or CTA.
*   **DO** embrace "Extreme Whitespace." Give the data-dense areas room to breathe by surrounding them with `surface` fields.

### Don't
*   **DON'T** use 1px solid white borders. They feel "bootstrap" and cheapen the premium charcoal aesthetic.
*   **DON'T** use standard "Drop Shadows." Use tonal shifts between surface tiers instead.
*   **DON'T** mix typography within a single line. Keep Monospace for data and Sans-serif for prose.
*   **DON'T** use icons for everything. Often, a well-typeset Monospace label (e.g., "[ STAT ]") is more sophisticated than a generic icon.