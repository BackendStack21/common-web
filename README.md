# shared-web-assets

Central asset hub for all 21no.de web properties. Served from **assets.21no.de**.

## Structure

```
├── css/
│   ├── tokens.css        # Design tokens (CSS variables)
│   ├── base.css          # Reset, typography, layout
│   ├── nav.css           # Sticky navigation
│   ├── hero.css          # Hero section + stats
│   ├── buttons.css       # .btn, .btn-primary, .btn-secondary
│   ├── cards.css         # .card, .project-card, .feature-grid
│   ├── footer.css        # Site footer
│   └── blog-carousel.css # Blog carousel + skeleton
├── fonts/
│   ├── fonts.css         # @font-face declarations
│   ├── Outfit-*.ttf      # Outfit (300–700)
│   └── JetBrainsMono-*.ttf  # JetBrains Mono (400–600)
└── README.md
```

## Usage

```html
<!-- Fonts -->
<link rel="stylesheet" href="https://assets.21no.de/fonts/fonts.css" />
<!-- Design system -->
<link rel="stylesheet" href="https://assets.21no.de/css/tokens.css" />
<link rel="stylesheet" href="https://assets.21no.de/css/base.css" />
<link rel="stylesheet" href="https://assets.21no.de/css/nav.css" />
<!-- Components as needed -->
<link rel="stylesheet" href="https://assets.21no.de/css/buttons.css" />
<link rel="stylesheet" href="https://assets.21no.de/css/cards.css" />
<link rel="stylesheet" href="https://assets.21no.de/css/hero.css" />
<link rel="stylesheet" href="https://assets.21no.de/css/footer.css" />
```

Page-specific styles stay inline in the project's own HTML.

## Adding a New Site

1. Point your site's HTML to `https://assets.21no.de/css/*.css`
2. Add any page-specific CSS inline
3. Done — no font or design system duplication
