# M3 Typography System Reference

## Type Scale (15 Baseline + 15 Emphasized Styles)

M3 defines 15 baseline type styles across 5 roles. Each has an emphasized variant (higher weight) for selection states and editorial emphasis.

### Type Roles
- **Display**: Large, expressive headlines for key moments
- **Headline**: High-emphasis text marking sections
- **Title**: Medium-emphasis titles for lists, cards
- **Body**: Long-form reading and explanations
- **Label**: Buttons, tabs, form labels

### Baseline Type Styles (using Roboto)
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

### Emphasized Type Styles

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

## Tailwind CSS Typography Config

```javascript
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
```
