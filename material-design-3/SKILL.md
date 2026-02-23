---
name: material-design-3
description: Design UI using Material Design 3 (M3) specifications. Use when building Android, web, or cross-platform interfaces following Google's latest design system. Includes dynamic color, typography scale, component specs, elevation, shape, motion, and accessibility guidelines.
allowed-tools:
  - Read
---

# Material Design 3 UI Design Skill

Build beautiful, accessible, and expressive user interfaces following Google's Material Design 3 specification.

## When to Use

- Building UI that follows Material Design 3
- Creating Android, web, or cross-platform interfaces with M3 theming
- Implementing M3 components (buttons, cards, chips, text fields, navigation)
- Setting up dynamic color, dark theme, or M3 token systems
- Reviewing UI code for M3 compliance

## Core Design Philosophy

**Personalization:** Dynamic color adapts UI to user wallpaper or content
**Accessibility:** Built-in contrast ratios and touch targets meet WCAG standards
**Expressiveness:** Shape morphing, motion physics, and emphasized typography
**Consistency:** Design tokens ensure systematic application across platforms

### Token Architecture

M3 uses three classes of design tokens:

1. **Reference Tokens** (`md.ref.*`): Raw values (hex colors, font sizes)
2. **System Tokens** (`md.sys.*`): Semantic decisions (color roles, type styles)
3. **Component Tokens** (`md.comp.*`): Component-specific assignments

```
md.ref.palette.primary40 -> md.sys.color.primary -> md.comp.filled-button.container.color
```

## Reference Files

Load the relevant reference file when you need detailed specs for implementation:

| When you need to... | Read | Contents |
|---------------------|------|----------|
| Pick colors or set up themes | `references/color-system.md` | 29+ color roles, fixed accents, light/dark values, contrast levels |
| Style text or configure fonts | `references/typography.md` | 15 baseline + 15 emphasized type styles, usage table, Tailwind config |
| Handle layout, shape, or animation | `references/layout-and-motion.md` | Window size classes, corner radii, elevation levels, easing curves |
| Look up component dimensions/tokens | `references/components.md` | Quick-reference table for all M3 components |
| See working code for a component | `references/examples.md` | Complete implementations: button, chip, checkbox, text field |
| Import CSS custom properties | `references/tokens.css` | All CSS custom properties and utility classes |

## Color Pairing Rules

**ALWAYS pair colors correctly for accessibility:**

| Container | Content |
|-----------|---------|
| `primary` | `on-primary` |
| `primary-container` | `on-primary-container` |
| `secondary` | `on-secondary` |
| `secondary-container` | `on-secondary-container` |
| `tertiary` | `on-tertiary` |
| `tertiary-container` | `on-tertiary-container` |
| `surface` | `on-surface` or `on-surface-variant` |
| `surface-container-*` | `on-surface` or `on-surface-variant` |
| `error` | `on-error` |
| `error-container` | `on-error-container` |

**NEVER:**
- Use `primary` text on `secondary-container`
- Use `on-primary` on `surface`
- Mix unpaired color roles

## Interaction States

### State Layer Opacity
```css
hover:   0.08
focus:   0.12
pressed: 0.12
dragged: 0.16
```

### State Layer Color Selection

The state layer color depends on the component's content color:

| Component | State Layer Color |
|-----------|-------------------|
| Filled button | `on-primary` |
| Tonal button | `on-secondary-container` |
| Outlined/Text button | `primary` |
| Icon button (standard) | `on-surface-variant` |
| Surface elements | `on-surface` |
| Navigation (active) | `on-secondary-container` |
| Navigation (inactive) | `on-surface-variant` |

### State Layer Implementation

**Recommended: color-mix() approach**
```css
.button:hover {
  background-color: color-mix(
    in srgb,
    var(--md-sys-color-on-primary) 8%,
    var(--md-sys-color-primary)
  );
}
```

**Fallback: pseudo-element overlay**
```css
.interactive::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  background-color: var(--md-sys-color-on-surface);
  opacity: 0;
  pointer-events: none;
}
.interactive:hover::before { opacity: 0.08; }
.interactive:focus-visible::before { opacity: 0.12; }
.interactive:active::before { opacity: 0.12; }
```

### Disabled States

Use `color-mix()` -- never `rgba()` with CSS custom properties:
```css
.button:disabled {
  background-color: color-mix(in srgb, var(--md-sys-color-on-surface) 12%, transparent);
  color: color-mix(in srgb, var(--md-sys-color-on-surface) 38%, transparent);
  pointer-events: none;
  box-shadow: none;
}
```

## Accessibility Requirements

### Touch Targets
- **Minimum:** 48x48dp for ALL interactive elements
- Even if visual size is smaller (chips: 32dp, checkboxes: 18dp), touch target MUST be 48dp

### Color Contrast
| Content | Minimum Ratio |
|---------|---------------|
| Normal text | 4.5:1 |
| Large text (18sp+ or 14sp bold) | 3:1 |
| UI components | 3:1 |
| Focus indicators | 3:1 |

### Focus Indicators
```css
.interactive:focus-visible {
  outline: 2px solid var(--md-sys-color-primary);
  outline-offset: 2px;
}
```

### Required ARIA Patterns
```html
<!-- Icon-only button -->
<button aria-label="Search"><svg>...</svg></button>

<!-- Toggle button -->
<button aria-pressed="false">Dark mode</button>

<!-- Progress indicator -->
<div role="progressbar" aria-valuenow="37" aria-valuemin="0" aria-valuemax="100"
     aria-label="Task completion"></div>
```

## Anti-Patterns (NEVER DO)

### Color
- Raw hex values instead of color role tokens
- `rgba()` with CSS custom properties (use `color-mix()`)
- Pairing unrelated roles (e.g., `primary` on `tertiary-container`)
- No dark theme support
- Hardcoded state layer colors

### Components
- Touch targets < 48dp
- Missing focus states or focus ring indicators
- Missing pressed/active state feedback
- Disabled states without proper opacity (38% content, 12% container)
- Incorrect elevation for component type
- Using `outline` for dividers (use `outline-variant`)

### Layout
- Same navigation across all window sizes
- Ignoring window size class breakpoints
- Fixed pixel widths instead of responsive layouts

### Typography
- Using type styles outside their intended purpose
- Line lengths exceeding 60 characters for body text
- Forgetting letter-spacing on label and title styles

## Implementation Checklist

Before delivering M3 UI code, verify:

### Color
- [ ] Using semantic color roles, not raw hex values
- [ ] Correct container/content pairings
- [ ] Light and dark theme support
- [ ] Error states use error color roles

### Components
- [ ] Touch targets >= 48dp on all interactive elements
- [ ] State layers for hover/focus/press using color tokens
- [ ] Focus indicators visible on keyboard navigation
- [ ] Pressed state provides visual feedback
- [ ] Disabled state: 12% container, 38% content opacity
- [ ] Correct elevation and shape for component type

### Layout
- [ ] Window size class responsive breakpoints
- [ ] Appropriate navigation for screen size
- [ ] Margins and gutters follow grid system

### Accessibility
- [ ] Color contrast >= 4.5:1 (text) / 3:1 (UI)
- [ ] ARIA labels on icon-only buttons
- [ ] Semantic HTML structure
- [ ] Form labels associated with inputs

### Critical Failures (Must Fix Before Delivery)
1. Touch target < 48dp on any interactive element
2. Missing focus indicator on interactive elements
3. Color contrast < 4.5:1 for text
4. Missing ARIA label on icon-only buttons
5. Hardcoded hex colors instead of tokens
6. No dark theme support

## Tailwind CSS M3 Color Config

```javascript
colors: {
  'primary': 'var(--md-sys-color-primary)',
  'on-primary': 'var(--md-sys-color-on-primary)',
  'primary-container': 'var(--md-sys-color-primary-container)',
  'on-primary-container': 'var(--md-sys-color-on-primary-container)',
  'secondary': 'var(--md-sys-color-secondary)',
  'on-secondary': 'var(--md-sys-color-on-secondary)',
  'secondary-container': 'var(--md-sys-color-secondary-container)',
  'on-secondary-container': 'var(--md-sys-color-on-secondary-container)',
  'tertiary': 'var(--md-sys-color-tertiary)',
  'on-tertiary': 'var(--md-sys-color-on-tertiary)',
  'tertiary-container': 'var(--md-sys-color-tertiary-container)',
  'on-tertiary-container': 'var(--md-sys-color-on-tertiary-container)',
  'error': 'var(--md-sys-color-error)',
  'on-error': 'var(--md-sys-color-on-error)',
  'error-container': 'var(--md-sys-color-error-container)',
  'on-error-container': 'var(--md-sys-color-on-error-container)',
  'surface': 'var(--md-sys-color-surface)',
  'on-surface': 'var(--md-sys-color-on-surface)',
  'on-surface-variant': 'var(--md-sys-color-on-surface-variant)',
  'surface-container-lowest': 'var(--md-sys-color-surface-container-lowest)',
  'surface-container-low': 'var(--md-sys-color-surface-container-low)',
  'surface-container': 'var(--md-sys-color-surface-container)',
  'surface-container-high': 'var(--md-sys-color-surface-container-high)',
  'surface-container-highest': 'var(--md-sys-color-surface-container-highest)',
  'outline': 'var(--md-sys-color-outline)',
  'outline-variant': 'var(--md-sys-color-outline-variant)',
  'inverse-surface': 'var(--md-sys-color-inverse-surface)',
  'inverse-on-surface': 'var(--md-sys-color-inverse-on-surface)',
  'inverse-primary': 'var(--md-sys-color-inverse-primary)',
},
```

## Resources

- [Material Design 3 Documentation](https://m3.material.io/)
- [Material Theme Builder](https://www.figma.com/community/plugin/1034969338659738588/material-theme-builder)
- [M3 Figma Design Kit](https://www.figma.com/community/file/1035203688168086460)
- [Material Color Utilities](https://github.com/material-foundation/material-color-utilities)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
