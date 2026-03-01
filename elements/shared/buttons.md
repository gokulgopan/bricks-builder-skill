# Shared Button Classes

Reusable button classes used across multiple elements. Reference these instead of re-defining button styles per component.

## `button-group`

Flex row wrapper for groups of buttons.

```json
{
  "id": "fogixp",
  "name": "button-group",
  "settings": {
    "_flexWrap": "wrap",
    "_direction": "row",
    "_columnGap": "var(--space-xs)",
    "_rowGap": "var(--space-xs)",
    "_alignItems": "center",
    "_display": "flex",
    "_width": "var(--w-fit)"
  }
}
```

**Usage**: Wrap `btn-primary` and/or `btn-secondary` buttons inside a `block` element with this class.

---

## `btn-primary`

Filled primary action button.

```json
{
  "id": "ekzwnh",
  "name": "btn-primary",
  "settings": {
    "_typography": {
      "font-size": "var(--text-m)",
      "color": { "raw": "var(--btn-primary-text)" },
      "font-weight": "500",
      "line-height": "var(--leading-relaxed)"
    },
    "_padding": {
      "left": "var(--btn-medium-padding-inline)",
      "right": "var(--btn-medium-padding-inline)",
      "bottom": "var(--btn-medium-padding-block)",
      "top": "var(--btn-medium-padding-block)"
    },
    "_border": {
      "radius": {
        "top": "var(--radius-s)",
        "right": "var(--radius-s)",
        "bottom": "var(--radius-s)",
        "left": "var(--radius-s)"
      }
    },
    "_background": { "color": { "raw": "var(--btn-primary-bg)" } },
    "_background:hover": { "color": { "raw": "var(--btn-primary-hover-bg)" } },
    "_cssTransition": "var(--btn-transition)"
  }
}
```

**Alternative**: Buttons can also use the built-in `"style": "primary"` property (seen in Navbar-1) instead of this global class.

---

## `btn-secondary`

Outlined/bordered secondary action button.

```json
{
  "id": "vrmhay",
  "name": "btn-secondary",
  "settings": {
    "_typography": {
      "font-size": "var(--text-m)",
      "color": { "raw": "var(--btn-secondary-text)" },
      "font-weight": "500",
      "line-height": "var(--leading-relaxed)"
    },
    "_padding": {
      "left": "var(--btn-medium-padding-inline)",
      "right": "var(--btn-medium-padding-inline)",
      "top": "var(--btn-medium-padding-block)",
      "bottom": "var(--btn-medium-padding-block)"
    },
    "_border": {
      "radius": {
        "top": "var(--radius-s)",
        "right": "var(--radius-s)",
        "bottom": "var(--radius-s)",
        "left": "var(--radius-s)"
      },
      "style": "solid",
      "color": { "raw": "var(--border-color)" },
      "width": {
        "top": "var(--border-width)",
        "right": "var(--border-width)",
        "bottom": "var(--border-width)",
        "left": "var(--border-width)"
      }
    },
    "_cssTransition": "var(--btn-transition)",
    "_background": { "color": { "raw": "var(--btn-secondary-bg)" } },
    "_background:hover": { "color": { "raw": "var(--btn-secondary-hover-bg)" } },
    "_border:hover": { "color": { "raw": "var(--btn-secondary-hover-border)" } },
    "_typography:hover": { "color": { "raw": "var(--btn-secondary-hover-text)" } },
    "_flexShrink": "0"
  }
}
```

**Alternative**: Buttons can also use the built-in `"style": "secondary"` property.

---

## Usage Pattern

```
Block (Button Group) — class: button-group
├── Button — class: btn-primary, text: "Get started", link: "#"
└── Button — class: btn-secondary, text: "Learn more", link: "#"
```

**Seen in**: CTA-1, Navbar-1 (uses `style` property instead)
