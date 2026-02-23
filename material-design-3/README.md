# Material Design 3 Claude Skill

A Claude Code skill for building UI following Google's Material Design 3 specification.

## Installation

Copy the `material-design-3` directory to your Claude Code skills folder:

```bash
cp -r material-design-3 ~/.claude/skills/
```

## Structure

```
material-design-3/
  SKILL.md                           # Core guide: rules, checklist, anti-patterns
  references/
    color-system.md                  # 26 color roles, light/dark theme values
    typography.md                    # Type scale (30 styles), usage table
    layout-and-motion.md             # Shape, elevation, motion, responsive layout
    components.md                    # Quick-reference specs for all M3 components
    examples.md                      # Complete code: button, chip, checkbox, text field
    tokens.css                       # CSS custom properties and utility classes
```

SKILL.md contains the essential rules and checklist that Claude always needs. The `references/` directory contains detailed specs that Claude loads on-demand when implementing specific aspects of M3.

## Usage

### In Claude Code

Reference the skill when building UI:

```
/material-design-3 Build a settings page with cards and toggles
```

Or invoke it contextually when Claude detects M3-related work.

### CSS Tokens

Import the token file in your project:

```html
<link rel="stylesheet" href="path/to/references/tokens.css">
```

### Using Tokens

```css
.my-button {
  background-color: var(--md-sys-color-primary);
  color: var(--md-sys-color-on-primary);
  border-radius: var(--md-sys-shape-corner-full);
  font-size: var(--md-sys-typescale-label-large-size);
}
```

### Key Concepts

**Color Pairing** - Always pair container colors with their `on-` counterpart:

| Container | Content |
|-----------|---------|
| `primary` | `on-primary` |
| `secondary-container` | `on-secondary-container` |
| `surface` | `on-surface` |
| `error` | `on-error` |

**Touch Targets** - All interactive elements must have 48dp minimum touch target.

**State Layers** - Use `color-mix()` with M3 tokens for hover/focus/pressed states.

**Disabled States** - Use `color-mix()` for proper opacity (12% container, 38% content).

**Dark Theme** - `tokens.css` supports three selectors: `.dark` class, `[data-theme="dark"]` attribute, and `@media (prefers-color-scheme: dark)` for automatic OS preference.

## Upgrading from Earlier Versions

If you previously imported `m3-tokens.css` directly, update your path:
- Before: `href="path/to/m3-tokens.css"`
- After: `href="path/to/references/tokens.css"`

## Resources

- [Material Design 3 Documentation](https://m3.material.io/)
- [Material Theme Builder](https://www.figma.com/community/plugin/1034969338659738588/material-theme-builder)
- [M3 Figma Design Kit](https://www.figma.com/community/file/1035203688168086460)
