# Contributing to CookList AI

Thanks for your interest in contributing! This document outlines the process and guidelines for contributing to CookList AI.

## Getting Started

1. **Fork** the repository on GitHub
2. **Clone** your fork locally:
   ```bash
   git clone git@github.com:YOUR_USERNAME/cooklist-ai.git
   cd cooklist-ai
   ```
3. **Create a branch** for your feature or fix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Open `index.html`** in your browser — no build step needed

## Development Setup

This is a zero-dependency static site. You just need:

- A modern browser (Chrome/Firefox/Safari/Edge)
- A text editor
- Optionally, a local HTTP server:
  ```bash
  # Python
  python3 -m http.server 8080
  
  # Node.js
  npx serve .
  
  # VS Code Live Server extension
  ```

## Code Style

### HTML
- Use semantic HTML5 elements
- Include accessibility attributes (`aria-*`, `role`, labels)
- Give interactive elements unique `id` attributes
- Indent with 2 spaces

### CSS
- Use CSS custom properties (design tokens) from `:root` — don't hardcode values
- Follow existing BEM-like naming: `.block-element`, `.btn-modifier`
- Read [`design.md`](design.md) before making visual changes
- Keep specificity low — avoid `!important` and deep nesting

### JavaScript
- Vanilla ES6+ — no frameworks or external dependencies
- Cache DOM elements at the top of the file
- Use event delegation for dynamic elements
- Prefer `const` and `let` over `var`
- Keep functions focused and well-commented

## Making Changes

### Adding Recipes

Add entries to `RECIPES_DB` in `app.js`. Each recipe needs:

```javascript
{
  name: "Recipe Name",
  diets: ["vegetarian"],          // supported diets
  time: 30,                       // prep time in minutes
  costPerPerson: 60,              // cost in ₹
  ingredients: ["Item 1", "Item 2"],
  substitutions: { "Item 1": "Alt" }
}
```

### Modifying the Design

1. Read `design.md` thoroughly
2. Use existing design tokens wherever possible
3. If adding new tokens, document them in `design.md`
4. Test at mobile and desktop breakpoints

### Bug Fixes

1. Describe the bug clearly in your PR
2. Include steps to reproduce
3. Test the fix across browsers if possible

## Pull Request Process

1. **Update documentation** if your changes affect the README, AGENTS.md, or design.md
2. **Test manually** — walk through the full app flow (Landing → Form → Results)
3. **Keep PRs focused** — one feature or fix per PR
4. **Write a clear PR description** explaining what and why

### PR Title Convention

```
feat: add new breakfast recipe options
fix: budget calculation with empty pantry
style: improve mobile responsive layout
docs: update README with deployment steps
```

## Reporting Issues

When opening an issue, please include:

- **Browser and version** you're using
- **Steps to reproduce** the problem
- **Expected vs actual behavior**
- **Screenshots** if it's a visual issue

## Design Guidelines

The app follows the **Air** design system. Key principles:

- ✅ Use `backdrop-filter: blur()` for glassmorphism cards
- ✅ Use Action Blue (`--color-action-blue`) only for interactive elements
- ✅ Maintain comfortable spacing with 4px base unit
- ❌ Don't use filled colored backgrounds for content blocks
- ❌ Don't add drop shadows — use surface color differentiation
- ❌ Don't introduce new fonts without updating design.md

---

Thank you for helping make CookList AI better! 🍳
