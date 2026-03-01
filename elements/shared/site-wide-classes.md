# Site-Wide Shared Classes

These class IDs appear on elements but are **NOT included** in the `globalClasses` array of exports. They are defined in the Bricks theme/site settings and applied across many components.

> **Important for generation**: When creating new elements, include these shared class IDs alongside the component-specific class. The exact styles they contain are unknown, but their presence is required for proper rendering.

## Confirmed Shared Classes

Classes that appear in **multiple** element exports:

| Class ID | Seen On | Applied To | Likely Purpose |
|---|---|---|---|
| `shvjdm` | CTA-1, Hero-1 | Section | Shared section base styles |

## Observed Shared Classes (Single Element)

Classes from Hero-1 that are likely shared (not in export, appear alongside component classes):

### Section Level
| Class ID | Likely Purpose |
|---|---|
| `hfc8yp` | Section styling |
| `ej8ua3` | Section styling |

### Inner Container Level
| Class ID | Likely Purpose |
|---|---|
| `kr1r6i` | Inner container styling |

### Content Level
| Class ID | Likely Purpose |
|---|---|
| `g56yok` | Content block styling |
| `jzdzdj` | Content block styling |

### Typography Level
| Class ID | Likely Purpose |
|---|---|
| `1yrow5` | Heading styling |
| `8y9zzg` | Description styling |

### Media Level
| Class ID | Likely Purpose |
|---|---|
| `uzl0vc` | Media wrapper styling |
| `3j5lp3` | Image styling |
| `52rigf` | Image styling |

### Button Level
| Class ID | Likely Purpose |
|---|---|
| `uhtqbo` | Button group styling |
| `bjt4kf` | Button base styling |

## Class Stacking Pattern

Elements typically stack classes in this order:
```
_cssGlobalClasses: [
  "shared-base-class-1",    // site-wide (not exported)
  "shared-base-class-2",    // site-wide (not exported)
  "component-specific-class" // component BEM class (exported)
]
```

The component-specific class is usually **last** in the array.

---

> **To resolve**: Ask the user to export their full site-wide global classes, or identify these IDs from the Bricks theme settings.
