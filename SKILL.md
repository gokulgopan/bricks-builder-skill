---
name: Bricks Builder Element Generator
description: Generate Bricks Builder element code from visual designs or descriptions, using a library of learned element patterns.
---

# Bricks Builder Element Generator

This skill enables generating **Bricks Builder** (WordPress page builder) element code that can be directly copied and pasted into Bricks Builder's JSON import system.

## How It Works

1. **Element Library**: The `elements/` directory contains categorized examples of Bricks Builder elements with reference images and JSON code.
2. **Shared Patterns**: The `elements/shared/` directory contains reusable classes (buttons, typography, section base) used across elements.
3. **Composition Rules**: The `resources/patterns/` directory teaches how to compose new elements correctly.
4. **Design Tokens**: The `resources/tokens.md` file lists all available CSS custom properties.

## Directory Structure

```
bricks_builder_skill/
├── SKILL.md                           # This file — skill instructions
├── elements/                          # Element examples by category
│   ├── _index.md                      # Master index of all elements
│   ├── shared/                        # Reusable classes & patterns
│   │   ├── buttons.md                 # btn-primary, btn-secondary, button-group
│   │   ├── section-base.md            # Section → Container base pattern
│   │   └── typography.md              # Heading group, description patterns
│   ├── layout/                        # Layout elements
│   ├── content/                       # Content elements
│   ├── media/                         # Media elements
│   ├── interactive/                   # Interactive elements
│   ├── forms/                         # Form elements
│   ├── navigation/                    # Navigation elements (navbar, footer)
│   └── composite/                     # Multi-element sections (hero, CTA, cards)
└── resources/
    ├── bricks_structure.md            # Bricks JSON format reference
    ├── tokens.md                      # Design token registry (all CSS variables)
    └── patterns/
        ├── section-pattern.md         # Section composition rules
        ├── naming-convention.md       # BEM class naming rules
        └── responsive-rules.md        # Breakpoint & responsive rules
```

## Generation Workflow

When asked to generate a new Bricks element:

### Step 1: Understand
- What does the user want visually and functionally?
- What existing elements are most similar?

### Step 2: Reference
- Read `resources/patterns/section-pattern.md` for composition rules
- Read `resources/patterns/naming-convention.md` for class naming
- Read `resources/patterns/responsive-rules.md` for responsive handling
- Read `resources/tokens.md` for available design tokens
- Read `elements/shared/` for reusable button/typography classes
- Find similar elements in category folders for layout reference

### Step 3: Compose
1. Start with Section → Container (Inner) structure
2. Add content blocks following the section-pattern rules
3. Apply BEM-named global classes with token-based values
4. Wire parent-child relationships with unique 6-char IDs
5. Add responsive breakpoint overrides
6. Include hover states for interactive elements
7. Wrap in the standard export format with `globalClasses` array

### Step 4: Output
- Present complete JSON in a code block
- User copies and pastes directly into Bricks Builder

## Adding New Elements

When the user shares a new element (image + code):

1. Identify the category
2. Create `elements/{category}/{element-name}.md` with: description, tree diagram, global classes table, full JSON code, key patterns
3. Save reference image alongside the markdown file
4. Update `elements/_index.md` with the new entry
5. Check for new design tokens → update `resources/tokens.md`
6. Check for new shared patterns → update `elements/shared/` files
7. Check for new element types → update `resources/bricks_structure.md`
