# Material Design 3 Claude Skill

A comprehensive Claude Code skill for building UI following Google's Material Design 3 specification.

## Installation

Copy the `material-design-3` directory to your Claude Code skills folder:

```bash
cp -r material-design-3 ~/.claude/skills/
```

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Complete M3 specification and implementation guidance |
| `m3-tokens.css` | CSS custom properties and utility classes |
| `components-reference.md` | Quick reference for component specs |

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
<link rel="stylesheet" href="path/to/m3-tokens.css">
```

Or in CSS:

```css
@import 'path/to/m3-tokens.css';
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

### Utility Classes

**Typography:**
```html
<h1 class="md-typescale-headline-large">Title</h1>
<p class="md-typescale-body-medium">Content</p>
```

**Elevation:**
```html
<div class="md-elevation-1">Elevated card</div>
```

**Shape:**
```html
<button class="md-shape-full">Pill button</button>
```

**State Layers:**
```html
<button class="md-state-layer md-state-layer--on-primary">
  Interactive
</button>
```

**Touch Targets:**
```html
<div class="md-touch-target-wrapper">
  <input type="checkbox">
</div>
```

**Responsive:**
```html
<nav class="md-nav-bottom">Mobile nav</nav>
<nav class="md-nav-rail">Desktop nav</nav>
```

## Key Concepts

### Color Pairing

Always pair container colors with their `on-` counterpart:

| Container | Content |
|-----------|---------|
| `primary` | `on-primary` |
| `secondary-container` | `on-secondary-container` |
| `surface` | `on-surface` |
| `error` | `on-error` |

### Touch Targets

All interactive elements must have 48dp minimum touch target, even if visually smaller:

```css
.small-checkbox {
  width: 18px;
  height: 18px;
}

/* Expand touch target */
.small-checkbox::before {
  content: '';
  position: absolute;
  width: 48px;
  height: 48px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### State Layers

Use pseudo-elements with M3 tokens for hover/focus/pressed states:

```css
.button::before {
  content: '';
  position: absolute;
  inset: 0;
  background-color: var(--md-sys-color-on-primary);
  opacity: 0;
}

.button:hover::before { opacity: 0.08; }
.button:focus-visible::before { opacity: 0.12; }
.button:active::before { opacity: 0.12; }
```

### Disabled States

Use `color-mix()` for proper opacity:

```css
.button:disabled {
  background-color: color-mix(in srgb, var(--md-sys-color-on-surface) 12%, transparent);
  color: color-mix(in srgb, var(--md-sys-color-on-surface) 38%, transparent);
}
```

## Validation Checklist

Before shipping M3 UI:

- [ ] Touch targets ≥ 48dp
- [ ] State layers use color tokens (no hardcoded RGBA)
- [ ] Focus indicators visible
- [ ] Pressed state provides feedback
- [ ] Disabled state: 12% container, 38% content opacity
- [ ] Color pairings correct
- [ ] Dark theme supported
- [ ] ARIA labels on icon-only buttons

## Resources

- [Material Design 3 Documentation](https://m3.material.io/)
- [Material Theme Builder](https://www.figma.com/community/plugin/1034969338659738588/material-theme-builder)
- [M3 Figma Design Kit](https://www.figma.com/community/file/1035203688168086460)
