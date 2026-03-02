# Bricks Builder JSON Structure Reference

This document describes the JSON structure used by Bricks Builder for element import/export. It will be updated as more examples are analyzed.

## Basic Structure

Bricks Builder elements are represented as a **JSON array** of element objects. Each object represents a single element in the page structure.

```json
[
  {
    "id": "abc123",
    "name": "element-type",
    "parent": 0,
    "children": ["def456"],
    "settings": { ... },
    "label": "Custom Label"
  }
]
```

## Common Element Properties

| Property   | Type            | Description                                      |
|------------|-----------------|--------------------------------------------------|
| `id`       | string          | Unique 6-character alphanumeric identifier       |
| `name`     | string          | Element type (e.g., `section`, `heading`, `text`) |
| `parent`   | string or `0`   | Parent element ID, `0` for root-level elements   |
| `children` | array of strings| IDs of child elements                            |
| `settings` | object          | All element configuration and styling            |
| `label`    | string          | Optional custom label shown in the editor        |
| `themeStyles` | array        | Theme style references (often empty `[]`)        |
| `cloneable` | boolean        | Whether element can be cloned in editor          |
| `deletable` | boolean        | Whether element can be deleted in editor         |

## Element Types

### Structure
- `section` — Page section (root-level wrapper)
- `container` — Flex/grid container
- `block` — Generic block wrapper (div), supports `tag` override
- `div` — Generic div wrapper

### Content
- `heading` — Heading (h1–h6)
- `text` — Rich text / paragraph
- `text-basic` — Basic text
- `image` — Image element
- `button` — Button element (supports `style`: `"primary"` / `"secondary"`)
- `icon` — Icon element
- `video` — Video element

### Dynamic Data (WordPress)
- `post-reading-time` — Post reading time (supports `suffix` property)

### Navigation
- `logo` — Site logo (has `logoText` and `logo` image properties)
- `nav-nested` — Responsive navigation wrapper with mobile menu support
- `text-link` — Text with link (used for nav items)
- `dropdown` — Dropdown trigger with chevron icon
- `toggle` — Hamburger menu toggle (has `animation` property, e.g., `"squeeze"`)

## Settings Object

The `settings` object varies by element type but commonly includes:

### Styling Properties
- `_cssGlobalClasses` — Array of global class IDs applied to the element
- `_cssCustom` — Custom CSS injected directly into the component (native Bricks feature)
- `_typography` — Font family, size, weight, letter-spacing, color, line-height
- `_typography:hover` — Hover state typography overrides
- `_background` — Background color, image, gradient
- `_background:hover` — Hover state background overrides
- `_border` — Border width, color, radius, style
- `_border:hover` — Hover state border overrides
- `_padding` — Padding (top, right, bottom, left)
- `_margin` — Margin (top, right, bottom, left)
- `_width` / `_widthMax` — Width and max-width
- `_height` / `_heightMin` / `_heightMax` — Height controls
- `_aspectRatio` — Aspect ratio (e.g., `"16 / 9"`)
- `_objectFit` — Object-fit for images (e.g., `"cover"`)
- `_cssTransition` — CSS transition value
- `_zIndex` — Z-index value
- `_interactions` — Array of native Bricks interactions (scroll animations, clicks). Example: `[{"trigger": "enterView", "action": "startAnimation", "animationType": "zoomIn"}]`

### Flex / Grid Layout Properties
- `_display` — Display type (`"flex"`, `"grid"`)
- `_direction` — Flex direction (`"row"`, `"column"`)
- `_flexWrap` — Flex wrap
- `_alignItems` / `_alignItemsGrid` — Vertical alignment
- `_alignContentGrid` — Content alignment inside grid
- `_justifyContent` — Horizontal alignment
- `_columnGap` / `_rowGap` — Gap values
- `_gridTemplateColumns` — CSS Grid template columns (`var(--grid-2)`, `repeat(12, 1fr)`)
- `_gridTemplateRows` — CSS Grid template rows (`repeat(4, 1fr)`)
- `_gridGap` — CSS Grid gap (`var(--grid-gap)`, `3rem`)
- `_gridItemColumnSpan` — Grid item column span (`1 / 9`, `6 / -1`, `span 2`)
- `_gridItemRowSpan` — Grid item row span (`1`, `span 2`)
- `_order` — CSS order property (e.g., `-1`)
- `_flexShrink` — Flex shrink value

### Content Properties
- `tag` — HTML tag (`"h1"`, `"h2"`, `"p"`, `"ul"`, `"li"`, `"figure"`, `"custom"`)
- `customTag` — Required when `tag` is `"custom"` (e.g., `"span"`)
- `text` — Text content
- `link` — Link object: `{ "type": "external", "url": "#" }`
- `image` — Image object: `{ "url": "...", "external": true, "filename": "..." }`
- `icon` — Icon object: Supports SVG upload (`{"library": "svg", "svg": {"id": 123}}`) or font icons (`{"library": "themify", "icon": "ti-heart"}`)

## Global Classes

Global classes are reusable style definitions stored in the `globalClasses` array of the export. Each has:

```json
{
  "id": "abc123",
  "name": "class-name",
  "settings": { ... },
  "category": "category-id",
  "modified": 1234567890,
  "user_id": 1
}
```

### Naming Convention (BEM-like)
- Block: `cta-1`, `btn-primary`
- Element: `cta-1__inner`, `cta-1__content`, `cta-1__heading-group`
- Modifier: _(not yet observed)_

### Reusable Component Classes
- `button-group` — Flex row wrapper for buttons
- `btn-primary` — Primary button styles
- `btn-secondary` — Secondary button with border

## Responsive Settings

Bricks uses **colon-suffixed keys** for responsive breakpoints:

| Breakpoint | Suffix | Example |
|---|---|---|
| Desktop (default) | _(none)_ | `_rowGap` |
| Tablet Portrait | `:tablet_portrait` | `_gridTemplateColumns:tablet_portrait` |
| Mobile Landscape | `:mobile_landscape` | `_rowGap:mobile_landscape` |
| Hover state | `:hover` | `_background:hover` |

## Design Token System

All elements use CSS custom properties for consistent theming:

- **Layout**: `--grid-2`, `--grid-1`, `--container-max-width`, `--container-width`, `--w-fit`
- **Spacing**: `--space-xxs`, `--space-xs`, `--space-xs-mobile`, `--space-s`, `--space-s-mobile`, `--space-m`, `--space-m-mobile`, `--space-l`, `--space-xl`, `--space-2xl`, `--space-none`, `--gutter`
- **Typography**: `--text-m`, `--text-l`, `--leading-relaxed`, `--leading-loose`
- **Colors**: `--text`, `--border-color`, `--bg-color`, `--color-light`, `--transparent-bg`, `--btn-primary-text`, `--btn-primary-bg`, `--btn-primary-hover-bg`, `--btn-secondary-text`, `--btn-secondary-bg`, `--btn-secondary-hover-bg`, `--btn-secondary-hover-border`, `--btn-secondary-hover-text`
- **Border**: `--border-width`, `--radius-s`, `--radius-none`
- **Transition**: `--btn-transition`
- **Button sizing**: `--btn-medium-padding-inline`, `--btn-medium-padding-block`

---

> **This document is a living reference.** It is updated as more element examples are added to the library.
