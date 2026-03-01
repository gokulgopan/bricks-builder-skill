# Shared Typography Classes

Reusable typography-related classes for headings and body text.

## Heading Group

A wrapper block that groups a heading and description together with consistent spacing.

**Class pattern**: `{component}__heading-group`

```json
{
  "name": "{component}__heading-group",
  "settings": {
    "_rowGap": "var(--space-s)",
    "_rowGap:mobile_landscape": "var(--space-s-mobile)"
  }
}
```

**Structure**:
```
Block (Heading Group) — class: {component}__heading-group
├── Heading (h2) — class: {component}__heading
└── Text-Basic (Description) — class: {component}__description
```

---

## Heading

**Class pattern**: `{component}__heading`

Typically **empty settings** — inherits from theme defaults.

```json
{
  "name": "{component}__heading",
  "settings": []
}
```

**Element settings**: `"tag": "h2"` (or h1–h6)

---

## Description

**Class pattern**: `{component}__description`

```json
{
  "name": "{component}__description",
  "settings": {
    "_typography": {
      "font-size": "var(--text-l)",
      "color": { "raw": "var(--text)" }
    }
  }
}
```

---

## Content Block

Wraps heading group + button group (or other content) with vertical spacing.

**Class pattern**: `{component}__content`

```json
{
  "name": "{component}__content",
  "settings": {
    "_rowGap": "var(--space-m)",
    "_rowGap:mobile_landscape": "var(--space-m-mobile)"
  }
}
```

---

## Common Typography Tokens

| Token | Purpose |
|---|---|
| `--text-m` | Medium body text size |
| `--text-l` | Large body/description text size |
| `--text` | Default text color |
| `--leading-relaxed` | Relaxed line-height |
| `--leading-loose` | Loose line-height (nav items) |
| `--space-s` / `--space-s-mobile` | Gap between heading and description |
| `--space-m` / `--space-m-mobile` | Gap between content groups |

## Observed In

- **CTA-1**: heading-group, heading, description, content patterns
