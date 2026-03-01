# Shared Section Base Pattern

Every Bricks component follows the same root structure. This is the foundational pattern for all elements.

## Structure

```
Section ({component}):  top-level wrapper
└── Container ({component}__inner):  layout container
    ├── ... content blocks
    └── ... content blocks
```

## Section Class Pattern

```json
{
  "name": "{component-name}",
  "settings": []
}
```

Sections typically have **empty or minimal settings** — styling is handled by the inner container and child blocks. The section class serves as a namespace.

## Inner Container Class Pattern

The inner container handles **layout and width constraints**:

```json
{
  "name": "{component-name}__inner",
  "settings": {
    "_width": "var(--container-width)",
    "_widthMax": "var(--container-max-width)"
  }
}
```

### Layout Variations Seen

| Layout | Key Settings | Example |
|---|---|---|
| **CSS Grid (2-col)** | `_display: "grid"`, `_gridTemplateColumns: "var(--grid-2)"` | CTA-1 |
| **Flex row** | `_direction: "row"`, `_justifyContent: "space-between"` | Navbar-1 |

### Common Inner Settings

- `_width: "var(--container-width)"` — responsive width
- `_widthMax: "var(--container-max-width)"` — max width cap
- `_alignItems: "center"` — vertical centering
- Grid gap or flex gap via `_gridGap`, `_columnGap`

## Element JSON Template

```json
[
  {
    "id": "SECTION_ID",
    "name": "section",
    "parent": 0,
    "children": ["INNER_ID"],
    "settings": { "_cssGlobalClasses": ["{component-class-id}"] },
    "label": "{Component Name}"
  },
  {
    "id": "INNER_ID",
    "name": "container",
    "parent": "SECTION_ID",
    "children": ["CHILD_1_ID", "CHILD_2_ID"],
    "settings": {
      "_cssGlobalClasses": ["{component}__inner-class-id"]
    },
    "label": "Inner"
  }
]
```

## Observed In

- **CTA-1**: Section → Container (grid 2-col) → Content + Media
- **Navbar-1**: Section → Container (flex row, space-between) → Logo + Nav
