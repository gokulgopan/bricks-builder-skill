# BEM Naming Convention for Bricks Classes

## Format

```
{component-name}__{sub-element}
```

## Rules

### 1. Component Name (Block)
- Lowercase, hyphenated
- Includes a number suffix for variants: `cta-1`, `navbar-1`, `hero-2`
- This is the **root class** applied to the `section` element

### 2. Sub-Element Names
- Double underscore `__` separator
- Describes the **purpose**, not the element type
- Examples: `inner`, `content`, `heading-group`, `media-wrapper`, `nav-items`

### 3. Complete Naming Map

| Element | Class Name Pattern | Example |
|---|---|---|
| Section | `{component}` | `cta-1` |
| Container | `{component}__inner` | `cta-1__inner` |
| Content wrapper | `{component}__content` | `cta-1__content` |
| Heading group | `{component}__heading-group` | `cta-1__heading-group` |
| Heading | `{component}__heading` | `cta-1__heading` |
| Description | `{component}__description` | `cta-1__description` |
| Media wrapper | `{component}__media-wrapper` | `cta-1__media-wrapper` |
| Image | `{component}__image` | `cta-1__image` |
| Button group | `button-group` | _(shared, not component-specific)_ |
| Primary button | `btn-primary` | _(shared)_ |
| Secondary button | `btn-secondary` | _(shared)_ |
| Nav items | `{component}__nav-items` | `navbar-1__nav-items` |
| Nav link | `{component}__nav-link` | `navbar-1__nav-link` |
| Toggle | `{component}__toggle` | `navbar-1__toggle` |
| Logo | `{component}__logo` | `navbar-1__logo` |

### 4. Shared vs Component-Specific Classes

| Type | Scope | Example |
|---|---|---|
| **Shared** | Reusable across all components | `button-group`, `btn-primary`, `btn-secondary` |
| **Component** | Specific to one component | `cta-1__inner`, `navbar-1__nav` |

### 5. When to Create New vs Reuse Existing

- **Reuse** shared classes for buttons, common typography
- **Create new** component-specific classes for layout, spacing, custom styling
- **Never inline styles** — always use global classes or design tokens
