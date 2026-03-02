# Design Token Registry

All known CSS custom properties (design tokens) used in the Bricks Builder design system. This is the **single source of truth** for available tokens when generating new elements.

> **Rule**: Never use hardcoded values. Always reference these tokens.

## Layout

| Token | Purpose |
|---|---|
| `--container-width` | Responsive container width |
| `--container-max-width` | Maximum container width |
| `--grid-1` | Single column grid template |
| `--grid-2` | Two-column grid template |
| `--grid-gap` | Uniform gap for grid layouts |
| `--w-fit` | Fit-content width |

> **Expected** (not yet confirmed): `--grid-3`, `--grid-4`, `--grid-12`

## Spacing

| Token | Purpose | Mobile Variant |
|---|---|---|
| `--space-xxs` | Extra extra small | — |
| `--space-xs` | Extra small | `--space-xs-mobile` |
| `--space-s` | Small | `--space-s-mobile` |
| `--space-m` | Medium | `--space-m-mobile` |
| `--space-l` | Large | — |
| `--space-xl` | Extra large | — |
| `--space-2xl` | 2× Extra large | — |
| `--space-none` | Zero spacing | — |
| `--gutter` | Page gutter / horizontal padding | — |

## Typography

| Token | Purpose |
|---|---|
| `--text-m` | Medium text size (buttons, nav) |
| `--text-l` | Large text size (descriptions) |
| `--leading-relaxed` | Relaxed line-height (buttons) |
| `--leading-loose` | Loose line-height (nav items) |

> **Expected** (not yet confirmed): `--text-s`, `--text-xl`, `--text-2xl`, heading size tokens

## Colors

### Text
| Token | Purpose |
|---|---|
| `--text` | Default body text color |

### Background
| Token | Purpose |
|---|---|
| `--bg-color` | Default background color |
| `--color-light` | Light accent background (dropdown hover) |
| `--neutral-ultra-light` | Very light neutral background |
| `--transparent-bg` | Transparent background |

### Buttons
| Token | Purpose |
|---|---|
| `--btn-primary-text` | Primary button text color |
| `--btn-primary-bg` | Primary button background |
| `--btn-primary-hover-bg` | Primary button hover background |
| `--btn-secondary-text` | Secondary button text color |
| `--btn-secondary-bg` | Secondary button background |
| `--btn-secondary-hover-bg` | Secondary button hover background |
| `--btn-secondary-hover-border` | Secondary button hover border color |
| `--btn-secondary-hover-text` | Secondary button hover text color |

### Border
| Token | Purpose |
|---|---|
| `--border-color` | Default border color |
| `--border-width` | Default border width |

## Border Radius

| Token | Purpose |
|---|---|
| `--radius-s` | Small radius (buttons, cards, dropdowns) |
| `--radius-none` | No radius |

> **Expected** (not yet confirmed): `--radius-m`, `--radius-l`, `--radius-full`

## Button Sizing

| Token | Purpose |
|---|---|
| `--btn-medium-padding-inline` | Medium button horizontal padding |
| `--btn-medium-padding-block` | Medium button vertical padding |

> **Expected** (not yet confirmed): `--btn-small-*`, `--btn-large-*`

## Transitions

| Token | Purpose |
|---|---|
| `--btn-transition` | Button hover transition |

---

> **This registry is updated as new elements reveal additional tokens.**
> Tokens marked "Expected" are logical extensions of the observed system but have not been confirmed in element examples yet.
