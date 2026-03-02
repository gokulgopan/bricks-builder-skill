# Single Blog Hero — Post Title & Meta Section

## Description

A comprehensive hero section for a single blog post. It features two primary containers: 
1. The upper container split into two columns: text content (category, h1 title, and a flex list of meta stats like likes/comments) and a visual column using a background image.
2. The lower overlapping container which holds the author profile card (avatar, name, date, and estimated reading time).

## Visual Reference

![Single Blog Hero Section](./single-blog-hero.png)

## Element Tree

```
Section (single-blog-banner)
├── Container (cz_single-blog--banner__content) — 2-Column Row
│   ├── Block (cz_single-blog--banner__column) — Left column
│   │   ├── Block (tag: span) — Category pill ("Travel")
│   │   ├── Heading (h1) — Post Title
│   │   └── Block (cz_blog--hero-slide-block--list) — Meta Stats flex row
│   │       ├── Div (Likes) — Themify icon + Text
│   │       ├── Div (Comments) — Themify icon + Text
│   │       ├── Div (Bookmark) — Themify icon only
│   │       └── Div (Share) — Themify icon + Text
│   └── Block (cz_single-blog--banner__col-image) — Right column
│       └── [No children] — Image is applied via `_background` property
└── Container (cz_blog--auth-container) — Overlapping bottom container
    └── Block (cz-admin-meta--block) — Author Card
        ├── Image — User Avatar
        └── Block — Author Info 
            ├── Heading — Author Name
            └── Div — Meta Row
                ├── Text-Basic — Date ("May 20, 2021")
                └── Post-Reading-Time — Dynamic Element (e.g., "1 min Read")
```

## Key Discoveries & New Patterns

### 1. Dynamic Element: `post-reading-time`
This is our first encounter with a Bricks dynamic data element!
- It is a specialized element type: `"name": "post-reading-time"`.
- It accepts a `suffix` property (e.g., `"suffix": " min Read"`).
- Proves Bricks has dedicated elements for WordPress post attributes.

### 2. Custom Tags via `customTag`
To enforce a `<span>` on a structural block, the settings use a dual-property approach:
```json
"tag": "custom",
"customTag": "span"
```

### 3. Background Images on Blocks
Instead of an `image` element, the right column uses a generic block with a background image applied in the settings.
```json
"_background": {
  "image": {
    "id": 4474,
    "url": "https://gallopbiz.in/ak-dev/wp-content/uploads/2025/10/2bcb92171e2b714e377280fde5f761c17c00dfc1.webp"
  }
}
```

### 4. Icon Fonts (Themify)
Unlike the previous element which used SVG uploads, this uses built-in font icons:
```json
"icon": {
  "library": "themify",
  "icon": "ti-heart"
}
```

### 5. Multi-Container Section Overlaps
The section has **two** direct `container` children. The second container (`erzmvf`) has a negative top margin (`_margin: {"bottom": "-70"}`) on desktop to physically overlap the content above it, creating a layered depth effect.

## Component Global Classes

| Class Name | Key Styles/Properties |
|---|---|
| `single-blog-banner` | `5%` padding sides/top, bg color `#e3e8ec`, `100px` bottom margin |
| `cz_single-blog--banner__content` | `align-items: stretch` (keeps columns equal height) |
| `cz_single-blog--banner__column` | `min-height: 320px`, `row-gap: 20px`, right padding |
| `cz_blog--hero-slide-ct--block` | Category pill: solid white border, `20px` radius, inline-flex |
| `cz_pinkspan-text` | `#991b1b` red text, `font-weight: 600`, `capitalize` |
| `cz_blog--hero-slide-block--list` | Flex row, `20px` gap |
| `cz_blog--hero-slide-block-rating--div` | Flex inline, `10px` gap, `align-items: center` |
| `cz_blog--hero-slide-block-rating--icon` | `30x30px` circle, white bg, flex center |
| `cz_single-blog--banner__col-image` | `-140px` bottom margin (overlap effect), `20px` border radius, `min-height` clamped |
| `cz_blog--auth-container` | Container acting as overlap anchor (`-70px` bottom margin) |
| `cz-admin-meta--block` | Author card: flex row, `8px` gap, `center` vertically |
| `cz-admin-meta--block_img` | Avatar: `40x40px`, `100px` (full) border radius, `object-fit: cover` |

## Design Tokens Discovered
This element relies entirely on hardcoded values (`#e3e8ec`, `20px`, `-140px`) rather than design tokens. This is a common pattern for specific, one-off component designs that don't fit a generic token system.

## JSON Code
*(Refer to original JSON structure in user input for full object hierarchy)*
