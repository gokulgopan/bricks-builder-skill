# Responsive Design Rules

## Breakpoint Suffixes

Bricks uses colon-suffixed keys on settings properties:

| Breakpoint | Suffix | Typical Use |
|---|---|---|
| **Desktop** | _(none)_ | Base styles |
| **Tablet Portrait** | `:tablet_portrait` | Grid → single column, nav → mobile menu |
| **Mobile Landscape** | `:mobile_landscape` | Reduced spacing, smaller gaps |
| **Hover** | `:hover` | Interactive states (bg, border, text color) |

## Common Responsive Overrides

### Layout
| Desktop | Tablet Override |
|---|---|
| `_gridTemplateColumns: "var(--grid-2)"` | `_gridTemplateColumns:tablet_portrait: "var(--grid-1)"` |
| `_direction: "row"` | `_direction:tablet_portrait: "column"` |
| `_width: "auto"` | `_width:tablet_portrait: "100%"` |

### Spacing
| Desktop | Mobile Override |
|---|---|
| `_rowGap: "var(--space-m)"` | `_rowGap:mobile_landscape: "var(--space-m-mobile)"` |
| `_rowGap: "var(--space-s)"` | `_rowGap:mobile_landscape: "var(--space-s-mobile)"` |
| `_padding: { top: "var(--space-s-mobile)" }` | `_padding:mobile_landscape: { top: "var(--space-xs)" }` |

### Navigation-Specific
| Desktop | Tablet Override |
|---|---|
| Horizontal nav links | Mobile menu (absolute, full-width) |
| Flex row buttons | `_direction:tablet_portrait: "column"`, stretch |
| Dropdown with border/radius | `dropdownBorder:tablet_portrait: { style: "none" }` |

## Rules for New Elements

1. **Always set desktop styles first** — these are the base
2. **Grid layouts** → collapse to single column on `tablet_portrait`
3. **Spacing tokens** → use the `*-mobile` variant on `mobile_landscape`
4. **Flex row layouts** → consider switching to `column` on `tablet_portrait`
5. **Interactive states** → use `:hover` suffix for bg, border, and typography
6. **Never use pixel values** — always use design tokens
