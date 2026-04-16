# Design System: Vercel (vercel.com)

## 1. Visual Theme & Atmosphere

Vercel's visual identity is the most radical simplicity in developer tooling: pure black on pure white, or pure white on pure black. There is no brand color in the traditional sense — the "brand" IS the chromatic axis itself. The light mode canvas is `#ffffff` with foreground `#000000`. The dark mode (which is Vercel's primary mode and the one most developers encounter) inverts exactly: `#000000` canvas, `#fafafa` foreground. That asymmetry — `#fafafa` instead of pure white in dark mode — is intentional; it eliminates the harshness of maximum contrast while preserving the black-and-white identity.

The 12-step gray scale is Vercel's design workhorse. Unlike most systems that use 6-8 grays, Vercel's full 12-step scale (`#fafafa` through `#171717`) provides granular control over surface, border, and text hierarchy. Every distinction in the interface — a card from its background, a disabled from an active state, a divider from a container wall — is expressed through a precise gray value rather than a shadow. Borders do the work of shadows here. This is a philosophical statement about interface density and clarity: depth through structure, not atmospherics.

Accent blue (`#0070f3`) appears sparingly and purposefully. It is the single chromatic event in an otherwise monochrome world — every link, every focus ring, every primary interactive CTA. Because blue appears so rarely, it carries enormous signal weight. The decorative gradient (`linear-gradient(90deg, #ff0080, #7928ca, #0070f3, #00dfd8)`) is reserved for rare hero moments — product launches, brand statements, section headers that need to announce themselves — and never appears on buttons, text, or status indicators. Geist, Vercel's proprietary variable font, completes the identity: geometric, precise, engineered.

**Key Characteristics:**
- Black/white chromatic axis — the palette IS the brand, with a single accent blue for interactivity
- 12-step gray scale as primary design tool — borders do the work of shadows
- Dark-first design philosophy — `#000000` canvas with `#fafafa` foreground (never pure white in dark mode)
- Geist variable font (proprietary) — geometric, pre-optimized, weights 100–900
- Geist Mono for all code — monospace precision signals developer culture
- Glass nav with `backdrop-filter: blur(8px) saturate(180%)` — transparency with structural separation
- Signature rainbow gradient (pink→purple→blue→cyan) used ONLY as rare decorative element
- Conservative radius theology — max 12px for panels, 6px for buttons and inputs (no pills except badges)
- Negative letter-spacing at display sizes — geometric tightness, normal at body text
- Footer is always `#000000` regardless of theme — the dark anchor

---

## 2. Color System & Tokens

### Light Theme

| Token | Name | Hex | Role | CSS Variable |
|-------|------|-----|------|-------------|
| `bg-primary` | White | `#ffffff` | Main page background | `--color-bg-primary` |
| `bg-secondary` | Gray 1 | `#fafafa` | Subtle backgrounds, card surfaces | `--color-bg-secondary` |
| `bg-tertiary` | Gray 2 | `#f5f5f5` | Input backgrounds, hover surfaces | `--color-bg-tertiary` |
| `text-primary` | Black | `#000000` | Headlines, primary text | `--color-text-primary` |
| `text-secondary` | Gray 9 | `#666666` | Body text, descriptions | `--color-text-secondary` |
| `text-tertiary` | Gray 8 | `#888888` | Captions, metadata, placeholders | `--color-text-tertiary` |
| `text-disabled` | Gray 7 | `#a8a8a8` | Disabled text | `--color-text-disabled` |
| `accent-primary` | Blue | `#0070f3` | Links, focus, primary interactive | `--color-accent-primary` |
| `accent-hover` | Blue Dark | `#0761d1` | Hover on blue elements | `--color-accent-hover` |
| `accent-light` | Blue Light | `#3291ff` | Dark mode accent | `--color-accent-light` |
| `border-default` | Gray 4 | `#e8e8e8` | Default borders, dividers | `--color-border-default` |
| `border-subtle` | Gray 3 | `#ededed` | Subtle card borders, nav border | `--color-border-subtle` |
| `border-strong` | Gray 6 | `#d8d8d8` | Active borders, hover borders | `--color-border-strong` |
| `border-focus` | Blue | `#0070f3` | Focus rings | `--color-border-focus` |
| `status-success` | Green | `#17c964` | Success states, deployment success | `--color-status-success` |
| `status-success-text` | Green Dark | `#12a150` | Success text, badge text | `--color-status-success-text` |
| `status-warning` | Amber | `#f5a623` | Warning states | `--color-status-warning` |
| `status-warning-text` | Amber Dark | `#c4841d` | Warning text | `--color-status-warning-text` |
| `status-error` | Red | `#ff6666` | Error states | `--color-status-error` |
| `status-error-text` | Red Dark | `#f21361` | Error text | `--color-status-error-text` |
| `overlay` | Black | `rgba(0,0,0,0.5)` | Modal backdrops | `--color-overlay` |

### Dark Theme

| Token | Hex (Dark) | Maps to Light | CSS Variable |
|-------|-----------|---------------|-------------|
| `bg-primary` | `#000000` | `#ffffff` | `--color-bg-primary` |
| `bg-secondary` | `#0a0a0a` | `#fafafa` | `--color-bg-secondary` |
| `bg-tertiary` | `#111111` | `#f5f5f5` | `--color-bg-tertiary` |
| `text-primary` | `#fafafa` | `#000000` | `--color-text-primary` |
| `text-secondary` | `#888888` | `#666666` | `--color-text-secondary` |
| `text-tertiary` | `#666666` | `#888888` | `--color-text-tertiary` |
| `text-disabled` | `#454545` | `#a8a8a8` | `--color-text-disabled` |
| `accent-primary` | `#3291ff` | `#0070f3` | `--color-accent-primary` |
| `accent-hover` | `#0070f3` | `#0761d1` | `--color-accent-hover` |
| `border-default` | `#2e2e2e` | `#e8e8e8` | `--color-border-default` |
| `border-subtle` | `#1a1a1a` | `#ededed` | `--color-border-subtle` |
| `border-strong` | `#454545` | `#d8d8d8` | `--color-border-strong` |
| `border-focus` | `#3291ff` | `#0070f3` | `--color-border-focus` |
| `status-success` | `#17c964` | `#17c964` | `--color-status-success` |
| `status-success-text` | `#3dd68c` | `#12a150` | `--color-status-success-text` |
| `status-warning` | `#f5a623` | `#f5a623` | `--color-status-warning` |
| `status-error` | `#ff6166` | `#ff6666` | `--color-status-error` |
| `overlay` | `rgba(0,0,0,0.7)` | `rgba(0,0,0,0.5)` | `--color-overlay` |

### Gray Scale — 12-Step System (Vercel Signature)

> This 12-step scale is Vercel's primary design vocabulary. Every surface, border, and text distinction is expressed through a precise step — never an approximation.

| Step | Light Hex | Dark Equivalent | Primary Use |
|------|-----------|-----------------|-------------|
| Gray 1 | `#fafafa` | `#0a0a0a` | Subtle backgrounds, card bg |
| Gray 2 | `#f5f5f5` | `#111111` | Input bg, hover surfaces |
| Gray 3 | `#ededed` | `#1a1a1a` | Subtle borders, nav border |
| Gray 4 | `#e8e8e8` | `#212121` | Default borders |
| Gray 5 | `#e2e2e2` | `#2a2a2a` | Input borders |
| Gray 6 | `#d8d8d8` | `#343434` | Strong borders, active |
| Gray 7 | `#a8a8a8` | `#3d3d3d` | Disabled text |
| Gray 8 | `#888888` | `#454545` | Mid — captions, metadata |
| Gray 9 | `#666666` | `#4e4e4e` | Body text (light mode) |
| Gray 10 | `#454545` | `#5c5c5c` | Labels, emphasized secondary |
| Gray 11 | `#2e2e2e` | `#6c6c6c` | Strong borders (dark mode) |
| Gray 12 | `#171717` | `#ededed` | Foreground on dark |

### Contrast Ratios (WCAG AA)

| Pair | Foreground | Background | Ratio | Pass AA | Pass AAA |
|------|-----------|-----------|-------|---------|----------|
| Heading (light) | `#000000` | `#ffffff` | 21:1 | Yes | Yes |
| Body text (light) gray 9 | `#666666` | `#ffffff` | 5.9:1 | Yes | No |
| Caption (light) gray 8 | `#888888` | `#ffffff` | 3.5:1 | **FAIL** for normal text (passes large text 3:1) | No |
| Accent blue on white | `#0070f3` | `#ffffff` | 4.4:1 | **FAIL** for small text — borderline | No |
| Accent blue dark for small text | `#0761d1` | `#ffffff` | 5.9:1 | Yes | No |
| Heading (dark) | `#fafafa` | `#000000` | 19.8:1 | Yes | Yes |
| Body text (dark) gray 8 | `#888888` | `#000000` | 5.9:1 | Yes | No |
| Blue on black (dark mode) | `#3291ff` | `#000000` | 5.4:1 | Yes | No |
| White on black button | `#ffffff` | `#000000` | 21:1 | Yes | Yes |

> **CRITICAL:** Gray 8 (`#888888`) is 3.5:1 on white — fails WCAG AA for normal text. Use only for captions/decorative metadata. Use Gray 9 (`#666666`, 5.9:1) as the minimum for body text. `#0070f3` is 4.4:1 on white — borderline fail for small text; use `#0761d1` for links smaller than 18px or non-bold 14px.

### Gradients

| Name | Value | Use |
|------|-------|-----|
| Hero rainbow (signature) | `linear-gradient(90deg, #ff0080, #7928ca, #0070f3, #00dfd8)` | RARE decorative hero moments only — NEVER buttons or text |
| Subtle blue wash | `linear-gradient(180deg, rgba(0,112,243,0.05) 0%, transparent 100%)` | Section transition fade |
| Card dark tint | `linear-gradient(135deg, rgba(255,255,255,0.03) 0%, transparent 100%)` | Dark mode card subtle surface |

---

## 3. Typography System

### Font Stack

| Role | Family | Fallbacks | CSS Variable |
|------|--------|-----------|-------------|
| Display | `Geist` | `Inter, SF Pro Display, system-ui, sans-serif` | `--font-display` |
| Body | `Geist` | `Inter, SF Pro Text, system-ui, sans-serif` | `--font-body` |
| Mono | `Geist Mono` | `SF Mono, Monaco, Consolas, monospace` | `--font-mono` |

**OpenType Features:** None required — Geist is pre-optimized as a variable font. Use `font-variant-numeric: tabular-nums` for data displays (deployment counts, metrics, pricing).

### Type Scale

| Token | Size | Weight | Line Height | Letter Spacing | Fluid (clamp) | CSS Variable |
|-------|------|--------|-------------|----------------|---------------|-------------|
| `display-2xl` | 72px | 700 | 1.0 | -3.6px | `clamp(40px, 6vw, 72px)` | `--text-display-2xl` |
| `display-xl` | 60px | 700 | 1.0 | -2.4px | `clamp(36px, 5vw, 60px)` | `--text-display-xl` |
| `display-lg` | 48px | 600 | 1.1 | -1.44px | `clamp(30px, 4vw, 48px)` | `--text-display-lg` |
| `heading-lg` | 36px | 600 | 1.2 | -0.72px | `clamp(26px, 3vw, 36px)` | `--text-heading-lg` |
| `heading-md` | 30px | 600 | 1.25 | -0.45px | `clamp(22px, 2.5vw, 30px)` | `--text-heading-md` |
| `heading-sm` | 24px | 600 | 1.3 | -0.24px | `clamp(20px, 2vw, 24px)` | `--text-heading-sm` |
| `body-lg` | 18px | 400 | 1.6 | normal | — | `--text-body-lg` |
| `body-md` | 16px | 400 | 1.5 | normal | — | `--text-body-md` |
| `body-sm` | 14px | 400 | 1.5 | normal | — | `--text-body-sm` |
| `label` | 13px | 500 | 1.4 | normal | — | `--text-label` |
| `caption` | 12px | 400 | 1.4 | 0.1px | — | `--text-caption` |
| `micro` | 11px | 500 | 1.2 | 0.3px | — | `--text-micro` |
| `code-lg` | 16px | 400 | 1.6 | normal | — | `--text-code-lg` |
| `code-md` | 14px | 500 | 1.5 | normal | — | `--text-code-md` |
| `code-sm` | 12px | 500 | 1.5 | normal | — | `--text-code-sm` |

### Typography Principles
- **Negative tracking at display sizes:** Letter-spacing tightens geometrically with scale — -3.6px at 72px, -2.4px at 60px, -1.44px at 48px, -0.72px at 36px, -0.45px at 30px, -0.24px at 24px, normal at 18px and below. This creates visual cohesion across the scale.
- **Weight 700 for display, 600 for headings, 400/500 for UI:** The weight jumps are deliberate steps — 600 creates clear heading hierarchy without display-level density, 500 serves label/UI emphasis.
- **Geist Mono is mandatory for ALL code:** Variable font, monospace, geometric precision. Using any other monospace font in a Vercel-style interface is a visual error.
- **Line-height compression at scale:** Display uses 1.0 (letterforms stack tightly). Headings open to 1.2–1.3. Body text at 1.5–1.6 for comfortable reading. Never use 1.0 below 30px.

---

## 4. Component Catalog

### 4.1 Buttons

**Primary Black (Light Mode Default)**
- Background: `#000000` → `var(--color-text-primary)`
- Text: `#ffffff`
- Padding: `8px 14px`
- Border Radius: `6px` → `var(--radius-md)`
- Font: 14px / 500 / Geist
- Border: none
- Shadow: none
- Hover: bg `#383838`
- Transition: `background-color 150ms cubic-bezier(0.25, 0.46, 0.45, 0.94)`

**Primary White (Dark Mode Default)**
- Background: `#ffffff`
- Text: `#000000`
- Padding: `8px 14px`
- Border Radius: `6px`
- Font: 14px / 500 / Geist
- Hover: bg `#e2e2e2`
- Transition: `background-color 150ms cubic-bezier(0.25, 0.46, 0.45, 0.94)`

**Ghost / Outline**
- Background: transparent
- Text: current color (inherits from context)
- Padding: `8px 14px`
- Border Radius: `6px`
- Border: `1px solid #ededed` (light) / `1px solid #2e2e2e` (dark)
- Font: 14px / 500 / Geist
- Hover: bg `#fafafa` (light) / bg `#0a0a0a` (dark), border `#d8d8d8` / `#454545`
- Transition: `background-color, border-color 150ms cubic-bezier(0.25, 0.46, 0.45, 0.94)`

**CTA Blue (Secondary)**
- Background: `#0070f3`
- Text: `#ffffff`
- Padding: `8px 14px`
- Border Radius: `6px`
- Font: 14px / 500 / Geist
- Hover: bg `#0761d1`
- Use: Non-primary CTAs, feature section callouts, docs "Deploy" actions

**Danger**
- Background: `rgba(255,102,102,0.1)` (light) / `rgba(255,102,102,0.15)` (dark)
- Text: `#f21361`
- Padding: `8px 14px`
- Border Radius: `6px`
- Border: `1px solid rgba(255,102,102,0.3)`
- Font: 14px / 500 / Geist
- Hover: bg `rgba(255,102,102,0.15)`, border `rgba(255,102,102,0.5)`

**Icon Button**
- Background: transparent
- Padding: `6px`
- Border Radius: `6px`
- Color: `var(--color-text-tertiary)` (gray 8)
- Hover: bg `var(--color-bg-secondary)` (gray 1 / `#0a0a0a`)
- Border: none

**Button Size System**

| Size | Height | Font Size | Padding | CSS Variable |
|------|--------|-----------|---------|-------------|
| xs | 28px | 12px | `4px 10px` | `--btn-xs` |
| sm | 32px | 14px | `6px 12px` | `--btn-sm` |
| md | 40px | 14px | `8px 14px` | `--btn-md` (default) |
| lg | 48px | 16px | `12px 20px` | `--btn-lg` |

### 4.2 Inputs

**Text Input**
- Background: `#ffffff` (light) / `#0a0a0a` (dark)
- Border: `1px solid #e2e2e2` → `var(--color-border-default)` (gray 5) — `1px solid #2a2a2a` dark
- Border Radius: `6px` → `var(--radius-md)`
- Padding: `8px 12px`
- Font: 14px / 400 / Geist
- Placeholder color: `#888888` → `var(--color-text-tertiary)`
- Label: 13px / 500 / Geist / `#000000` (light) / `#fafafa` (dark) — positioned above, `margin-bottom: 6px`
- Helper text: 12px / 400 / gray 8 — below input
- Focus: border `#0070f3`, box-shadow `0 0 0 3px rgba(0,112,243,0.15)`

**Select** — same as Text Input, with chevron icon right-aligned in gray 8
**Textarea** — same as Text Input, `min-height: 96px`, `resize: vertical`
**Checkbox** — 16x16px, `border-radius: 4px`, border `1px solid #d8d8d8`, checked bg `#000000` (light) / `#ffffff` (dark), check mark inverted
**Radio** — 16x16px, `border-radius: 50%`, selected dot `#000000` (light) / `#ffffff` (dark), border `1px solid #d8d8d8`
**Toggle / Switch** — 40x22px track, 18px thumb. Off: track `#e2e2e2` (light) / `#2a2a2a` (dark), On: track `#000000` (light) / `#ffffff` (dark), thumb `#ffffff` / `#000000`

### 4.3 Cards

**Default Card**
- Background: `#fafafa` (light) / `#0a0a0a` (dark)
- Border: `1px solid #ededed` (light) / `1px solid #1a1a1a` (dark)
- Border Radius: `8px` → `var(--radius-lg)`
- Padding: `24px`
- Shadow: none (border provides depth)
- Hover: border-color `#d8d8d8` (light) / `#2e2e2e` (dark), subtle shadow `rgba(0,0,0,0.05) 0 1px 2px`

**Interactive Card**
- Same as Default Card
- Hover: translateY(-1px), border strengthens, shadow sm, transition 150ms
- Focus: ring `0 0 0 2px #0070f3`

**Feature Card (Dashboard / Product)**
- Background: `#ffffff` (light) / `#0a0a0a` (dark)
- Border: `1px solid #e8e8e8` (light) / `1px solid #2e2e2e` (dark)
- Border Radius: `8px`
- Padding: `24px`
- Shadow: `rgba(0,0,0,0.05) 0 1px 2px` — minimal, border does the work

### 4.4 Navigation

**Top Nav / Header**
- Background: `rgba(255,255,255,0.8)` (light) / `rgba(0,0,0,0.8)` (dark) with `backdrop-filter: blur(8px) saturate(180%)`
- Height: `64px`
- Position: `sticky`, `top: 0`, `z-index: 50`
- Border-bottom: `1px solid #ededed` (light) / `1px solid #1a1a1a` (dark)
- Logo: Vercel triangle + wordmark, left-aligned, 20px height
- Links: 14px / 400 / Geist / `#666666` (light) / `#888888` (dark). Hover: `#000000` / `#fafafa`, transition 100ms
- CTA: "Deploy" primary black/white button, right side
- Secondary link: "Log In" ghost or text link
- Mobile: hamburger → full-screen overlay menu

**Dashboard Sidebar**
- Width: 240px (desktop), 64px (collapsed icon-only)
- Background: `#fafafa` (light) / `#0a0a0a` (dark)
- Border-right: `1px solid #ededed` (light) / `1px solid #1a1a1a` (dark)
- Nav item: 36px height, 8px 12px padding, 6px radius, 13px/500/Geist
- Active item: bg `#000000` (light) / `#ffffff` (dark), text `#ffffff` / `#000000`
- Hover item: bg `#f5f5f5` (light) / `#111111` (dark)

**Footer**
- Background: `#000000` (ALWAYS dark, regardless of theme)
- Text: `#888888` (gray 8), links hover `#ffffff`
- Multi-column grid: Product / Resources / Company / Legal
- Bottom bar: copyright + socials
- Border-top: `1px solid #1a1a1a`
- Font: Geist 14px / 400

### 4.5 Modals & Dialogs

- Overlay: `rgba(0,0,0,0.5)` → `var(--color-overlay)`
- Container: bg `#ffffff` (light) / `#0a0a0a` (dark), border `1px solid #ededed` / `1px solid #2e2e2e`, radius `8px`, shadow `rgba(0,0,0,0.15) 0 8px 30px`, max-width `480px`
- Header: `heading-sm` (24px/600/Geist), close button (icon button top-right)
- Body: padding `24px`, overflow-y auto if exceeds `70vh`
- Footer: padding `16px 24px`, buttons right-aligned, `gap: 8px`
- Enter animation: scale 0.96→1.0 + opacity 0→1, 200ms `cubic-bezier(0.25, 0.46, 0.45, 0.94)`

### 4.6 Dropdowns & Menus

- Container: bg `#ffffff` (light) / `#0a0a0a` (dark), border `1px solid #e8e8e8` / `1px solid #2e2e2e`, radius `8px`, shadow `rgba(0,0,0,0.08) 0 4px 12px`
- Item: padding `8px 12px`, font 14px/400/Geist, color `#666666` / `#888888`, radius `4px` inside
- Item hover: bg `#fafafa` (light) / `#111111` (dark), text `#000000` / `#fafafa`
- Active item: bg `#f5f5f5` / `#171717`, text `#000000` / `#fafafa`
- Divider: `1px solid #ededed` / `1px solid #1a1a1a`
- Group label: 11px/500/Geist/uppercase/gray 8, padding `8px 12px`, letter-spacing 0.3px

### 4.7 Badges & Tags

| Variant | Background | Text | Border | Radius | Padding |
|---------|-----------|------|--------|--------|---------|
| Default | `#fafafa` (light) / `#171717` (dark) | `#666666` / `#888888` | `1px solid #e8e8e8` / `#2e2e2e` | `9999px` | `2px 8px` |
| Blue / Info | `rgba(0,112,243,0.1)` | `#0761d1` (light) / `#3291ff` (dark) | none | `9999px` | `2px 8px` |
| Success | `rgba(23,201,100,0.1)` | `#12a150` | none | `9999px` | `2px 8px` |
| Warning | `rgba(245,166,35,0.15)` | `#c4841d` | none | `9999px` | `2px 8px` |
| Error | `rgba(242,19,97,0.1)` | `#f21361` | none | `9999px` | `2px 8px` |
| Black (status) | `#000000` (light) / `#ffffff` (dark) | `#ffffff` / `#000000` | none | `9999px` | `2px 8px` |

> All badges use Geist 11px/500. The pill radius (`9999px`) is the only context where Vercel uses full rounding — it signals categorical labels, not interactive controls.

### 4.8 Tooltips

- Background: `#000000` (light) / `#fafafa` (dark) — always inverted from surrounding context
- Text: `#ffffff` / `#000000`, 12px / 400 / Geist
- Radius: `6px`
- Padding: `6px 10px`
- Arrow: `5px`, same bg
- Max width: `240px`
- Shadow: `rgba(0,0,0,0.15) 0 4px 12px`

### 4.9 Toasts & Notifications

- Container: bg `#ffffff` (light) / `#0a0a0a` (dark), border `1px solid #e8e8e8` / `#2e2e2e`, radius `8px`, shadow `rgba(0,0,0,0.08) 0 4px 12px`, padding `12px 16px`, max-width `360px`
- Icon: 16px, color per variant (success `#17c964` / warning `#f5a623` / error `#ff6666` / info `#0070f3`)
- Title: 13px / 500 / Geist / `#000000` (light) / `#fafafa` (dark)
- Message: 13px / 400 / Geist / gray 9 / gray 8
- Close button: icon button 6px padding, top-right
- Position: `bottom-right`, offset `16px` from edges
- Stack: `gap: 8px` between toasts, max 3 visible
- Enter: translateX(100%)→0 + opacity 0→1, 200ms `cubic-bezier(0.25, 0.46, 0.45, 0.94)`

### 4.10 Tables

- Header: bg `#fafafa` (light) / `#0a0a0a` (dark), text 12px/500/uppercase/gray 8, border-bottom `1px solid #e8e8e8` / `#2e2e2e`, letter-spacing 0.2px
- Row: bg transparent, hover bg `#fafafa` / `#0a0a0a`, border-bottom `1px solid #ededed` / `#1a1a1a`
- Cell: padding `12px 16px`, text 14px/400/Geist
- Numeric cells: 14px/400 with `font-variant-numeric: tabular-nums`, right-aligned
- Striped variant: alternate bg `#fafafa` / `#0a0a0a`

### 4.11 Tabs

- Container: border-bottom `1px solid #ededed` (light) / `#1a1a1a` (dark)
- Tab (inactive): padding `10px 16px`, font 14px/400/Geist, color gray 9 / gray 8
- Tab (active): color `#000000` (light) / `#fafafa` (dark), font-weight 500, border-bottom `2px solid #000000` / `#ffffff`
- Tab hover: color `#000000` / `#fafafa`, transition 100ms
- Focus: ring `0 0 0 2px #0070f3`, rounded

### 4.12 Avatars

| Size | Dimensions | Font Size | Radius |
|------|-----------|-----------|--------|
| xs | 20px | 9px | 50% |
| sm | 28px | 12px | 50% |
| md | 36px | 14px | 50% |
| lg | 48px | 18px | 50% |
| xl | 64px | 24px | 50% |

> Vercel uses circular avatars for users. Team/org avatars use `6px` radius (matching card system).

### 4.13 Pagination

- Button: 32x32px, radius `6px`, font 14px/400/Geist
- Default: bg transparent, text gray 8, border `1px solid #e8e8e8` / `#2e2e2e`
- Active: bg `#000000` (light) / `#ffffff` (dark), text `#ffffff` / `#000000`, border-color matches bg
- Hover: bg `#fafafa` / `#0a0a0a`, border `#d8d8d8` / `#454545`
- Disabled: opacity 0.4, cursor `not-allowed`
- Gap: `4px`
- Ellipsis: gray 8, same 32px container

### 4.14 Progress & Loading

- Progress bar: height `3px`, track `#e2e2e2` / `#2a2a2a`, fill `#000000` / `#ffffff`, radius `9999px`
- Deployment progress: fill `#0070f3`, same track
- Spinner: 18px, `#000000` / `#ffffff`, stroke 2px, animation `spin 600ms linear infinite`
- Skeleton: bg `#f5f5f5` / `#111111`, shimmer `linear-gradient(90deg, transparent, rgba(255,255,255,0.05), transparent)` (dark) / `linear-gradient(90deg, transparent, rgba(0,0,0,0.04), transparent)` (light), radius matching component
- Code block: bg `#fafafa` / `#0a0a0a`, border `1px solid #ededed` / `#1a1a1a`, radius `8px`, padding `16px 20px`, Geist Mono 14px/500

---

## 5. Component State Matrix

| Component | Default | Hover | Active/Pressed | Focus | Disabled | Loading | Error |
|-----------|---------|-------|---------------|-------|----------|---------|-------|
| **Button Primary (Light)** | bg `#000000` | bg `#383838` | bg `#171717`, scale(0.98) | ring `0 0 0 2px #0070f3` offset 2px | bg `#000000`, opacity 0.4, `not-allowed` | spinner white 14px + text opacity 0.5 | — |
| **Button Primary (Dark)** | bg `#ffffff` | bg `#e2e2e2` | bg `#d4d4d4`, scale(0.98) | ring `0 0 0 2px #3291ff` offset 2px | bg `#ffffff`, opacity 0.4, `not-allowed` | spinner black 14px + text opacity 0.5 | — |
| **Button Ghost** | border `#ededed`/`#2e2e2e` | border `#d8d8d8`/`#454545`, bg subtle | scale(0.98) | ring `0 0 0 2px #0070f3` | opacity 0.4, `not-allowed` | spinner gray | — |
| **Button CTA Blue** | bg `#0070f3` | bg `#0761d1` | bg `#0552b2`, scale(0.98) | ring `0 0 0 2px #0070f3` offset 2px | opacity 0.4, `not-allowed` | spinner white | — |
| **Input Text** | border gray 5 | border gray 6 | — | border `#0070f3`, ring `0 0 0 3px rgba(0,112,243,0.15)` | bg gray 2, opacity 0.6, `not-allowed` | — | border `#ff6666`, ring `0 0 0 3px rgba(255,102,102,0.15)` |
| **Checkbox** | border gray 6 | border gray 9 | — | ring `0 0 0 2px #0070f3` | opacity 0.4 | — | border `#ff6666` |
| **Card Interactive** | border gray 3/11 | border gray 6/11 stronger, translateY(-1px), shadow sm | border gray 8, translateY(0) | ring `0 0 0 2px #0070f3` | opacity 0.5 | skeleton shimmer | — |
| **Link** | color `#0070f3` (light) / `#3291ff` (dark) | underline, color `#0761d1` / `#0070f3` | color darker | ring `0 0 0 2px #0070f3` offset 2px | color gray 8, no pointer | — | — |
| **Tab** | color gray 9/8 | color `#000000`/`#fafafa` | color + 2px indicator | ring inset `0 0 0 2px #0070f3` | opacity 0.4 | — | — |
| **Select** | border gray 5 | border gray 6 | — | border `#0070f3`, ring `0 0 0 3px rgba(0,112,243,0.15)` | opacity 0.5 | spinner gray | border `#ff6666` |
| **Toggle** | track gray 5 | track gray 6 (off) / `#383838` (on) | — | ring `0 0 0 2px #0070f3` | opacity 0.4 | — | — |

### Focus Ring Standard
```css
/* Box-shadow approach — preserves border-radius, no outline gap artifacts */
box-shadow: 0 0 0 2px var(--color-border-focus);
outline: none;

/* Or for links / elements needing offset: */
outline: 2px solid #0070f3;
outline-offset: 2px;
```

### Disabled Pattern
```css
opacity: 0.4;
cursor: not-allowed;
pointer-events: none;
```

### Error Input Pattern
```css
border-color: #ff6666;
box-shadow: 0 0 0 3px rgba(255, 102, 102, 0.15);
```

---

## 6. Layout & Spacing System

### Spacing Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `space-0` | 0px | `p-0` | `--space-0` | Reset |
| `space-px` | 1px | `p-px` | `--space-px` | Hairlines |
| `space-1` | 4px | `p-1` | `--space-1` | Badge padding, icon gaps, micro spacing |
| `space-2` | 8px | `p-2` | `--space-2` | Button padding-y, badge padding-x |
| `space-3` | 12px | `p-3` | `--space-3` | Input padding, tight component gaps |
| `space-4` | 16px | `p-4` | `--space-4` | Button padding-x, component gap |
| `space-5` | 20px | `p-5` | `--space-5` | Mobile section padding |
| `space-6` | 24px | `p-6` | `--space-6` | Card padding, section sub-gap |
| `space-8` | 32px | `p-8` | `--space-8` | Section internal gap |
| `space-10` | 40px | `p-10` | `--space-10` | Section gap mobile |
| `space-12` | 48px | `p-12` | `--space-12` | Section gap tablet |
| `space-16` | 64px | `p-16` | `--space-16` | Section gap desktop, nav height |
| `space-20` | 80px | `p-20` | `--space-20` | Hero padding, large section gap |
| `space-24` | 96px | `p-24` | `--space-24` | Maximum section separation |

### Grid

| Property | Value | CSS Variable |
|----------|-------|-------------|
| Max content width (marketing) | `1200px` | `--grid-max-width` |
| Max content width (dashboard) | `1440px` | `--grid-max-width-dashboard` |
| Column count | 12 | `--grid-columns` |
| Gutter | `24px` | `--grid-gutter` |
| Margin (mobile) | `16px` | `--grid-margin-sm` |
| Margin (tablet) | `32px` | `--grid-margin-md` |
| Margin (desktop) | `auto` (centered) | `--grid-margin-lg` |

### Border Radius Scale

> Vercel uses a conservative geometric scale — no aggressive rounding. The system signals precision and developer infrastructure. Pill radius (`9999px`) is reserved exclusively for badges and status pills.

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `radius-none` | 0px | `rounded-none` | `--radius-none` | Full-bleed elements, table cells |
| `radius-xs` | 2px | — | `--radius-xs` | Micro elements, inline code spans |
| `radius-sm` | 4px | `rounded` | `--radius-sm` | Checkboxes, radio, small tags |
| `radius-md` | 6px | `rounded-md` | `--radius-md` | Buttons, inputs, dropdowns (default) |
| `radius-lg` | 8px | `rounded-lg` | `--radius-lg` | Cards, modals, code blocks |
| `radius-xl` | 12px | `rounded-xl` | `--radius-xl` | Large panels, feature sections |
| `radius-full` | 9999px | `rounded-full` | `--radius-full` | Badges, status pills, avatars only |

---

## 7. Depth & Elevation

> **Vercel's elevation philosophy: borders do the work of shadows.** Surface separation is achieved through gray-scale step differences and 1px borders — not shadow spread. Shadows are used sparingly and minimally, never as the primary depth mechanism.

### Shadow Scale

| Token | Value | Tailwind | CSS Variable | Use |
|-------|-------|---------|-------------|-----|
| `shadow-sm` | `rgba(0,0,0,0.05) 0 1px 2px` | `shadow-sm` | `--shadow-sm` | Subtle hover lift on cards |
| `shadow-md` | `rgba(0,0,0,0.08) 0 4px 12px` | `shadow-md` | `--shadow-md` | Dropdowns, toasts, popovers |
| `shadow-lg` | `rgba(0,0,0,0.15) 0 8px 30px` | `shadow-lg` | `--shadow-lg` | Modals, elevated panels |
| `shadow-dark-md` | `rgba(0,0,0,0.3) 0 4px 12px` | — | `--shadow-dark-md` | Dark mode dropdowns, toasts |
| `shadow-dark-lg` | `rgba(0,0,0,0.5) 0 8px 30px` | — | `--shadow-dark-lg` | Dark mode modals |
| `shadow-focus` | `0 0 0 2px #0070f3` | — | `--shadow-focus` | Focus ring (light) |
| `shadow-focus-dark` | `0 0 0 2px #3291ff` | — | `--shadow-focus-dark` | Focus ring (dark) |

> Borders (`1px solid gray 3` light / `1px solid gray 11` dark) replace `shadow-xs` for component separation — they communicate structure more precisely than ambient shadow at this scale.

### Z-Index Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `z-base` | 0 | `--z-base` | Default content |
| `z-raised` | 1 | `--z-raised` | Inline lifted cards |
| `z-dropdown` | 10 | `--z-dropdown` | Dropdowns, menus |
| `z-sticky` | 50 | `--z-sticky` | Sticky nav, table headers |
| `z-overlay` | 60 | `--z-overlay` | Modal backdrop |
| `z-modal` | 70 | `--z-modal` | Modal content |
| `z-popover` | 80 | `--z-popover` | Popovers, tooltips |
| `z-toast` | 90 | `--z-toast` | Toast notifications |
| `z-top` | 100 | `--z-top` | Skip-to-content, critical overlays |

---

## 8. Motion & Animation System

> Vercel motion is fast, snappy, and precise. Nothing bounces. Nothing overshoots. The interface responds immediately and transitions complete quickly — developer-grade feedback that respects the user's time.

### Duration Scale

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `duration-instant` | 0ms | `--duration-instant` | Immediate state changes |
| `duration-fast` | 100ms | `--duration-fast` | Hover feedback, color transitions |
| `duration-normal` | 150ms | `--duration-normal` | Button hover, nav link, most micro-interactions |
| `duration-moderate` | 200ms | `--duration-moderate` | Modal enter/exit, dropdown open, tab switch |
| `duration-slow` | 300ms | `--duration-slow` | Complex entrance animations |
| `duration-slower` | 500ms | `--duration-slower` | Page transitions, orchestrated sequences |

### Easing Functions

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `ease-default` | `cubic-bezier(0.4, 0, 0.2, 1)` | `--ease-default` | General transitions (Material ease) |
| `ease-vercel` | `cubic-bezier(0.25, 0.46, 0.45, 0.94)` | `--ease-vercel` | Vercel default — smooth ease-out-quad, most UI interactions |
| `ease-out-quart` | `cubic-bezier(0.16, 1, 0.3, 1)` | `--ease-out-quart` | Fast-start entrances — modal, dropdown, toast |
| `ease-in` | `cubic-bezier(0.4, 0, 1, 1)` | `--ease-in` | Elements exiting view |
| `ease-out` | `cubic-bezier(0, 0, 0.2, 1)` | `--ease-out` | Elements entering view |

> There is NO bounce easing in Vercel's system. `cubic-bezier(0.34, 1.56, 0.64, 1)` and spring physics do not exist here — they signal consumer playfulness. Vercel is precise.

### Common Transitions

| Interaction | Property | Duration | Easing |
|------------|----------|----------|--------|
| Button hover | `background-color` | 100ms | ease-vercel |
| Button active | `transform` | 100ms | ease-default |
| Link hover | `color` | 100ms | ease-vercel |
| Card hover | `border-color, box-shadow, transform` | 150ms | ease-vercel |
| Modal enter | `opacity, transform (scale 0.96→1)` | 200ms | ease-out-quart |
| Modal exit | `opacity, transform` | 150ms | ease-in |
| Dropdown open | `opacity, transform (translateY -4px→0)` | 150ms | ease-out-quart |
| Toast enter | `transform (translateX), opacity` | 200ms | ease-out-quart |
| Toast exit | `opacity` | 150ms | ease-in |
| Focus ring | `box-shadow` | 100ms | ease-vercel |
| Nav border on scroll | `border-color, backdrop-filter` | 150ms | ease-vercel |
| Tab indicator | `border-color, color` | 100ms | ease-vercel |

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
| Library | Geist Icons (Vercel internal) + Lucide React for generic UI |
| Default size | 16px |
| Stroke width | 1.5px |
| Color | `currentColor` (inherits from parent text) |

### Icon Sizes

| Token | Value | CSS Variable | Use |
|-------|-------|-------------|-----|
| `icon-xs` | 12px | `--icon-xs` | Inline, badge icons, breadcrumb separators |
| `icon-sm` | 14px | `--icon-sm` | Button icons, input prefix/suffix |
| `icon-md` | 16px | `--icon-md` | Navigation items, cards (default) |
| `icon-lg` | 20px | `--icon-lg` | Feature cards, section headers |
| `icon-xl` | 24px | `--icon-xl` | Hero elements, empty states |
| `icon-2xl` | 32px | `--icon-2xl` | Large feature illustrations |

### Feature Icon Container
- Square: `40px`, bg `#f5f5f5` (light) / `#111111` (dark), border `1px solid #e8e8e8` / `#2e2e2e`, radius `8px`
- Icon: `icon-lg` (20px), `currentColor` (inherits gray 9 or adjusted by parent)

---

## 10. Accessibility Contract

### Targets

| Criterion | Target | Standard |
|-----------|--------|----------|
| Color contrast (normal text) | 4.5:1 minimum | WCAG AA |
| Color contrast (large text ≥18px / bold ≥14px) | 3:1 minimum | WCAG AA |
| Color contrast (UI components, icons) | 3:1 minimum | WCAG AA |
| Touch target size | 44x44px minimum | WCAG 2.5.8 |
| Focus indicator | 2px ring, 3:1 contrast | WCAG 2.4.7 |
| Motion | Respect `prefers-reduced-motion` | WCAG 2.3.3 |

### Known Contrast Issues

| Element | Current Ratio | Fix |
|---------|--------------|-----|
| Gray 8 (`#888888`) on white — normal text | 3.5:1 | **FAILS AA.** Use only for captions/decorative. Use gray 9 (`#666666`, 5.9:1) for body text. |
| `#0070f3` on white — small text links | 4.4:1 | **Borderline fail.** Use `#0761d1` (5.9:1) for links at <18px or non-bold <14px. |
| Pink accent `#ff0080` on white | 3.8:1 | **FAILS AA for normal text.** Decorative gradient use only — never text. |
| Gray 7 (`#a8a8a8`) on white — disabled | 2.9:1 | **FAILS AA.** Acceptable for disabled UI (WCAG 1.4.3 exempt), but disabled informational text must use gray 9. |

### Focus Management

- All interactive elements: `box-shadow: 0 0 0 2px #0070f3` (light) / `0 0 0 2px #3291ff` (dark) on `:focus-visible`
- `outline: none` when box-shadow focus is applied
- Focus order follows DOM order (logical left-to-right, top-to-bottom)
- Modal traps focus within dialog until Escape key or explicit close
- Skip-to-content: `<a href="#main" class="sr-only focus:not-sr-only focus:absolute focus:top-4 focus:left-4 focus:z-[100]">`
- Dashboard sidebar: keyboard-navigable with arrow keys between items

### ARIA Patterns

| Component | Role | Key Attributes |
|-----------|------|---------------|
| Modal | `dialog` | `aria-modal="true"`, `aria-labelledby` |
| Dropdown | `menu` / `menuitem` | `aria-expanded`, `aria-haspopup="true"` |
| Tabs | `tablist` / `tab` / `tabpanel` | `aria-selected`, `aria-controls`, `aria-orientation` |
| Toast | `status` or `alert` | `role="alert"` for errors, `role="status"` for info |
| Toggle | `switch` | `aria-checked` |
| Tooltip | `tooltip` | `aria-describedby` on trigger |
| Progress bar | `progressbar` | `aria-valuenow`, `aria-valuemin="0"`, `aria-valuemax="100"` |
| Deployment status | `status` | `role="status"`, `aria-live="polite"` |

### Keyboard Navigation

| Component | Key | Action |
|-----------|-----|--------|
| Button | `Enter`, `Space` | Activate |
| Modal | `Escape` | Close, return focus to trigger |
| Dropdown | `Arrow Up/Down` | Navigate items |
| Dropdown | `Enter` | Select item |
| Dropdown | `Escape` | Close |
| Tabs | `Arrow Left/Right` | Switch tab |
| Checkbox | `Space` | Toggle |
| Toggle | `Space`, `Enter` | Toggle on/off |
| Sidebar nav | `Arrow Up/Down` | Navigate items |

---

## 11. Do's and Don'ts

### Do
1. Use Geist for all text and Geist Mono for ALL code — these fonts are non-negotiable and define the visual identity
2. Apply negative letter-spacing proportionally: -3.6px at 72px, scaling to normal at 18px and below
3. Use the 12-step gray scale for every surface, border, and text distinction — it is Vercel's primary design vocabulary
4. Rely on borders (`1px solid gray 3/4/5`) for depth separation rather than shadows — structure over atmospherics
5. Dark mode foreground is `#fafafa`, NOT `#ffffff` — the distinction reduces eye strain and is intentional
6. Use `#0761d1` for small text links (<18px) instead of `#0070f3` — it passes WCAG AA (5.9:1 vs 4.4:1)
7. Apply the glass nav pattern: translucent bg + `backdrop-filter: blur(8px) saturate(180%)` + 1px border separation
8. Keep motion fast and snappy — 100-200ms transitions, no bounce, no spring physics — developer interfaces are precise
9. The footer is ALWAYS `#000000` regardless of active theme — it's the dark anchor of every page
10. Use `font-variant-numeric: tabular-nums` on all numeric data (deployment counts, metrics, build times)

### Don't
1. Don't use the hero gradient (`#ff0080` → `#7928ca` → `#0070f3` → `#00dfd8`) for buttons, text, borders, or interactive elements — it's a RARE decorative accent only
2. Don't use gray 8 (`#888888`) as body text on white — 3.5:1 fails WCAG AA; use gray 9 (`#666666`, 5.9:1) minimum
3. Don't use `#0070f3` for links smaller than 18px on white — use `#0761d1` which passes AA (5.9:1)
4. Don't add large border-radius (12px+) to buttons or inputs — 6px is the button/input ceiling; geometric precision is the identity
5. Don't use heavy drop shadows for depth — a 1px border change (e.g., gray 3→gray 6) communicates hover more precisely
6. Don't use any non-Geist fonts — no Inter, no system-ui as the primary, no fallback escalation in production
7. Don't add spring or bounce easing — `cubic-bezier(0.34, 1.56, 0.64, 1)` and its variants are banned; Vercel never bounces
8. Don't use pure white (`#ffffff`) as foreground text in dark mode — use `#fafafa`; this is documented system behavior
9. Don't use the pink (`#ff0080`), purple (`#7928ca`), or cyan (`#00dfd8`) accents as standalone UI colors — they exist only inside the rainbow gradient
10. Don't center-align body paragraphs exceeding 3 lines — left-align for readability; center is for hero labels and short stats only

---

## 12. Responsive Behavior

### Breakpoints

| Token | Width | CSS | Tailwind | Key Changes |
|-------|-------|-----|----------|-------------|
| `sm` | 640px | `@media (min-width: 640px)` | `sm:` | 2-col grids, stacked CTAs go side-by-side |
| `md` | 768px | `@media (min-width: 768px)` | `md:` | Nav expands, form layouts 2-col |
| `lg` | 1024px | `@media (min-width: 1024px)` | `lg:` | Full desktop nav, 3-col feature grids |
| `xl` | 1280px | `@media (min-width: 1280px)` | `xl:` | 1200px content width reached, generous margins |
| `2xl` | 1536px | `@media (min-width: 1536px)` | `2xl:` | Large-monitor breathing room |

### Responsive Type Scale

| Token | Mobile (<640) | Tablet (768) | Desktop (1024+) |
|-------|--------------|-------------|----------------|
| `display-2xl` | 40px | 56px | 72px |
| `display-xl` | 36px | 48px | 60px |
| `display-lg` | 30px | 38px | 48px |
| `heading-lg` | 26px | 30px | 36px |
| `heading-md` | 22px | 26px | 30px |

### Layout Shifts

| Component | Mobile (<768) | Tablet (768-1023) | Desktop (1024+) |
|-----------|--------------|-------------------|----------------|
| Nav | Hamburger → overlay | Full horizontal | Full horizontal |
| Hero | Stacked center, padding 20px | Stacked center, padding 40px | Stacked center, padding 80px |
| Feature grid | 1 column stacked | 2 columns | 3 columns |
| Dashboard sidebar | Hidden / bottom sheet | Collapsed icon-only | Full 240px |
| Cards | Full width stacked | 2 columns | 3 columns |
| Footer | Stacked single column | 2×2 grid | 4-column grid |
| CTAs | Full width stacked | Side-by-side | Side-by-side |
| Code panels | Full width, scrollable | Full width | Side-by-side with preview |

### Touch Targets
- Minimum size: 44x44px
- Minimum gap between adjacent targets: 8px
- Mobile CTA buttons: full width, 48px min height
- Nav hamburger: 44x44px touch area
- Icon buttons: 44x44px touch area even when icon is 14-16px

---

## 13. Code Snippets

### Button Primary Black (JSX + Tailwind)

```jsx
<button
  className="bg-black hover:bg-[#383838] active:bg-[#171717] active:scale-[0.98] text-white px-[14px] py-2 rounded-md text-sm font-medium transition-colors duration-100 focus:outline-none focus:ring-2 focus:ring-[#0070f3] focus:ring-offset-2 disabled:opacity-40 disabled:cursor-not-allowed"
  style={{ fontFamily: 'Geist, Inter, system-ui, sans-serif' }}
>
  Deploy
</button>
```

### Button Ghost (JSX + Tailwind)

```jsx
<button
  className="bg-transparent hover:bg-[#fafafa] dark:hover:bg-[#0a0a0a] text-current px-[14px] py-2 rounded-md text-sm font-medium border border-[#ededed] dark:border-[#2e2e2e] hover:border-[#d8d8d8] dark:hover:border-[#454545] transition-[background-color,border-color] duration-150 focus:outline-none focus:ring-2 focus:ring-[#0070f3] focus:ring-offset-2 disabled:opacity-40 disabled:cursor-not-allowed"
>
  Cancel
</button>
```

### Card Component (JSX + Tailwind)

```jsx
<div className="bg-[#fafafa] dark:bg-[#0a0a0a] border border-[#ededed] dark:border-[#1a1a1a] rounded-lg p-6 hover:border-[#d8d8d8] dark:hover:border-[#2e2e2e] hover:shadow-[rgba(0,0,0,0.05)_0_1px_2px] hover:-translate-y-px transition-[border-color,box-shadow,transform] duration-150 focus:outline-none focus:ring-2 focus:ring-[#0070f3]">
  <h3 className="text-base font-semibold text-black dark:text-[#fafafa] mb-2 leading-snug tracking-[-0.24px]">
    {title}
  </h3>
  <p className="text-sm text-[#666666] dark:text-[#888888] leading-[1.5]">
    {description}
  </p>
</div>
```

### Glass Nav (JSX + Tailwind)

```jsx
<header className="sticky top-0 z-50 bg-white/80 dark:bg-black/80 backdrop-blur-[8px] saturate-[180%] border-b border-[#ededed] dark:border-[#1a1a1a]">
  <nav className="max-w-[1200px] mx-auto px-6 h-16 flex items-center justify-between">
    {/* Logo left */}
    <a href="/" className="flex items-center gap-2 text-black dark:text-[#fafafa]">
      <svg width="20" height="20" viewBox="0 0 76 65" fill="currentColor">
        <path d="M37.5274 0L75.0548 65H0L37.5274 0Z" />
      </svg>
      <span className="text-sm font-medium">Vercel</span>
    </a>
    {/* Links */}
    <div className="hidden md:flex items-center gap-6">
      {['Products', 'Solutions', 'Docs', 'Pricing'].map(link => (
        <a
          key={link}
          href={`/${link.toLowerCase()}`}
          className="text-sm text-[#666666] dark:text-[#888888] hover:text-black dark:hover:text-[#fafafa] transition-colors duration-100 focus:outline-none focus:ring-2 focus:ring-[#0070f3] rounded-sm"
        >
          {link}
        </a>
      ))}
    </div>
    {/* CTAs */}
    <div className="flex items-center gap-3">
      <a href="/login" className="text-sm text-[#666666] hover:text-black dark:text-[#888888] dark:hover:text-[#fafafa] transition-colors duration-100">
        Log In
      </a>
      <button className="bg-black dark:bg-white text-white dark:text-black px-[14px] py-2 rounded-md text-sm font-medium hover:bg-[#383838] dark:hover:bg-[#e2e2e2] transition-colors duration-100">
        Deploy
      </button>
    </div>
  </nav>
</header>
```

### Code Block (JSX + Tailwind)

```jsx
<div className="bg-[#fafafa] dark:bg-[#0a0a0a] border border-[#ededed] dark:border-[#1a1a1a] rounded-lg p-5 overflow-x-auto">
  <pre className="text-sm font-medium leading-[1.5] text-[#000000] dark:text-[#fafafa]"
    style={{ fontFamily: 'Geist Mono, SF Mono, Monaco, Consolas, monospace' }}
  >
    <code>{children}</code>
  </pre>
</div>
```

### CSS Custom Properties (Root)

```css
:root {
  /* === BRAND AXIS === */
  --vercel-black:    #000000;
  --vercel-white:    #fafafa; /* dark mode foreground — NOT #ffffff */
  --vercel-blue:     #0070f3;
  --vercel-blue-dark:#0761d1; /* use for small text links — 5.9:1 on white */
  --vercel-blue-light:#3291ff; /* dark mode accent */

  /* === GRAY SCALE (12-step) === */
  --gray-1:  #fafafa;
  --gray-2:  #f5f5f5;
  --gray-3:  #ededed;
  --gray-4:  #e8e8e8;
  --gray-5:  #e2e2e2;
  --gray-6:  #d8d8d8;
  --gray-7:  #a8a8a8; /* disabled text only */
  --gray-8:  #888888; /* captions only — 3.5:1 on white, FAILS AA for normal text */
  --gray-9:  #666666; /* body text minimum — 5.9:1 on white, passes AA */
  --gray-10: #454545;
  --gray-11: #2e2e2e;
  --gray-12: #171717;

  /* === SURFACES (Light) === */
  --color-bg-primary:   #ffffff;
  --color-bg-secondary: #fafafa; /* = gray-1 */
  --color-bg-tertiary:  #f5f5f5; /* = gray-2 */

  /* === TEXT (Light) === */
  --color-text-primary:   #000000;
  --color-text-secondary: #666666; /* gray-9 */
  --color-text-tertiary:  #888888; /* gray-8 — captions only */
  --color-text-disabled:  #a8a8a8; /* gray-7 */

  /* === INTERACTIVE === */
  --color-accent-primary: #0070f3;
  --color-accent-hover:   #0761d1;
  --color-accent-light:   #3291ff;

  /* === BORDERS === */
  --color-border-subtle:  #ededed; /* gray-3 */
  --color-border-default: #e8e8e8; /* gray-4 */
  --color-border-input:   #e2e2e2; /* gray-5 */
  --color-border-strong:  #d8d8d8; /* gray-6 */
  --color-border-focus:   #0070f3;

  /* === STATUS === */
  --color-status-success:       #17c964;
  --color-status-success-text:  #12a150;
  --color-status-warning:       #f5a623;
  --color-status-warning-text:  #c4841d;
  --color-status-error:         #ff6666;
  --color-status-error-text:    #f21361;
  --color-overlay:              rgba(0, 0, 0, 0.5);

  /* === TYPOGRAPHY === */
  --font-display: 'Geist', Inter, 'SF Pro Display', system-ui, sans-serif;
  --font-body:    'Geist', Inter, 'SF Pro Text', system-ui, sans-serif;
  --font-mono:    'Geist Mono', 'SF Mono', Monaco, Consolas, monospace;

  /* === SPACING === */
  --space-1: 4px;   --space-2: 8px;   --space-3: 12px;
  --space-4: 16px;  --space-5: 20px;  --space-6: 24px;
  --space-8: 32px;  --space-10: 40px; --space-12: 48px;
  --space-16: 64px; --space-20: 80px; --space-24: 96px;

  /* === RADIUS (geometric — conservative) === */
  --radius-none: 0px;
  --radius-xs:   2px;
  --radius-sm:   4px;
  --radius-md:   6px;  /* buttons, inputs default */
  --radius-lg:   8px;  /* cards, modals, code blocks */
  --radius-xl:   12px; /* large panels */
  --radius-full: 9999px; /* badges ONLY */

  /* === SHADOWS (minimal — borders do the work) === */
  --shadow-sm:      rgba(0, 0, 0, 0.05) 0 1px 2px;
  --shadow-md:      rgba(0, 0, 0, 0.08) 0 4px 12px;
  --shadow-lg:      rgba(0, 0, 0, 0.15) 0 8px 30px;
  --shadow-focus:   0 0 0 2px #0070f3;

  /* === MOTION === */
  --duration-fast:     100ms;
  --duration-normal:   150ms;
  --duration-moderate: 200ms;
  --duration-slow:     300ms;
  --ease-vercel:       cubic-bezier(0.25, 0.46, 0.45, 0.94);
  --ease-out-quart:    cubic-bezier(0.16, 1, 0.3, 1);
  --ease-default:      cubic-bezier(0.4, 0, 0.2, 1);
  --ease-in:           cubic-bezier(0.4, 0, 1, 1);

  /* === Z-INDEX === */
  --z-base:     0;
  --z-raised:   1;
  --z-dropdown: 10;
  --z-sticky:   50;
  --z-overlay:  60;
  --z-modal:    70;
  --z-popover:  80;
  --z-toast:    90;
  --z-top:      100;

  /* === GRID === */
  --grid-max-width:           1200px;
  --grid-max-width-dashboard: 1440px;
  --grid-gutter:              24px;
  --grid-columns:             12;
}

.dark {
  --color-bg-primary:   #000000;
  --color-bg-secondary: #0a0a0a;
  --color-bg-tertiary:  #111111;
  --color-text-primary:   #fafafa; /* NEVER #ffffff — intentional */
  --color-text-secondary: #888888;
  --color-text-tertiary:  #666666;
  --color-text-disabled:  #454545;
  --color-accent-primary: #3291ff;
  --color-accent-hover:   #0070f3;
  --color-border-subtle:  #1a1a1a;
  --color-border-default: #2e2e2e;
  --color-border-input:   #2a2a2a;
  --color-border-strong:  #454545;
  --color-border-focus:   #3291ff;
  --color-overlay:        rgba(0, 0, 0, 0.7);
  --shadow-sm:  rgba(0, 0, 0, 0.2) 0 1px 2px;
  --shadow-md:  rgba(0, 0, 0, 0.3) 0 4px 12px;
  --shadow-lg:  rgba(0, 0, 0, 0.5) 0 8px 30px;
  --shadow-focus: 0 0 0 2px #3291ff;
}
```

### Tailwind Config Extension

```js
// tailwind.config.js
module.exports = {
  darkMode: 'class',
  theme: {
    extend: {
      colors: {
        vercel: {
          black:      '#000000',
          white:      '#fafafa', // dark mode foreground
          blue:       '#0070f3',
          'blue-dark':'#0761d1',
          'blue-light':'#3291ff',
          // 12-step gray scale
          'gray-1':  '#fafafa',
          'gray-2':  '#f5f5f5',
          'gray-3':  '#ededed',
          'gray-4':  '#e8e8e8',
          'gray-5':  '#e2e2e2',
          'gray-6':  '#d8d8d8',
          'gray-7':  '#a8a8a8',
          'gray-8':  '#888888',
          'gray-9':  '#666666',
          'gray-10': '#454545',
          'gray-11': '#2e2e2e',
          'gray-12': '#171717',
          // Rare accents — gradient use only
          pink:   '#ff0080',
          purple: '#7928ca',
          cyan:   '#00dfd8',
        },
        surface: {
          primary:   'var(--color-bg-primary)',
          secondary: 'var(--color-bg-secondary)',
          tertiary:  'var(--color-bg-tertiary)',
        }
      },
      fontFamily: {
        sans:  ['Geist', 'Inter', 'SF Pro Display', 'system-ui', 'sans-serif'],
        mono:  ['Geist Mono', 'SF Mono', 'Monaco', 'Consolas', 'monospace'],
      },
      fontSize: {
        'display-2xl': ['72px', { lineHeight: '1.0',  letterSpacing: '-3.6px', fontWeight: '700' }],
        'display-xl':  ['60px', { lineHeight: '1.0',  letterSpacing: '-2.4px', fontWeight: '700' }],
        'display-lg':  ['48px', { lineHeight: '1.1',  letterSpacing: '-1.44px', fontWeight: '600' }],
        'heading-lg':  ['36px', { lineHeight: '1.2',  letterSpacing: '-0.72px', fontWeight: '600' }],
        'heading-md':  ['30px', { lineHeight: '1.25', letterSpacing: '-0.45px', fontWeight: '600' }],
        'heading-sm':  ['24px', { lineHeight: '1.3',  letterSpacing: '-0.24px', fontWeight: '600' }],
      },
      maxWidth: {
        'vercel':      '1200px',
        'vercel-dash': '1440px',
      },
      borderRadius: {
        'xs':   '2px',
        'sm':   '4px',
        'md':   '6px',
        'lg':   '8px',
        'xl':   '12px',
        // 'full': '9999px' — badges only, already in Tailwind
      },
      boxShadow: {
        'v-sm':    'rgba(0,0,0,0.05) 0 1px 2px',
        'v-md':    'rgba(0,0,0,0.08) 0 4px 12px',
        'v-lg':    'rgba(0,0,0,0.15) 0 8px 30px',
        'v-focus': '0 0 0 2px #0070f3',
        'v-focus-dark': '0 0 0 2px #3291ff',
        'v-dark-md': 'rgba(0,0,0,0.3) 0 4px 12px',
        'v-dark-lg': 'rgba(0,0,0,0.5) 0 8px 30px',
      },
      transitionTimingFunction: {
        'vercel':    'cubic-bezier(0.25, 0.46, 0.45, 0.94)',
        'quart-out': 'cubic-bezier(0.16, 1, 0.3, 1)',
      },
      transitionDuration: {
        '100': '100ms',
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
| Primary button (light) | bg `#000000`, text `#ffffff`, hover `#383838` |
| Primary button (dark) | bg `#ffffff`, text `#000000`, hover `#e2e2e2` |
| CTA blue | bg `#0070f3`, text `#ffffff`, hover `#0761d1` |
| Background light | `#ffffff` / `#fafafa` (alternating) |
| Background dark | `#000000` / `#0a0a0a` (alternating) |
| Heading text (light) | `#000000` |
| Heading text (dark) | `#fafafa` (NOT `#ffffff`) |
| Body text (light) | `#666666` (gray 9 — 5.9:1 on white) |
| Body text (dark) | `#888888` (gray 8 — 5.9:1 on black) |
| Caption text | `#888888` light / `#666666` dark — captions/meta only |
| Small text links | `#0761d1` light / `#3291ff` dark (passes WCAG AA) |
| Font display | `Geist` — all roles |
| Font mono | `Geist Mono` — ALL code without exception |
| Default radius | `6px` (buttons/inputs), `8px` (cards) |
| Max radius | `12px` (panels), `9999px` (badges only) |
| Primary shadow | `rgba(0,0,0,0.08) 0 4px 12px` — used sparingly |
| Depth system | 1px borders — NOT shadows |
| Focus ring | `0 0 0 2px #0070f3` (light) / `0 0 0 2px #3291ff` (dark) |
| Motion speed | 100–200ms, cubic-bezier(0.25,0.46,0.45,0.94) — NEVER bouncy |
| Gradient | `linear-gradient(90deg, #ff0080, #7928ca, #0070f3, #00dfd8)` — hero/decorative ONLY |

### Example Prompts

- "Create a Vercel-style hero section on `#ffffff` (light) / `#000000` (dark). Headline at `clamp(40px,6vw,72px)`, Geist weight 700, letter-spacing -3.6px, color `#000000` / `#fafafa`. Subtitle 18px/400/`#666666`/`#888888`. Two buttons: primary black/white (bg `#000000`/`#ffffff`, text `#ffffff`/`#000000`, hover `#383838`/`#e2e2e2`, 6px radius, 8px 14px padding) and ghost (border `#ededed`/`#2e2e2e`, transparent bg, same dimensions). Do NOT use the rainbow gradient on these buttons."

- "Build a Vercel-style feature card grid (3 columns desktop, 1 mobile). Cards: bg `#fafafa` / `#0a0a0a`, border `1px solid #ededed` / `1px solid #1a1a1a`, 8px radius, 24px padding. Hover: border strengthens to `#d8d8d8` / `#2e2e2e`, shadow `rgba(0,0,0,0.05) 0 1px 2px`, translateY(-1px), transition 150ms ease-vercel. NO large drop shadows — borders do the work. Icon container: 40px, 8px radius, `#f5f5f5`/`#111111` bg. Title: 16px/600/Geist/`#000000`/`#fafafa`, tracking -0.24px. Body: 14px/400/`#666666`/`#888888`."

- "Create a Vercel glass nav: bg `rgba(255,255,255,0.8)` / `rgba(0,0,0,0.8)`, `backdrop-filter: blur(8px) saturate(180%)`, border-bottom `1px solid #ededed` / `1px solid #1a1a1a`, height 64px, sticky z-50. Logo left (triangle + wordmark). Links: 14px/400/Geist/`#666666` hover `#000000` (100ms). Right: 'Log In' text link + 'Deploy' primary button (bg `#000000` / `#ffffff`, 6px radius, 8px 14px)."

- "Design a deployment status badge using Vercel's pill system: success state = bg `rgba(23,201,100,0.1)`, text `#12a150`, 9999px radius, 2px 8px padding, Geist 11px/500. Error state = bg `rgba(242,19,97,0.1)`, text `#f21361`. Building state = bg `#fafafa`/`#171717`, text `#666666`/`#888888`, border `1px solid #e8e8e8`/`#2e2e2e`. All badges must use Geist Mono for version strings."

- "Build a Vercel-style code block: bg `#fafafa` / `#0a0a0a`, border `1px solid #ededed` / `#1a1a1a`, 8px radius, 16px 20px padding. Font: Geist Mono 14px/500, line-height 1.5, text `#000000` / `#fafafa`. Syntax tokens: keywords use `#000000`/`#fafafa` weight 600; strings use `#0070f3`/`#3291ff`; comments use `#888888`. Add copy button (ghost button sm, top-right, icon-only, 32px height)."

### Pre-flight Checklist for Generated UI

1. Every interactive element has visible focus state (`0 0 0 2px #0070f3` light / `0 0 0 2px #3291ff` dark)
2. Body text uses gray 9 (`#666666`) minimum on white — NOT gray 8 (`#888888`, 3.5:1, fails AA)
3. Small text links use `#0761d1` light (5.9:1) not `#0070f3` (4.4:1) — borderline AA fail
4. Dark mode foreground is `#fafafa` — never `#ffffff` (intentional system decision)
5. All code uses Geist Mono — no exceptions, no Inter, no fallback font used in production UI
6. Buttons use 6px radius, cards use 8px radius, panels use 12px max — badges are the only 9999px elements
7. The rainbow gradient (`#ff0080` → `#7928ca` → `#0070f3` → `#00dfd8`) appears on ZERO interactive elements
8. Depth hierarchy uses border-color changes and 1px gray-step differences — not heavy drop shadows
9. All animations are 100–200ms maximum with `cubic-bezier(0.25, 0.46, 0.45, 0.94)` or faster — no bounce, no spring
10. Animations respect `prefers-reduced-motion` — all transitions suppressed to 0.01ms
11. Touch targets are minimum 44x44px on mobile — icon buttons need padding to reach target
12. Footer is always `#000000` background regardless of active light/dark theme
13. `font-variant-numeric: tabular-nums` applied to all metric displays, deployment counts, and pricing
14. Focus trap active in all modals — Escape closes and returns focus to the trigger element
