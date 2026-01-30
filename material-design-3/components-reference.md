# Material Design 3 Components Reference

Quick reference for all M3 components with their key specifications.

## Action Components

### Buttons
| Type | Container | Content | Elevation |
|------|-----------|---------|-----------|
| Filled | `primary` | `on-primary` | 0 |
| Tonal | `secondary-container` | `on-secondary-container` | 0 |
| Elevated | `surface-container-low` | `primary` | 1 |
| Outlined | transparent | `on-surface-variant` | 0 |
| Text | transparent | `primary` | 0 |

**Sizes:** XS (32dp), Small (40dp), Medium (48dp), Large (56dp), XL (64dp)
**Shape:** Full (pill) or Square
**Icon size:** 20dp (small), 24dp (large)

### Button Groups
Organize related buttons with shape-shifting interactions.

### Extended FABs
| Size | Height | Container | Icon/Label |
|------|--------|-----------|------------|
| Default | 56dp | `primary-container` | `on-primary-container` |

**Elevation:** Level 3
**Shape:** Large (16dp) or Full

### FABs
| Size | Dimensions | Container |
|------|------------|-----------|
| Small | 40x40dp | `primary-container` |
| Default | 56x56dp | `primary-container` |
| Large | 96x96dp | `primary-container` |

**Elevation:** Level 3

### FAB Menu
Opens from FAB to display multiple related actions.

### Icon Buttons
| Type | Container | Icon |
|------|-----------|------|
| Standard | transparent | `on-surface-variant` |
| Filled | `primary` | `on-primary` |
| Tonal | `secondary-container` | `on-secondary-container` |
| Outlined | transparent + border | `on-surface-variant` |

**Size:** 40dp (standard), 48dp (with touch target)

### Segmented Buttons
Select options or switch views.
- Height: 40dp
- Shape: Full (pill)
- Selected: `secondary-container`

### Split Buttons
Button + related actions menu.

---

## Containment Components

### Cards
| Type | Container | Elevation |
|------|-----------|-----------|
| Elevated | `surface-container-low` | 1 |
| Filled | `surface-container-highest` | 0 |
| Outlined | `surface` + `outline-variant` | 0 |

**Shape:** 12dp corner radius
**Padding:** 16dp

### Dialogs
| Type | Width | Container |
|------|-------|-----------|
| Basic | 280-560dp | `surface-container-high` |
| Full-screen | 100% | `surface` |

**Shape:** 28dp corner radius
**Elevation:** Level 3

### Bottom Sheets
| Type | Container |
|------|-----------|
| Modal | `surface-container-low` |
| Standard | `surface-container-low` |

**Shape:** 28dp top corners
**Elevation:** Level 1 (modal)

### Side Sheets
| Type | Width | Container |
|------|-------|-----------|
| Modal | 400dp max | `surface-container-low` |
| Standard | 400dp max | `surface-container-low` |

### Carousel
Shows collection of items that scroll on/off screen.

### Divider
- Color: `outline-variant`
- Thickness: 1dp

### Lists
- Item height: 56dp (one-line), 72dp (two-line), 88dp (three-line)
- Container: `surface`
- Leading icon: 24dp
- Padding: 16dp horizontal

---

## Communication Components

### Badges
Small status indicators on icons.
- Size: 6dp (dot), 16dp+ (with number)
- Container: `error`
- Text: `on-error`

### Progress Indicators
| Type | Track | Indicator |
|------|-------|-----------|
| Linear | `surface-container-highest` | `primary` |
| Circular | `surface-container-highest` | `primary` |

**Height (linear):** 4dp

### Loading Indicators
Show progress with short wait time.
Uses shape morphing for expression.

### Snackbar
- Container: `inverse-surface`
- Text: `inverse-on-surface`
- Action: `inverse-primary`
- Height: 48dp (single line)
- Shape: 4dp corner radius

### Tooltips
| Type | Container | Text |
|------|-----------|------|
| Plain | `inverse-surface` | `inverse-on-surface` |
| Rich | `surface-container` | `on-surface` |

**Elevation:** Level 2 (rich)

---

## Navigation Components

### Navigation Bar (Bottom)
- Height: 80dp
- Container: `surface-container`
- Active: `secondary-container` pill with `on-secondary-container` icon
- Inactive: `on-surface-variant`
- Items: 3-5

### Navigation Rail
| State | Width |
|-------|-------|
| Collapsed | 80dp |
| Expanded | 360dp |

- Container: `surface-container`
- FAB position: Top

### Navigation Drawer
| Type | Width |
|------|-------|
| Modal | 360dp |
| Standard | 360dp |

- Container: `surface-container`
- Active item: `secondary-container`

### App Bars
| Type | Height | Container |
|------|--------|-----------|
| Top (center-aligned) | 64dp | `surface` |
| Top (small) | 64dp | `surface` |
| Top (medium) | 112dp | `surface` |
| Top (large) | 152dp | `surface` |

**Scrolled elevation:** Level 2

### Tabs
| Type | Height | Indicator |
|------|--------|-----------|
| Primary | 48dp | `primary` underline |
| Secondary | 48dp | `primary` underline |

**Max tabs:** 6

---

## Selection Components

### Checkbox
- Size: 18dp (icon)
- Touch target: 48dp
- Selected: `primary`
- Unselected: `on-surface-variant` border

### Radio Button
- Size: 20dp
- Touch target: 48dp
- Selected: `primary`
- Unselected: `on-surface-variant` border

### Switch
- Track: 52x32dp
- Handle: 28dp (on), 24dp (off)
- Selected track: `primary`
- Unselected track: `surface-container-highest`

### Chips
| Type | Height | Container (unselected) |
|------|--------|------------------------|
| Assist | 32dp | `surface` + `outline` |
| Filter | 32dp | `surface` + `outline` |
| Input | 32dp | `surface` + `outline` |
| Suggestion | 32dp | `surface` + `outline` |

**Shape:** 8dp corner radius
**Selected filter:** `secondary-container`

### Slider
- Track height: 4dp
- Handle: 20dp
- Active: `primary`
- Inactive: `surface-container-highest`

### Menus
- Container: `surface-container`
- Elevation: Level 2
- Item height: 48dp
- Width: 112-280dp

---

## Text Input Components

### Text Fields
| Type | Container | Height |
|------|-----------|--------|
| Filled | `surface-container-highest` | 56dp |
| Outlined | transparent | 56dp |

**Shape:** 4dp top corners (filled), 4dp all corners (outlined)
**Padding:** 16dp horizontal

**States:**
- Enabled indicator: `on-surface-variant`
- Focused indicator: `primary`
- Error indicator: `error`

### Search
- Container: `surface-container-high`
- Height: 56dp
- Shape: Full (pill)
- Elevation: Level 3

---

## Date & Time

### Date Pickers
| Type | Container |
|------|-----------|
| Modal | `surface-container-high` |
| Docked | `surface-container-high` |

**Elevation:** Level 3
**Shape:** 28dp corner radius

### Time Pickers
| Type | Container |
|------|-----------|
| Modal | `surface-container-high` |
| Docked | `surface-container-high` |

**Elevation:** Level 3

---

## Toolbars

Display frequently used actions relevant to current page.
- Container: `surface-container`
- Height: 48-64dp
- Elevation: Level 2

---

## State Layer Reference

Apply these opacities for state overlays:

```css
/* State layer uses the content color at these opacities */
hover: 8%
focus: 12%
pressed: 12%
dragged: 16%
```

---

## Spacing Reference

Common spacing values used in M3 components:

| Token | Value | Usage |
|-------|-------|-------|
| 4dp | xs | Icon padding |
| 8dp | sm | Chip internal padding |
| 12dp | md | Button-icon spacing |
| 16dp | lg | Card padding, list item padding |
| 24dp | xl | Section margins |
| 32dp | 2xl | Large gaps |

---

## Icon Sizes

| Context | Size |
|---------|------|
| Button leading icon | 20dp |
| Icon button | 24dp |
| Navigation icon | 24dp |
| FAB icon | 24dp |
| Large FAB icon | 36dp |
| List item icon | 24dp |
| Chip icon | 18dp |
