# M3 Color System Reference

## Color Roles (29 Standard Roles + Fixed Accents)

M3 assigns colors to UI elements through semantic roles, not raw hex values.

### Primary Accent Colors
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

### Surface Colors
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

### Error & Outline
```css
--md-sys-color-error:
--md-sys-color-on-error:
--md-sys-color-error-container:
--md-sys-color-on-error-container:

--md-sys-color-outline: /* Important boundaries (text field borders) */
--md-sys-color-outline-variant: /* Decorative elements (dividers) */
```

### Inverse Colors (for contrasting elements like snackbars)
```css
--md-sys-color-inverse-surface:
--md-sys-color-inverse-on-surface:
--md-sys-color-inverse-primary:
```

### Additional Surface & Utility Colors
```css
--md-sys-color-surface-dim: /* Dimmer surface variant */
--md-sys-color-surface-bright: /* Brighter surface variant */
--md-sys-color-scrim: /* Overlay behind modals (typically #000000) */
--md-sys-color-shadow: /* Drop shadow color (typically #000000) */
```

### Fixed Accent Colors (consistent across light/dark themes)
```css
/* Primary Fixed */
--md-sys-color-primary-fixed:
--md-sys-color-primary-fixed-dim:
--md-sys-color-on-primary-fixed:
--md-sys-color-on-primary-fixed-variant:

/* Secondary Fixed */
--md-sys-color-secondary-fixed:
--md-sys-color-secondary-fixed-dim:
--md-sys-color-on-secondary-fixed:
--md-sys-color-on-secondary-fixed-variant:

/* Tertiary Fixed */
--md-sys-color-tertiary-fixed:
--md-sys-color-tertiary-fixed-dim:
--md-sys-color-on-tertiary-fixed:
--md-sys-color-on-tertiary-fixed-variant:
```

## Baseline Light Theme Values
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

## Baseline Dark Theme Values

Apply dark theme using any of these selectors (all supported in `tokens.css`):
- `.dark` class on a parent element
- `[data-theme="dark"]` attribute
- `@media (prefers-color-scheme: dark)` for automatic OS preference

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

## Contrast Levels

M3 supports three contrast levels:
- **Standard** (default): Mixed contrast for visual hierarchy
- **Medium**: 3:1 minimum ratio
- **High**: 7:1 ratio for maximum accessibility
