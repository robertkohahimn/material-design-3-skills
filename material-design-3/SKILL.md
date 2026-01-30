---
name: material-design-3
description: Design UI using Material Design 3 (M3) specifications. Use when building Android, web, or cross-platform interfaces following Google's latest design system. Includes complete color system with dynamic color, typography scale, component specs, elevation tokens, shape system, motion physics, and accessibility guidelines. Enables proper M3 theming, responsive layouts with window size classes, and expressive components.
---

# Material Design 3 UI Design Skill

Build beautiful, accessible, and expressive user interfaces following Google's Material Design 3 specification. This skill provides the complete M3 design system including dynamic color, typography, components, motion, shape, and elevation.

## 1. Core Design Philosophy

Material Design 3 (M3) is built on these principles:

**Personalization:** Dynamic color enables UI that adapts to user wallpaper or content
**Accessibility:** Built-in contrast ratios and touch targets meet WCAG standards
**Expressiveness:** M3 Expressive adds emotion through shape morphing, motion physics, and emphasized typography
**Consistency:** Design tokens ensure systematic application across platforms

### Token Architecture

M3 uses three classes of design tokens:

1. **Reference Tokens** (`md.ref.*`): Raw values (hex colors, font sizes)
2. **System Tokens** (`md.sys.*`): Semantic decisions (color roles, type styles)
3. **Component Tokens** (`md.comp.*`): Component-specific assignments

```
Example chain:
md.ref.palette.primary40 → md.sys.color.primary → md.comp.filled-button.container.color
```

---

## 2. Color System

### Color Roles (26 Standard Roles)

M3 assigns colors to UI elements through semantic roles, not raw hex values.

#### Primary Accent Colors
```css
/* Primary - for high-emphasis elements (FABs, prominent buttons) */
--md-sys-color-primary: /* Tone 40 light / Tone 80 dark */
--md-sys-color-on-primary: /* Tone 100 light / Tone 20 dark */
--md-sys-color-primary-container: /* Tone 90 light / Tone 30 dark */
--md-sys-color-on-primary-container: /* Tone 30 light / Tone 90 dark */

/* Secondary - for less prominent elements (filter chips, tonal buttons) */
--md-sys-color-secondary:
--md-sys-color-on-secondary:
--md-sys-color-secondary-container:
--md-sys-color-on-secondary-container:

/* Tertiary - for contrasting accents */
--md-sys-color-tertiary:
--md-sys-color-on-tertiary:
--md-sys-color-tertiary-container:
--md-sys-color-on-tertiary-container:
```

#### Surface Colors
```css
/* Background surfaces */
--md-sys-color-surface: /* Default background */
--md-sys-color-on-surface: /* Text/icons on surface */
--md-sys-color-on-surface-variant: /* Lower emphasis text */

/* Surface containers (for cards, sheets, dialogs) */
--md-sys-color-surface-container-lowest:
--md-sys-color-surface-container-low:
--md-sys-color-surface-container: /* Default */
--md-sys-color-surface-container-high:
--md-sys-color-surface-container-highest:
```

#### Error & Outline
```css
--md-sys-color-error:
--md-sys-color-on-error:
--md-sys-color-error-container:
--md-sys-color-on-error-container:

--md-sys-color-outline: /* Important boundaries (text field borders) */
--md-sys-color-outline-variant: /* Decorative elements (dividers) */
```

#### Inverse Colors (for contrasting elements like snackbars)
```css
--md-sys-color-inverse-surface:
--md-sys-color-inverse-on-surface:
--md-sys-color-inverse-primary:
```

### Baseline Light Theme Values
```css
:root {
  /* Primary */
  --md-sys-color-primary: #6750A4;
  --md-sys-color-on-primary: #FFFFFF;
  --md-sys-color-primary-container: #EADDFF;
  --md-sys-color-on-primary-container: #4F378B;

  /* Secondary */
  --md-sys-color-secondary: #625B71;
  --md-sys-color-on-secondary: #FFFFFF;
  --md-sys-color-secondary-container: #E8DEF8;
  --md-sys-color-on-secondary-container: #4A4458;

  /* Tertiary */
  --md-sys-color-tertiary: #7D5260;
  --md-sys-color-on-tertiary: #FFFFFF;
  --md-sys-color-tertiary-container: #FFD8E4;
  --md-sys-color-on-tertiary-container: #633B48;

  /* Error */
  --md-sys-color-error: #B3261E;
  --md-sys-color-on-error: #FFFFFF;
  --md-sys-color-error-container: #F9DEDC;
  --md-sys-color-on-error-container: #8C1D18;

  /* Surface */
  --md-sys-color-surface: #FEF7FF;
  --md-sys-color-on-surface: #1D1B20;
  --md-sys-color-on-surface-variant: #49454F;
  --md-sys-color-surface-container-lowest: #FFFFFF;
  --md-sys-color-surface-container-low: #F7F2FA;
  --md-sys-color-surface-container: #F3EDF7;
  --md-sys-color-surface-container-high: #ECE6F0;
  --md-sys-color-surface-container-highest: #E6E0E9;

  /* Outline */
  --md-sys-color-outline: #79747E;
  --md-sys-color-outline-variant: #CAC4D0;

  /* Inverse */
  --md-sys-color-inverse-surface: #322F35;
  --md-sys-color-inverse-on-surface: #F5EFF7;
  --md-sys-color-inverse-primary: #D0BCFF;
}
```

### Baseline Dark Theme Values
```css
.dark {
  /* Primary */
  --md-sys-color-primary: #D0BCFF;
  --md-sys-color-on-primary: #381E72;
  --md-sys-color-primary-container: #4F378B;
  --md-sys-color-on-primary-container: #EADDFF;

  /* Secondary */
  --md-sys-color-secondary: #CCC2DC;
  --md-sys-color-on-secondary: #332D41;
  --md-sys-color-secondary-container: #4A4458;
  --md-sys-color-on-secondary-container: #E8DEF8;

  /* Tertiary */
  --md-sys-color-tertiary: #EFB8C8;
  --md-sys-color-on-tertiary: #492532;
  --md-sys-color-tertiary-container: #633B48;
  --md-sys-color-on-tertiary-container: #FFD8E4;

  /* Error */
  --md-sys-color-error: #F2B8B5;
  --md-sys-color-on-error: #601410;
  --md-sys-color-error-container: #8C1D18;
  --md-sys-color-on-error-container: #F9DEDC;

  /* Surface */
  --md-sys-color-surface: #141218;
  --md-sys-color-on-surface: #E6E0E9;
  --md-sys-color-on-surface-variant: #CAC4D0;
  --md-sys-color-surface-container-lowest: #0F0D13;
  --md-sys-color-surface-container-low: #1D1B20;
  --md-sys-color-surface-container: #211F26;
  --md-sys-color-surface-container-high: #2B2930;
  --md-sys-color-surface-container-highest: #36343B;

  /* Outline */
  --md-sys-color-outline: #938F99;
  --md-sys-color-outline-variant: #49454F;

  /* Inverse */
  --md-sys-color-inverse-surface: #E6E0E9;
  --md-sys-color-inverse-on-surface: #322F35;
  --md-sys-color-inverse-primary: #6750A4;
}
```

### Color Pairing Rules

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

### Contrast Levels

M3 supports three contrast levels:
- **Standard** (default): Mixed contrast for visual hierarchy
- **Medium**: 3:1 minimum ratio
- **High**: 7:1 ratio for maximum accessibility

---

## 3. Typography System

### Type Scale (30 Styles)

M3 has 15 baseline + 15 emphasized type styles across 5 roles.

#### Type Roles
- **Display**: Large, expressive headlines for key moments
- **Headline**: High-emphasis text marking sections
- **Title**: Medium-emphasis titles for lists, cards
- **Body**: Long-form reading and explanations
- **Label**: Buttons, tabs, form labels

#### Baseline Type Styles (using Roboto)
```css
/* Display */
--md-sys-typescale-display-large-font: Roboto;
--md-sys-typescale-display-large-size: 57px;
--md-sys-typescale-display-large-line-height: 64px;
--md-sys-typescale-display-large-weight: 400;
--md-sys-typescale-display-large-tracking: -0.25px;

--md-sys-typescale-display-medium-size: 45px;
--md-sys-typescale-display-medium-line-height: 52px;

--md-sys-typescale-display-small-size: 36px;
--md-sys-typescale-display-small-line-height: 44px;

/* Headline */
--md-sys-typescale-headline-large-size: 32px;
--md-sys-typescale-headline-large-line-height: 40px;

--md-sys-typescale-headline-medium-size: 28px;
--md-sys-typescale-headline-medium-line-height: 36px;

--md-sys-typescale-headline-small-size: 24px;
--md-sys-typescale-headline-small-line-height: 32px;

/* Title */
--md-sys-typescale-title-large-size: 22px;
--md-sys-typescale-title-large-line-height: 28px;
--md-sys-typescale-title-large-weight: 400;

--md-sys-typescale-title-medium-size: 16px;
--md-sys-typescale-title-medium-line-height: 24px;
--md-sys-typescale-title-medium-weight: 500;
--md-sys-typescale-title-medium-tracking: 0.15px;

--md-sys-typescale-title-small-size: 14px;
--md-sys-typescale-title-small-line-height: 20px;
--md-sys-typescale-title-small-weight: 500;
--md-sys-typescale-title-small-tracking: 0.1px;

/* Body */
--md-sys-typescale-body-large-size: 16px;
--md-sys-typescale-body-large-line-height: 24px;
--md-sys-typescale-body-large-weight: 400;
--md-sys-typescale-body-large-tracking: 0.5px;

--md-sys-typescale-body-medium-size: 14px;
--md-sys-typescale-body-medium-line-height: 20px;
--md-sys-typescale-body-medium-tracking: 0.25px;

--md-sys-typescale-body-small-size: 12px;
--md-sys-typescale-body-small-line-height: 16px;
--md-sys-typescale-body-small-tracking: 0.4px;

/* Label */
--md-sys-typescale-label-large-size: 14px;
--md-sys-typescale-label-large-line-height: 20px;
--md-sys-typescale-label-large-weight: 500;
--md-sys-typescale-label-large-tracking: 0.1px;

--md-sys-typescale-label-medium-size: 12px;
--md-sys-typescale-label-medium-line-height: 16px;
--md-sys-typescale-label-medium-weight: 500;
--md-sys-typescale-label-medium-tracking: 0.5px;

--md-sys-typescale-label-small-size: 11px;
--md-sys-typescale-label-small-line-height: 16px;
--md-sys-typescale-label-small-weight: 500;
--md-sys-typescale-label-small-tracking: 0.5px;
```

#### Emphasized Type Styles

Use emphasized styles for selection states, actions, headlines, and editorial emphasis. They have higher weight than baseline.

```css
/* Token swap example */
/* Baseline: md.sys.typescale.label-large */
/* Emphasized: md.sys.typescale.emphasized.label-large */
```

### Typography Usage
| Element | Type Style |
|---------|------------|
| Hero headline | Display Large/Medium |
| Section headers | Headline Large/Medium |
| Card titles | Title Medium |
| Body text | Body Large/Medium |
| Button labels | Label Large |
| Captions | Body Small |
| Overlines | Label Small |

---

## 4. Shape System

### Corner Radius Scale
```css
--md-sys-shape-corner-none: 0px;
--md-sys-shape-corner-extra-small: 4px;
--md-sys-shape-corner-small: 8px;
--md-sys-shape-corner-medium: 12px;
--md-sys-shape-corner-large: 16px;
--md-sys-shape-corner-large-increased: 20dp;
--md-sys-shape-corner-extra-large: 28px;
--md-sys-shape-corner-extra-large-increased: 32dp;
--md-sys-shape-corner-extra-extra-large: 48dp;
--md-sys-shape-corner-full: 9999px; /* Pill shape */
```

### Component Shape Mapping
| Component | Shape |
|-----------|-------|
| Buttons | Full (pill) |
| Cards | Medium (12dp) |
| Dialogs | Extra Large (28dp) |
| FABs | Large (16dp) or Full |
| Chips | Small (8dp) |
| Text Fields | Extra Small top (4dp) |
| Bottom Sheets | Extra Large top (28dp) |

### Shape Morph (M3 Expressive)

Buttons and interactive elements can morph shape on press/selection:
- **Round button pressed**: Corners compress from full to 8-16dp
- **Toggle selected**: Round → Square transition
- **Toggle unselected**: Square → Round transition

---

## 5. Elevation System

### Elevation Levels
```css
--md-sys-elevation-level0: 0dp;   /* Flat surfaces */
--md-sys-elevation-level1: 1dp;   /* Cards, banners */
--md-sys-elevation-level2: 3dp;   /* App bars (scrolled), menus */
--md-sys-elevation-level3: 6dp;   /* FABs, dialogs */
--md-sys-elevation-level4: 8dp;   /* (Hover state increase) */
--md-sys-elevation-level5: 12dp;  /* (Not default resting) */
```

### Component Elevation Defaults
| Level | Components |
|-------|------------|
| 0 | Buttons (filled/tonal/outlined), cards (filled/outlined), chips, tabs |
| 1 | Elevated cards, elevated chips, banners, modal sheets |
| 2 | Menus, navigation bar, app bar (scrolled), tooltips |
| 3 | FABs, dialogs, date/time pickers, search |

### Elevation Behavior
- **Hover**: +1 level (FAB 3→4)
- **Disabled**: No elevation change
- Use tonal surface colors instead of shadows in M3

---

## 6. Motion System (M3 Expressive)

### Motion Schemes

**Expressive** (default): Bouncy, overshoots final values
**Standard**: Functional, minimal bounce

### Spring Tokens

M3 uses physics-based springs instead of easing curves.

```
Spatial springs: Movement (position, rotation, size)
Effects springs: Color, opacity changes

Speeds:
- Fast: Small components (switches, buttons)
- Default: Partial screen (sheets, rails)
- Slow: Full-screen animations
```

### Duration Guidelines (Legacy)
```css
--md-sys-motion-duration-short1: 50ms;
--md-sys-motion-duration-short2: 100ms;
--md-sys-motion-duration-short3: 150ms;
--md-sys-motion-duration-short4: 200ms;
--md-sys-motion-duration-medium1: 250ms;
--md-sys-motion-duration-medium2: 300ms;
--md-sys-motion-duration-medium3: 350ms;
--md-sys-motion-duration-medium4: 400ms;
--md-sys-motion-duration-long1: 450ms;
--md-sys-motion-duration-long2: 500ms;
--md-sys-motion-duration-long3: 550ms;
--md-sys-motion-duration-long4: 600ms;
```

### Easing (Legacy)
```css
--md-sys-motion-easing-standard: cubic-bezier(0.2, 0, 0, 1);
--md-sys-motion-easing-standard-decelerate: cubic-bezier(0, 0, 0, 1);
--md-sys-motion-easing-standard-accelerate: cubic-bezier(0.3, 0, 1, 1);
--md-sys-motion-easing-emphasized: cubic-bezier(0.2, 0, 0, 1);
--md-sys-motion-easing-emphasized-decelerate: cubic-bezier(0.05, 0.7, 0.1, 1);
--md-sys-motion-easing-emphasized-accelerate: cubic-bezier(0.3, 0, 0.8, 0.15);
```

---

## 7. Interaction States

### State Layer Opacity
```css
--md-sys-state-hover-state-layer-opacity: 0.08;
--md-sys-state-focus-state-layer-opacity: 0.12;
--md-sys-state-pressed-state-layer-opacity: 0.12;
--md-sys-state-dragged-state-layer-opacity: 0.16;
```

### State Behavior
| State | Visual Treatment |
|-------|-----------------|
| Enabled | Default styling |
| Disabled | 38% opacity, no interaction |
| Hover | 8% state layer overlay |
| Focused | 12% state layer + focus ring |
| Pressed | 12% state layer (ripple) |
| Dragged | 16% state layer + elevation |

### Focus Indicators
- Keyboard focus requires visible ring indicator
- Focus ring must have 3:1 contrast against adjacent colors

---

## 8. Layout System

### Window Size Classes
| Class | Width | Typical Devices |
|-------|-------|-----------------|
| Compact | <600dp | Phone portrait |
| Medium | 600-839dp | Tablet portrait, foldable |
| Expanded | 840-1199dp | Tablet landscape, desktop |
| Large | 1200-1599dp | Desktop |
| Extra-large | 1600dp+ | Ultra-wide monitors |

### Responsive Navigation
| Window Size | Navigation |
|-------------|------------|
| Compact | Bottom navigation bar |
| Medium | Navigation rail (collapsed) |
| Expanded | Navigation rail or drawer |
| Large/XL | Expanded navigation drawer |

### Layout Grid
- **Margins**: 16dp (compact), 24dp (medium+)
- **Gutters**: 16-24dp between columns
- **Columns**: 4 (compact), 8 (medium), 12 (expanded+)

### Pane Recommendations
| Window Size | Panes |
|-------------|-------|
| Compact | 1 |
| Medium | 1 (recommended) or 2 |
| Expanded | 2 (recommended) |
| Large | 2 (recommended) |
| Extra-large | 2-3 |

---

## 9. Component Specifications

### Buttons

**Types:** Default, Toggle
**Colors:** Elevated, Filled (default), Tonal, Outlined, Text
**Shapes:** Round (default), Square
**Sizes:** XS, Small (default), Medium, Large, XL

#### Measurements
| Size | Height | Horizontal Padding | Icon Size |
|------|--------|-------------------|-----------|
| XS | 32dp | 12dp | 18dp |
| Small | 40dp | 16dp | 20dp |
| Medium | 48dp | 20dp | 20dp |
| Large | 56dp | 24dp | 24dp |
| XL | 64dp | 28dp | 24dp |

#### Button Colors
| Style | Container | Label/Icon |
|-------|-----------|------------|
| Filled | `primary` | `on-primary` |
| Tonal | `secondary-container` | `on-secondary-container` |
| Elevated | `surface-container-low` | `primary` |
| Outlined | transparent + `outline-variant` border | `on-surface-variant` |
| Text | transparent | `primary` |

### Cards

**Types:** Elevated, Filled, Outlined

| Type | Container | Elevation |
|------|-----------|-----------|
| Elevated | `surface-container-low` | Level 1 |
| Filled | `surface-container-highest` | Level 0 |
| Outlined | `surface` + `outline-variant` border | Level 0 |

**Measurements:**
- Corner radius: 12dp
- Padding: 16dp
- Gap between cards: 8dp max

### Text Fields

**Types:** Filled, Outlined

#### Filled Text Field
- Container: `surface-container-highest`
- Active indicator: `primary` (focused), `on-surface-variant` (enabled)
- Corner radius: 4dp top only
- Height: 56dp

#### Outlined Text Field
- Border: `outline` (enabled), `primary` (focused)
- Corner radius: 4dp
- Height: 56dp

**Common Measurements:**
- Left/right padding: 16dp (no icons), 12dp (with icons)
- Icon spacing: 16dp from text
- Supporting text top padding: 4dp

### FABs (Floating Action Buttons)

| Type | Size | Container |
|------|------|-----------|
| Small | 40dp | `primary-container` |
| Default | 56dp | `primary-container` |
| Large | 96dp | `primary-container` |
| Extended | 56dp height | `primary-container` |

- Icon: `on-primary-container`
- Elevation: Level 3
- Corner radius: Large (16dp) or Full

### Navigation Components

#### Navigation Bar (Bottom)
- Height: 80dp
- Container: `surface-container`
- Active icon: `on-secondary-container` in `secondary-container` pill
- Inactive icon: `on-surface-variant`

#### Navigation Rail
- Width: 80dp (collapsed), 360dp (expanded)
- Container: `surface-container`

#### Navigation Drawer
- Width: 360dp
- Container: `surface-container`

### Chips

**Types:** Assist, Filter, Input, Suggestion

- Height: 32dp
- Corner radius: 8dp (small)
- Horizontal padding: 16dp

### Dialogs

- Container: `surface-container-high`
- Corner radius: 28dp (extra-large)
- Elevation: Level 3
- Max width: 560dp

---

## 10. Accessibility Requirements

### Touch Targets
- **Minimum:** 48x48dp
- **Recommended:** 48x48dp with 8dp spacing

### Color Contrast
| Content | Minimum Ratio |
|---------|---------------|
| Normal text | 4.5:1 |
| Large text (18sp+ or 14sp bold) | 3:1 |
| UI components | 3:1 |
| Focus indicators | 3:1 |

### Semantic Structure
- Use proper heading hierarchy
- Provide labels for all form inputs
- Icon-only buttons require `aria-label`
- Images need descriptive `alt` text

---

## 11. Implementation Checklist

Before delivering M3 UI code:

### Color ✓
- [ ] Using semantic color roles, not raw hex values
- [ ] Correct container/content pairings
- [ ] Light and dark theme support
- [ ] Error states use error color roles

### Typography ✓
- [ ] Using M3 type scale tokens
- [ ] Correct role for context (body for reading, label for buttons)
- [ ] Emphasized styles only for selection/emphasis

### Components ✓
- [ ] Correct elevation for component type
- [ ] Proper shape/corner radius
- [ ] State layers for hover/focus/press
- [ ] Disabled state at 38% opacity

### Layout ✓
- [ ] Window size class responsive breakpoints
- [ ] Appropriate navigation for screen size
- [ ] Margins and gutters follow grid system

### Accessibility ✓
- [ ] Touch targets ≥ 48dp
- [ ] Color contrast ≥ 4.5:1 (text) / 3:1 (UI)
- [ ] Focus indicators visible
- [ ] Semantic HTML structure

---

## 12. Tailwind CSS M3 Configuration

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        // Primary
        'primary': 'var(--md-sys-color-primary)',
        'on-primary': 'var(--md-sys-color-on-primary)',
        'primary-container': 'var(--md-sys-color-primary-container)',
        'on-primary-container': 'var(--md-sys-color-on-primary-container)',
        // Secondary
        'secondary': 'var(--md-sys-color-secondary)',
        'on-secondary': 'var(--md-sys-color-on-secondary)',
        'secondary-container': 'var(--md-sys-color-secondary-container)',
        'on-secondary-container': 'var(--md-sys-color-on-secondary-container)',
        // Tertiary
        'tertiary': 'var(--md-sys-color-tertiary)',
        'on-tertiary': 'var(--md-sys-color-on-tertiary)',
        'tertiary-container': 'var(--md-sys-color-tertiary-container)',
        'on-tertiary-container': 'var(--md-sys-color-on-tertiary-container)',
        // Error
        'error': 'var(--md-sys-color-error)',
        'on-error': 'var(--md-sys-color-on-error)',
        'error-container': 'var(--md-sys-color-error-container)',
        'on-error-container': 'var(--md-sys-color-on-error-container)',
        // Surface
        'surface': 'var(--md-sys-color-surface)',
        'on-surface': 'var(--md-sys-color-on-surface)',
        'on-surface-variant': 'var(--md-sys-color-on-surface-variant)',
        'surface-container-lowest': 'var(--md-sys-color-surface-container-lowest)',
        'surface-container-low': 'var(--md-sys-color-surface-container-low)',
        'surface-container': 'var(--md-sys-color-surface-container)',
        'surface-container-high': 'var(--md-sys-color-surface-container-high)',
        'surface-container-highest': 'var(--md-sys-color-surface-container-highest)',
        // Outline
        'outline': 'var(--md-sys-color-outline)',
        'outline-variant': 'var(--md-sys-color-outline-variant)',
        // Inverse
        'inverse-surface': 'var(--md-sys-color-inverse-surface)',
        'inverse-on-surface': 'var(--md-sys-color-inverse-on-surface)',
        'inverse-primary': 'var(--md-sys-color-inverse-primary)',
      },
      borderRadius: {
        'none': '0',
        'xs': '4px',
        'sm': '8px',
        'md': '12px',
        'lg': '16px',
        'xl': '28px',
        'full': '9999px',
      },
      fontSize: {
        'display-large': ['57px', { lineHeight: '64px', letterSpacing: '-0.25px' }],
        'display-medium': ['45px', { lineHeight: '52px' }],
        'display-small': ['36px', { lineHeight: '44px' }],
        'headline-large': ['32px', { lineHeight: '40px' }],
        'headline-medium': ['28px', { lineHeight: '36px' }],
        'headline-small': ['24px', { lineHeight: '32px' }],
        'title-large': ['22px', { lineHeight: '28px' }],
        'title-medium': ['16px', { lineHeight: '24px', letterSpacing: '0.15px', fontWeight: '500' }],
        'title-small': ['14px', { lineHeight: '20px', letterSpacing: '0.1px', fontWeight: '500' }],
        'body-large': ['16px', { lineHeight: '24px', letterSpacing: '0.5px' }],
        'body-medium': ['14px', { lineHeight: '20px', letterSpacing: '0.25px' }],
        'body-small': ['12px', { lineHeight: '16px', letterSpacing: '0.4px' }],
        'label-large': ['14px', { lineHeight: '20px', letterSpacing: '0.1px', fontWeight: '500' }],
        'label-medium': ['12px', { lineHeight: '16px', letterSpacing: '0.5px', fontWeight: '500' }],
        'label-small': ['11px', { lineHeight: '16px', letterSpacing: '0.5px', fontWeight: '500' }],
      },
      boxShadow: {
        'elevation-1': '0 1px 2px 0 rgb(0 0 0 / 0.3), 0 1px 3px 1px rgb(0 0 0 / 0.15)',
        'elevation-2': '0 1px 2px 0 rgb(0 0 0 / 0.3), 0 2px 6px 2px rgb(0 0 0 / 0.15)',
        'elevation-3': '0 4px 8px 3px rgb(0 0 0 / 0.15), 0 1px 3px rgb(0 0 0 / 0.3)',
        'elevation-4': '0 6px 10px 4px rgb(0 0 0 / 0.15), 0 2px 3px rgb(0 0 0 / 0.3)',
        'elevation-5': '0 8px 12px 6px rgb(0 0 0 / 0.15), 0 4px 4px rgb(0 0 0 / 0.3)',
      },
      transitionTimingFunction: {
        'standard': 'cubic-bezier(0.2, 0, 0, 1)',
        'standard-decelerate': 'cubic-bezier(0, 0, 0, 1)',
        'standard-accelerate': 'cubic-bezier(0.3, 0, 1, 1)',
        'emphasized': 'cubic-bezier(0.2, 0, 0, 1)',
        'emphasized-decelerate': 'cubic-bezier(0.05, 0.7, 0.1, 1)',
        'emphasized-accelerate': 'cubic-bezier(0.3, 0, 0.8, 0.15)',
      },
    },
  },
}
```

---

## 13. Anti-Patterns (NEVER DO)

### Color Anti-Patterns
- Using raw hex values instead of color role tokens
- Pairing unrelated color roles (e.g., `primary` on `tertiary-container`)
- Ignoring dark theme support
- Using color alone to convey information

### Component Anti-Patterns
- Touch targets smaller than 48dp
- Missing focus states
- Incorrect elevation for component type
- Using outline color for dividers (use outline-variant)

### Layout Anti-Patterns
- Same navigation pattern across all window sizes
- Ignoring window size class breakpoints
- Fixed pixel widths instead of responsive layouts

### Typography Anti-Patterns
- Using type styles outside their intended purpose
- Mixing multiple type scales
- Line lengths exceeding 60 characters for body text

---

## Resources

- [Material Design 3 Documentation](https://m3.material.io/)
- [Material Theme Builder](https://www.figma.com/community/plugin/1034969338659738588/material-theme-builder)
- [M3 Figma Design Kit](https://www.figma.com/community/file/1035203688168086460)
- [Material Color Utilities](https://github.com/material-foundation/material-color-utilities)
