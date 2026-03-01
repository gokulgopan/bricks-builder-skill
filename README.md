# 🧱 Bricks Builder Element Generator — AI Skill

An AI skill that learns from Bricks Builder element examples and generates new, production-ready element code that can be directly pasted into the Bricks Builder editor.

---

## 🎯 Purpose

Bricks Builder is a powerful WordPress page builder that represents elements as JSON structures. This skill acts as a **pattern library and generation engine** — by studying real element examples (images + copied JSON code), the AI learns:

- The JSON structure and element types
- Design token system (CSS custom properties)
- BEM-like class naming conventions
- Section composition patterns
- Responsive breakpoint rules

With enough examples, the AI can **generate entirely new elements** that match your design system.

---

## 📁 Project Structure

```
bricks_builder_skill/
│
├── SKILL.md                             # Core skill instructions & generation workflow
├── README.md                            # This file
│
├── elements/                            # Element library (examples + shared patterns)
│   ├── _index.md                        # Master index of all elements
│   │
│   ├── shared/                          # Reusable patterns across elements
│   │   ├── buttons.md                   # btn-primary, btn-secondary, button-group
│   │   ├── section-base.md              # Section → Container base structure
│   │   ├── typography.md                # Heading group, description, content block
│   │   └── site-wide-classes.md         # Shared class IDs (not exported, in theme)
│   │
│   ├── composite/                       # Multi-element sections
│   │   ├── cta-1.md + cta-1.png         # Call-to-Action section
│   │   └── hero-1.md + hero-1.png       # Hero section
│   │
│   ├── navigation/                      # Navigation elements
│   │   └── navbar-1.md + navbar-1.png   # Top navigation bar
│   │
│   ├── layout/                          # Layout elements (empty)
│   ├── content/                         # Content elements (empty)
│   ├── media/                           # Media elements (empty)
│   ├── interactive/                     # Interactive elements (empty)
│   └── forms/                           # Form elements (empty)
│
└── resources/                           # Reference documentation
    ├── bricks_structure.md              # Bricks JSON format & element types
    ├── tokens.md                        # Design token registry (CSS variables)
    └── patterns/                        # Composition rules for generation
        ├── section-pattern.md           # How sections are composed
        ├── naming-convention.md         # BEM class naming rules
        └── responsive-rules.md          # Breakpoint & responsive rules
```

---

## 📚 Element Library

### Current Elements (3)

| Element | Category | Description |
|---------|----------|-------------|
| **Navbar 1** | Navigation | Responsive navbar with logo, nav links, dropdown, CTA buttons, mobile hamburger |
| **CTA 1** | Composite | Two-column CTA: heading (h2) + description + buttons + image (16:9) |
| **Hero 1** | Composite | Two-column hero: heading (h1) + description + buttons + image (1:1) |

### Shared Patterns Extracted

| Pattern | File | Description |
|---------|------|-------------|
| Buttons | `shared/buttons.md` | `button-group`, `btn-primary`, `btn-secondary` with full JSON |
| Section Base | `shared/section-base.md` | Universal Section → Container structure |
| Typography | `shared/typography.md` | Heading group, description, content block patterns |
| Site-Wide Classes | `shared/site-wide-classes.md` | Tracking shared class IDs across elements |

---

## 🧩 How It Works

### Adding Elements

1. **Copy** an element from Bricks Builder (Ctrl+C on any element)
2. **Share** the copied JSON + a screenshot with the AI
3. The AI documents the element with:
   - Visual reference image
   - Element tree diagram
   - Global classes table
   - Design tokens used
   - Full JSON code
   - Key patterns identified

### Generating Elements

When you ask the AI to generate a new element, it:

1. **References** the pattern library (`resources/patterns/`)
2. **Checks** the design token registry (`resources/tokens.md`)
3. **Finds** similar elements in the library (`elements/`)
4. **Reuses** shared classes (`elements/shared/`)
5. **Composes** valid Bricks JSON following all conventions
6. **Outputs** copyable code ready to paste into Bricks Builder

---

## 🔑 Key Patterns Learned

### JSON Structure
Elements are a **flat array** with parent-child linking via IDs:
```json
{
  "content": [...elements...],
  "source": "bricksCopiedElements",
  "version": "2.2-rc2",
  "globalClasses": [...styles...],
  "globalElements": []
}
```

### Composition Rule
Every component follows:
```
Section (component-name)
└── Container (component__inner) — handles layout
    ├── Content blocks — grouped by purpose
    └── Media / Interactive blocks
```

### BEM Class Naming
```
{component-name}__{sub-element}

Examples:
  hero-1              → Section
  hero-1__inner       → Container
  hero-1__content     → Content wrapper
  hero-1__heading     → Heading element
```

### Design Token System
All values use CSS custom properties — **no hardcoded values**:
- Spacing: `--space-xs` through `--space-2xl`
- Typography: `--text-m`, `--text-l`
- Colors: `--text`, `--bg-color`, `--btn-primary-bg`
- Layout: `--grid-2`, `--container-max-width`
- Border: `--radius-s`, `--border-width`

### Responsive Breakpoints
Colon-suffixed keys on settings properties:
- `:tablet_portrait` — grid collapse, nav → mobile
- `:mobile_landscape` — spacing adjustments
- `:hover` — interactive states

---

## 🏗️ Element Types Known

| Category | Types |
|----------|-------|
| **Structure** | `section`, `container`, `block`, `div` |
| **Content** | `heading`, `text`, `text-basic`, `image`, `button`, `icon`, `video` |
| **Navigation** | `logo`, `nav-nested`, `text-link`, `dropdown`, `toggle` |

---

## 📈 Growing the Library

The more elements you add, the better the AI becomes at generating new ones. Priority elements to add:

- [ ] Footer section
- [ ] Feature grid / card layout
- [ ] Testimonials / reviews
- [ ] Stats / numbers section
- [ ] Pricing cards
- [ ] FAQ / Accordion
- [ ] Contact form
- [ ] Gallery / portfolio grid

---

## 📝 Changelog

### v1.0.0 (2026-03-02)
- Initial skill setup with 3 elements (Navbar-1, CTA-1, Hero-1)
- Optimized structure with shared patterns, composition rules, and token registry
- Documented 17 element types, 30+ design tokens, and responsive rules
