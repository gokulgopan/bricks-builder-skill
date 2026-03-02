# 🤖 AI Capabilities: Bricks Builder Element Generation

This document outlines exactly what I (the AI) have learned how to generate for Bricks Builder, based on the element examples provided so far. 

As you add more examples to the library, these capabilities will expand.

---

## 🏗️ Layout & Composition Skills
I know how to build the structural foundation of your pages:

- **Universal Section Pattern**: Creating proper `<section>` wrappers with inner layout containers.
- **2-Column Grids**: Building standard split layouts (like Hero and CTA sections) using CSS Grid.
- **12-Column Advanced Grids**: Creating complex, overlapping layouts using `repeat(12, 1fr)` and column spanning (e.g., spanning cols 1-8 for content, cols 6-12 for images).
- **Flexbox Layouts**: Building horizontal bars (like Navigation) using flex row, space-between, and wrap controls.
- **Responsive Collapse**: Implementing breakpoint overrides (e.g., forcing a 2-column grid to become a 1-column grid on tablets).

## 🎨 Styling & Theming Skills
I know how to style elements to match your design system:

- **BEM Class Naming**: Automatically generating clean, organized class names (e.g., `hero-1`, `hero-1__content`, `hero-1__heading`).
- **Design Token Integration**: Mapping visual requirements to your exact CSS variables instead of hardcoded pixels:
  - Sizes/Spacing: `var(--space-m)`, `var(--container-width)`
  - Colors: `var(--bg-color)`, `var(--text)`
  - Typography: `var(--text-l)`, `var(--leading-relaxed)`
  - Borders: `var(--radius-s)`
- **Hover & Interactive States**: Applying `:hover` overrides for backgrounds, borders, and text colors.
- **Custom CSS Injection**: Writing raw CSS into the native `_cssCustom` property for things Bricks settings can't handle (like staggered `nth-child` grid layouts).

## 🧱 Component-Specific Skills
I can reliably generate these specific types of UI components:

### 1. Buttons & Call-to-Actions
- Creating primary (filled) and secondary (outlined) buttons.
- Grouping buttons correctly with flex-wrap and responsive gaps.
- Applying dual-styling approaches (both Bricks native `style: "primary"` and custom classes like `btn-primary`).

### 2. Navigation Menus
- Building fully responsive top navbars.
- Implementing the Bricks `nav-nested` element with dropdown support.
- Configuring mobile hamburger menus (trigger breakpoints, stretch alignment, off-canvas positioning).
- Setting up dropdown animations (e.g., translateY: 40px to 0px).

### 3. Hero & Feature Sections
- Composing content blocks with H1/H2 headings, descriptions, and CTAs.
- Handling responsive spacing gaps between text elements.
- Managing media wrappers with aspect-ratio controls (1:1 square, 16:9 widescreen) and `object-fit: cover`.

### 4. Semantic Lists & Cards
- Building grids of cards (like services or features).
- Overriding default `div` tags with semantic `<ul>` and `<li>` tags.
- Resetting default browser list styling using injected CSS.
- Integrating SVG icons directly from the WordPress media library into cards.

---

## 🚀 What I Can't Do Yet (Training Needed)
To be fully capable of building an entire site, I still need examples of:

1. **Dynamic Data**: How Bricks handles pulling dynamic content (like `{post_title}` or ACF fields).
2. **Complex Media**: Carousels, sliders, or video background integrations.
3. **Forms**: The exact JSON structure for native Bricks forms.
4. **Footers**: Multi-column footer layouts with widget areas or complex sub-menus.
5. **Query Loops**: How Bricks structures repeater elements for blog posts or custom post types.

> **Want me to learn these?** Just copy the element in Bricks, paste the JSON, and provide a screenshot!
