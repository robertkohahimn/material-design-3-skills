# M3 Layout, Shape, Elevation & Motion Reference

## Shape System

### Corner Radius Scale
```css
--md-sys-shape-corner-none: 0px;
--md-sys-shape-corner-extra-small: 4px;
--md-sys-shape-corner-small: 8px;
--md-sys-shape-corner-medium: 12px;
--md-sys-shape-corner-large: 16px;
--md-sys-shape-corner-large-increased: 20px;
--md-sys-shape-corner-extra-large: 28px;
--md-sys-shape-corner-extra-large-increased: 32px;
--md-sys-shape-corner-extra-extra-large: 48px;
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
- **Toggle selected**: Round -> Square transition
- **Toggle unselected**: Square -> Round transition

## Elevation System

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
- **Hover**: +1 level (FAB 3->4)
- **Disabled**: No elevation change
- Use tonal surface colors instead of shadows in M3

## Motion System (M3 Expressive)

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
--md-sys-motion-duration-extra-long1: 700ms;
--md-sys-motion-duration-extra-long2: 800ms;
--md-sys-motion-duration-extra-long3: 900ms;
--md-sys-motion-duration-extra-long4: 1000ms;
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

## Layout System

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

## Tailwind CSS Config Extensions

```javascript
borderRadius: {
  'none': '0',
  'xs': '4px',
  'sm': '8px',
  'md': '12px',
  'lg': '16px',
  'xl': '28px',
  'full': '9999px',
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
```
