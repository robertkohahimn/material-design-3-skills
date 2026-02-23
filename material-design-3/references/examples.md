# M3 Complete Component Examples

Reference implementations demonstrating all states, accessibility, and proper token usage.

## Filled Button (Complete)
```html
<button class="md-button md-button--filled">
  <span class="md-button__label">Submit</span>
</button>
```

```css
.md-button {
  /* Base */
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 64px;
  min-height: 40px;
  padding: 0 24px;
  border: none;
  border-radius: var(--md-sys-shape-corner-full);
  cursor: pointer;
  isolation: isolate;

  /* Typography */
  font-family: var(--md-sys-typescale-label-large-font);
  font-size: var(--md-sys-typescale-label-large-size);
  font-weight: var(--md-sys-typescale-label-large-weight);
  line-height: var(--md-sys-typescale-label-large-line-height);
  letter-spacing: var(--md-sys-typescale-label-large-tracking);

  /* Motion */
  transition:
    box-shadow var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard),
    transform var(--md-sys-motion-duration-short2) var(--md-sys-motion-easing-standard);
}

/* State layer */
.md-button::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  opacity: 0;
  pointer-events: none;
  transition: opacity var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard);
}

/* Filled variant */
.md-button--filled {
  background-color: var(--md-sys-color-primary);
  color: var(--md-sys-color-on-primary);
}

.md-button--filled::before {
  background-color: var(--md-sys-color-on-primary);
}

/* States */
.md-button--filled:hover::before {
  opacity: 0.08;
}

.md-button--filled:hover {
  box-shadow: var(--md-sys-elevation-shadow-1);
}

.md-button--filled:focus-visible {
  outline: 2px solid var(--md-sys-color-primary);
  outline-offset: 2px;
}

.md-button--filled:focus-visible::before {
  opacity: 0.12;
}

.md-button--filled:active::before {
  opacity: 0.12;
}

.md-button--filled:active {
  transform: scale(0.98);
}

/* Disabled */
.md-button--filled:disabled {
  background-color: color-mix(in srgb, var(--md-sys-color-on-surface) 12%, transparent);
  color: color-mix(in srgb, var(--md-sys-color-on-surface) 38%, transparent);
  box-shadow: none;
  cursor: not-allowed;
  pointer-events: none;
}

.md-button--filled:disabled::before {
  display: none;
}
```

## Chip (Complete with Touch Target)
```html
<button class="md-chip md-chip--filter" aria-pressed="false">
  <span class="md-chip__label">Filter</span>
</button>
```

```css
.md-chip {
  /* Base */
  position: relative;
  display: inline-flex;
  align-items: center;
  height: 32px;
  padding: 0 16px;
  border: 1px solid var(--md-sys-color-outline);
  border-radius: var(--md-sys-shape-corner-small);
  background-color: transparent;
  cursor: pointer;

  /* Typography */
  font-family: var(--md-sys-typescale-label-large-font);
  font-size: var(--md-sys-typescale-label-large-size);
  font-weight: var(--md-sys-typescale-label-large-weight);
  line-height: var(--md-sys-typescale-label-large-line-height);
  letter-spacing: var(--md-sys-typescale-label-large-tracking);
  color: var(--md-sys-color-on-surface-variant);
}

/* Touch target expansion (REQUIRED) */
.md-chip::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  transform: translateY(-50%);
  height: 48px;
}

/* State layer */
.md-chip::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  background-color: var(--md-sys-color-on-surface-variant);
  opacity: 0;
  pointer-events: none;
}

.md-chip:hover::before {
  opacity: 0.08;
}

.md-chip:focus-visible {
  outline: 2px solid var(--md-sys-color-primary);
  outline-offset: 2px;
}

.md-chip:focus-visible::before {
  opacity: 0.12;
}

/* Selected state */
.md-chip--filter[aria-pressed="true"] {
  background-color: var(--md-sys-color-secondary-container);
  border-color: transparent;
  color: var(--md-sys-color-on-secondary-container);
}

.md-chip--filter[aria-pressed="true"]::before {
  background-color: var(--md-sys-color-on-secondary-container);
}
```

## Checkbox (Complete with Touch Target)
```html
<label class="md-checkbox">
  <input type="checkbox" class="md-checkbox__input">
  <span class="md-checkbox__box"></span>
  <span class="md-checkbox__label">Accept terms</span>
</label>
```

```css
.md-checkbox {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  cursor: pointer;
  /* Ensure touch target */
  min-height: 48px;
}

.md-checkbox__input {
  position: absolute;
  opacity: 0;
  width: 48px;
  height: 48px;
  margin: 0;
  cursor: pointer;
}

.md-checkbox__box {
  position: relative;
  width: 18px;
  height: 18px;
  border: 2px solid var(--md-sys-color-on-surface-variant);
  border-radius: 2px;
  transition: all var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard);
}

/* Touch target expansion */
.md-checkbox__box::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 48px;
  height: 48px;
  border-radius: var(--md-sys-shape-corner-full);
  background-color: var(--md-sys-color-on-surface);
  opacity: 0;
  transition: opacity var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard);
}

.md-checkbox__input:hover + .md-checkbox__box::before {
  opacity: 0.08;
}

.md-checkbox__input:focus-visible + .md-checkbox__box {
  outline: 2px solid var(--md-sys-color-primary);
  outline-offset: 2px;
}

.md-checkbox__input:checked + .md-checkbox__box {
  background-color: var(--md-sys-color-primary);
  border-color: var(--md-sys-color-primary);
}

.md-checkbox__input:checked + .md-checkbox__box::after {
  content: '';
  position: absolute;
  left: 5px;
  top: 1px;
  width: 5px;
  height: 10px;
  border: solid var(--md-sys-color-on-primary);
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
}

.md-checkbox__label {
  font-family: var(--md-sys-typescale-body-medium-font);
  font-size: var(--md-sys-typescale-body-medium-size);
  line-height: var(--md-sys-typescale-body-medium-line-height);
  color: var(--md-sys-color-on-surface);
}
```

## Text Field - Filled (Complete)
```html
<div class="md-text-field md-text-field--filled">
  <input type="text" class="md-text-field__input" id="email" placeholder=" " required>
  <label class="md-text-field__label" for="email">Email address</label>
  <div class="md-text-field__indicator"></div>
</div>
```

```css
.md-text-field {
  position: relative;
  width: 100%;
}

.md-text-field--filled {
  background-color: var(--md-sys-color-surface-container-highest);
  border-radius: var(--md-sys-shape-corner-extra-small) var(--md-sys-shape-corner-extra-small) 0 0;
}

.md-text-field__input {
  width: 100%;
  height: 56px;
  padding: 24px 16px 8px 16px;
  border: none;
  background: transparent;
  font-family: var(--md-sys-typescale-body-large-font);
  font-size: var(--md-sys-typescale-body-large-size);
  line-height: var(--md-sys-typescale-body-large-line-height);
  color: var(--md-sys-color-on-surface);
  caret-color: var(--md-sys-color-primary);
}

.md-text-field__input:focus {
  outline: none;
}

.md-text-field__label {
  position: absolute;
  left: 16px;
  top: 16px;
  font-family: var(--md-sys-typescale-body-large-font);
  font-size: var(--md-sys-typescale-body-large-size);
  color: var(--md-sys-color-on-surface-variant);
  pointer-events: none;
  transition: all var(--md-sys-motion-duration-short3) var(--md-sys-motion-easing-standard);
}

.md-text-field__input:focus + .md-text-field__label,
.md-text-field__input:not(:placeholder-shown) + .md-text-field__label {
  top: 8px;
  font-size: var(--md-sys-typescale-body-small-size);
}

.md-text-field__input:focus + .md-text-field__label {
  color: var(--md-sys-color-primary);
}

.md-text-field__indicator {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 1px;
  background-color: var(--md-sys-color-on-surface-variant);
}

.md-text-field__input:focus ~ .md-text-field__indicator {
  height: 2px;
  background-color: var(--md-sys-color-primary);
}

/* Error state */
.md-text-field--error .md-text-field__label,
.md-text-field--error .md-text-field__input:focus + .md-text-field__label {
  color: var(--md-sys-color-error);
}

.md-text-field--error .md-text-field__indicator,
.md-text-field--error .md-text-field__input:focus ~ .md-text-field__indicator {
  background-color: var(--md-sys-color-error);
}

.md-text-field--error .md-text-field__input {
  caret-color: var(--md-sys-color-error);
}
```
