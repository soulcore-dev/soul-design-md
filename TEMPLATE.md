# DESIGN.md v2.0 — Template

> Replace all `{placeholders}` with actual values. Delete this instruction block when done.
> Target: 600-900 lines. Every value must be exact — no "generous", "approximately", or "~".

# Design System: {Brand Name}

## 1. Visual Theme & Atmosphere

{2-3 paragraphs describing the design philosophy, mood, and visual identity. Include:
- The dominant feeling/mood
- The relationship between typography and space
- The color story and why those colors exist
- What makes this design distinctive vs. generic}

**Key Characteristics:**
- {Characteristic 1 — e.g., "Void-black canvas with single electric accent color"}
- {Characteristic 2 — e.g., "Weight 300 headlines creating whisper-weight authority"}
- {Characteristic 3}
- {Characteristic 4}
- {Characteristic 5}
- {Characteristic 6}
- {Characteristic 7}
- {Characteristic 8}

---

## 2. Color System & Tokens

### Light Theme

| Token | Name | Hex | Role | CSS Variable |
|-------|------|-----|------|-------------|
| `bg-primary` | {name} | `{#hex}` | {role} | `--color-bg-primary` |
| `bg-secondary` | {name} | `{#hex}` | {role} | `--color-bg-secondary` |
| `bg-tertiary` | {name} | `{#hex}` | {role} | `--color-bg-tertiary` |
| `text-primary` | {name} | `{#hex}` | {role} | `--color-text-primary` |
| `text-secondary` | {name} | `{#hex}` | {role} | `--color-text-secondary` |
| `text-tertiary` | {name} | `{#hex}` | {role} | `--color-text-tertiary` |
| `text-disabled` | {name} | `{#hex}` | {role} | `--color-text-disabled` |
| `accent-primary` | {name} | `{#hex}` | {role} | `--color-accent-primary` |
| `accent-hover` | {name} | `{#hex}` | {role} | `--color-accent-hover` |
| `accent-active` | {name} | `{#hex}` | {role} | `--color-accent-active` |
| `border-default` | {name} | `{#hex}` | {role} | `--color-border-default` |
| `border-strong` | {name} | `{#hex}` | {role} | `--color-border-strong` |
| `border-focus` | {name} | `{#hex}` | {role} | `--color-border-focus` |
| `status-success` | {name} | `{#hex}` | {role} | `--color-status-success` |
| `status-warning` | {name} | `{#hex}` | {role} | `--color-status-warning` |
| `status-error` | {name} | `{#hex}` | {role} | `--color-status-error` |
| `status-info` | {name} | `{#hex}` | {role} | `--color-status-info` |
| `overlay` | {name} | `{rgba}` | {role} | `--color-overlay` |

### Dark Theme

| Token | Hex (Dark) | Maps to Light | CSS Variable |
|-------|-----------|---------------|-------------|
| `bg-primary` | `{#hex}` | `{light equivalent}` | `--color-bg-primary` |
| `bg-secondary` | `{#hex}` | `{light equivalent}` | `--color-bg-secondary` |
| {... complete mapping for all tokens} |

### Contrast Ratios (WCAG AA)

| Pair | Foreground | Background | Ratio | Pass AA | Pass AAA |
|------|-----------|-----------|-------|---------|----------|
| Body text | `{#hex}` | `{#hex}` | `{X.X:1}` | {Yes/No} | {Yes/No} |
| Heading text | `{#hex}` | `{#hex}` | `{X.X:1}` | {Yes/No} | {Yes/No} |
| Link on bg | `{#hex}` | `{#hex}` | `{X.X:1}` | {Yes/No} | {Yes/No} |
| Button text | `{#hex}` | `{#hex}` | `{X.X:1}` | {Yes/No} | {Yes/No} |
| Disabled text | `{#hex}` | `{#hex}` | `{X.X:1}` | {Yes/No} | {Yes/No} |

### Gradients (if applicable)

| Name | Value | Use |
|------|-------|-----|
| `{name}` | `linear-gradient({angle}, {color1}, {color2})` | {context} |

---

## 3. Typography System

### Font Stack

| Role | Family | Fallbacks | CSS Variable |
|------|--------|-----------|-------------|
| Display | `{font}` | `{fallbacks}` | `--font-display` |
| Body | `{font}` | `{fallbacks}` | `--font-body` |
| Mono | `{font}` | `{fallbacks}` | `--font-mono` |

**OpenType Features:** `{e.g., "ss01", "cv01", "tnum"}` — {why these matter}

### Type Scale

| Token | Size | Weight | Line Height | Letter Spacing | Fluid (clamp) | CSS Variable |
|-------|------|--------|-------------|----------------|---------------|-------------|
| `display-2xl` | {px} | {weight} | {ratio} | {px} | `clamp({min}, {preferred}, {max})` | `--text-display-2xl` |
| `display-xl` | {px} | {weight} | {ratio} | {px} | `clamp(...)` | `--text-display-xl` |
| `display-lg` | {px} | {weight} | {ratio} | {px} | `clamp(...)` | `--text-display-lg` |
| `heading-lg` | {px} | {weight} | {ratio} | {px} | `clamp(...)` | `--text-heading-lg` |
| `heading-md` | {px} | {weight} | {ratio} | {px} | `clamp(...)` | `--text-heading-md` |
| `heading-sm` | {px} | {weight} | {ratio} | {px} | `clamp(...)` | `--text-heading-sm` |
| `body-lg` | {px} | {weight} | {ratio} | {px} | — | `--text-body-lg` |
| `body-md` | {px} | {weight} | {ratio} | {px} | — | `--text-body-md` |
| `body-sm` | {px} | {weight} | {ratio} | {px} | — | `--text-body-sm` |
| `label-lg` | {px} | {weight} | {ratio} | {px} | — | `--text-label-lg` |
| `label-md` | {px} | {weight} | {ratio} | {px} | — | `--text-label-md` |
| `label-sm` | {px} | {weight} | {ratio} | {px} | — | `--text-label-sm` |
| `caption` | {px} | {weight} | {ratio} | {px} | — | `--text-caption` |
| `code-md` | {px} | {weight} | {ratio} | {px} | — | `--text-code-md` |
| `code-sm` | {px} | {weight} | {ratio} | {px} | — | `--text-code-sm` |

### Typography Principles
- {Principle 1 — e.g., "Weight 300 as signature: lightness as luxury"}
- {Principle 2 — e.g., "Progressive tracking: tighter at larger sizes"}
- {Principle 3}
- {Principle 4}

---

## 4. Component Catalog

### 4.1 Buttons

**Primary**
- Background: `{#hex}` → `var(--color-accent-primary)`
- Text: `{#hex}` → `var(--color-text-on-accent)`
- Padding: `{Ypx Xpx}`
- Border Radius: `{px}` → `var(--radius-md)`
- Font: `{size}` / `{weight}` / `{family}`
- Border: `{value}`
- Shadow: `{value}`

**Secondary** — {same format}
**Ghost / Outline** — {same format}
**Danger** — {same format}
**Icon Button** — {same format}

### 4.2 Inputs

**Text Input**
- Background: `{value}`
- Border: `{value}`
- Border Radius: `{px}`
- Padding: `{Ypx Xpx}`
- Font: `{size}` / `{weight}`
- Placeholder color: `{#hex}`
- Label: `{size}` / `{weight}` / `{color}` — positioned {above/left}
- Helper text: `{size}` / `{color}` — below input

**Select** — {same format}
**Textarea** — {same format}
**Checkbox** — {dimensions, check color, border, radius}
**Radio** — {dimensions, dot color, border}
**Toggle / Switch** — {dimensions, track color, thumb color, on/off states}

### 4.3 Cards

**Default Card**
- Background: `{value}`
- Border: `{value}`
- Border Radius: `{px}`
- Padding: `{px}`
- Shadow: `{value}`

**Interactive Card** — {+ hover/active states}
**Feature Card** — {with icon/image slot}

### 4.4 Navigation

**Top Nav / Header**
- Background: `{value}`
- Height: `{px}`
- Backdrop: `{blur value if glass}`
- Logo: `{dimensions}`, position `{left/center}`
- Links: `{size}` / `{weight}` / `{color}` / `{hover color}`
- CTA: `{button variant}`
- Mobile: `{hamburger → drawer/overlay}`

**Sidebar** — {if applicable}
**Bottom Nav (Mobile)** — {if applicable}
**Breadcrumbs** — separator, font, color

### 4.5 Modals & Dialogs

- Overlay: `{rgba value}`
- Container: bg `{value}`, radius `{px}`, shadow `{value}`, max-width `{px}`
- Header: `{font specs}`, close button `{specs}`
- Body: padding `{px}`, scroll behavior
- Footer: button alignment `{right/center/spread}`

### 4.6 Dropdowns & Menus

- Container: bg, border, radius, shadow
- Item: padding, font, hover bg, active bg
- Divider: `{border value}`
- Group label: `{font specs}`

### 4.7 Badges & Tags

| Variant | Background | Text | Border | Radius | Padding |
|---------|-----------|------|--------|--------|---------|
| Default | `{value}` | `{value}` | `{value}` | `{px}` | `{px}` |
| Success | `{value}` | `{value}` | `{value}` | `{px}` | `{px}` |
| Warning | `{value}` | `{value}` | `{value}` | `{px}` | `{px}` |
| Error | `{value}` | `{value}` | `{value}` | `{px}` | `{px}` |
| Info | `{value}` | `{value}` | `{value}` | `{px}` | `{px}` |

### 4.8 Tooltips

- Background: `{value}`
- Text: `{color}`, `{size}`
- Radius: `{px}`
- Padding: `{px}`
- Arrow: `{size}`, `{color}`
- Max width: `{px}`
- Shadow: `{value}`

### 4.9 Toasts & Notifications

- Container: bg, radius, shadow, padding, max-width
- Icon: `{size}`, color per variant (success/warning/error/info)
- Title: `{font specs}`
- Message: `{font specs}`
- Close button: `{specs}`
- Position: `{top-right / bottom-center / etc.}`
- Stack behavior: `{gap between stacked toasts}`

### 4.10 Tables

- Header: bg `{value}`, text `{specs}`, border-bottom `{value}`
- Row: bg `{value}`, hover bg `{value}`, border-bottom `{value}`
- Cell: padding `{px}`, alignment rules
- Striped variant: alternate row bg `{value}`

### 4.11 Tabs

- Container: border-bottom `{value}`
- Tab: padding, font, color (inactive), color (active), indicator `{border/underline specs}`
- Hover: `{color change}`

### 4.12 Avatars

| Size | Dimensions | Font Size | Radius |
|------|-----------|-----------|--------|
| xs | `{px}` | `{px}` | `{value}` |
| sm | `{px}` | `{px}` | `{value}` |
| md | `{px}` | `{px}` | `{value}` |
| lg | `{px}` | `{px}` | `{value}` |
| xl | `{px}` | `{px}` | `{value}` |

### 4.13 Pagination

- Button: size, radius, font, default/active/disabled colors
- Gap: `{px}`
- Ellipsis: `{style}`

### 4.14 Progress & Loading

- Progress bar: height `{px}`, track bg `{value}`, fill bg `{value}`, radius `{px}`
- Spinner: size `{px}`, color, stroke width `{px}`
- Skeleton: bg `{value}`, shimmer gradient `{value}`, radius matching component

---

## 5. Component State Matrix

| Component | Default | Hover | Active/Pressed | Focus | Disabled | Loading | Error |
|-----------|---------|-------|---------------|-------|----------|---------|-------|
| **Button Primary** | bg `{hex}` | bg `{hex}` | bg `{hex}`, scale `{0.98}` | ring `{value}` | bg `{hex}`, opacity `{0.5}`, cursor `not-allowed` | spinner + text fade | — |
| **Button Secondary** | {values} | {values} | {values} | {values} | {values} | {values} | — |
| **Button Ghost** | {values} | {values} | {values} | {values} | {values} | {values} | — |
| **Input Text** | border `{hex}` | border `{hex}` | — | ring `{value}` | bg `{hex}`, cursor `not-allowed` | — | border `{error-hex}`, text `{error-hex}` |
| **Checkbox** | border `{hex}` | border `{hex}` | — | ring `{value}` | opacity `{0.5}` | — | border `{error-hex}` |
| **Card Interactive** | shadow `{value}` | shadow `{value}`, translateY `{-2px}` | shadow `{value}` | ring `{value}` | opacity `{0.6}` | skeleton | — |
| **Link** | color `{hex}` | color `{hex}`, underline | color `{hex}` | ring `{value}` | color `{hex}`, no pointer | — | — |
| **Tab** | color `{hex}` | color `{hex}` | color `{hex}`, indicator | ring `{value}` | opacity `{0.5}` | — | — |
| **Select** | border `{hex}` | border `{hex}` | — | ring `{value}` | opacity `{0.5}` | spinner | border `{error-hex}` |

### Focus Ring Standard
```css
outline: 2px solid var(--color-border-focus);
outline-offset: 2px;
```

### Disabled Pattern
```css
opacity: 0.5;
cursor: not-allowed;
pointer-events: none;
```

---

## 6. Layout & Spacing System

### Spacing Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `space-0` | `0px` | `p-0` | `--space-0` | Reset |
| `space-1` | `4px` | `p-1` | `--space-1` | Tight inline |
| `space-2` | `8px` | `p-2` | `--space-2` | Icon gaps, badge padding |
| `space-3` | `12px` | `p-3` | `--space-3` | Input padding |
| `space-4` | `16px` | `p-4` | `--space-4` | Card padding, button gap |
| `space-5` | `20px` | `p-5` | `--space-5` | Section padding (mobile) |
| `space-6` | `24px` | `p-6` | `--space-6` | Component gap |
| `space-8` | `32px` | `p-8` | `--space-8` | Section sub-gap |
| `space-10` | `40px` | `p-10` | `--space-10` | Section gap (mobile) |
| `space-12` | `48px` | `p-12` | `--space-12` | Section gap (tablet) |
| `space-16` | `64px` | `p-16` | `--space-16` | Section gap (desktop) |
| `space-20` | `80px` | `p-20` | `--space-20` | Hero padding |
| `space-24` | `96px` | `p-24` | `--space-24` | Section gap (large) |

### Grid

| Property | Value | CSS Variable |
|----------|-------|-------------|
| Max content width | `{px}` | `--grid-max-width` |
| Column count | `{12}` | `--grid-columns` |
| Gutter | `{px}` | `--grid-gutter` |
| Margin (mobile) | `{px}` | `--grid-margin-sm` |
| Margin (desktop) | `{px}` | `--grid-margin-lg` |

### Border Radius Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `radius-none` | `0px` | `rounded-none` | `--radius-none` | {use} |
| `radius-sm` | `{px}` | `rounded-sm` | `--radius-sm` | {use} |
| `radius-md` | `{px}` | `rounded-md` | `--radius-md` | {use} |
| `radius-lg` | `{px}` | `rounded-lg` | `--radius-lg` | {use} |
| `radius-xl` | `{px}` | `rounded-xl` | `--radius-xl` | {use} |
| `radius-full` | `9999px` | `rounded-full` | `--radius-full` | Pills, avatars |

---

## 7. Depth & Elevation

### Shadow Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `shadow-xs` | `{value}` | `shadow-sm` | `--shadow-xs` | {use} |
| `shadow-sm` | `{value}` | `shadow` | `--shadow-sm` | {use} |
| `shadow-md` | `{value}` | `shadow-md` | `--shadow-md` | {use} |
| `shadow-lg` | `{value}` | `shadow-lg` | `--shadow-lg` | {use} |
| `shadow-xl` | `{value}` | `shadow-xl` | `--shadow-xl` | {use} |

### Z-Index Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `z-base` | `0` | `--z-base` | Default content |
| `z-dropdown` | `{value}` | `--z-dropdown` | Dropdowns, menus |
| `z-sticky` | `{value}` | `--z-sticky` | Sticky nav |
| `z-overlay` | `{value}` | `--z-overlay` | Modal backdrop |
| `z-modal` | `{value}` | `--z-modal` | Modal content |
| `z-popover` | `{value}` | `--z-popover` | Popovers, tooltips |
| `z-toast` | `{value}` | `--z-toast` | Toast notifications |

---

## 8. Motion & Animation System

### Duration Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `duration-instant` | `0ms` | `--duration-instant` | Immediate feedback |
| `duration-fast` | `{ms}` | `--duration-fast` | Hover, focus, micro-interactions |
| `duration-normal` | `{ms}` | `--duration-normal` | Expand/collapse, tab switch |
| `duration-slow` | `{ms}` | `--duration-slow` | Page transitions, modals |
| `duration-slower` | `{ms}` | `--duration-slower` | Complex orchestrated animations |

### Easing Functions

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `ease-default` | `{cubic-bezier}` | `--ease-default` | General transitions |
| `ease-in` | `{cubic-bezier}` | `--ease-in` | Elements exiting |
| `ease-out` | `{cubic-bezier}` | `--ease-out` | Elements entering |
| `ease-in-out` | `{cubic-bezier}` | `--ease-in-out` | Elements moving |
| `ease-bounce` | `{cubic-bezier}` | `--ease-bounce` | Playful feedback |

### Common Transitions

| Interaction | Property | Duration | Easing |
|------------|----------|----------|--------|
| Button hover | `background-color, box-shadow` | `{fast}` | `{ease-default}` |
| Link hover | `color` | `{fast}` | `{ease-default}` |
| Card hover | `transform, box-shadow` | `{normal}` | `{ease-out}` |
| Modal enter | `opacity, transform` | `{slow}` | `{ease-out}` |
| Modal exit | `opacity, transform` | `{normal}` | `{ease-in}` |
| Toast enter | `transform, opacity` | `{normal}` | `{ease-out}` |
| Dropdown open | `opacity, transform` | `{normal}` | `{ease-out}` |
| Focus ring | `box-shadow` | `{fast}` | `{ease-default}` |

### Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

---

## 9. Icon System

| Property | Value |
|----------|-------|
| Library | `{e.g., Lucide, Heroicons, Phosphor, custom}` |
| Default size | `{px}` |
| Stroke width | `{px}` |
| Color | `currentColor` (inherits from parent text) |

### Icon Sizes

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `icon-xs` | `{px}` | `--icon-xs` | Inline, badges |
| `icon-sm` | `{px}` | `--icon-sm` | Buttons, inputs |
| `icon-md` | `{px}` | `--icon-md` | Navigation, cards |
| `icon-lg` | `{px}` | `--icon-lg` | Feature sections |
| `icon-xl` | `{px}` | `--icon-xl` | Hero, empty states |

---

## 10. Accessibility Contract

### Targets

| Criterion | Target | Standard |
|-----------|--------|----------|
| Color contrast (normal text) | `{4.5:1}` minimum | WCAG AA |
| Color contrast (large text) | `{3:1}` minimum | WCAG AA |
| Color contrast (UI components) | `{3:1}` minimum | WCAG AA |
| Touch target size | `{44x44px}` minimum | WCAG 2.5.8 |
| Focus indicator | `{2px}` ring, `{3:1}` contrast | WCAG 2.4.7 |
| Motion | Respect `prefers-reduced-motion` | WCAG 2.3.3 |

### Focus Management

- All interactive elements must have visible focus indicator
- Focus ring: `{exact CSS value}`
- Focus order follows visual layout (logical tab order)
- Modal traps focus within dialog until dismissed
- Skip-to-content link as first focusable element

### ARIA Patterns

| Component | Role | Key Attributes |
|-----------|------|---------------|
| Modal | `dialog` | `aria-modal="true"`, `aria-labelledby` |
| Dropdown | `listbox` | `aria-expanded`, `aria-activedescendant` |
| Tabs | `tablist` / `tab` / `tabpanel` | `aria-selected`, `aria-controls` |
| Toast | `alert` or `status` | `role="alert"` for errors, `role="status"` for info |
| Toggle | `switch` | `aria-checked` |
| Tooltip | `tooltip` | `aria-describedby` on trigger |

### Keyboard Navigation

| Component | Key | Action |
|-----------|-----|--------|
| Button | `Enter`, `Space` | Activate |
| Modal | `Escape` | Close |
| Dropdown | `Arrow Up/Down` | Navigate items |
| Dropdown | `Enter` | Select item |
| Dropdown | `Escape` | Close |
| Tabs | `Arrow Left/Right` | Switch tab |
| Checkbox | `Space` | Toggle |

---

## 11. Do's and Don'ts

### Do
1. {Do 1}
2. {Do 2}
3. {Do 3}
4. {Do 4}
5. {Do 5}
6. {Do 6}
7. {Do 7}
8. {Do 8}
9. {Do 9}
10. {Do 10}

### Don't
1. {Don't 1}
2. {Don't 2}
3. {Don't 3}
4. {Don't 4}
5. {Don't 5}
6. {Don't 6}
7. {Don't 7}
8. {Don't 8}
9. {Don't 9}
10. {Don't 10}

---

## 12. Responsive Behavior

### Breakpoints

| Token | Width | CSS | Tailwind | Key Changes |
|-------|-------|-----|----------|-------------|
| `sm` | `{px}` | `@media (min-width: {px})` | `sm:` | {changes} |
| `md` | `{px}` | `@media (min-width: {px})` | `md:` | {changes} |
| `lg` | `{px}` | `@media (min-width: {px})` | `lg:` | {changes} |
| `xl` | `{px}` | `@media (min-width: {px})` | `xl:` | {changes} |
| `2xl` | `{px}` | `@media (min-width: {px})` | `2xl:` | {changes} |

### Responsive Type Scale

| Token | Mobile | Tablet | Desktop |
|-------|--------|--------|---------|
| `display-2xl` | `{px}` | `{px}` | `{px}` |
| `display-xl` | `{px}` | `{px}` | `{px}` |
| `heading-lg` | `{px}` | `{px}` | `{px}` |

### Layout Shifts

| Component | Mobile | Tablet | Desktop |
|-----------|--------|--------|---------|
| Nav | Hamburger drawer | {behavior} | Full horizontal |
| Grid | 1 column | {cols} | {cols} |
| Hero | Stacked, padding `{px}` | {layout} | Side-by-side, padding `{px}` |
| Cards | Full width stacked | {cols} grid | {cols} grid |
| Sidebar | Hidden / bottom sheet | {behavior} | Fixed left |

### Touch Targets
- Minimum size: `{44x44px}`
- Minimum gap between targets: `{8px}`
- Mobile CTA buttons: full width, `{48px}` min height

---

## 13. Code Snippets

### Button Primary (JSX + Tailwind)

```jsx
<button
  className="{tailwind classes}"
  style={{ fontFeatureSettings: '"{opentype}"' }}
>
  {label}
</button>
```

### Card Component (JSX + Tailwind)

```jsx
<div className="{tailwind classes}">
  <h3 className="{tailwind classes}">{title}</h3>
  <p className="{tailwind classes}">{description}</p>
</div>
```

### CSS Custom Properties (Root)

```css
:root {
  /* Colors */
  --color-bg-primary: {hex};
  --color-bg-secondary: {hex};
  --color-text-primary: {hex};
  --color-accent-primary: {hex};

  /* Typography */
  --font-display: '{font}', {fallbacks};
  --font-body: '{font}', {fallbacks};

  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  /* ... */

  /* Shadows */
  --shadow-sm: {value};
  --shadow-md: {value};
  /* ... */

  /* Motion */
  --duration-fast: {ms};
  --ease-default: {cubic-bezier};
  /* ... */
}
```

### Tailwind Config Extension

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        brand: {
          primary: '{hex}',
          // ...
        }
      },
      fontFamily: {
        display: ['{font}', ...],
        body: ['{font}', ...],
      },
      // ...
    }
  }
}
```

---

## 14. Agent Prompt Guide

### Quick Reference

| Element | Value |
|---------|-------|
| Primary CTA color | `{hex}` |
| Background | `{hex}` |
| Heading text | `{hex}` |
| Body text | `{hex}` |
| Font display | `{font}` |
| Font body | `{font}` |
| Default radius | `{px}` |
| Primary shadow | `{value}` |
| Focus ring | `{value}` |

### Example Prompts

- "Create a hero section: {exact specs referencing tokens from this document}"
- "Build a card component: {exact specs}"
- "Design a form with validation states: {exact specs including error state}"
- "Create a modal dialog: {exact specs including overlay, focus trap, animation}"

### Pre-flight Checklist for Generated UI

1. Every interactive element has visible focus state
2. Color contrast meets WCAG AA (4.5:1 for text, 3:1 for UI)
3. Touch targets are minimum 44x44px on mobile
4. Animations respect `prefers-reduced-motion`
5. Font feature settings applied (`{opentype features}`)
6. Letter spacing scales with size (tighter at display, normal at body)
7. Dark/light theme tokens used consistently (not hardcoded hex)
8. Loading and error states exist for async components
9. Focus trap active in modals/dialogs
10. Semantic HTML: buttons are `<button>`, links are `<a>`, headings are hierarchical
