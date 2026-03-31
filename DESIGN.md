# Design System: High-End Editorial Beauty

## 1. Overview & Creative North Star: "The Velvet Editorial"
The objective of this design system is to transcend the standard "service provider" website and position the brand as a curated, high-fashion experience. The Creative North Star is **"The Velvet Editorial"**—a design philosophy that treats every screen like a spread in a premium fashion magazine.

To achieve this, we break away from rigid, boxy templates. We embrace **intentional asymmetry**, where images may bleed off-canvas or overlap typography, and we utilize a **high-contrast typography scale** to create a sense of rhythmic pacing. This isn't just a UI; it is an atmosphere of warmth, luxury, and artisanal precision.

---

## 2. Colors & Tonal Depth
The palette is rooted in deep, earthy sophistication, contrasted by luminosity. 

### The "No-Line" Rule
Standard 1px solid borders are strictly prohibited for sectioning. Structural boundaries must be defined through:
1.  **Background Color Shifts:** Transitioning from `surface` (#1d100b) to `surface_container_low` (#261813).
2.  **Tonal Transitions:** Using the `Light Section` (#FAF8F5) to create "interruptions" in the dark flow, signaling a shift in content (e.g., from a services list to a testimonial).

### Surface Hierarchy & Nesting
Treat the interface as physical layers of fine paper. 
- Use `surface_container_lowest` (#180b07) for the most recessed elements.
- Use `surface_container_high` (#362621) for elevated interactive elements.
- **Nesting:** A `primary_container` (#c8a96a) card should sit on a `surface_container` (#2b1c17) background to provide a soft, natural lift.

### The "Glass & Gold" Signature
- **Glassmorphism:** For floating navigation or modal overlays, use `surface_bright` (#46352f) at 60% opacity with a `backdrop-blur` of 12px.
- **Signature Textures:** Use subtle linear gradients for CTAs, transitioning from `primary` (#e5c483) to `primary_container` (#c8a96a) at a 45-degree angle to mimic the shimmer of brushed gold.

---

## 3. Typography: Editorial Authority
Typography is our primary tool for storytelling. We pair the timeless elegance of `Newsreader` (representing Playfair) with the architectural clarity of `Manrope` (representing Jost).

- **Display & Headlines (Newsreader):** Use `display-lg` for hero moments. Lean heavily into *italics* for specific keywords to evoke a sensual, editorial voice.
- **Body & Labels (Manrope):** Use `body-lg` (light weight) for descriptions. Ensure a wide letter-spacing (`0.02em`) for labels to maintain a high-fashion, "boutique" feel.
- **Hierarchy:** The jump between `headline-lg` (2rem) and `body-md` (0.875rem) should be drastic. High contrast in scale creates the "premium magazine" look.

---

## 4. Elevation & Depth
We reject traditional drop shadows in favor of **Tonal Layering**.

- **The Layering Principle:** Depth is achieved by stacking. Place a `surface_container_highest` element over a `surface` background. The color difference alone should provide the "lift."
- **Ambient Shadows:** If an element must float (like a "Book Now" FAB), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(29, 16, 11, 0.15);`. The shadow color must be a tint of the `surface` color, never pure black or grey.
- **The "Ghost Border" Fallback:** If a border is required for input fields, use the `outline_variant` (#4d463a) at **20% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text. No border. Sharp corners or `DEFAULT` (0.25rem) radius only.
- **Secondary:** Transparent background with a `primary` "Ghost Border" (20% opacity).
- **Interactive State:** On hover, primary buttons should subtly expand (scale 1.02) with a smooth `0.4s ease-out` transition.

### Cards & Lists
- **Forbid Dividers:** Do not use lines to separate list items. Use vertical whitespace (Spacing Scale `8` or `10`) or alternating background tints between `surface_container_low` and `surface_container_lowest`.
- **Editorial Cards:** Images in cards should have a slight `0.25rem` radius. Text should overlap the image slightly using negative margins to break the "grid" feel.

### Input Fields
- Underlined style only (using the `outline_variant` at 30% opacity).
- Focused state: The underline transforms into the `primary` gold color and expands from the center.

### Signature Component: "The Gold Accent"
A horizontal line using the `primary` (#e5c483) color, 2px thick, but only 40px wide. Use this to precede section titles or to separate a pull-quote from body text. It is the "artisanal" stamp of the brand.

---

## 6. Do's and Don'ts

### Do:
- **Use Generous Whitespace:** If you think there is enough space, add 20% more. Luxury is defined by what you *don't* fill.
- **Smooth Scroll Reveals:** Animate elements as they enter the viewport. Use a "fade-in and slide-up" effect with a long duration (0.8s) and a soft cubic-bezier easing.
- **Intentional Asymmetry:** Offset images from their containers to create a dynamic, non-template layout.

### Don't:
- **No Harsh Borders:** Never use 100% opaque borders for containers. It breaks the "Velvet" feel.
- **No Pure Greys:** Every "neutral" must be tinted with mocha (#1d100b) or rose (#D9A99A). Pure grey feels industrial; tinted neutrals feel expensive.
- **No Crowding:** Avoid placing more than three service offerings in a single horizontal row. Use a carousel or vertical stack to maintain focus.

### Accessibility Note:
While the aesthetic is "soft," ensure that all `on_surface` text on `background` maintains a 4.5:1 contrast ratio. Use the `primary_fixed` variants for smaller text that requires extra legibility against the dark mocha backgrounds.