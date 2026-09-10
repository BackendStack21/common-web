# shared-web-assets

Central asset hub for all 21no.de web properties. Served from **assets.21no.de**.

## Structure

```
├── css/
│   ├── tokens.css        # Design tokens (CSS variables)
│   ├── base.css          # Reset, typography, layout, effects, animations
│   ├── nav.css           # Sticky navigation
│   ├── hero.css          # Hero section + stats
│   ├── buttons.css       # .btn, .btn-primary, .btn-secondary
│   ├── cards.css         # .card, .project-card, .feature-grid
│   ├── footer.css        # Site footer
│   ├── blog-carousel.css # Blog carousel + skeleton
│   └── org-page.css      # Opt-in editorial organization page layout
├── fonts/
│   ├── fonts.css         # @font-face declarations
│   ├── SpaceGrotesk-Variable.ttf  # Space Grotesk (variable, 300–700)
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

Page-specific styles normally stay in the consuming project. The organization page's
editorial layout is available as an explicit opt-in shared stylesheet.

## Organization page layout

Load `org-page.css` **after** the shared tokens, base, and component styles:

```html
<link rel="stylesheet" href="https://assets.21no.de/css/org-page.css" />
<body class="lab-home">
  <!-- Organization page content -->
</body>
```

Both the stylesheet and the `lab-home` body class are required. Every rule is scoped
to that class (including the reduced-motion rule on its containing `html`). Existing
sites keep their identity unless they explicitly opt in; the default tokens and
components are unchanged.

The layout includes the editorial hero, static release strip, principles, featured
project, project cards, publication rows, responsive spacing, and focus states.
It uses the existing component classes plus `.principles`, `.featured-project`,
`.collection-title`, `.collection-link`, `.publication-list`, and `.publication-row`.
Markup, content, and release-feed behavior remain in the website repository.

Publish this asset before deploying a consumer that links to it. The organization
website should load this file directly rather than maintain a second CSS copy.

## Adding a New Site

1. Point your site's HTML to `https://assets.21no.de/css/*.css`
2. Add any page-specific CSS inline
3. Done — no font or design system duplication
