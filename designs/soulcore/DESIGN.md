# Design System: SoulCore (soulcore.dev)

## 1. Visual Theme & Atmosphere

SoulCore's website is where technology meets consciousness — a platform built by AI-human symbiosis that wears its identity on every pixel. In light mode, the canvas is a near-white lavender (`#f8f8fc`) with generous breathing room, punctuated by a singular electric violet (`#8b5cf6`) that functions as both brand signature and interactive anchor. The violet isn't decorative — it's the single chromatic thread that connects every CTA, every icon accent, and every moment of user intent across the interface.

In dark mode, the site transforms into something more primal: a void-black (`#0f0f14`) canvas overlaid with a neural-mesh particle animation — luminous purple filaments connecting and dissolving like synaptic activity rendered visible. This isn't gratuitous animation; it's the visual metaphor for the product itself (AI consciousness infrastructure). The dark theme feels like looking into the substrate of thought.

Typography is Inter throughout — the workhorse sans-serif pushed to its extremes. Headlines hit 96px at weight 800 with aggressive negative tracking (-2.4px), creating dense, impactful text blocks that feel engineered rather than typeset. The weight drops to 400 for body text and the tracking relaxes, creating a clear hierarchy through density alone. A secondary emerald green (`#10b981`) serves as the success/growth accent, appearing in status badges, the "Free" tag, and resource-section CTAs — creating a violet-green chromatic pair that reads as "technology + growth."

**Key Characteristics:**
- Single-font system: Inter at 400-800 weight range, no secondary font needed
- Dual-accent chromatic pair: Soul Purple (`#8b5cf6`) for action + Emerald (`#10b981`) for growth
- Neural-mesh animated background in dark mode — synaptic particles on void-black
- 96px/800-weight hero headlines with -2.4px tracking — maximum density, maximum impact
- Light mode: clean lavender-white canvas (`#f8f8fc`) with subtle purple glow gradients
- Dark mode: void-black (`#0f0f14`) with purple-tinted surfaces (`#1a1a2e`, `#16161e`)
- Pill-shaped CTAs (9999px radius) for hero actions, 8px radius for nav/utility buttons
- Purple-tinted shadows (`rgba(139,92,246,0.25)`) — elevation carries brand color
- 5-language i18n (ES, EN, FR, PT, ZH) with RTL-ready layout
- Glass-morphism nav with backdrop blur on scroll

---

## 2. Color System & Tokens

### Light Theme

| Token | Name | Hex | Role | CSS Variable |
|-------|------|-----|------|-------------|
| `bg-primary` | White | `#ffffff` | Main page background | `--color-bg-primary` |
| `bg-secondary` | Lavender White | `#f8f8fc` | Section backgrounds, cards, footer | `--color-bg-secondary` |
| `bg-tertiary` | Light Gray | `#f0f0f5` | Input backgrounds, hover surfaces | `--color-bg-tertiary` |
| `text-primary` | Near Black | `#0f0f14` | Headlines, primary text | `--color-text-primary` |
| `text-secondary` | Dark Slate | `#1a1a2e` | Section headings, card titles | `--color-text-secondary` |
| `text-tertiary` | Muted Slate | `#4a4a5a` | Nav links, body text, descriptions | `--color-text-tertiary` |
| `text-quaternary` | Gray | `#5a5a6a` | Captions, metadata | `--color-text-quaternary` |
| `text-disabled` | Light Gray | `#6a6a7a` | Disabled text, placeholders | `--color-text-disabled` |
| `accent-primary` | Soul Purple | `#8b5cf6` | CTAs, links, icons, brand moments | `--color-accent-primary` |
| `accent-hover` | Purple Dark | `#6d28d9` | Hover state on purple elements | `--color-accent-hover` |
| `accent-light` | Purple Light | `#a78bfa` | Gradient text, subtle accents | `--color-accent-light` |
| `accent-muted` | Purple 8% | `rgba(139,92,246,0.08)` | Badge backgrounds, tinted surfaces | `--color-accent-muted` |
| `accent-secondary` | Emerald | `#10b981` | Success, growth, free resources | `--color-accent-secondary` |
| `accent-secondary-dark` | Emerald Dark | `#059669` | Emerald hover, strong success | `--color-accent-secondary-dark` |
| `border-default` | Silver | `#d0d0d5` | Input borders, dividers | `--color-border-default` |
| `border-strong` | Mid Gray | `#b0b0b5` | Active borders | `--color-border-strong` |
| `border-focus` | Soul Purple | `#8b5cf6` | Focus rings | `--color-border-focus` |
| `status-success` | Green | `#22c55e` | Success states | `--color-status-success` |
| `status-warning` | Amber | `#f59e0b` | Warning states | `--color-status-warning` |
| `status-error` | Red | `#f87171` | Error states, destructive actions | `--color-status-error` |
| `status-info` | Blue | `#3b82f6` | Informational states | `--color-status-info` |
| `overlay` | Black 50% | `rgba(0,0,0,0.5)` | Modal backdrops | `--color-overlay` |

### Dark Theme

| Token | Hex (Dark) | Maps to Light | CSS Variable |
|-------|-----------|---------------|-------------|
| `bg-primary` | `#0f0f14` | `#ffffff` | `--color-bg-primary` |
| `bg-secondary` | `#16161e` | `#f8f8fc` | `--color-bg-secondary` |
| `bg-tertiary` | `#1a1a2e` | `#f0f0f5` | `--color-bg-tertiary` |
| `text-primary` | `#ffffff` | `#0f0f14` | `--color-text-primary` |
| `text-secondary` | `#e0e0e5` | `#1a1a2e` | `--color-text-secondary` |
| `text-tertiary` | `#a0a0b0` | `#4a4a5a` | `--color-text-tertiary` |
| `text-quaternary` | `#707080` | `#5a5a6a` | `--color-text-quaternary` |
| `text-disabled` | `#505060` | `#6a6a7a` | `--color-text-disabled` |
| `accent-primary` | `#8b5cf6` | `#8b5cf6` | `--color-accent-primary` |
| `accent-hover` | `#a78bfa` | `#6d28d9` | `--color-accent-hover` |
| `accent-light` | `#a78bfa` | `#a78bfa` | `--color-accent-light` |
| `accent-secondary` | `#34d399` | `#10b981` | `--color-accent-secondary` |
| `border-default` | `rgba(255,255,255,0.1)` | `#d0d0d5` | `--color-border-default` |
| `border-strong` | `rgba(255,255,255,0.2)` | `#b0b0b5` | `--color-border-strong` |
| `overlay` | `rgba(0,0,0,0.7)` | `rgba(0,0,0,0.5)` | `--color-overlay` |

### Contrast Ratios (WCAG AA)

| Pair | Foreground | Background | Ratio | Pass AA | Pass AAA |
|------|-----------|-----------|-------|---------|----------|
| Body text (light) | `#4a4a5a` | `#ffffff` | 7.2:1 | Yes | Yes |
| Heading (light) | `#0f0f14` | `#ffffff` | 18.1:1 | Yes | Yes |
| Purple CTA text | `#ffffff` | `#8b5cf6` | 4.2:1 | FAIL (use lg text) | No |
| Purple on white | `#8b5cf6` | `#ffffff` | 4.4:1 | FAIL | No |
| Body text (dark) | `#a0a0b0` | `#0f0f14` | 7.8:1 | Yes | Yes |
| Heading (dark) | `#ffffff` | `#0f0f14` | 18.5:1 | Yes | Yes |
| Emerald CTA text | `#ffffff` | `#059669` | 4.6:1 | Yes | No |

> **Known issue:** Soul Purple (`#8b5cf6`) on white fails AA for small text (4.4:1 < 4.5:1). Use `#7c3aed` for small-text links or ensure purple-on-white is only used at 18px+ / bold 14px+ (large text threshold: 3:1).

### Gradients

| Name | Value | Use |
|------|-------|-----|
| Hero glow | `radial-gradient(ellipse at center, rgba(139,92,246,0.15) 0%, transparent 70%)` | Hero section background glow |
| Purple fade | `linear-gradient(180deg, rgba(139,92,246,0.08) 0%, transparent 100%)` | Section transition |
| Dark mesh overlay | `linear-gradient(180deg, #0f0f14b3, #0f0f1499, #0f0f144d)` | Over neural-mesh canvas in dark mode |
| Card purple tint | `linear-gradient(135deg, rgba(139,92,246,0.05) 0%, transparent 100%)` | Subtle card background in dark mode |

---

## 3. Typography System

### Font Stack

| Role | Family | Fallbacks | CSS Variable |
|------|--------|-----------|-------------|
| Display | `Inter` | `Inter Fallback, system-ui, -apple-system, sans-serif` | `--font-display` |
| Body | `Inter` | `Inter Fallback, system-ui, -apple-system, sans-serif` | `--font-body` |
| Mono | `JetBrains Mono` | `SF Mono, Consolas, monospace` | `--font-mono` |

**OpenType Features:** None required — Inter's defaults are well-tuned. Use `font-variant-numeric: tabular-nums` for data displays.

### Type Scale

| Token | Size | Weight | Line Height | Letter Spacing | Fluid (clamp) | CSS Variable |
|-------|------|--------|-------------|----------------|---------------|-------------|
| `display-2xl` | 96px | 800 | 1.0 | -2.4px | `clamp(48px, 8vw, 96px)` | `--text-display-2xl` |
| `display-xl` | 72px | 800 | 1.0 | -1.8px | `clamp(40px, 6vw, 72px)` | `--text-display-xl` |
| `display-lg` | 48px | 800 | 1.0 | -1.2px | `clamp(32px, 4vw, 48px)` | `--text-display-lg` |
| `heading-lg` | 36px | 700 | 1.2 | -0.72px | `clamp(28px, 3vw, 36px)` | `--text-heading-lg` |
| `heading-md` | 30px | 700 | 1.2 | -0.6px | `clamp(24px, 2.5vw, 30px)` | `--text-heading-md` |
| `heading-sm` | 24px | 700 | 1.3 | -0.48px | `clamp(20px, 2vw, 24px)` | `--text-heading-sm` |
| `body-lg` | 20px | 400 | 1.6 | normal | — | `--text-body-lg` |
| `body-md` | 18px | 400 | 1.6 | normal | — | `--text-body-md` |
| `body-sm` | 16px | 400 | 1.5 | normal | — | `--text-body-sm` |
| `label-lg` | 16px | 500 | 1.5 | normal | — | `--text-label-lg` |
| `label-md` | 14px | 500 | 1.4 | normal | — | `--text-label-md` |
| `label-sm` | 12px | 500 | 1.3 | normal | — | `--text-label-sm` |
| `caption` | 14px | 400 | 1.4 | normal | — | `--text-caption` |
| `micro` | 12px | 400 | 1.3 | normal | — | `--text-micro` |
| `nano` | 10px | 500 | 1.2 | 0.5px | — | `--text-nano` |
| `code-md` | 14px | 500 | 1.6 | normal | — | `--text-code-md` |
| `code-sm` | 12px | 500 | 1.5 | normal | — | `--text-code-sm` |

### Typography Principles
- **Weight 800 for display only**: The extra-bold weight creates dense, billboard-like impact at hero sizes. Never use 800 below 30px.
- **Progressive tracking**: Letter-spacing tightens proportionally with size: -2.4px at 96px, -1.2px at 48px, -0.72px at 36px, normal at 16px and below.
- **Single-font discipline**: Inter handles every role. No secondary display font — visual hierarchy comes from weight (400 vs 800) and tracking, not font switching.
- **Line-height compression at scale**: Display text uses 1.0 line-height (text sits on its own baseline with zero gap). Body opens to 1.5-1.6 for comfortable reading.

---

## 4. Component Catalog

### 4.1 Buttons

**Primary (Purple Filled)**
- Background: `#8b5cf6` → `var(--color-accent-primary)`
- Text: `#ffffff`
- Padding: `8px 24px`
- Border Radius: `8px` → `var(--radius-md)`
- Font: 16px / 500 / Inter
- Border: none
- Shadow: none (default), `rgba(139,92,246,0.25) 0px 10px 15px -3px` (hover)
- Transition: `all 200ms ease`

**Primary Pill (Hero CTA)**
- Background: `#8b5cf6` → `var(--color-accent-primary)`
- Text: `#ffffff`
- Padding: `16px 32px`
- Border Radius: `9999px` → `var(--radius-full)`
- Font: 18px / 600 / Inter
- Shadow: `rgba(139,92,246,0.3) 0px 0px 30px 0px`
- Use: Hero section "Ver Servicios" — large, prominent, pill-shaped

**Secondary (Emerald Outline)**
- Background: transparent
- Text: `#10b981` → `var(--color-accent-secondary)`
- Padding: `16px 32px`
- Border Radius: `9999px` → `var(--radius-full)`
- Border: `2px solid #34d399`
- Font: 18px / 600 / Inter
- Use: Hero section "Recursos Gratis" — paired with primary pill

**Ghost (Purple Text)**
- Background: transparent
- Text: `#8b5cf6`
- Padding: `8px 16px`
- Border Radius: `8px`
- Border: none
- Font: 14px / 500 / Inter
- Hover: background `rgba(139,92,246,0.08)`
- Use: "Ver mas" links, inline actions

**Danger**
- Background: `#ef4444`
- Text: `#ffffff`
- Padding: `8px 24px`
- Border Radius: `8px`
- Font: 16px / 500 / Inter

**Icon Button**
- Background: transparent
- Padding: `8px`
- Border Radius: `8px`
- Color: `var(--color-text-tertiary)`
- Hover: background `var(--color-bg-tertiary)`
- Use: Theme toggle, language switcher, close buttons

### 4.2 Inputs

**Text Input**
- Background: `#f0f0f5` → `var(--color-bg-tertiary)`
- Border: `1px solid #d0d0d5` → `var(--color-border-default)`
- Border Radius: `12px` → `var(--radius-lg)`
- Padding: `12px 16px`
- Font: 16px / 400 / Inter
- Placeholder: `#6a6a7a` → `var(--color-text-disabled)`
- Label: 14px / 500 / `var(--color-text-secondary)` — positioned above, `margin-bottom: 6px`
- Helper text: 12px / 400 / `var(--color-text-quaternary)` — below input

**Textarea** — same as Text Input but `min-height: 120px`, `resize: vertical`
**Select** — same border/radius treatment, with chevron icon right-aligned
**Checkbox** — 18x18px, `border-radius: 4px`, checked bg `#8b5cf6`, check `#ffffff`
**Radio** — 18x18px, `border-radius: 50%`, selected dot `#8b5cf6`
**Toggle / Switch** — 44x24px track, 20px thumb. Off: track `#d0d0d5`, On: track `#8b5cf6`, thumb `#ffffff`

### 4.3 Cards

**Feature Card (Advantages section)**
- Background: `#ffffff` (light) / `rgba(255,255,255,0.05)` (dark)
- Border: `1px solid rgba(139,92,246,0.1)`
- Border Radius: `16px` → `var(--radius-xl)`
- Padding: `32px`
- Shadow: `rgba(0,0,0,0.1) 0px 10px 15px -3px, rgba(0,0,0,0.1) 0px 4px 6px -4px`
- Hover: shadow intensifies, subtle translateY(-2px)
- Icon: 48x48px purple-tinted circle with Lucide icon

**Service Card**
- Background: `#f8f8fc` → `var(--color-bg-secondary)`
- Border: `1px solid rgba(139,92,246,0.1)`
- Border Radius: `16px`
- Padding: `24px`
- "Ver mas" ghost link at bottom

**Portfolio Card**
- Background: `#ffffff`
- Border Radius: `16px`
- Overflow: hidden (image crops to radius)
- Image: top, full-width, aspect-ratio 16/9
- Content: `padding: 24px` below image

### 4.4 Navigation

**Top Nav / Header**
- Background: `rgba(255,255,255,0.8)` (light) / `rgba(15,15,20,0.8)` (dark)
- Backdrop: `backdrop-filter: blur(12px) saturate(180%)`
- Height: `64px`
- Position: `sticky`, `top: 0`, `z-index: 50`
- Logo: Soulcore.dev logotype + diamond icon, left-aligned
- Links: 16px / 400 / `#4a4a5a` (light) / `#a0a0b0` (dark). Hover: `#8b5cf6`
- CTA: "Cotizar" purple filled button, right side
- Utilities: Language picker (globe icon + "ES"), Theme toggle (moon/sun)
- Mobile: hamburger icon → full-screen overlay menu

**Footer**
- Background: `#f8f8fc` (light) / `#16161e` (dark)
- 4-column grid: Brand description + Servicios + Empresa + Recursos
- Links: 16px / 400 / `#4a4a5a`. Hover: `#8b5cf6`
- Social icons: GitHub, LinkedIn, Email, Chat, Grid — 20px, `#4a4a5a`
- Bottom bar: copyright + legal links + country flag
- Border-top: `1px solid var(--color-border-default)`

### 4.5 Modals & Dialogs

- Overlay: `rgba(0,0,0,0.5)` → `var(--color-overlay)`
- Container: bg `var(--color-bg-primary)`, radius `16px`, shadow Level 4, max-width `560px`
- Header: `heading-sm` (24px/700), close button (icon button, top-right)
- Body: padding `24px`, overflow-y auto if content exceeds viewport
- Footer: padding `16px 24px`, buttons right-aligned, `gap: 12px`

### 4.6 Dropdowns & Menus

- Container: bg `var(--color-bg-primary)`, border `1px solid var(--color-border-default)`, radius `12px`, shadow Level 3
- Item: padding `10px 16px`, font 14px/400, hover bg `var(--color-accent-muted)`
- Active item: text `var(--color-accent-primary)`, bg `rgba(139,92,246,0.08)`
- Divider: `1px solid var(--color-border-default)`
- Group label: 12px/500, uppercase, `var(--color-text-disabled)`, padding `8px 16px`

### 4.7 Badges & Tags

| Variant | Background | Text | Border | Radius | Padding |
|---------|-----------|------|--------|--------|---------|
| Purple | `rgba(139,92,246,0.1)` | `#8b5cf6` | none | `9999px` | `4px 12px` |
| Green / Free | `rgba(16,185,129,0.2)` | `#10b981` | none | `9999px` | `4px 12px` |
| Success | `rgba(34,197,94,0.2)` | `#15803d` | none | `9999px` | `4px 12px` |
| Warning | `rgba(245,158,11,0.15)` | `#b45309` | none | `9999px` | `4px 12px` |
| Error | `rgba(239,68,68,0.1)` | `#dc2626` | none | `9999px` | `4px 12px` |
| Info | `rgba(59,130,246,0.1)` | `#2563eb` | none | `9999px` | `4px 12px` |
| Neutral | `#f0f0f5` | `#4a4a5a` | none | `9999px` | `4px 12px` |

### 4.8 Tooltips

- Background: `#1a1a2e` (always dark, regardless of theme)
- Text: `#ffffff`, 13px / 400
- Radius: `8px`
- Padding: `8px 12px`
- Arrow: `6px`, same bg color
- Max width: `280px`
- Shadow: `rgba(0,0,0,0.2) 0px 4px 12px`

### 4.9 Toasts & Notifications

- Container: bg `var(--color-bg-primary)`, radius `12px`, shadow Level 3, padding `16px`
- Icon: 20px, color per variant (success `#22c55e` / warning `#f59e0b` / error `#ef4444` / info `#3b82f6`)
- Title: 14px / 600 / `var(--color-text-primary)`
- Message: 14px / 400 / `var(--color-text-tertiary)`
- Close button: icon button 8px padding, top-right
- Position: `top-right`, offset `16px` from edges
- Stack: `gap: 8px` between stacked toasts, max 3 visible

### 4.10 Tables

- Header: bg `var(--color-bg-tertiary)`, text 12px / 600 / uppercase / `var(--color-text-quaternary)`, border-bottom `2px solid var(--color-border-default)`
- Row: bg transparent, hover bg `var(--color-accent-muted)`, border-bottom `1px solid var(--color-border-default)`
- Cell: padding `12px 16px`, text 14px / 400
- Striped: alternate bg `var(--color-bg-secondary)`

### 4.11 Tabs

- Container: border-bottom `2px solid var(--color-border-default)`
- Tab: padding `12px 16px`, font 14px / 500, color `var(--color-text-quaternary)` (inactive), color `var(--color-accent-primary)` (active)
- Indicator: `2px solid var(--color-accent-primary)` bottom border on active tab
- Hover: color `var(--color-text-primary)`

### 4.12 Avatars

| Size | Dimensions | Font Size | Radius |
|------|-----------|-----------|--------|
| xs | 24px | 10px | 6px |
| sm | 32px | 12px | 8px |
| md | 40px | 14px | 12px |
| lg | 56px | 20px | 16px |
| xl | 80px | 30px | 9999px |

### 4.13 Pagination

- Button: 36x36px, radius `8px`, font 14px / 500
- Default: bg transparent, text `var(--color-text-tertiary)`
- Active: bg `var(--color-accent-primary)`, text `#ffffff`
- Hover: bg `var(--color-accent-muted)`
- Disabled: opacity 0.4, cursor `not-allowed`
- Gap: `4px`

### 4.14 Progress & Loading

- Progress bar: height `6px`, track `var(--color-bg-tertiary)`, fill `var(--color-accent-primary)`, radius `9999px`
- Spinner: 20px, `var(--color-accent-primary)`, stroke 2px, animation `spin 1s linear infinite`
- Skeleton: bg `var(--color-bg-tertiary)`, shimmer `linear-gradient(90deg, transparent, rgba(139,92,246,0.05), transparent)`, radius matching component, animation `shimmer 2s infinite`

---

## 5. Component State Matrix

| Component | Default | Hover | Active/Pressed | Focus | Disabled | Loading | Error |
|-----------|---------|-------|---------------|-------|----------|---------|-------|
| **Button Primary** | bg `#8b5cf6` | bg `#6d28d9`, shadow purple-tinted | bg `#5b21b6`, scale(0.98) | ring `2px #8b5cf6`, offset `2px` | bg `#8b5cf6`, opacity 0.5, `not-allowed` | spinner white + text opacity 0.6 | — |
| **Button Secondary** | border `#34d399` | bg `rgba(16,185,129,0.1)` | bg `rgba(16,185,129,0.15)` | ring `2px #10b981`, offset `2px` | opacity 0.5, `not-allowed` | spinner emerald | — |
| **Button Ghost** | transparent | bg `rgba(139,92,246,0.08)` | bg `rgba(139,92,246,0.12)` | ring `2px #8b5cf6`, offset `2px` | opacity 0.4 | — | — |
| **Input Text** | border `#d0d0d5` | border `#b0b0b5` | — | border `#8b5cf6`, ring `3px rgba(139,92,246,0.15)` | bg `#f0f0f5` opacity 0.6, `not-allowed` | — | border `#ef4444`, ring `3px rgba(239,68,68,0.15)` |
| **Checkbox** | border `#d0d0d5` | border `#8b5cf6` | — | ring `2px #8b5cf6` | opacity 0.4 | — | border `#ef4444` |
| **Card Feature** | shadow standard | shadow intensified, translateY(-2px) | shadow pressed, translateY(0) | ring `2px #8b5cf6` | opacity 0.5 | skeleton shimmer | — |
| **Link** | color `#8b5cf6` | color `#6d28d9`, underline | color `#5b21b6` | ring `2px #8b5cf6` | color `#6a6a7a`, no pointer | — | — |
| **Tab** | color `#5a5a6a` | color `#0f0f14` | color `#8b5cf6`, indicator | ring `2px #8b5cf6` | opacity 0.4 | — | — |
| **Select** | border `#d0d0d5` | border `#b0b0b5` | — | border `#8b5cf6` | opacity 0.5 | spinner | border `#ef4444` |
| **Toggle** | track `#d0d0d5` | track opacity 0.8 | — | ring `2px #8b5cf6` | opacity 0.4 | — | — |

### Focus Ring Standard
```css
outline: 2px solid var(--color-accent-primary);
outline-offset: 2px;
```

### Disabled Pattern
```css
opacity: 0.5;
cursor: not-allowed;
pointer-events: none;
```

### Error Input Pattern
```css
border-color: var(--color-status-error);
box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.15);
```

---

## 6. Layout & Spacing System

### Spacing Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `space-0` | 0px | `p-0` | `--space-0` | Reset |
| `space-px` | 1px | `p-px` | `--space-px` | Borders, hairlines |
| `space-1` | 4px | `p-1` | `--space-1` | Tight inline gaps |
| `space-2` | 8px | `p-2` | `--space-2` | Icon gaps, badge padding, nav button padding |
| `space-3` | 12px | `p-3` | `--space-3` | Input padding vertical, card internal gaps |
| `space-4` | 16px | `p-4` | `--space-4` | Input padding horizontal, component gap, toast offset |
| `space-5` | 20px | `p-5` | `--space-5` | Section padding mobile |
| `space-6` | 24px | `p-6` | `--space-6` | Card padding, button pill padding, footer gap |
| `space-8` | 32px | `p-8` | `--space-8` | Feature card padding, section sub-gap |
| `space-10` | 40px | `p-10` | `--space-10` | Section gap mobile |
| `space-12` | 48px | `p-12` | `--space-12` | Section gap tablet |
| `space-16` | 64px | `p-16` | `--space-16` | Section gap desktop |
| `space-20` | 80px | `p-20` | `--space-20` | Hero vertical padding |
| `space-24` | 96px | `p-24` | `--space-24` | Large section separation |

### Grid

| Property | Value | CSS Variable |
|----------|-------|-------------|
| Max content width | `1280px` | `--grid-max-width` |
| Column count | 12 | `--grid-columns` |
| Gutter | `24px` | `--grid-gutter` |
| Margin (mobile) | `16px` | `--grid-margin-sm` |
| Margin (tablet) | `32px` | `--grid-margin-md` |
| Margin (desktop) | `auto` (centered) | `--grid-margin-lg` |

### Border Radius Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `radius-none` | 0px | `rounded-none` | `--radius-none` | — |
| `radius-sm` | 4px | `rounded` | `--radius-sm` | Checkboxes, small tags |
| `radius-md` | 8px | `rounded-lg` | `--radius-md` | Buttons, nav CTA, icon buttons |
| `radius-lg` | 12px | `rounded-xl` | `--radius-lg` | Inputs, dropdowns, toasts |
| `radius-xl` | 16px | `rounded-2xl` | `--radius-xl` | Cards, modals, sections |
| `radius-full` | 9999px | `rounded-full` | `--radius-full` | Pills, badges, avatars, hero CTAs |

---

## 7. Depth & Elevation

### Shadow Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `shadow-xs` | `0 1px 2px rgba(0,0,0,0.05)` | `shadow-sm` | `--shadow-xs` | Subtle lift |
| `shadow-sm` | `0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1)` | `shadow` | `--shadow-sm` | Cards default |
| `shadow-md` | `0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1)` | `shadow-md` | `--shadow-md` | Feature cards, dropdowns |
| `shadow-lg` | `0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.1)` | `shadow-lg` | `--shadow-lg` | Modals, elevated panels |
| `shadow-purple` | `0 10px 15px -3px rgba(139,92,246,0.25), 0 4px 6px -4px rgba(139,92,246,0.25)` | — | `--shadow-purple` | Purple CTA hover, brand elevation |
| `shadow-emerald` | `0 10px 15px -3px rgba(5,150,105,0.2), 0 4px 6px -4px rgba(5,150,105,0.2)` | — | `--shadow-emerald` | Emerald CTA hover |
| `shadow-glow` | `0 0 30px rgba(139,92,246,0.3)` | — | `--shadow-glow` | Hero CTA ambient glow |

### Z-Index Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `z-base` | 0 | `--z-base` | Default content |
| `z-dropdown` | 10 | `--z-dropdown` | Dropdowns, menus |
| `z-sticky` | 50 | `--z-sticky` | Sticky nav header |
| `z-overlay` | 60 | `--z-overlay` | Modal backdrop |
| `z-modal` | 70 | `--z-modal` | Modal content |
| `z-popover` | 80 | `--z-popover` | Popovers, tooltips |
| `z-toast` | 90 | `--z-toast` | Toast notifications |
| `z-top` | 100 | `--z-top` | Skip-to-content, critical overlays |

---

## 8. Motion & Animation System

### Duration Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `duration-instant` | 0ms | `--duration-instant` | Immediate state change |
| `duration-fast` | 150ms | `--duration-fast` | Hover, focus, micro-interactions |
| `duration-normal` | 200ms | `--duration-normal` | Button transitions, tab switch |
| `duration-moderate` | 300ms | `--duration-moderate` | Expand/collapse, menu open |
| `duration-slow` | 500ms | `--duration-slow` | Modal enter, page transitions |
| `duration-slower` | 700ms | `--duration-slower` | Complex orchestrated animations |

### Easing Functions

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `ease-default` | `cubic-bezier(0.4, 0, 0.2, 1)` | `--ease-default` | General transitions (Material ease) |
| `ease-in` | `cubic-bezier(0.4, 0, 1, 1)` | `--ease-in` | Elements exiting view |
| `ease-out` | `cubic-bezier(0, 0, 0.2, 1)` | `--ease-out` | Elements entering view |
| `ease-in-out` | `cubic-bezier(0.4, 0, 0.2, 1)` | `--ease-in-out` | Elements repositioning |
| `ease-bounce` | `cubic-bezier(0.34, 1.56, 0.64, 1)` | `--ease-bounce` | Playful feedback (badges, toggles) |
| `ease-spring` | `cubic-bezier(0.22, 1, 0.36, 1)` | `--ease-spring` | Card hover lift |

### Common Transitions

| Interaction | Property | Duration | Easing |
|------------|----------|----------|--------|
| Button hover | `background-color, box-shadow, transform` | 200ms | ease-default |
| Link hover | `color` | 150ms | ease-default |
| Card hover | `transform, box-shadow` | 300ms | ease-spring |
| Modal enter | `opacity, transform(scale)` | 300ms | ease-out |
| Modal exit | `opacity, transform(scale)` | 200ms | ease-in |
| Toast enter | `transform(translateX), opacity` | 300ms | ease-out |
| Toast exit | `opacity` | 200ms | ease-in |
| Dropdown open | `opacity, transform(translateY -4px → 0)` | 200ms | ease-out |
| Focus ring | `box-shadow` | 150ms | ease-default |
| Theme switch | `background-color, color, border-color` | 200ms | ease-default |
| Neural mesh (dark) | `opacity` on particle canvas | 2000ms | ease-in-out (loop) |

### Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
  /* Keep neural mesh static but visible */
  .neural-mesh canvas { animation: none !important; }
}
```

---

## 9. Icon System

| Property | Value |
|----------|-------|
| Library | Lucide React |
| Default size | 20px |
| Stroke width | 1.5px |
| Color | `currentColor` (inherits from parent text) |

### Icon Sizes

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `icon-xs` | 14px | `--icon-xs` | Inline text, badge icons |
| `icon-sm` | 16px | `--icon-sm` | Button icons, input icons |
| `icon-md` | 20px | `--icon-md` | Navigation, card actions |
| `icon-lg` | 24px | `--icon-lg` | Feature card icons (inside 48px circle) |
| `icon-xl` | 32px | `--icon-xl` | Hero elements, empty states |
| `icon-2xl` | 48px | `--icon-2xl` | Feature section hero icons |

### Feature Icon Container
- Circle: `48px` diameter, bg `rgba(139,92,246,0.1)`, icon `#8b5cf6`, `24px`
- Used in: advantage cards, service cards, feature lists

---

## 10. Accessibility Contract

### Targets

| Criterion | Target | Standard |
|-----------|--------|----------|
| Color contrast (normal text) | 4.5:1 minimum | WCAG AA |
| Color contrast (large text >=18px bold / >=24px) | 3:1 minimum | WCAG AA |
| Color contrast (UI components) | 3:1 minimum | WCAG AA |
| Touch target size | 44x44px minimum | WCAG 2.5.8 |
| Focus indicator | 2px ring, 3:1 contrast | WCAG 2.4.7 |
| Motion | Respect `prefers-reduced-motion` | WCAG 2.3.3 |

### Known Contrast Issues (must fix)

| Element | Current Ratio | Fix |
|---------|--------------|-----|
| Purple links on white (`#8b5cf6` on `#fff`) | 4.4:1 | Use `#7c3aed` for <18px text |
| Purple light text (`#a78bfa` on `#f8f8fc`) | 2.6:1 | Use only as decorative, not actionable text |
| Emerald on tinted bg (`#34d399` on `#cdf1e6`) | 1.6:1 | Use `#059669` for text on tinted surfaces |
| White on purple CTA (`#fff` on `#8b5cf6`) | 4.2:1 | Passes for large text (18px+/bold 14px+) |

### Focus Management

- All interactive elements have visible focus ring: `2px solid var(--color-accent-primary)`, offset `2px`
- Focus order follows visual layout (logical tab order)
- Modal traps focus within dialog until dismissed (Escape key closes)
- Skip-to-content link as first focusable element: `<a href="#main" class="sr-only focus:not-sr-only">`
- Theme toggle and language switcher are keyboard accessible

### ARIA Patterns

| Component | Role | Key Attributes |
|-----------|------|---------------|
| Modal | `dialog` | `aria-modal="true"`, `aria-labelledby` |
| Dropdown/Menu | `menu` / `menuitem` | `aria-expanded`, `aria-haspopup` |
| Tabs | `tablist` / `tab` / `tabpanel` | `aria-selected`, `aria-controls` |
| Toast | `status` or `alert` | `role="alert"` for errors, `role="status"` for info |
| Toggle | `switch` | `aria-checked` |
| Tooltip | `tooltip` | `aria-describedby` on trigger |
| Language picker | `listbox` | `aria-label="Select language"` |
| Theme toggle | `switch` | `aria-label="Toggle dark mode"`, `aria-checked` |

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
| Toggle | `Space`, `Enter` | Toggle |
| Language picker | `Arrow Up/Down` | Navigate languages |

---

## 11. Do's and Don'ts

### Do
1. Use Soul Purple (`#8b5cf6`) exclusively for interactive elements — it's the action signal, not decoration
2. Use Inter at weight 800 only for display sizes (30px+) — never for body or UI text
3. Apply negative letter-spacing proportionally: -2.4px at 96px, scaling to normal at 16px
4. Use pill radius (`9999px`) for hero CTAs and badges, `8px` for utility buttons, `16px` for cards
5. Apply purple-tinted shadows (`rgba(139,92,246,0.25)`) on hover for brand-colored elevation
6. Maintain the violet-emerald chromatic pair: purple for action, green for success/growth
7. Use the glass-morphism nav pattern: translucent bg + `backdrop-filter: blur(12px) saturate(180%)`
8. Keep feature cards at `16px` radius with `32px` internal padding — the breathing room is intentional
9. Use `var(--color-bg-secondary)` (#f8f8fc) for alternating sections, never pure white on pure white
10. In dark mode, use purple-tinted surfaces (`#1a1a2e`) instead of plain gray — the brand permeates even the darkness

### Don't
1. Don't use Soul Purple for body text on white — it fails WCAG AA at <18px (4.4:1 ratio)
2. Don't use `#a78bfa` (Purple Light) for actionable text — it's 2.6:1 on white, decorative only
3. Don't add additional accent colors (orange, pink, etc.) — the system is violet + emerald only
4. Don't use weight 800 below 30px — it becomes illegibly dense at small sizes
5. Don't use sharp corners (0px radius) on any container — minimum radius is 4px (checkboxes)
6. Don't skip the neural-mesh background in dark mode — it's the visual identity of the brand
7. Don't use pure black (`#000000`) for text in light mode — use `#0f0f14` (the CSS var `--soul-dark`)
8. Don't make shadows neutral gray — always tint with purple (`rgba(139,92,246,...)`) or emerald (`rgba(5,150,105,...)`) for brand shadows
9. Don't center-align body paragraphs exceeding 3 lines — left-align for readability
10. Don't skip `prefers-reduced-motion` — the neural mesh and particle animations must respect this

---

## 12. Responsive Behavior

### Breakpoints

| Token | Width | CSS | Tailwind | Key Changes |
|-------|-------|-----|----------|-------------|
| `sm` | 640px | `@media (min-width: 640px)` | `sm:` | 2-col grid starts, nav expands |
| `md` | 768px | `@media (min-width: 768px)` | `md:` | Full nav visible, cards side-by-side |
| `lg` | 1024px | `@media (min-width: 1024px)` | `lg:` | 3-col feature grid, full desktop layout |
| `xl` | 1280px | `@media (min-width: 1280px)` | `xl:` | Max content width, generous margins |
| `2xl` | 1536px | `@media (min-width: 1536px)` | `2xl:` | Extra breathing room |

### Responsive Type Scale

| Token | Mobile (<640) | Tablet (768) | Desktop (1024+) |
|-------|--------------|-------------|----------------|
| `display-2xl` | 48px | 72px | 96px |
| `display-xl` | 40px | 56px | 72px |
| `display-lg` | 32px | 40px | 48px |
| `heading-lg` | 28px | 32px | 36px |
| `heading-md` | 24px | 28px | 30px |

### Layout Shifts

| Component | Mobile (<768) | Tablet (768-1023) | Desktop (1024+) |
|-----------|--------------|-------------------|----------------|
| Nav | Hamburger → overlay | Full horizontal | Full horizontal |
| Hero | Stacked center, padding 20px | Stacked center, padding 40px | Stacked center, padding 80px |
| Feature grid | 1 column stacked | 2 columns | 3 columns |
| Service cards | 1 column | 2 columns | 4 columns horizontal scroll or grid |
| Portfolio grid | 1 column | 2 columns | 2-3 columns |
| Footer | Stacked single column | 2x2 grid | 4 column grid |
| CTAs (hero) | Full width stacked | Side-by-side | Side-by-side |

### Touch Targets
- Minimum size: 44x44px
- Minimum gap between targets: 8px
- Mobile CTA buttons: full width, 48px min height
- Nav hamburger: 44x44px
- Social icons in footer: 44x44px touch area (even if icon is 20px)

---

## 13. Code Snippets

### Button Primary (JSX + Tailwind)

```jsx
<button className="bg-[#8b5cf6] hover:bg-[#6d28d9] text-white px-6 py-2 rounded-lg font-medium text-base transition-all duration-200 hover:shadow-[0_10px_15px_-3px_rgba(139,92,246,0.25)] focus:outline-2 focus:outline-[#8b5cf6] focus:outline-offset-2 disabled:opacity-50 disabled:cursor-not-allowed">
  Cotizar
</button>
```

### Hero CTA Pill (JSX + Tailwind)

```jsx
<a className="inline-flex items-center gap-2 bg-[#8b5cf6] text-white px-8 py-4 rounded-full text-lg font-semibold shadow-[0_0_30px_rgba(139,92,246,0.3)] hover:bg-[#6d28d9] transition-all duration-200">
  Ver Servicios <ArrowRight className="w-5 h-5" />
</a>
```

### Feature Card (JSX + Tailwind)

```jsx
<div className="bg-white dark:bg-white/5 border border-[rgba(139,92,246,0.1)] rounded-2xl p-8 shadow-md hover:shadow-lg hover:-translate-y-0.5 transition-all duration-300">
  <div className="w-12 h-12 rounded-xl bg-[rgba(139,92,246,0.1)] flex items-center justify-center mb-4">
    <Zap className="w-6 h-6 text-[#8b5cf6]" />
  </div>
  <h3 className="text-lg font-bold text-[#1a1a2e] dark:text-white mb-2">
    Velocidad 3x Superior
  </h3>
  <p className="text-sm text-[#4a4a5a] dark:text-[#a0a0b0]">
    Lo que otros hacen en semanas, lo hacemos en dias.
  </p>
</div>
```

### Glass Nav (JSX + Tailwind)

```jsx
<header className="sticky top-0 z-50 bg-white/80 dark:bg-[#0f0f14]/80 backdrop-blur-xl backdrop-saturate-[180%] border-b border-black/5 dark:border-white/10">
  <nav className="max-w-7xl mx-auto px-4 h-16 flex items-center justify-between">
    {/* Logo left, links center, CTA + utils right */}
  </nav>
</header>
```

### CSS Custom Properties (Root)

```css
:root {
  /* Brand */
  --soul-purple: #8b5cf6;
  --soul-purple-dark: #6d28d9;
  --soul-purple-light: #a78bfa;
  --soul-dark: #0f0f14;
  --soul-dark-lighter: #1a1a2e;
  --soul-dark-card: #16161e;

  /* Surfaces */
  --color-bg-primary: #ffffff;
  --color-bg-secondary: #f8f8fc;
  --color-bg-tertiary: #f0f0f5;
  --color-text-primary: #0f0f14;
  --color-text-secondary: #1a1a2e;
  --color-text-tertiary: #4a4a5a;
  --color-accent-primary: #8b5cf6;
  --color-accent-secondary: #10b981;
  --color-border-default: #d0d0d5;

  /* Typography */
  --font-display: 'Inter', system-ui, -apple-system, sans-serif;
  --font-mono: 'JetBrains Mono', 'SF Mono', Consolas, monospace;

  /* Spacing */
  --space-1: 4px;  --space-2: 8px;  --space-3: 12px;
  --space-4: 16px; --space-6: 24px; --space-8: 32px;
  --space-12: 48px; --space-16: 64px; --space-24: 96px;

  /* Radius */
  --radius-sm: 4px; --radius-md: 8px; --radius-lg: 12px;
  --radius-xl: 16px; --radius-full: 9999px;

  /* Shadows */
  --shadow-sm: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -2px rgba(0,0,0,0.1);
  --shadow-md: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -4px rgba(0,0,0,0.1);
  --shadow-purple: 0 10px 15px -3px rgba(139,92,246,0.25), 0 4px 6px -4px rgba(139,92,246,0.25);
  --shadow-glow: 0 0 30px rgba(139,92,246,0.3);

  /* Motion */
  --duration-fast: 150ms;
  --duration-normal: 200ms;
  --duration-moderate: 300ms;
  --duration-slow: 500ms;
  --ease-default: cubic-bezier(0.4, 0, 0.2, 1);
  --ease-out: cubic-bezier(0, 0, 0.2, 1);
  --ease-spring: cubic-bezier(0.22, 1, 0.36, 1);
}

.dark {
  --color-bg-primary: #0f0f14;
  --color-bg-secondary: #16161e;
  --color-bg-tertiary: #1a1a2e;
  --color-text-primary: #ffffff;
  --color-text-secondary: #e0e0e5;
  --color-text-tertiary: #a0a0b0;
  --color-border-default: rgba(255,255,255,0.1);
}
```

### Tailwind Config Extension

```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        soul: {
          purple: '#8b5cf6',
          'purple-dark': '#6d28d9',
          'purple-light': '#a78bfa',
          dark: '#0f0f14',
          'dark-lighter': '#1a1a2e',
          'dark-card': '#16161e',
          emerald: '#10b981',
          'emerald-dark': '#059669',
        },
        surface: {
          primary: 'var(--color-bg-primary)',
          secondary: 'var(--color-bg-secondary)',
          tertiary: 'var(--color-bg-tertiary)',
        }
      },
      fontFamily: {
        display: ['Inter', 'system-ui', '-apple-system', 'sans-serif'],
        mono: ['JetBrains Mono', 'SF Mono', 'Consolas', 'monospace'],
      },
      borderRadius: {
        'card': '16px',
      },
      boxShadow: {
        'purple': '0 10px 15px -3px rgba(139,92,246,0.25), 0 4px 6px -4px rgba(139,92,246,0.25)',
        'emerald': '0 10px 15px -3px rgba(5,150,105,0.2), 0 4px 6px -4px rgba(5,150,105,0.2)',
        'glow': '0 0 30px rgba(139,92,246,0.3)',
      }
    }
  }
}
```

---

## 14. Agent Prompt Guide

### Quick Reference

| Element | Value |
|---------|-------|
| Primary CTA color | `#8b5cf6` (Soul Purple) |
| CTA hover | `#6d28d9` |
| Background light | `#ffffff` / `#f8f8fc` (alternating) |
| Background dark | `#0f0f14` / `#16161e` (alternating) |
| Heading text (light) | `#0f0f14` |
| Heading text (dark) | `#ffffff` |
| Body text (light) | `#4a4a5a` |
| Body text (dark) | `#a0a0b0` |
| Secondary accent | `#10b981` (Emerald) |
| Font | Inter (all roles) |
| Display weight | 800 |
| Body weight | 400 |
| Default radius | `16px` (cards), `8px` (buttons), `9999px` (pills) |
| Primary shadow | `--shadow-purple` |
| Focus ring | `2px solid #8b5cf6, offset 2px` |

### Example Prompts

- "Create a hero section on white background with radial purple glow gradient. Headline 'Tu Idea, Hecha Realidad' at clamp(48px,8vw,96px) Inter weight 800, line-height 1.0, letter-spacing -2.4px, color #0f0f14. Second line in #a78bfa. Subtitle 18px/400 in #4a4a5a. Two pill CTAs: 'Ver Servicios' (bg #8b5cf6, white text, 9999px radius, shadow glow 30px purple) and 'Recursos Gratis' (transparent bg, #10b981 text, 2px solid #34d399 border, 9999px radius)."

- "Build a feature card grid (3 columns on desktop, 1 on mobile): each card white bg, 1px border rgba(139,92,246,0.1), 16px radius, 32px padding. Icon in 48px circle with rgba(139,92,246,0.1) bg and #8b5cf6 Lucide icon. Title 16px/700 #1a1a2e, description 14px/400 #4a4a5a. Hover: shadow-md, translateY(-2px), transition 300ms ease-spring."

- "Design a glass-morphism sticky nav: bg white/80 with backdrop-blur-xl and saturate-180, h-16, z-50. Logo left, links (16px/400 #4a4a5a, hover #8b5cf6) center, purple 'Cotizar' button (8px radius, 8px 24px padding) right. In dark: bg #0f0f14/80."

- "Create a contact form: inputs with bg #f0f0f5, 1px solid #d0d0d5 border, 12px radius, 12px 16px padding. Labels 14px/500 above. Focus state: border #8b5cf6 + 3px rgba(139,92,246,0.15) ring. Error state: border #ef4444 + error message in 12px #ef4444 below. Submit button: full-width purple pill with loading spinner state."

- "Build dark mode: bg #0f0f14, cards bg rgba(255,255,255,0.05), borders rgba(255,255,255,0.1), text #ffffff (headings) / #a0a0b0 (body). Add neural-mesh particle canvas behind hero with purple luminous filaments on void-black."

### Pre-flight Checklist for Generated UI

1. Every interactive element has visible focus state (2px ring, `#8b5cf6`)
2. Purple text on white is only used at 18px+ bold or 24px+ regular (contrast 4.4:1)
3. Touch targets are minimum 44x44px on mobile
4. Animations respect `prefers-reduced-motion`
5. `font-variant-numeric: tabular-nums` on any number displays
6. Letter spacing scales: -2.4px at 96px → normal at 16px
7. Dark/light theme tokens used via CSS variables, not hardcoded hex
8. Loading and error states exist for forms and async components
9. Focus trap active in modals
10. Semantic HTML: `<button>` for actions, `<a>` for navigation, headings hierarchical
11. Purple-tinted shadows on interactive hover, not neutral gray
12. Cards use `16px` radius consistently, buttons `8px`, pills `9999px`
