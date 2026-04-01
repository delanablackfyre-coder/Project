# Design System Specification

## 1. Overview & Creative North Star: The Digital Sanctuary
This design system is engineered to function as a **Digital Sanctuary**. Moving beyond the utilitarian nature of standard mobile interfaces, our goal is to provide a "trauma-informed" environment that prioritizes emotional safety, cognitive ease, and a sense of gentle protection.

We break the "standard app template" by moving away from rigid grids and clinical borders. Instead, we embrace **Organic Fluidity**. The interface should feel like layered sheets of handmade paper or soft, frosted glass. We use intentional asymmetry—such as off-center typography and overlapping soft-edged containers—to create a human, non-judgmental atmosphere that feels less like a machine and more like a supportive companion.

---

## 2. Colors & Tonal Atmosphere
Our palette avoids the "anxiety-inducing" extremes of pure black and white. Instead, we use a sophisticated range of warmth and softness to soothe the user's nervous system.

### The "No-Line" Rule
To maintain the sanctuary feel, **1px solid borders are strictly prohibited** for sectioning or containment. Traditional lines create visual "noise" and "barriers." Boundaries must be defined through:
1.  **Background Shifts:** Transitioning from `surface` (#fbfbe2) to `surface-container-low` (#f5f5dc).
2.  **Tonal Transitions:** Using subtle value shifts to imply a change in content without "locking" the user in a box.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use a "Nesting" principle to define importance:
*   **Base:** `surface` (#fbfbe2) – The foundation.
*   **Secondary Content:** `surface-container-low` (#f5f5dc) – Softly recessed areas.
*   **Interactive Focus:** `surface-container-highest` (#e4e4cc) – For elements requiring the most attention.

### The "Glass & Gradient" Rule
For floating action sheets or navigation bars, use **Glassmorphism**. Apply `primary_container` (#c8a2c8) at 70% opacity with a heavy `backdrop-blur` (16px+). This creates a sense of depth and lightness, allowing the background colors to bleed through, ensuring the UI never feels "heavy" or oppressive.

### Signature Textures
Main Calls to Action (CTAs) should utilize a **Signature Gradient**:
*   *Direction:* 135° Linear
*   *From:* `primary` (#745475)
*   *To:* `primary_container` (#c8a2c8)
This gradient adds a "soulful" shimmer that flat colors lack, providing a gentle tactile quality.

---

## 3. Typography
We utilize **Plus Jakarta Sans** (our interpretation of the brand's sans-serif roots) for its modern, open counters and friendly demeanor. The goal is to reduce cognitive load by emphasizing a clear, editorial hierarchy.

*   **Display & Headlines:** Use `display-md` or `headline-lg` for welcoming messages. These should be set with generous line-height (1.4) to feel airy.
*   **Body Text:** `body-lg` is our workhorse. We never use pure black; all text is rendered in `on_surface` (#1b1d0e) or `on_surface_variant` (#4c444b) for a softer, charcoal-like legibility.
*   **Editorial Spacing:** Avoid centering all text. Use left-aligned layouts with wide margins (`spacing.8` to `spacing.12`) to provide "breathing room" for the user to process information without feeling overwhelmed.

---

## 4. Elevation & Depth
In this system, depth is a feeling, not a shadow.

*   **The Layering Principle:** Rather than using shadows to lift objects, we "stack" colors. A `surface-container-lowest` card (#ffffff) placed atop a `surface-container-low` (#f5f5dc) background creates a natural, soft lift.
*   **Ambient Shadows:** When a floating element (like a FAB) is necessary, use a "Tinted Ambient Shadow." The shadow should be `primary` (#745475) at 6% opacity, with a blur of 32px and a Y-offset of 8px. This mimics soft, colored light rather than a dark void.
*   **The Ghost Border:** For form fields, use the "Ghost Border"—the `outline_variant` token at 15% opacity. It provides a whisper of structure without the aggression of a solid stroke.

---

## 5. Components

### Buttons & Interaction
*   **Primary Action:** Large, generous buttons (`rounded.xl` / 3rem) using the Signature Gradient. High internal padding (`spacing.4` vertical, `spacing.8` horizontal).
*   **Secondary/Tertiary:** Soft background shifts using `secondary_container`. No borders.
*   **Touch Targets:** All interactive elements must maintain a minimum 48dp height to ensure they are easy to hit even if a user is experiencing physical stress or tremors.

### Cards & Content Buckets
*   **Style:** `rounded.lg` (2rem) or `rounded.xl` (3rem) corners.
*   **Division:** **Never use horizontal dividers.** Separate content using vertical white space (`spacing.6` or `spacing.8`) or by placing content on a slightly different surface tone.

### Supportive Input Fields
*   **Structure:** Soft, pill-shaped or highly rounded rectangles. Use `surface_container_highest` for the field background.
*   **Feedback:** Error states use `error` (#ba1a1a) but must be accompanied by a supportive "Soft Green" (`success` logic) icon or message to mitigate the "punitive" feeling of standard error messages.

### The "Safety Exit" Component (Unique Context)
A persistent, high-contrast (using `tertiary_container`) button designed to look like a generic "Resource" or "Home" button, allowing the user to quickly navigate away to a neutral screen. It uses `rounded.full` for a distinct, tactile feel.

---

## 6. Do's & Don'ts

### Do:
*   **Do** use asymmetrical layouts where one side has more negative space than the other.
*   **Do** use overlapping elements (e.g., an illustration slightly overlapping a text container) to create a hand-crafted, editorial feel.
*   **Do** prioritize `surface-container-low` for large background areas to keep the app feeling "warm."

### Don't:
*   **Don't** use `none` or `sm` roundedness. Everything must be `md` or higher to maintain the "Soft" brand promise.
*   **Don't** use pure white backgrounds except for the most important "Surface Lowest" cards.
*   **Don't** use standard 1px dividers. If you need separation, use a `2rem` gap of empty space.
*   **Don't** use "Alert Red" for warnings. Use the `secondary` (#7b5455) or `error` tones with muted opacities to guide, not alarm.