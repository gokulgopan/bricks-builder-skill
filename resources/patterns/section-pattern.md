# Section Composition Pattern

## Rule: Every Component Starts with Section → Container

All Bricks components follow a consistent root structure:

```
Section (component-name)
└── Container (component__inner)
    ├── Content Block(s)
    └── Media / Interactive Block(s)
```

## Composition Rules

### 1. Section (Root)
- Element type: `section`
- Parent: `0` (always root)
- Label: The component name (e.g., "CTA 1", "Navbar 1")
- Class: `{component-name}` (often empty settings — acts as namespace)
- Has exactly **one child**: the inner container

### 2. Inner Container
- Element type: `container`
- Label: always `"Inner"`
- Class: `{component-name}__inner`
- Handles **layout** (grid or flex) and **width constraints**
- Always has: `_width: "var(--container-width)"` and `_widthMax: "var(--container-max-width)"`

### 3. Content Blocks
- Element type: `block`
- Used as **grouping wrappers** (like divs)
- Named by purpose: "Content", "Media Wrapper", "Heading Group", "Button Group"
- Class: `{component-name}__{purpose}` (e.g., `cta-1__content`)

### 4. Atomic Elements (Leaves)
- `heading`, `text-basic`, `button`, `image` — the actual content
- Always inside at least one wrapper block
- Class: `{component-name}__{element-type}` (e.g., `cta-1__heading`)

## Layout Patterns

### Two-Column (Content + Media)
```
Container (grid 2-col)
├── Block (Content)
│   ├── Block (Heading Group) → heading + description
│   └── Block (Button Group) → buttons
└── Block (Media) → image/video
```
Grid: `_gridTemplateColumns: "var(--grid-2)"`, responsive: `var(--grid-1)` on tablet

### Horizontal Bar (Logo + Nav)
```
Container (flex row, space-between)
├── Logo
└── Nav (text links + buttons + toggle)
```
Flex: `_direction: "row"`, `_justifyContent: "space-between"`, `_flexWrap: "nowrap"`

## ID Generation Rules

When generating new elements:
1. All IDs must be **6 characters**, alphanumeric, lowercase
2. Each element gets a **unique** ID
3. Parent-child relationships must be **wired in both directions** (`parent` field + `children` array)
4. Root section's parent is always `0` (number, not string)
5. All other parents are **strings** (the parent element's ID)
