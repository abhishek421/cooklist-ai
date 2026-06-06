# Frost — Style Reference
> animated mesh gradients, frosted glass, soft pastels

**Theme:** light-translucent

Frost's visual system evokes a dreamy, premium, living experience. It replaces flat backgrounds with an animated, organic mesh gradient in soft pastel tones (lavender, rose, peach, mint). UI elements become frosted glass panels with progressive blur, creating depth through varying levels of transparency rather than heavy shadows. The single violet accent color guides interaction with soft glows, while typography combines the technical precision of Inter with the modern, geometric softness of Outfit.

## Tokens — Colors

| Name | Value | Token | Role |
|------|-------|-------|------|
| Glass White | `rgba(255, 255, 255, 0.12)` | `--color-glass-white` | Base glass layer (Level 1) |
| Glass Strong | `rgba(255, 255, 255, 0.22)` | `--color-glass-strong` | Elevated glass layer (Level 2/3) |
| Glass Border | `rgba(255, 255, 255, 0.25)` | `--color-glass-border` | Frosted luminous borders |
| Accent | `#7c5bf5` | `--color-accent` | Primary violet accent for interactive elements |
| Accent Glow | `rgba(124, 91, 245, 0.3)` | `--color-accent-glow` | Hover glows and selection states |
| Text Primary | `#ffffff` | `--color-text-primary` | Main text on frosted surfaces |
| Text Secondary| `rgba(255, 255, 255, 0.7)` | `--color-text-secondary`| Muted text |
| Charcoal Text | `#1b1b1b` | `--color-charcoal-text` | Only for rare high-contrast needs |

**Background Mesh Gradient Stops:**
- Rose: `#f4a0b5` (`--color-rose`)
- Peach: `#f7c59f` (`--color-peach`)
- Lavender: `#b8a9e8` (`--color-lavender`)
- Mint: `#a8dcd1` (`--color-mint`)

## Tokens — Typography

### Control — Functional text across UI elements including buttons, body text, links, and navigation items. Acts as the primary workhorse font for readability. · `--font-control`
- **Substitute:** Inter
- **Weights:** 400, 500, 700

### Control Compressed — Modern geometric sans for headlines, pairing softness with clarity. · `--font-control-compressed`
- **Substitute:** Outfit
- **Weights:** 700, 900

### Control Cursive — Expressive, decorative headlines. · `--font-control-cursive`
- **Substitute:** Dancing Script

### Control TNT — Secondary expressive font for occasional data points. · `--font-control-tnt`
- **Substitute:** Space Mono

## Tokens — Spacing & Shapes

**Base unit:** 4px
**Density:** comfortable

### Border Radius
| Element | Value |
|---------|-------|
| cards | 20px |
| links | 8px |
| inputs | 12px |
| buttons | 9999px (pill) |

## Glass Levels (Surfaces)

The design strongly minimizes shadows, opting instead for progressive background blur (`backdrop-filter`) and varying white opacity to convey depth.

| Level | Background Opacity | Blur | Purpose |
|-------|--------------------|------|---------|
| 0 | `transparent` | None | The animated mesh background layer |
| 1 | `0.05` | `8px` | Subtle overlays, headers, inputs, secondary tags |
| 2 | `0.15` | `16px` | Interactive cards, feature panels |
| 3 | `0.25` | `24px` | Elevated modal forms, primary focal containers |

## Do's and Don'ts

### Do
- Prioritize white text (`#ffffff`) on frosted glass surfaces.
- Use soft, rounded radii (`20px` for cards, `12px` for inputs) to maintain the bubbly, organic feel.
- Implement subtle float and shimmer micro-animations for interactive elements.
- Use glowing borders instead of dark drop shadows to highlight active states.

### Don't
- Do not use solid color backgrounds for cards; always use semi-transparent `rgba` with `backdrop-filter`.
- Avoid heavy, dark drop shadows; use soft, diffused, low-opacity shadows if absolutely necessary.
- Do not use sharp corners (e.g., `0px` or `4px`) for primary UI surfaces.
- Avoid flat, static backgrounds — the environment should feel alive but unobtrusive.

## Agent Prompt Guide

When building new components, apply the correct "Glass Level" utility classes (`.glass-panel-1`, `.glass-panel-2`, `.glass-panel-3`) or replicate their properties.

Example Component Prompts:
1. Create an input field: `background: var(--glass-bg-1)`, `border: 1px solid var(--color-glass-border)`, `border-radius: 12px`, with white text. Focus state should add `box-shadow: 0 0 0 3px var(--color-accent-glow)`.
2. Create a feature card: Use `.feature-card` class which applies Glass Level 2 (`var(--glass-bg-2)`, `blur(16px)`). On hover, increase to `var(--glass-bg-3)` and apply `transform: translateY(-4px)`.
